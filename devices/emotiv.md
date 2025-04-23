---
description: EEG Headset
icon: brain
---

# EMOTIV

EMOTIV headsets are a lineup of research-grade EEG equipment for brain-computer interfaces and scientific research. To learn more, you can visit their [website](https://www.emotiv.com/products/epoc-x). By installing their custom launcher, this app can connect to any one of the headsets and receive EEG or movement signals.

## Using it with the app

Before starting, make sure to charge the device, and pour saline solution (it can just be water with salt) on the electrodes to make them conductive. Afterwards, you can plug in the USB dongle provided to get started.

1. Download the [EMOTIV launcher](https://www.emotiv.com/emotiv-launcher/). Follow the steps described in the app **to connect.** Once the device is turned on and connected, proceed to the web application.
2. Open the devices window of the web application and click on the EMOTIV card to attempt connection. If you're logged in and the device is connected, you may go back to the EMOTIV launcher and get a prompt to approve the connection.
3. The web app should now be able to connect. If you run into any issues, re-attempt it and make sure the device is showing up in the launcher and there are no other permission prompts.

{% hint style="info" %}
Regardless of whether you have a license or not, you can still connect your device to this app, however, if you don’t have a license you won’t be able to see or use the raw data.&#x20;
{% endhint %}



#### Resources

* [Connecting your EEG Headset](https://docs.google.com/document/d/16AQA_SosiXh-t3TxD4xfYg7LHqXBWzvemVvP0wAE29k/edit?usp=sharing).&#x20;
* [EMOTIV](https://www.emotiv.com)

## Signals

### Sensors

* **EEG:** electroencephalography measures **brain activity** by capturing electrical activity from the brain. This device has four EEG electrodes meant to capture information from the frontal and temporal lobes of the brain as measured through the scalp.
* **Accelerometer & Gyroscope:** the accelerometer and gyroscope provide information about the movement and rotation of the device in 3D space.

### Output

Since the launcher provides an interface for every EMOTIV product, different headsets might have different EEG electrodes. All EMOTIV systems are aligned and described their positions according to the international 10-20 naming system.&#x20;

#### EEG raw signal

With a paid subscription, the EMOTIV will provide raw values for each electrode. Using the EMOTIV X (one of their flagship products) as an example, you would get the following electrode locations

* AF3, F7, F3, FC5, T7, P7, O1, O2, P8, T8, FC6, F4, F8, AF4

#### EEG band power

Band power quantifies a signal's strength in a specific frequency range. The calculation is performed by EMOTIV according to their [specifications](https://www.emotiv.com/tools/knowledge-base/research-information/how-are-band-powers-calculated?srsltid=AfmBOool5hV84faMH3hpZkTfRWeOJYMf280E6RJSXzJCkUAhw9jxjklg) and averaged across all electrodes.

* Theta: 4 - 8 Hz band power
* Alpha: 8 - 12 Hz band power
* Low beta: 12 - 16 Hz band power
* High beta: 16 - 25 Hz band power
* Gamma: 25 - 45 Hz band power
