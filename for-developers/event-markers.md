---
icon: map-pin
---

# Event markers

While You: Quantified mainly focuses on online visualization and real-time experiences, event markers also exist if someone wants to use them for recordings. Event markers are treated like other devices but are streamed from within the visualization. This means you trigger event markers from within a visual.

### Function to send event markers

To send event markers, call the following function inside a P5.js visual.

```javascript
sendEvent(message);
```

The message has to be a JavaScript object, which means it needs to have a key, and value pair structure, such as:

```javascript
const message = { key: value }
```

This also means you can do something more akin to a JSON.

```javascript
const message = {
    key1: value1,
    key2: value2,
    key3: value3,
}
```

With that pre-scripted function, you will send an event that will be **saved alongside the timestamp** when it was transmitted.&#x20;

While an advanced use-case, by leveraging P5.js and JavaScript function, you can send events triggered by

* [A key press](https://p5js.org/reference/p5/keyPressed/)
* [A button press](https://p5js.org/reference/p5/createButton/)
* [A specific time interval](https://developer.mozilla.org/en-US/docs/Web/API/setInterval)

<details>

<summary>Look into the code behind the function</summary>

Event markers were added through the [postMessage method](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) provided in JavaScript. They are a function being called in the P5.js iframe, which opens up the possibility for integration into other platforms.

```javascript
function sendEvent(message) {
  if (typeof message === 'object') {
    window.parent.postMessage(JSON.stringify(message));
  }
}
```

</details>



