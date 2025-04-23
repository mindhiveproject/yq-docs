---
description: Video-based Heart Rate Estimation
icon: heart-pulse
---

# Video Heart Rate

To estimate the heart rate from video we are using an open-source algorithm that masks the face from the video using ML models and uses image-processing methods to track subtle changes in color and try to infer a person's heart rate. This method is often known as rPPG (remote photopletismography).

{% hint style="info" %}
Video heart rate can be greatly influenced by camera quality and lighting conditions. It's best to avoid over or under-exposing the frame.
{% endhint %}

### Output

* Heart Rate: a single number representing the estimated heart rate.

## Attribution

{% embed url="https://github.com/prouast/heartbeat-js/tree/master?tab=readme-ov-file" %}
