
# MaskGCT-Windows

MaskGCT-Windows is a Windows-compatible implementation of **MaskGCT**: a state-of-the-art, zero-shot, non-autoregressive Text-to-Speech (TTS) model that eliminates the need for explicit text-speech alignment and duration prediction. This implementation allows users to leverage the model's powerful capabilities in a Windows environment.

[![arXiv](https://img.shields.io/badge/arXiv-Paper-COLOR.svg)](https://arxiv.org/abs/2409.00750) [![HuggingFace Model](https://img.shields.io/badge/%F0%9F%A4%97%20HuggingFace-model-yellow)](https://huggingface.co/amphion/maskgct) [![HuggingFace Demo](https://img.shields.io/badge/%F0%9F%A4%97%20HuggingFace-demo-pink)](https://huggingface.co/spaces/amphion/maskgct) [![Key Features](https://img.shields.io/badge/README-Key%20Features-blue)]([../../../models/tts/maskgct/README.md](https://github.com/open-mmlab/Amphion/blob/main/models/tts/maskgct/README.md))

---

## Overview

**MaskGCT** is a fully non-autoregressive TTS model using a two-stage approach:
1. Predicting semantic tokens from text using a self-supervised learning (SSL) model.
2. Generating acoustic tokens conditioned on the semantic tokens using a mask-and-predict learning paradigm.

MaskGCT generates high-quality, intelligible, and similar speech in a parallel manner. It outperforms other zero-shot TTS models when trained on large-scale, diverse datasets. You can find more details and audio samples on the [demo page](https://maskgct.github.io/).

---

## Prerequisites

- **Python 3.10**: Install Anaconda Python or regular Python 3.10.
- **Git**: Install Git for Windows (see instructions below).
- **eSpeak-NG**: A text-to-phoneme converter used in MaskGCT.
- **FFmpeg**: Required for audio processing.

---

## Installation Steps

### 1. Installing Git

1. Download Git for Windows from the [official Git website](https://git-scm.com/download/win).
2. Run the installer and follow the on-screen instructions.
3. After installation, you should be able to use Git commands in your terminal.

---

### 2. Installing eSpeak-NG

1. Download `espeak-ng-X64.msi` from [this link](https://github.com/espeak-ng/espeak-ng/releases) and run the installer.
2. Add the following environment variable:
   - **Variable Name**: `PHONEMIZER_ESPEAK_LIBRARY`
   - **Value**: `C:\Program Files\eSpeak NG\libespeak-ng.dll`
3. **Note**: Remember to restart your terminal to apply the changes.

---

### 3. Installing FFmpeg

1. Download and install FFmpeg from the [official FFmpeg website](https://ffmpeg.org/download.html).
2. Add the path to `ffmpeg.exe` to your system's environment variables.

---

### 4. Setting Up the Python Environment

1. Clone the repository:
   ```bash
   git clone https://github.com/justinjohn0306/MaskGCT-Windows.git
   cd MaskGCT-Windows
   ```
2. Create a Conda environment and install dependencies:
   ```bash
   conda create -n maskgct python=3.10
   conda activate maskgct
   pip install -r requirements.txt
   ```

---

### 5. Downloading the Models

1. Download the pre-trained models from [this link](https://drive.google.com/file/d/1WRySDFvSvAsbReyYJWOOnHcYkQeDSDXt/view?usp=sharing).
2. Unzip the downloaded file and place the contents inside the repository.

---

## Usage

You can run MaskGCT using the **Gradio Playground** with the following command:

### Running Gradio App
```bash
python app.py
```

---

## Citations

If you use MaskGCT in your research, please cite the following papers:

```bibtex
@article{wang2024maskgct,
  title={MaskGCT: Zero-Shot Text-to-Speech with Masked Generative Codec Transformer},
  author={Wang, Yuancheng and others},
  journal={arXiv preprint arXiv:2409.00750},
  year={2024}
}
@inproceedings{amphion,
  author={Zhang, Xueyao and others},
  title={Amphion: An Open-Source Audio, Music and Speech Generation Toolkit},
  booktitle={{IEEE} SLT Workshop},
  year={2024}
}
```
