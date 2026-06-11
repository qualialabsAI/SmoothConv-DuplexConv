
<p align="center">
  <img src="figs/logo_1.png" alt="SmoothConv & DuplexConv" width="720">
</p>

# SmoothConv & DuplexConv: Large-Scale Chinese Full-Duplex Speech Datasets for Conversational AI

<p align="center">
  <a href=""><img src="https://img.shields.io/badge/arXiv-Paper-COLOR.svg" alt="arXiv"></a>
  <a href="https://qualialabsai.github.io/SmoothConv-DuplexConv"><img src="https://img.shields.io/badge/%F0%9F%8E%AC%20Demo-Page-2563eb" alt="Demo Page"></a>
  <a href="https://huggingface.co/datasets/qualialabsAI"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20HuggingFace-Dataset-yellow" alt="HuggingFace"></a>
  <a href="https://github.com/qualialabsAI/SmoothConv-DuplexConv"><img src="https://img.shields.io/badge/GitHub-Repo-green" alt="GitHub"></a>
</p>

This is the official repository for the **SmoothConv** and **DuplexConv** datasets, co-developed by **ASLP@NPU** and **QualiaLabs**.

## Introduction

Open-source Chinese speech corpora remain dominated by single-speaker, read, or scripted data. **Multi-channel, spontaneous full-duplex multi-party conversation**, with overlapping speech, backchannels, interruptions, pauses, and turn transitions, is still scarce.

**SmoothConv** and **DuplexConv** are constructed from the **same underlying conversational sources** and are designed to complement each other. Together they provide **2,100 hours** of natural Chinese dialogue in **Tutoring** and **Social Chat**. **SmoothConv** (100 hours) offers high-fidelity expert human annotations for benchmarking and supervised training; **DuplexConv** (2,000 hours) provides large-scale LLM-assisted annotations for Speech LLM pre-training and data-driven modeling of conversational speech systems.

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

### SmoothConv (100 Hours — Expert Human Annotation)

**SmoothConv** contains **100 hours** of naturally occurring multi-party Chinese conversations in multi-channel **Tutoring** and **Social Chat** recordings. Unlike corpora dominated by read or scripted speech, it captures realistic full-duplex dynamics: overlapping speech, backchannels, interruptions, pauses, and turn transitions. Trained experts provide fine-grained labels, including:

- **Aligned transcripts** with millisecond-level timestamps
- **Turn-taking & overlap** (speaker switches, overlaps, floor-holding)
- **Pauses & sound events** (laughter, coughs, breaths, silence, etc.)
- **Speaker attributes** (gender, age, emotion, and related interaction tags)

### DuplexConv (2,000 Hours — LLM-Assisted Annotation)

**DuplexConv** scales to **2,000 hours** in the same domains, sharing a unified data design with SmoothConv. An LLM-assisted pipeline produces transcripts, speaker-aware conversational structures, turn-level interaction information, and scene-level contextual labels for large-scale Speech LLM pre-training and data-driven modeling.

Together, SmoothConv and DuplexConv bridge fine-grained human annotation and large-scale training in realistic full-duplex settings. See the [Demo Page](https://qualialabsai.github.io/SmoothConv-DuplexConv) for distribution charts.

---

## Dataset Statistics

| | SmoothConv | DuplexConv |
| :--- | :---: | :---: |
| **Annotation** | Expert human | LLM-assisted |
| **Duration** | 100.53 h | 2,000.21 h |
| **Audio files** | 2,503 | 93,709 |
| **Mean clip length** | 144.6 s | 76.8 s |
| **Clip length range** | 60.0 – 634.7 s | 8.0 – 618.3 s |
| **Domains** | Tutoring, Social Chat | Tutoring, Social Chat |


---

## FastTurn Test Set

A related **turn-state evaluation benchmark** derived from SmoothConv, available on [HuggingFace](https://huggingface.co/datasets/ASLP-lab/FastTurn-Testset). It combines real conversational segments with 1,000 synthesized **wait** samples (text: DeepSeek V3; audio: IndexTTS2) to supplement the naturally rare wait class.

| Turn State | Source | Samples | Duration (h) |
|------------|--------|--------:|-------------:|
| Complete | real-world | 14,709 | 9.64 |
| Incomplete | real-world | 3,643 | 2.15 |
| Backchannel | real-world | 3,080 | 0.42 |
| Wait | synthesized | 1,000 | 0.71 |

See the [FastTurn repository](https://github.com/ASLP-lab/FastTurn) for details.

---

## Contact

For questions or collaboration: [jimz@qualialabs.ai](mailto:jimz@qualialabs.ai)

---

## Ethics Statement

Guidelines for the responsible collection, release, and use of SmoothConv and DuplexConv.

- **Informed consent.** Conversations were recorded with the knowledge and consent of participants. Personal identifiers have been removed or anonymized prior to release.
- **Privacy protection.** The datasets are released for academic and research purposes only. Users must not attempt to re-identify speakers or reconstruct private information from the audio or annotations.
- **Intended use.** SmoothConv and DuplexConv are intended for research on spoken dialogue, turn-taking, and speech understanding. They must not be used for unauthorized surveillance, impersonation, or generating deceptive content.
- **Limitations & bias.** Annotations may contain errors; DuplexConv labels are machine-assisted. Researchers should account for domain, demographic, and annotation bias when training or evaluating models.
- **Responsible use.** By using these datasets, you agree to comply with applicable laws and ethical guidelines. Report suspected misuse to [jimz@qualialabs.ai](mailto:jimz@qualialabs.ai).

---

## License

Released under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

---

## Citation

If you use SmoothConv or DuplexConv in your research, please cite:

```bibtex
@article{wang2026duoconv,
  title   = {DuoConv: Large-Scale Chinese Full-Duplex Speech Datasets for Conversational AI},
  author  = {Chengyou Wang and Chunjiang He and Bo Wu and Yuyu Ji and Jimeng Zheng and Ruofei Chen and Lei Xie},
  journal = {arXiv preprint arXiv:0000.00000},
  year    = {2026},
  note    = {Placeholder; paper forthcoming}
}
```
