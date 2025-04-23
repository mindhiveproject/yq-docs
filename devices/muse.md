---
description: EEG & PPG Headset
icon: brain
---

# Muse

The Muse S and Muse 2 are research-grade EEG headbands for meditation and sleep. Visit the [Muse website](https://choosemuse.com) to learn more.&#x20;

## Using it in the platform

The Muse 2 headband is only compatible with Chromium-based browsers, which include Google Chrome, Microsoft Edge, and Opera.&#x20;

**To connect**, you don’t have to download anything. Simply turn on the device and proceed to connect it through the application using Bluetooth. If you have connectivity issues, oftentimes the best solution is to restart the device.

## Signals

### Sensors

* **EEG:** electroencephalography measures **brain activity** by capturing electrical activity from the brain. This device has four EEG electrodes meant to capture information from the frontal and temporal lobes of the brain as measured through the scalp.
* **PPG:** photopletismography measures changes in blood flow through light absorption or scattering by the hemoglobin in the blood.

### Output

#### **EEG raw signals**

According to the 10-20 international system, the Muse has the following electrodes.

* TP9&#x20;
* TP10
* AF8
* AF7

#### **EEG band power**

Band power quantifies a signal's strength in a specific frequency range. The value provided is the average power across all electrodes. The calculation is performed using a fast Fourier Transform at 20 Hz on a 2-second window

* Theta: 4 - 8 Hz band power
* Alpha: 8 - 12 Hz band power
* Low beta: 12 - 16 Hz band power
* High beta: 16 - 25 Hz band power
* Gamma: 25 - 45 Hz band power

#### **Other**

* PPG: raw signal obtained by the light sensor
* Heart rate: heart rate calculation from PPG&#x20;

## Attribution

To connect to the Muse on the browser, we used the implementation provided on the following GitHub.&#x20;

{% embed url="https://github.com/urish/muse-js" %}
