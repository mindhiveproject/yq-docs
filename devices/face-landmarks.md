---
description: Video-based Facial Expression Detection
icon: camera-movie
---

# Face Landmarks

Face landmark detection relies on the open-source project, [Media Pipe](https://ai.google.dev/edge/mediapipe/solutions/guide). They provide AI/ML models that run on-device to analyze live video frames. This feature of the platform uses face landmark detection to calculate scores (coefficients corresponding to different expressions) of 52 locations across the face.

<details>

<summary>More information about the model</summary>

Traditionally, these models have been used to get face locations, calculate expressions, and, most notably, apply effects and filters.

</details>

### Output

The following list provides the predicted shapes

```
1 - browDownLeft
2 - browDownRight
3 - browInnerUp
4 - browOuterUpLe
5 - browOuterUpRight
6 - cheekPuff
7 - cheekSquintLe
8 - cheekSquintRight
9 - eyeBlinkLe
10 - eyeBlinkRight
11 - eyeLookDownLe
12 - eyeLookDownRight 13 - eyeLookInLe
14 - eyeLookInRight
15 - eyeLookOutLe
16 - eyeLookOutRight
17 - eyeLookUpLe
18 - eyeLookUpRight
19 - eyeSquintLe
20 - eyeSquintRight
21 - eyeWideLeft
22 - eyeWideRight
23 - jawForward
24 - jawLeft
25 - jawOpen
26 - jawRight
27 - mouthClose
28 - mouthDimpleLe
29 - mouthDimpleRight
30 - mouthFrownLe
31 - mouthFrownRight
32 - mouthFunnel
33 - mouthLe
34 - mouthLowerDownLe 35 - mouthLowerDownRight 36 - mouthPressLe
37 - mouthPressRight
38 - mouthPucker
39 - mouthRight
40 - mouthRollLower
41 - mouthRollUpper
42 - mouthShrugLower
43 - mouthShrugUpper
44 - mouthSmileLe
45 - mouthSmileRight
46 - mouthStretchLe
47 - mouthStretchRight
48 - mouthUpperUpLe
49 - mouthUpperUpRight 50 - noseSneerLe
51 - noseSneerRight
52 - tongueOut
```

This information was obtained from their [documentation](https://ai.google.dev/edge/mediapipe/solutions/vision/face_landmarker/index).



