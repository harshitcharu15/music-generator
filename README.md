# 🎼 Transformer-Based Music Generation Using Bach Cello Suites  
*A deep learning pipeline for tokenizing MIDI, training a Transformer, and generating new Bach-style music.*

This repository contains the full workflow and Colab notebook for generating symbolic music using a Transformer model trained on **J.S. Bach’s Cello Suites**. The project builds on the concepts from *Generative Deep Learning, 2nd Edition (Foster, 2023)* and adapts them for a dual-stream (note + duration) tokenization format.

---

## 🚀 Project Overview

This project demonstrates how to:

- Load MIDI files (Bach Cello Suites)
- Tokenize each **note** and **duration** into discrete vocabulary items  
- Train a Transformer model that learns Bach-style phrasing and motifs  
- Generate music starting from custom **START tokens**
- Export the generated sequence back into a **MIDI file**
- Play or download the output for further analysis

The training follows a sequence-to-sequence autoregressive structure, where the model predicts the next (note, duration) pair given prior tokens.

---

## 📁 Repository Structure

```text
bach-transformer-music-generation/
│
├── bach-transformer-music-generation.ipynb        # Full Colab-ready notebook
├── generated_bach_cello_transformer_sample.mid    # Example output MIDI file
├── README.md
└── /data
     └── bach_cello_midi/   # (User uploads Bach MIDI files here)
