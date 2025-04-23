---
icon: waveform
---

# Voice Emotion

This data source uses a [Speech Emotion Analyzer](https://github.com/tabahi/WebSpeechAnalyzer?tab=readme-ov-file) demo based on the **formantanalyzer** JavaScript library. This algorithm extracts syllables from the Mel-spectrogram of the input and feeds relevant statistical features into a single-layer neural network that classifies. This model was trained on datasets of actors going through dialogues or improvising. It predicts the following categories:

* Happiness
* Sadness
* Anger
* Neutral

From these labels, we output **valence** and **arousal** scores by using the relative happiness probability (for valence) and neutral probability (for arousal).

## Attribution

{% embed url="https://github.com/tabahi/WebSpeechAnalyzer" %}



