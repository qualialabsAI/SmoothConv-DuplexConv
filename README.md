
<p align="center">
  <img src="figs/logo_1.png" alt="SmoothConv & DuplexConv" width="720">
</p>

# SmoothConv & DuplexConv: Large-Scale Chinese Full-Duplex Speech Datasets for Conversational AI

<p align="center">
  <a href=""><img src="https://img.shields.io/badge/arXiv-Paper-COLOR.svg" alt="arXiv"></a>
  <a href="https://qualialabsai.github.io/SmoothConv-DuplexConv"><img src="https://img.shields.io/badge/%F0%9F%8E%AC%20Demo-Page-2563eb" alt="Demo Page"></a>
  <a href="https://huggingface.co/datasets/qualialabsAI"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20HuggingFace-Dataset-yellow" alt="HuggingFace"></a>
  <a href="https://github.com/qualialabsAI/SmoothConv"><img src="https://img.shields.io/badge/GitHub-Repo-green" alt="GitHub"></a>
</p>

This is the official repository for the **SmoothConv** and **DuplexConv** datasets, co-developed by **ASLP@NPU** and **QualiaLabs**.

## Introduction

Open-source Chinese speech corpora remain dominated by single-speaker, read, or scripted data. **Multi-channel, spontaneous full-duplex multi-party conversation**—with overlaps, backchannels, interruptions, and pauses—is still scarce.

**SmoothConv** and **DuplexConv** address this gap with **2,100 hours** of natural Chinese multi-party dialogue in **Tutoring** and **Social Chat**. **SmoothConv** (100h) provides expert human annotations for fine-grained analysis and benchmarking; **DuplexConv** (2,000h) scales coverage via an LLM-assisted pipeline with transcripts, turn structure, and scene-level context. Together they support research on turn-taking, interruption handling, and full-duplex spoken dialogue.

> 🎬 **[Demo Page](https://qualialabsai.github.io/SmoothConv-DuplexConv)** · Annotation sample videos and dataset distribution charts.

---

## News

- **2026/06**: Official open-source release of **[SmoothConv](https://huggingface.co/datasets/qualialabsAI/SmoothConv)** (100h) and **[DuplexConv](https://huggingface.co/datasets/qualialabsAI/DuplexConv)** (2,000h).
- **2026/04/06**: Released the **[FastTurn Test Set](https://huggingface.co/datasets/ASLP-lab/FastTurn-Testset)**, constructed from a subset of SmoothConv data, for turn-state prediction evaluation.

---

## Download

* **SmoothConv**: [HuggingFace](https://huggingface.co/datasets/qualialabsAI/SmoothConv)
* **DuplexConv**: [HuggingFace](https://huggingface.co/datasets/qualialabsAI/DuplexConv)
* **FastTurn Test Set**: [HuggingFace](https://huggingface.co/datasets/ASLP-lab/FastTurn-Testset)

---

## Dataset Overview

Recordings are **multi-channel** captures of real-world, unscripted dialogue in **Tutoring** and **Social Chat**. Two complementary annotation modes are derived from the same or closely related conversation sources—one emphasizing annotation precision, one emphasizing coverage at scale:

### SmoothConv (~100 Hours — Expert Human Annotation)

A high-precision dataset for fine-tuning and benchmarking full-duplex dialogue models. Human annotators label real multi-party Chinese conversations with:

- **Aligned transcripts**: ASR text with millisecond-level timestamps at segment and turn boundaries.
- **Turn-taking & overlap**: Speaker switches, overlaps, and floor-holding—key signals for VAD and turn prediction.
- **Pauses & sound events**: Laughter, coughs, breaths, background noise, and silence.
- **Speaker attributes**: Gender and emotion tags per segment.

### DuplexConv (~2,000 Hours — LLM-Assisted Annotation at Scale)

DuplexConv draws from the **same or closely related conversation sources** as SmoothConv at much larger scale (~2,000 hours). An **automated LLM pipeline** produces transcripts, turn structure, and scene-level context labels.

- **Large-scale coverage**: ~2,000 hours of multi-turn Chinese dialogue.
- **Automated labels**: Dialogue content, speaker tone, emotional atmosphere, and conversational context.

---

## Dataset Statistics

### Global Overview

| Metrics | SmoothConv (Human Annotation) | DuplexConv (LLM Annotation) |
| :--- | :---: | :---: |
| **Language** | Chinese (zh) | Chinese (zh) |
| **Total Audio Duration** | **100.53 hours** | **2000.21 hours** |
| **Total Audio Files** | 2,503 | 93,709 |
| **Mean Duration** | 144.59 sec | 76.84 sec |
| **Duration Range** | 60.0 – 634.7 sec | 8.0 – 618.3 sec |
| **Domains** | Tutoring, Social Chat | Tutoring, Social Chat |

### SmoothConv

The current open-source release contains **100.53 hours** of conversational audio across **Tutoring** and **Social Chat**. Turn-taking labels include **complete**, **incomplete**, **backchannel**, and **wait**.

### FastTurn Test Set

A dedicated evaluation set for turn-state prediction, built from a subset of SmoothConv data. It combines real-world segments with 1,000 synthetically generated **wait** samples (text via DeepSeek V3, audio via IndexTTS2). Since **wait** is rare in natural speech, synthetic samples supplement the set.

| Turn State | Source | Samples | Duration (h) |
|------------|--------|--------:|-------------:|
| Complete | real-world | 14,709 | 9.64 |
| Incomplete | real-world | 3,643 | 2.15 |
| Backchannel | real-world | 3,080 | 0.42 |
| Wait | synthesized | 1,000 | 0.71 |

For details, see the [FastTurn repository](https://github.com/ASLP-lab/FastTurn).

---

## Contact

For questions or collaboration: [jimz@qualialabs.ai](mailto:jimz@qualialabs.ai)

---

## License

Released under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

## Citation

If you use SmoothConv or DuplexConv in your research, please cite:

```bibtex
@misc{smoothconv_duplexconv2026,
  author       = {{ASLP@NPU} and {QualiaLabs}},
  title        = {SmoothConv and DuplexConv: Large-Scale Chinese Full-Duplex Speech Datasets for Conversational AI},
  year         = {2026},
  publisher    = {GitHub},
  howpublished = {\url{https://github.com/qualialabsAI/SmoothConv}}
}
```
