<div align="center">

# Awesome Turkish Speech Models [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

**A curated list of ready-to-use, open-weight Turkish Text-to-Speech (TTS) and Speech-to-Text (STT / ASR) models.**

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Turkish](https://img.shields.io/badge/Language-Turkish_(TR)-E30A17.svg)](#)

*Focused strictly on pre-trained and fine-tuned models ready for inference and integration.*

</div>

---

## Contents

- [Quick Comparison](#quick-comparison)
  - [TTS Models Overview](#tts-models-overview)
  - [STT Models Overview](#stt-models-overview)
- [Text-to-Speech (TTS) Models](#text-to-speech-tts-models)
  - [Turkish-Native & Fine-Tuned](#turkish-native--fine-tuned)
  - [Multilingual & Zero-Shot Cloning](#multilingual--zero-shot-cloning)
  - [Lightweight & Edge (CPU / ONNX)](#lightweight--edge-cpu--onnx)
- [Speech-to-Text (STT / ASR) Models](#speech-to-text-stt--asr-models)
  - [Turkish-Native & Streaming](#turkish-native--streaming)
  - [High-Accuracy Turkish Fine-Tunes](#high-accuracy-turkish-fine-tunes)
  - [Multilingual Foundation Models](#multilingual-foundation-models)
  - [Inference Runtimes](#inference-runtimes)
- [Contributing](#contributing)

---

## Quick Comparison

### TTS Models Overview

| Model | Architecture | Params | Key Strength | Hardware | License |
| :--- | :--- | :---: | :--- | :--- | :--- |
| **[EMA Lightning](https://huggingface.co/canberkkkkkk/ema-lightning)** | Flow Matching | Compact | Ultra-low WER, fast synthesis | GPU / Low VRAM | Apache-2.0 |
| **[Ahenk Cep](https://huggingface.co/ozgurguler/ahenk-cep-tr)** | EMA Lightning (Distilled) | 8.6M | 34 MB FP32, runs in browser | CPU / Browser | Open |
| **[Trendyol-TTS](https://huggingface.co/Trendyol/Trendyol-TTS)** | VoxCPM2 | 2.38B | High-fidelity Turkish prosody | GPU (8+ GB VRAM) | Research |
| **[Orpheus-TTS-TR](https://huggingface.co/Karayakar/Orpheus-TTS-Turkish-PT-5000)** | Llama-3.2-3B | 3B | Emotion tags (laugh, sigh, etc.) | GPU (8+ GB VRAM) | Llama 3.2 |
| **[F5-TTS-Turkish](https://huggingface.co/marduk-ra/F5-TTS-Turkish)** | Flow Matching | ~335M | Zero-shot Turkish voice cloning | GPU (4–6 GB VRAM) | CC-BY-NC-4.0 |
| **[Chatterbox](https://huggingface.co/ResembleAI/chatterbox)** | Multilingual TTS | ~500M | Native TR + ONNX export available | GPU / ONNX | MIT |
| **[Coqui XTTS-v2](https://huggingface.co/coqui/XTTS-v2)** | GPT + HiFi-GAN | ~467M | 6-sec voice cloning, streaming | GPU (4–6 GB VRAM) | CPML |
| **[Piper TTS (TR)](https://github.com/rhasspy/piper)** | VITS / ONNX | ~15–30M | Ultra-fast local CPU synthesis | CPU / Edge | MIT |

### STT Models Overview

| Model | Architecture | Params | Key Strength | Hardware | License |
| :--- | :--- | :---: | :--- | :--- | :--- |
| **[Balbal v2](https://huggingface.co/erayyapagci/balbal-v2)** | Conformer-CTC + Refiner | 45M | 236x real-time on CPU, ~5.2% FLEURS WER | CPU / Edge | Open |
| **[Seda v0.2-Tiny](https://huggingface.co/atasoglu/seda-v0.2-tiny)** | Zipformer2 Transducer | 4.5M | Real-time streaming on phones & browsers | CPU / Mobile | Open |
| **[MihuAI STT v2](https://huggingface.co/mihuai/turkish-stt-66m-v2)** | Streaming Transducer | 66M | 68 MB INT8, `sherpa-onnx` native | CPU / Edge | Open |
| **[UfakZeka Kulak](https://huggingface.co/ufakai/ufakzeka-kulak)** | NeMo / GGUF | 31.6M | Trained from scratch for Turkish | CPU / Edge | Open |
| **[TurkMedSTT](https://huggingface.co/turkmedstt/whisper-large-v3-turkish-general)** | Whisper Large-v3 | 1.55B | General & medical Turkish fine-tunes | GPU (6–8 GB VRAM) | Apache-2.0 |
| **[Kashgari-Large](https://huggingface.co/turkish-sa-asr/kashgari-large-v1.0)** | Large ASR | 2B | ~4.53% WER on FLEURS Turkish | GPU (8+ GB VRAM) | Research |
| **[Whisper Large-v3-Turbo](https://huggingface.co/openai/whisper-large-v3-turbo)** | Encoder-Decoder | 809M | Best all-around multilingual baseline | GPU (4–6 GB VRAM) | MIT |
| **[Vosk (TR)](https://alphacephei.com/vosk/models)** | Kaldi | Lightweight | Fully offline streaming on embedded devices | CPU / Edge | Apache-2.0 |

---

## Text-to-Speech (TTS) Models

### Turkish-Native & Fine-Tuned

- [Trendyol-TTS](https://huggingface.co/Trendyol/Trendyol-TTS) - 2.38B-parameter Turkish TTS research model built on top of `openbmb/VoxCPM2` with merged weights.
- [EMA Lightning](https://huggingface.co/canberkkkkkk/ema-lightning) - Apache-2.0 licensed flow-matching Turkish TTS model recognized for very low WER and natural speech synthesis.
- [Ahenk TTS](https://huggingface.co/ozgurguler/ahenk-tts-tr) - Turkish TTS adaptation built on the VoxCPM architecture.
- [Orpheus-TTS-Turkish](https://huggingface.co/Karayakar/Orpheus-TTS-Turkish-PT-5000) - 3B Llama-3.2-based Turkish fine-tune supporting inline non-verbal emotion tags such as laughter, sighs, and gasps.
- [F5-TTS-Turkish](https://huggingface.co/marduk-ra/F5-TTS-Turkish) - Community Turkish fine-tune of the non-autoregressive `SWivid/F5-TTS` flow-matching architecture for zero-shot voice cloning.
- [Qwen3-TTS-Turkish](https://huggingface.co/hcfk/qwen3-tts-turkish) - Experimental Turkish LoRA adaptation of `Qwen/Qwen3-TTS-0.6B-Base`.
- [Gokbilge TTS](https://github.com/gokbilge/gokbilge-tts) - Open-source Turkish-native TTS project with reproducible training recipes and Turkish text normalization.
- [Turkish-TTS](https://github.com/Boran-Sert/Turkish-TTS) - Open-source modular TTS engine focused on streaming inference and low-latency Turkish synthesis.

### Multilingual & Zero-Shot Cloning

- [Chatterbox](https://huggingface.co/ResembleAI/chatterbox) - MIT-licensed multilingual TTS model supporting Turkish out of the box with zero-shot voice cloning; also available as [Chatterbox Multilingual ONNX](https://huggingface.co/onnx-community/chatterbox-multilingual-ONNX).
- [Coqui XTTS-v2](https://huggingface.co/coqui/XTTS-v2) - Widely used multilingual model with native Turkish support, 6-second voice cloning, and low-latency streaming.
- [KugelAudio-0-Open](https://huggingface.co/kugelaudio/kugelaudio-0-open) - Open-weight multilingual speech synthesis model with Turkish language support.
- [Bark](https://huggingface.co/suno/bark) - Transformer-based text-to-audio model capable of generating expressive Turkish speech with non-verbal cues.

### Lightweight & Edge (CPU / ONNX)

- [Ahenk Cep](https://huggingface.co/ozgurguler/ahenk-cep-tr) - Distilled 8.6M-parameter (34 MB FP32) student model using the EMA Lightning architecture, fast enough to run directly in web browsers.
- [Piper TTS](https://github.com/rhasspy/piper) - Fast local neural TTS system using ONNX Runtime, including `tr_TR-dfki-medium` and `tr_TR-fgl-medium` Turkish voices.
- [Meta MMS-TTS (tur)](https://huggingface.co/facebook/mms-tts-tur) - Lightweight VITS-based Turkish TTS checkpoint from Meta's Massively Multilingual Speech project.

---

## Speech-to-Text (STT / ASR) Models

### Turkish-Native & Streaming

- [Balbal v2](https://huggingface.co/erayyapagci/balbal-v2) - 45M-parameter Conformer-CTC model with a 3-pass iterative refiner and 6-gram KenLM, running at 236x real-time on 8 CPU threads (~5.22% FLEURS TR WER).
- [Balbal v2-Manas](https://huggingface.co/erayyapagci/balbal-v2-manas) - Higher-accuracy variant of the Balbal v2 architecture achieving ~4.06% WER on FLEURS Turkish.
- [Seda v0.2](https://huggingface.co/atasoglu/seda-v0.2) - Turkish streaming ASR model designed for use with `sedalib`.
- [Seda v0.2-Tiny](https://huggingface.co/atasoglu/seda-v0.2-tiny) - Ultra-compact 4.5M-parameter streaming Zipformer2 transducer built for slow CPUs, mobile devices, and web browsers.
- [MihuAI Turkish STT (66M v2)](https://huggingface.co/mihuai/turkish-stt-66m-v2) - 66M-parameter (68 MB INT8) online transducer optimized for real-time inference via `sherpa-onnx`.
- [UfakZeka Kulak](https://huggingface.co/ufakai/ufakzeka-kulak) - 31.6M-parameter Turkish speech recognizer trained from scratch, distributed in both `.nemo` and `GGUF` formats.
- [Duyu-small](https://huggingface.co/KaanAydinli/Duyu-small) - Compact Turkish automatic speech recognition model with an interactive demo.
- [Turkish-STT](https://github.com/Boran-Sert/Turkish-STT) - Open-source Turkish STT framework optimized for real-time voice agents with streaming, VAD, diarization, and punctuation.

### High-Accuracy Turkish Fine-Tunes

- [TurkMedSTT General](https://huggingface.co/turkmedstt/whisper-large-v3-turkish-general) - Apache-2.0 merged LoRA fine-tune of Whisper Large-v3 trained on 140 hours of balanced Turkish speech (~7.92% WER).
- [TurkMedSTT Medical](https://huggingface.co/turkmedstt/whisper-large-v3-turkish-medical) - Domain-adapted Turkish medical ASR checkpoint built on Whisper Large-v3.
- [Kashgari-Large v1.0](https://huggingface.co/turkish-sa-asr/kashgari-large-v1.0) - 2B-parameter research ASR model reporting ~4.53% WER on the FLEURS Turkish test set.
- [Bitig-Large v1.0](https://huggingface.co/turkish-sa-asr/bitig-large-v1.0) - 2B-parameter Turkish automatic speech recognition model from the `turkish-sa-asr` collection.
- [Wav2Vec2-Large-XLSR-53-Turkish](https://huggingface.co/mpoyraz/wav2vec2-xls-r-300m-cv7-turkish) - 300M-parameter CTC acoustic model fine-tuned on Mozilla Common Voice Turkish.

### Multilingual Foundation Models

- [OpenAI Whisper Large-v3-Turbo](https://huggingface.co/openai/whisper-large-v3-turbo) - MIT-licensed pruned Whisper v3 delivering strong Turkish accuracy at significantly faster decoding speeds.
- [NVIDIA Nemotron-3.5-Transcribe](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B) - Large-scale multilingual transcription model supporting Turkish.
- [Microsoft VibeVoice-ASR](https://huggingface.co/microsoft/VibeVoice-ASR) - 9B-parameter multilingual speech recognition model.
- [Meta omniASR-CTC-7B](https://huggingface.co/facebook/omniASR-CTC-7B) - 7B-parameter multilingual CTC foundation model for speech recognition.
- [Vosk Turkish](https://alphacephei.com/vosk/models) - Apache-2.0 offline streaming Kaldi model (`vosk-model-small-tr-0.3`) built for embedded and mobile applications.

### Inference Runtimes

- [Faster-Whisper](https://github.com/SYSTRAN/faster-whisper) - CTranslate2 reimplementation of Whisper running up to 4x faster with INT8/FP16 quantization and lower VRAM usage.
- [Whisper.cpp](https://github.com/ggerganov/whisper.cpp) - High-performance C/C++ port of Whisper enabling zero-dependency Turkish ASR on CPU and Apple Silicon via GGUF.

---

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) before opening a Pull Request or submitting a model via [Issues](../../issues/new/choose).
