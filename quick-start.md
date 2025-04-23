---
description: Start using our application
---

# ⚡ Quick Start

{% hint style="info" %}
&#x20;**Before starting,** if you are a student or want a refresher on biosensing and data, we recommend that you take a look at the [educational resources](educational-resources.md).
{% endhint %}

This section will teach you how to use the application and guide you through the process of:

1. [#connecting-to-a-device](quick-start.md#connecting-to-a-device "mention")
   1. [#using-pre-recorded-data](quick-start.md#using-pre-recorded-data "mention")
   2. [#using-your-computer](quick-start.md#using-your-computer "mention")
   3. [#other-devices](quick-start.md#other-devices "mention")
2. [#recording-data](quick-start.md#recording-data "mention")
3. [#working-with-a-visual](quick-start.md#working-with-a-visual "mention")
4. [#code-editing](quick-start.md#code-editing "mention")
   1. [#making-an-account](quick-start.md#making-an-account "mention")
   2. [#changing-a-visual](quick-start.md#changing-a-visual "mention")

## Connecting to a device

1. The first step when connecting to a device is to go into the "devices" window at the corner. Here you can view every available data source.
2. To **add a new one**, click on the card and connection will be attempted.

Below is a list of suggestions on the different types of devices available within the platform for you to get started. Once you have data streaming in the platform, you may[ record the data ](quick-start.md#recording-data)or [head directly into a visual](quick-start.md#working-with-a-visual)

### Using pre-recorded data

1. To upload, add a new device, select _Upload a file_ and a new popup will appear
2. Here, you must upload the original zip file used for the recording. You may also make small changes and compress the files into a new zip, but the web app may fail to reproduce those files.

The object that is being played back should behave similarly to a connected device. You need to click on the **play button** to start streaming the data. Once the file ends, playback will stop, but you have the option to start again, rewind, or loop.

### Using your computer

Some devices don't require additional hardware and may work with your computer's webcam and microphone, such as the [Face Landmarks](devices/face-landmarks.md), [Video Heart Rate](devices/video-heart-rate.md), and Audio Volume. To connect make sure to:

* Always leave the window open in the same browser. Closing it or dismissing it may interrupt the stream.
* Grant browser permission. Whatever data you record will remain local and will never be sent to any of our servers.

### Other devices

Other devices may require specialized hardware and slightly different instructions. Please visit the sections for the two EEG & PPG devices for which we currently offer full support.

* [EMOTIV](devices/emotiv.md)
* [Muse](devices/muse.md)

<details>

<summary>For scientists – LSL </summary>

You may also connect local LSL datastreams to the app; however, this functionality doesn't have full support. For more information [view the respective page in the guide.](devices/lsl.md) &#x20;

</details>

## Recording data

1. To record a file, simply start streaming using your device and press the **record button,** accessible at any time from the "devices" window.&#x20;
2. It will save the streamed data to your computer as a .zip with multiple .csv files that contain data points, timestamps, and some metadata.

{% hint style="danger" %}
Avoid **deletion** of the .zip file if you ever want to play back the pre-recorded data.
{% endhint %}

## Working with a visual

The "visuals" tab provides the list of visuals that are available in the platform.

If it’s your first time using the tool, we recommend following the visualizations on the home page. It helps to learn how data is mapped into the application, how to adjust the range, and some of the metrics we’re getting.&#x20;

Once you have selected a visual:

1. In the left window, you can control parameters manually or assign biometric data to the field using the toggles at the edge of the parameters.
2. You can adjust the range manually by looking at the numeric values or choosing auto range. This function waits until it has acquired a certain amount of data points. It then calculates the minimum and maximum from that buffer and maps the value so that it falls within that range.

#### Suggested starting visualizations

<table data-view="cards" data-full-width="false"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Circle tutorial</strong></td><td>The circle tutorial is the best visualization to learn about <em>code editing</em> and customization.</td><td></td></tr><tr><td><strong>Power bars</strong></td><td>The power bars are an amazing visualization to show the real-time changing values of each frequency band. They also include a time-series plot.</td><td></td></tr></tbody></table>



## Code editing

All visuals are created based on P5.js, so you should be able to follow [any of their tutorials](https://p5js.org/tutorials/) to learn about its usage. This guide will cover platform-specific materials.

### Making an account

You can use the app without making an account and access most of its functionality. Code editing is the only feature limited to registered users. Other features may come soon for registered users. If you want to create an account follow the instructions

1. Go to the [youquantified.com ](https://youquantified.com)URL and navigate to "explore visuals"
2. You can log in or sign up with your email, a unique username, and a secure password.

### Changing a visual

After you have created an account on the platform, code editing allows you to edit any visualization, delete parameters, and add new ones.&#x20;

1. To get started, simply click on the edit button on any of the ones we have. A copy will be created.&#x20;
   * In this screen, you can rename your visualization by going into the top bar (when you access it again you won’t be able to rename it, be careful).&#x20;
2. To edit the code, use the code icon. Any changes will be instantly made live. You can download your code as text at any time.
3. To add or delete parameters, simply click the + or - icons. New parameters can only have unique names. We recommend using simple names.

To reference parameters in code, you must use the following syntax:

```javascript
data?.[“MY PARAMETER NAME”]
```

Where `“MY PARAMETER NAME”` is the exact name of your parameter as a string.
