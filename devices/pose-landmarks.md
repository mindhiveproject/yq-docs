---
description: Video-based Pose Tracking
hidden: true
---

# Pose Landmarks

Pose landmark detection relies on the open-source project, [Media Pipe](https://ai.google.dev/edge/mediapipe/solutions/guide). They provide AI/ML models that run on-device to analyze images or live video frames. This feature of the platform uses [pose landmark detection ](https://ai.google.dev/edge/mediapipe/solutions/vision/pose_landmarker)to detect people in the scene and track the approximate location of 33 body parts.

### Output

The models output each landmark's normalized location of x, y, and z coordinates. The three coordinates correspond to:

* `x` and `y`: Landmark coordinates normalized to `[0.0, 1.0]` by the image width and height respectively.
* `z`: Represents the landmark depth with the depth at the midpoint of hips being the origin, and the smaller the value the closer the landmark is to the camera. The magnitude of `z` uses roughly the same scale as `x`.

The following list describes the approximate key points they track:

```
0 - nose
1 - left eye (inner)
2 - left eye
3 - left eye (outer)
4 - right eye (inner)
5 - right eye
6 - right eye (outer)
7 - left ear
8 - right ear
9 - mouth (left)
10 - mouth (right)
11 - left shoulder
12 - right shoulder
13 - left elbow
14 - right elbow
15 - left wrist
16 - right wrist
17 - left pinky
18 - right pinky
19 - left index
20 - right index
21 - left thumb
22 - right thumb
23 - left hip
24 - right hip
25 - left knee
26 - right knee
27 - left ankle
28 - right ankle
29 - left heel
30 - right heel
31 - left foot index
32 - right foot index
```

This information was directly retrieved from their [documentation](https://github.com/google-ai-edge/mediapipe/blob/master/docs/solutions/pose.md#output).&#x20;

&#x20;
