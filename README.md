# BiAVIS: Binaural Audio-Visual Instance Segmentation

This is the official implementation for BiAVIS:

> Binaural Audio-Visual Instance Segmentation

# 📋 Abstract

Audio-visual segmentation (AVS) aims to segment sounding objects at the pixel level by integrating auditory and visual cues. Existing methods are predominantly developed under the monaural setting and primarily rely on cross-modal semantic correspondence, which limits their ability to distinguish visually similar instances of the same semantic class. In contrast, humans naturally exploit binaural hearing, where interaural differences and direction-dependent acoustic filtering introduced by the head and pinnae provide physically grounded spatial cues for accurate sound source localization. Motivated by this observation, we introduce binaural audio-visual instance segmentation (BiAVIS), a new task that leverages synchronized binaural audio and video frames to segment sounding instances. To advance research on this task, we establish two benchmarks by manually annotating an existing binaural audio-visual dataset and collecting a new real-world dataset, BiAVIS-Bench, in more challenging and diverse scenarios. The proposed BiAVIS model (BiAVISM) features an audio-only sound source localization network that directly projects binaural spatial cues onto the image plane to learn spatial and semantic priors for sounding instances. A query-level audio-visual fusion strategy is subsequently introduced to inject these informative priors into the instance segmentation decoder. Extensive experiments conducted on the two proposed benchmarks demonstrate the superior performance of BiAVISM over previous monaural AVS methods, especially in resolving instance-level intra-class ambiguity. On the more challenging BiAVIS-Bench, BiAVISM achieves 26.65 mAP and 45.90 FSLA, corresponding to relative improvements of approximately 35.35% over AVISM in mean average precision (mAP) and 11.62% over ACVIS in frame-level sound localization accuracy (FSLA).

# 🪧 Overview

![overview](./assets/overview.png)

- We propose BiAVISM, a binaural audio-visual instance segmentation framework. It takes a video frame and synchronized binaural audio as input, and segments the sounding instances.
- An audio-only sound source localization network projects binaural spatial cues onto the image plane as dense sounding and class probability maps.
- Binaural priors are injected into a query-based segmentation decoder by query-level audio-visual fusion.
- The model is trained with segmentation, class-wise localization, and audio-visual consistency losses.

# 🗣️ Acknowledgements

Our localization backbone builds on [BAST](https://github.com/ShengKuangCN/BAST), and the visual decoder follows the query design of [Mask2Former](https://github.com/facebookresearch/Mask2Former). We also thank the authors of [AVISM](https://github.com/ruohaoguo/avis), [AVSegFormer](https://github.com/vvvb-github/AVSegFormer), and [COMBO](https://github.com/yannqi/COMBO-AVS) for their baselines and public code.
