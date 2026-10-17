# Intelligent Real-Time Arabic Sign Language Translation

Senior Design Project 2 (B.Sc. Electrical Engineering, Islamic University of Madinah) - a complete system that translates **continuous sign language video into natural, spoken Arabic** in real time, for live webcam use or uploaded recordings.

## Pipeline
1. **Feature extraction** - Google MediaPipe Holistic: hand, face and body landmarks per frame.
2. **Idle detection & segmentation** - a hand-position state machine splits the stream into sign sequences.
3. **Classification** - a Bidirectional LSTM trained on the **ArabSign** dataset recognises 50 sentence classes (**92.07 % test accuracy** reported in the paper).
4. **LLM refinement** - a large language model turns raw predictions into grammatical Arabic.
5. **Text-to-speech** - the refined text is synthesised to audio.

## Contents
| Path | What it is |
|---|---|
| [`paper/Final_SDP2_Report.pdf`](paper/Final_SDP2_Report.pdf) | Final project report (68 pages): literature review, design, training/evaluation, future work |
| [`paper/LLM_and_TTS_Comparative_Analysis.pdf`](paper/LLM_and_TTS_Comparative_Analysis.pdf) | Study comparing five LLMs and several TTS engines for Arabic sign-gloss correction |
| `figures/` | System architecture, BiLSTM architecture, training curve, per-class results, latency plot |

## Code
The Flask/SocketIO web application (inference pipeline, LLM + TTS integration, model weights) is a team project hosted by a teammate at
**https://github.com/MoBa02/ASLTranslator** - see that repository for the source and setup instructions.

## Acknowledgements
Trained and evaluated on the **ArabSign** dataset: H. Luqman, *ArabSign: A Multi-modality Dataset and Benchmark for Continuous Arabic Sign Language Recognition*, IEEE FG 2023. The dataset is not redistributed here.
