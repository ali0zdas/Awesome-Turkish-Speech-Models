# Awesome Turkish Speech Models [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of ready-to-use, open-weight **Turkish Text-to-Speech (TTS)** and **Speech-to-Text (STT / ASR)** models.

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Awesome Lint](https://github.com/ali0zdas/Awesome-Turkish-Speech-Models/actions/workflows/lint.yml/badge.svg)](https://github.com/ali0zdas/Awesome-Turkish-Speech-Models/actions/workflows/lint.yml)

This list focuses strictly on pre-trained and fine-tuned models with downloadable weights ready for inference, local deployment, or voice agent pipelines.

## Contents

- [Quick Comparison](#quick-comparison)
  - [TTS Models Overview](#tts-models-overview)
  - [STT Models Overview](#stt-models-overview)
- [Text-to-Speech (TTS) Models](#text-to-speech-tts-models)
  - [Turkish-Native & Fine-Tuned](#turkish-native--fine-tuned)
  - [Lightweight & Edge (CPU / ONNX / Browser)](#lightweight--edge-cpu--onnx--browser)
  - [Multilingual Foundation & Zero-Shot Cloning](#multilingual-foundation--zero-shot-cloning)
  - [TTS Engines & Serving Frameworks](#tts-engines--serving-frameworks)
- [Speech-to-Text (STT / ASR) Models](#speech-to-text-stt--asr-models)
  - [Turkish-Native & Edge Streaming](#turkish-native--edge-streaming)
  - [High-Accuracy Turkish Fine-Tunes](#high-accuracy-turkish-fine-tunes)
  - [Multilingual Foundation Models](#multilingual-foundation-models)
  - [STT Runtimes & Serving Frameworks](#stt-runtimes--serving-frameworks)
- [Benchmarks & Community Collections](#benchmarks--community-collections)
- [Contributing](#contributing)

## Quick Comparison

### TTS Models Overview

| Model | Type / Base | Params | Key Highlight | Hardware |
| :--- | :--- | :---: | :--- | :--- |
| **Clarvia-TTS-Tiny** | Compact Neural | 4.54M | Ultra-tiny footprint for edge synthesis | CPU / Edge |
| **Ahenk Cep** | EMA Lightning (Distilled) | 8.6M | 34 MB FP32, runs directly in web browsers | CPU / Browser |
| **Seda-TTS v0.1** | Low-Latency TR TTS | Compact | ~0.1 s time-to-first-audio on 1 CPU thread | CPU / Edge |
| **Piper TTS (TR)** | VITS / ONNX | ~15–30M | Fast offline synthesis, MIT licensed | CPU / Edge |
| **Freya-TTS** | Turkish Neural TTS | 0.2B | Clean Python library (`freyatts`) | GPU / Low VRAM |
| **Anka TTS** | Reference-Guided TTS | 336M | Turkish synthesis with reference voice cloning | GPU (4–6 GB VRAM) |
| **EMA Lightning** | Flow Matching | Compact | Apache-2.0, very low WER, fast synthesis | GPU / Low VRAM |
| **Chatterbox** | Multilingual TTS | ~500M | MIT licensed, native TR + ONNX export | GPU / ONNX |
| **OmniVoice** | Multilingual Cloning | 0.6B | Fast zero-shot multilingual voice cloning | GPU (4–6 GB VRAM) |
| **Trendyol-TTS** | VoxCPM2 Fine-Tune | 2.38B | High-fidelity Turkish prosody (48 kHz) | GPU (8+ GB VRAM) |
| **Kizagan-TTS-v1.0** | Large Turkish TTS | 2B | Dedicated Turkish large-scale synthesis | GPU (8+ GB VRAM) |
| **Orpheus-TTS-TR** | Llama-3.2-3B | 3B | Inline emotion tags (laugh, sigh, gasp) | GPU (8+ GB VRAM) |

### STT Models Overview

| Model | Architecture | Params | Reported Benchmark / Highlight | Hardware |
| :--- | :--- | :---: | :--- | :--- |
| **Seda v0.2-Tiny** | Zipformer2 Transducer | 4.5M | Real-time streaming on phones & browsers | CPU / Mobile |
| **UfakZeka Kulak** | NeMo / GGUF | 31.6M | Trained from scratch for Turkish | CPU / Edge |
| **Balbal v2 / Manas** | Conformer-CTC + Refiner | 45M | 236x real-time on CPU; ~4.06–5.22% FLEURS WER | CPU / Edge |
| **Vitopeb STT 66M v2** | Streaming Zipformer | 66M | 68 MB INT8 (`sherpa-onnx`); 6.21% FLEURS WER (Damga) | CPU / Edge |
| **Qwen3-ASR** | Multilingual ASR | 0.6B / 1.7B | Strong modern multilingual baseline | GPU (4–6 GB VRAM) |
| **Whisper Large-v3-Turbo** | Encoder-Decoder | 809M | MIT licensed, strong speed-to-accuracy ratio | GPU (4–6 GB VRAM) |
| **TurkMedSTT General** | Whisper Large-v3 LoRA | 1.55B | Apache-2.0, trained on 140h balanced Turkish | GPU (6–8 GB VRAM) |
| **BuzzASR Turkish** | Whisper Large-v3 | 1.55B | SOTA open CER on combined FLEURS + Common Voice | GPU (6–8 GB VRAM) |
| **Kashgari-Large v1.0** | Large ASR (CTranslate2) | 2B | 4.53% FLEURS WER, 5.39% Common Voice 17 WER | GPU (8+ GB VRAM) |
| **Bitig-Large v1.0** | Large ASR (CTranslate2) | 2B | 4.69% FLEURS WER, evaluated across parliament & calls | GPU (8+ GB VRAM) |

## Text-to-Speech (TTS) Models

### Turkish-Native & Fine-Tuned

- [Ahenk TTS](https://huggingface.co/ozgurguler/ahenk-tts-tr) - CC-BY-4.0 licensed Turkish TTS model built on the VoxCPM architecture.
- [Anka TTS](https://huggingface.co/krmkayabasi/Anka-TTS) - 336M-parameter Turkish TTS model supporting reference audio voice cloning.
- [Antalia Mini](https://huggingface.co/cloud0day3/antalia-mini) - Compact Turkish TTS model packaged with a standalone Python wheel for quick installation.
- [DizgeTTS-Antalia](https://huggingface.co/iatagun/DizgeTTS-Antalia) - Turkish TTS model developed alongside the DizgeBERT G2P pipeline.
- [Drama-3 TR Speaker](https://huggingface.co/kasparovabi/drama-3-tr-speaker) - Turkish speaker adaptation built on the Fish Audio Drama-3 architecture.
- [Drifting-TTS-TR](https://huggingface.co/Vyvo/drifting-tts-tr) - Experimental Turkish speech synthesis checkpoint.
- [EMA Lightning](https://huggingface.co/canberkkkkkk/ema-lightning) - Apache-2.0 flow-matching Turkish TTS model known for low WER and natural prosody.
- [F5-TTS-Turkish](https://huggingface.co/marduk-ra/F5-TTS-Turkish) - Community Turkish fine-tune of the non-autoregressive F5-TTS flow-matching model for zero-shot voice cloning.
- [Freya-TTS](https://huggingface.co/freyavoice/Freya-TTS) - 0.2B-parameter Turkish TTS model with a lightweight `freyatts` Python inference package.
- [Gokbilge TTS](https://github.com/gokbilge/gokbilge-tts) - Open-source Turkish TTS built on VITS/Piper and trained on the ISSAI Turkish speech corpus.
- [Kani-TTS-400M-TR](https://huggingface.co/Anilosan15/kani-tts-400m-0.3-tr) - 400M-parameter Turkish text-to-speech model.
- [Kikiri Turkish Base](https://huggingface.co/duxx/kikiri-turkish-base) - Base Turkish text-to-speech checkpoint.
- [Kizagan-TTS-v1.0](https://huggingface.co/AlicanKiraz0/Kizagan-TTS-v1.0) - 2B-parameter open-weight Turkish speech synthesis model.
- [Nefes 0.5](https://huggingface.co/alicangunduz/nefes-0.5) - Community Turkish text-to-speech model.
- [Okur TTS](https://huggingface.co/ahakan/okur-tts) - Turkish text-to-speech checkpoint focused on clear narration.
- [Orpheus-KhanAcademy-TR](https://huggingface.co/kadirnar/Orpheus-KhanAcademy-TR) - 3B Orpheus TTS fine-tune trained on Turkish educational narration.
- [Orpheus-TTS-Turkish](https://huggingface.co/Karayakar/Orpheus-TTS-Turkish-PT-5000) - 3B Llama-3.2-based Turkish TTS fine-tune supporting inline non-verbal cues like laughter and sighs.
- [Qwen3-TTS-Turkish](https://huggingface.co/hcfk/qwen3-tts-turkish) - Turkish LoRA adaptation of `Qwen/Qwen3-TTS-0.6B-Base`.
- [Trendyol-TTS](https://huggingface.co/Trendyol/Trendyol-TTS) - 2.38B-parameter Turkish TTS model fine-tuned on `openbmb/VoxCPM2` with merged weights.
- [Yazgi-TTS-1](https://huggingface.co/erkamk/yazgi-tts-1) - Turkish text-to-speech model trained across multiple Turkish speech corpora.
- [Zerre TTS](https://huggingface.co/erkint/zerre-tts) - Lightweight community Turkish TTS checkpoint.

### Lightweight & Edge (CPU / ONNX / Browser)

- [Ahenk Cep](https://huggingface.co/ozgurguler/ahenk-cep-tr) - Distilled 8.6M-parameter (34 MB FP32) EMA Lightning student model fast enough to run in web browsers.
- [Clarvia-TTS-Tiny](https://huggingface.co/wite-tech/clarvia-tts-tiny) - Ultra-small 4.54M-parameter Turkish TTS model built for resource-constrained edge environments.
- [Meta MMS-TTS (tur)](https://huggingface.co/facebook/mms-tts-tur) - 36.3M-parameter VITS Turkish checkpoint from Meta's Massively Multilingual Speech project.
- [Piper TTS](https://github.com/rhasspy/piper) - Fast local neural TTS system powered by ONNX Runtime, with Turkish voices (`tr_TR-dfki-medium`, `tr_TR-fgl-medium`) hosted in [piper-voices](https://huggingface.co/rhasspy/piper-voices).
- [Pocket-TTS Turkish](https://huggingface.co/wite-tech/pocket-tts-turkish) - 0.1B-parameter compact Turkish TTS model for local deployment.
- [Seda-TTS v0.1](https://huggingface.co/atasoglu/seda-tts-v0.1) - Small low-latency Turkish TTS running on a single CPU thread with ~0.1 s time-to-first-audio.

### Multilingual Foundation & Zero-Shot Cloning

- [Audio8-TTS-Realistic-Air](https://huggingface.co/Edge0/Audio8-TTS-Realistic-Air) - 0.6B-parameter fast multilingual TTS checkpoint supporting Turkish.
- [Bark](https://huggingface.co/suno/bark) - Transformer-based text-to-audio model supporting expressive Turkish speech and non-verbal sounds (lighter variant: [bark-small](https://huggingface.co/suno/bark-small)).
- [Chatterbox](https://huggingface.co/ResembleAI/chatterbox) - MIT-licensed multilingual zero-shot TTS supporting Turkish, with a ready-to-use [ONNX export](https://huggingface.co/onnx-community/chatterbox-multilingual-ONNX).
- [Coqui XTTS-v2](https://huggingface.co/coqui/XTTS-v2) - Multilingual TTS model with native Turkish support, 6-second voice cloning, and low-latency streaming.
- [Fish Audio Drama-3](https://huggingface.co/fishaudio/drama-3) - 36B-parameter expressive multilingual speech synthesis model.
- [Fish Audio S2-Pro](https://huggingface.co/fishaudio/s2-pro) - 5B-parameter multilingual TTS model with zero-shot voice cloning.
- [Higgs-TTS-3-4B](https://huggingface.co/bosonai/higgs-tts-3-4b) - 5B-parameter multilingual speech generation model from Boson AI.
- [Kitten-TTS-2](https://huggingface.co/KittenML/kitten-tts-2) - 2B-parameter open-weight multilingual TTS model.
- [KugelAudio-0-Open](https://huggingface.co/kugelaudio/kugelaudio-0-open) - 9B-parameter open-weight multilingual TTS model supporting Turkish.
- [MOSS-TTS-Realtime](https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Realtime) - 2B-parameter streaming multilingual TTS built for real-time voice agents.
- [OmniVoice](https://huggingface.co/k2-fsa/OmniVoice) - 0.6B-parameter multilingual zero-shot voice cloning model from the k2-fsa ecosystem.
- [VoxCPM2](https://huggingface.co/openbmb/VoxCPM2) - 2B-parameter multilingual speech synthesis foundation model widely used as a base for Turkish fine-tunes.
- [ZONOS3-Mini](https://huggingface.co/Zyphra/ZONOS3-Mini) - 0.9B-parameter compact multilingual TTS model from Zyphra.

### TTS Engines & Serving Frameworks

- [Turkish-TTS](https://github.com/Boran-Sert/Turkish-TTS) - Modular Python library, HTTP/WebSocket 48 kHz streaming server, and single-call LoRA trainer wrapping Trendyol-TTS / VoxCPM2 weights.

## Speech-to-Text (STT / ASR) Models

### Turkish-Native & Edge Streaming

- [Balbal v2](https://huggingface.co/erayyapagci/balbal-v2) - 45M-parameter Conformer-CTC model with a 3-pass iterative refiner and 6-gram KenLM running at 236x real-time on 8 CPU threads (~5.22% FLEURS WER).
- [Balbal v2-Manas](https://huggingface.co/erayyapagci/balbal-v2-manas) - Higher-accuracy Balbal v2 variant achieving ~4.06% WER on FLEURS Turkish.
- [Duyu-small](https://huggingface.co/KaanAydinli/Duyu-small) - Compact Turkish automatic speech recognition checkpoint.
- [Seda v0.2](https://huggingface.co/atasoglu/seda-v0.2) - Turkish streaming ASR model designed for low-latency transcription with `sedalib`.
- [Seda v0.2-Tiny](https://huggingface.co/atasoglu/seda-v0.2-tiny) - 4.5M-parameter streaming Zipformer2 transducer tailored for mobile devices, slow CPUs, and browsers.
- [UfakZeka Kulak](https://huggingface.co/ufakai/ufakzeka-kulak) - 31.6M-parameter Turkish speech recognizer trained from scratch, distributed in `.nemo` and `GGUF` formats.
- [Vitopeb Turkish STT 66M v2](https://huggingface.co/Vitopeb/turkish-stt-66m-v2) - 66M-parameter (68 MB INT8) streaming Zipformer transducer for `sherpa-onnx`, scoring 6.21% WER on FLEURS-TR with Damga normalization (successor to `mihuai/turkish-stt`).

### High-Accuracy Turkish Fine-Tunes

- [Bitig-Large v1.0](https://huggingface.co/turkish-sa-asr/bitig-large-v1.0) - 2B-parameter Turkish ASR model with CTranslate2 builds, scoring 4.69% WER on FLEURS Turkish.
- [BuzzASR Turkish](https://huggingface.co/BuzzASR/turkish) - Monolingual Whisper Large-v3 fine-tune (EMNLP 2026 Findings) achieving state-of-the-art open-source CER on combined FLEURS and Common Voice Turkish test sets.
- [Kashgari-Large v1.0](https://huggingface.co/turkish-sa-asr/kashgari-large-v1.0) - 2B-parameter Turkish ASR research model with CTranslate2 support, reporting 4.53% WER on FLEURS and 5.39% WER on Common Voice 17.
- [TurkMedSTT General](https://huggingface.co/turkmedstt/whisper-large-v3-turkish-general) - Apache-2.0 merged LoRA fine-tune of Whisper Large-v3 trained on ~140 hours of balanced Turkish speech.
- [TurkMedSTT Medical](https://huggingface.co/turkmedstt/whisper-large-v3-turkish-medical) - Domain-adapted Turkish medical speech recognition model built on Whisper Large-v3.
- [Wav2Vec2-Large-XLSR-53-Turkish](https://huggingface.co/mpoyraz/wav2vec2-xls-r-300m-cv7-turkish) - 300M-parameter CTC acoustic model fine-tuned on Mozilla Common Voice Turkish.
- [Whisper Base Turkish 1.1](https://huggingface.co/ysdede/whisper-base-turkish-1.1) - Lightweight Turkish fine-tune of OpenAI Whisper Base for fast low-resource transcription.

### Multilingual Foundation Models

- [Meta MMS-1B-All](https://huggingface.co/facebook/mms-1b-all) - 1B-parameter wav2vec 2.0 adapter-based multilingual ASR model covering 1,000+ languages including Turkish.
- [Meta omniASR-CTC-7B](https://huggingface.co/facebook/omniASR-CTC-7B) - 7B-parameter multilingual CTC foundation model for automatic speech recognition.
- [Meta SeamlessM4T v2 Large](https://huggingface.co/facebook/seamless-m4t-v2-large) - Multimodal speech recognition and speech translation model with full Turkish audio and text support.
- [Microsoft VibeVoice-ASR](https://huggingface.co/microsoft/VibeVoice-ASR) - 9B-parameter multilingual speech recognition model.
- [NVIDIA Nemotron-3.5-Transcribe](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B) - Large-scale multilingual MoE transcription model supporting Turkish.
- [OpenAI Whisper Large-v3-Turbo](https://huggingface.co/openai/whisper-large-v3-turbo) - MIT-licensed 809M-parameter pruned Whisper v3 delivering high Turkish accuracy at fast decoding speeds.
- [Qwen3-ASR-0.6B](https://huggingface.co/Qwen/Qwen3-ASR-0.6B) - Compact multilingual automatic speech recognition model from the Qwen3-ASR family.
- [Qwen3-ASR-1.7B](https://huggingface.co/Qwen/Qwen3-ASR-1.7B) - High-accuracy 1.7B-parameter multilingual ASR checkpoint compatible with Hugging Face `transformers`.
- [Vosk Turkish](https://alphacephei.com/vosk/models) - Apache-2.0 lightweight offline streaming Kaldi model (`vosk-model-small-tr-0.3`) for embedded and mobile apps.

### STT Runtimes & Serving Frameworks

- [Faster-Whisper](https://github.com/SYSTRAN/faster-whisper) - CTranslate2 reimplementation of Whisper running up to 4x faster with INT8/FP16 quantization and lower VRAM usage.
- [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) - Cross-platform offline and streaming speech runtime powering ONNX/Zipformer Turkish edge models on CPU, Android, iOS, and WebAssembly.
- [Turkish-STT](https://github.com/Boran-Sert/Turkish-STT) - Open-source Turkish STT framework tailored for real-time voice agents with streaming, VAD, diarization, and punctuation.
- [Whisper.cpp](https://github.com/ggerganov/whisper.cpp) - High-performance C/C++ port of Whisper for zero-dependency Turkish ASR on CPU and Apple Silicon via GGUF.

## Benchmarks & Community Collections

- [Atasoglu Turkish STT Collection](https://huggingface.co/collections/atasoglu/turkish-stt-asr-models) - Actively maintained Hugging Face collection tracking open Turkish ASR checkpoints.
- [Atasoglu Turkish TTS Collection](https://huggingface.co/collections/atasoglu/turkish-tts-models) - Actively maintained Hugging Face collection cataloging Turkish-native and multilingual TTS models.
- [Turkish-SA-ASR Collection](https://huggingface.co/collections/turkish-sa-asr/turkish-speech-recognition) - Research collection publishing CTranslate2-ready Turkish ASR models and standardized evaluation scripts.
- [TurkMedSTT Benchmark & Models](https://huggingface.co/turkmedstt) - Organization hosting the 20-model, 1,060-clip `turkish-asr-benchmark` and medical/general Turkish ASR evaluations.
- [Turkish Speech & Text Collection](https://huggingface.co/collections/yagmurtuncer/turkish-speech-and-text-turkce-ses-ve-metin) - Community hub covering Turkish ASR leaderboards, synthetic speech, and Damga text normalization.

## Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.
