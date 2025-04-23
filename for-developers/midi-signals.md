---
description: 'Get MIDI output from You: Quantified devices.'
icon: piano-keyboard
---

# MIDI Signals

For people interested in performative arts, there are easy workarounds to output You: Quantified signals as MIDI by leveraging the capabilities of the [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/MIDIOutput). A quick implementation is shown in the beta version of the [MIDI controller visualization](https://youquantified.com/visuals/clwo77ykc0005ptjvtuil8vjb).  It is also important to be familiar with the MIDI output standard to know how to send notes and messages.

### MIDI Protocol

When sending MIDI signals, you (as the programmer) are engineering a new MIDI device! It is exciting, but it also means there is a bit of a learning curve. The MIDI Association has a rather comprehensive [article](https://midi.org/about-midi-part-3midi-messages) explaining the notes and a useful [table](https://midi.org/expanded-midi-1-0-messages-list) that summarises some of that information.&#x20;

For this guide, I will introduce basic concepts that I find the most useful and cover them in a way that's intuitive to start with. However, by all means, feel free to dive deeper and discover the depths of this protocol.&#x20;

First, messages are usually output as a series of 3 data bytes (status + 2 bytes of data). This would make an array with three numbers:&#x20;

```
message = [status, data1, data2]
```

You can write the data in binary, decimal or hex format (the table will often contain every one of those representations).&#x20;

#### Control Change

Control change messages are meant to be used for knobs or pedals. The message you send depends on the rotation of your knob. Here, the three bytes represent:

1. Channel – There are multiple channels that range from 176 to 191 that may be used for different functions.
2. Control Change – This would be the equivalent of specifying a "knob". Each channel can have 127 different knobs. MIDI controllers sometimes reserve certain numbers for specific functions (i.e. a pedal vs an actual knob), however, that doesn't necessarily have to be the case.
3. Value – The value that you're sending, ranging from 0 to 127.

#### Notes

These messages are meant to be used for playing keys or notes. A note message can be broken down into the following components:

1. Channel & Status –  There are a total of 16 channels (think of them as 16 different piano keyboards). However, the first byte changes depending on whether you are sending a channel-on or channel-off signal. For example, channel 1 has a hex value of `0x80` for note off and `0x90` note on.&#x20;
2. Note – Next comes the actual key you are playing. Different piano keys are represented by different numbers. The middle C, for example, has a note value of 60. There are a lot of [images](https://www.tinyloops.com/doc/drumcomputers/) that compare them to pianos. They range from 0 to 127.
3. Velocity – This last number would represent how hard you pressed the key on a scale from 0 to 127.

### Preparing a virtual MIDI port on my computer

The MIDI output from the web requires a virtual device to work. This means you have to create an internal device that's unoccupied and running in the background. Depending on your operating system, the steps to follow are slightly different. Outlined below are some recommended tutorials:

* [MacOS](https://medium.com/@keybaudio/virtual-midi-devices-on-macos-a45cdbdffdaf)
* [Windows](https://manuals.morningstar.io/mc-midi-controller/creating-virtual-midi-ports-in-windows-os)

### How to integrate MIDI into P5.js code?

The general steps followed for the visual will be outlined here so that users can integrate MIDI output into any visual or adapt the code to their liking.

#### Step 1 - Create global MIDI variables to store the object

```
let midi = null;
let outputPort = null;
```

#### Step 2 - Create functions that may act as either buttons or knobs.&#x20;

For noteOn/noteOff messages (which act like keys from a piano), a simple function can look like the following:

```javascript
function updateMIDINote(midiOutput, noteOn, note_num) {
  let noteStatus =  noteOn ? 0x90 : 0x80; // If note is off, turn it on and viceversa
  const noteOnMessage = [noteStatus, 60 + note_num, 127]; // note on, full velocity
  midiOutput.send(noteOnMessage); // sends the message.
}
```

Providing an example for a control change message taken from a value that ranges between 0 and 1.

```javascript
function controlChangeMessage(midiOutput, controlNum, value) {
  let controlChangeMessage = [0xB0, controlNum, floor(map(value, 0, 1, 0, 127, true))];
  midiOutput.send(controlChangeMessage);
}
```

#### Step 3 - Integrate functions into your code

It's important to be mindful of the fact that a void draw gets called every time a frame is refreshed in P5.js, so handling MIDI logic on your draw function may be tricky. There are multiple multiple approaches:

{% hint style="success" %}
Handling everything in the draw function and making additional code to save previous values. You can take a look at [this](https://youquantified.com/visuals/cm1gso9g20007ptbyprk8wl2y) example.
{% endhint %}

{% hint style="info" %}
Overwriting the data event listener function and adding the MIDI logic in that function.

```javascript
window.addEventListener("message", (event)=>{
    data = JSON.parse(event.data);
    // Add MIDI logic that works with the data in here
})
```
{% endhint %}
