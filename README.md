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
├── bach-transformer-music-generation.ipynb   # Full Colab-ready notebook
├── generated_bach_cello_transformer_sample.mid # Example output MIDI file
├── README.md
└── /data
     └── bach_cello_midi/   # (User uploads Bach MIDI files here)
```

---

## 🧠 Model Architecture

The model consists of:

- **Dual token streams:**  
  - Note vocabulary (pitch names: C3, D#4, etc.)  
  - Duration vocabulary (quarter, half, whole encoded as floating values)

- **Embedding layers**
- **Token + Positional Encoding**
- **Stack of Transformer Blocks**
  - Multi-Head Attention  
  - Feed-forward layers  
  - LayerNorm + Dropout  
- **Two output heads:**  
  - Next-note prediction  
  - Next-duration prediction  

This design allows the Transformer to jointly model melody and rhythm.

---

## 📦 Dependencies

The notebook automatically installs:

- TensorFlow 2.15  
- music21  
- NumPy  
- Google Colab utilities  

The environment is GPU-compatible for faster training.

---

## 📚 How to Use the Notebook

### 1️⃣ Upload your MIDI files  
Place your Bach Cello Suite `.mid` files in:

```text
/content/bach_cello_midi/
```

You can upload manually or through the Colab upload dialog.

### 2️⃣ Run all cells  
The notebook performs:

- Data parsing  
- Tokenization  
- Vocabulary building  
- Dataset batching  
- Transformer training  
- Autoregressive generation  
- MIDI export  

### 3️⃣ Generate new music  
The notebook provides:

- A **top-k sampling** generator  
- A **temperature-based** creativity controller  
- Automatic MIDI rendering  

### 4️⃣ Download the generated MIDI  
The notebook outputs:

```text
generated_bach_transformer_sample.mid
```

Play it in:

- MuseScore  
- Ableton  
- GarageBand  
- Any online MIDI player  

---

## 🎧 Sample Output

A generated example MIDI file is included:

👉 `generated_bach_cello_transformer_sample.mid`

This file was created using the seed tokens **START_NOTE** and **START_DUR**, producing a Bach-like melodic line in G major.

---

## 🔍 Improvements in This Version

Compared to the raw code in the textbook’s repository, this implementation includes:

✔ Dual-stream note-duration tokenization  
✔ Top-k sampling to prevent repetition  
✔ Temperature control for creativity  
✔ Longer sequence windows  
✔ Cleaned MIDI parsing  
✔ Fully unified training + generation notebook  
✔ MIDI export with music21  

These enhancements result in **more coherent, tonally stable, and stylistically Bach-like** output.

---

## 🎯 Applications

- Music composition assistance  
- Symbolic music research  
- Transformer sequence modeling experiments  
- Creative AI projects  
- Coursework and academic submissions  
- Portfolio showcase for generative AI work  

---

## 📝 Citation

If you use this code in academic work:

```text
Foster, D. (2023). Generative Deep Learning: Teaching Machines to Paint, Write, 
Compose, and Play (2nd ed.). O’Reilly Media.

Kohli, H. (2025). Transformer-Based Music Generation Using Bach Cello Suites 
(Unpublished project report). University of the Cumberlands.
```

---

## 📄 License

This repository is for educational and research purposes.  
You may modify or extend it for personal, academic, or professional use.

---

## ⭐ Acknowledgments

- David Foster — *Generative Deep Learning 2nd Edition*  
- Google Colab for GPU compute  
- J.S. Bach for timeless musical architecture 🎻  
