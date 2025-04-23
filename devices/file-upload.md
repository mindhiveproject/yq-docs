---
icon: folder-arrow-up
---

# File Upload



## Uploading data

1. To upload, add a new device, select _Upload a file_ and a new popup will appear
2. Here, you must upload the original zip file used for the recording. You may also make small changes and compress the files into a new zip, but the web app may fail to reproduce those files.

The object that is being played back should behave similarly to a connected device. You need to click on the **play button** to start streaming the data. Once the file ends, playback will stop, but you have the option to start again, rewind, or loop.

## Recording data

1. To record a file, simply start streaming using your device and press the **record button,** accessible at any time from the "devices" window.&#x20;
2. It will save the streamed data to your computer as a .zip with multiple .csv files that contain data points, timestamps, and some metadata.

{% hint style="danger" %}
Avoid **deletion** of the .zip file if you ever want to play back the pre-recorded data.
{% endhint %}

## Information about pre-recorded data

The files recorded for this application will typically follow the convention `deviceName_datetime`. They will be downloaded as a zip file with the following minimum contents:

* README.txt with basic information about the folder and its contents.
* metadata.csv where the devices and files are described and correlated

The other files will be .csv recordings of the datastreams. If you ever want to unzip a folder, modify a file, compress it, and re-upload it, it is important to avoid modifying the files above, otherwise it might not work.

