
<p align="center">
  <img src="figs/logo.png" alt="SmoothConv & DuplexConv" width="920">
</p>

# SmoothConv & DuplexConv: Large-Scale Chinese Full-Duplex Speech Datasets for Conversational AI

<p align="center">
  <a href=""><img src="https://img.shields.io/badge/arXiv-Paper-COLOR.svg" alt="arXiv"></a>
  <a href="https://huggingface.co/datasets/qualialabsAI"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20HuggingFace-Dataset-yellow" alt="HuggingFace"></a>
  <a href="https://github.com/qualialabsAI/SmoothConv"><img src="https://img.shields.io/badge/GitHub-Repo-green" alt="GitHub"></a>
</p>

This is the official repository for the **SmoothConv** and **DuplexConv** twin datasets, co-developed by **ASLP@NPU** and **QualiaLabs**.

Open-source Chinese speech resources remain dominated by single-channel, scripted, or read-aloud corpora. **Large-scale, multi-channel datasets of spontaneous full-duplex dialogue**—with turn overlaps, backchannels, pauses, and real-time interruptions—are still scarce. **SmoothConv** and **DuplexConv** address this gap with **2,100 hours** of multi-party Chinese conversations in **Tutoring** and **Social Chat**, supporting turn-taking modeling, real-time interruption handling, and Speech LLM research.

<p align="center">
  <strong><a href="https://qualialabsai.github.io/SmoothConv-DuplexConv">Demo Page</a></strong> — Annotation sample videos and dataset distribution charts.
</p>

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

Recordings are **multi-channel** captures of real-world, unscripted dialogue in **Tutoring** and **Social Chat**. Two complementary annotation modes are derived from the same or closely related conversation sources—one for fine-tuning and benchmarking, one for large-scale pre-training:

### SmoothConv (~100 Hours — Expert Human Annotation)

A high-precision dataset for fine-tuning and benchmarking full-duplex dialogue models. Human annotators label real multi-party Chinese conversations with:

- **Aligned transcripts**: ASR text with millisecond-level timestamps at segment and turn boundaries.
- **Turn-taking & overlap**: Speaker switches, overlaps, and floor-holding—key signals for VAD and turn prediction.
- **Pauses & sound events**: Laughter, coughs, breaths, background noise, and silence.
- **Speaker attributes**: Gender and emotion tags per segment.

### DuplexConv (~2,000 Hours — LLM-Assisted Annotation at Scale)

DuplexConv draws from the **same or closely related conversation sources** as SmoothConv at much larger scale (~2,000 hours). An **automated LLM pipeline** produces transcripts, turn structure, and scene-level context labels—providing the volume needed for Speech LLM pre-training.

- **Scale for pre-training**: ~2,000 hours of multi-turn Chinese dialogue.
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
