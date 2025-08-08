# 🧠 English to Spanish Translator using LSTM (TensorFlow)

This project implements a sequence-to-sequence (seq2seq) neural machine translation model that translates English sentences into Spanish using TensorFlow and LSTM-based encoder-decoder architecture.

---

## 📌 Table of Contents

* Overview
* Dataset
* Model Architecture
* Installation
* Training
* Usage
* Example Output
* Future Improvements
* License

---

## 📖 Overview

This project is a minimal working demo of an LSTM-based neural machine translation system.
It uses:

* TextVectorization for tokenization
* Embedding layers with masking for variable-length input
* LSTM encoder-decoder for sequence modeling
* Greedy decoding for generating translations

It’s designed for learning purposes and can be extended with more advanced features like attention mechanisms or Transformers.

---

## 📂 Dataset

The dataset used is the English-Spanish parallel corpus from TensorFlow’s public storage.

Source: spa-eng.zip from [https://storage.googleapis.com/download.tensorflow.org/data/spa-eng.zip](https://storage.googleapis.com/download.tensorflow.org/data/spa-eng.zip)

It contains thousands of English-Spanish sentence pairs in the format:
English sentence → Spanish sentence

Example:
I like cars. → Me gustan los coches.

---

## 🏗 Model Architecture

The model follows the classic seq2seq encoder-decoder design:

1. Encoder: TextVectorization → Embedding → LSTM (returns hidden and cell states)
2. Decoder: TextVectorization → Embedding → LSTM (initialized with encoder states) → Dense Softmax
3. Training: Loss is Sparse Categorical Crossentropy and optimizer is Nadam

---

## ⚙ Installation

1. Clone the repository
2. Install dependencies: TensorFlow and NumPy

---

## 🏋 Training

Train the model on the dataset with the given script.
Uses 100,000 sentence pairs, vocabulary size 1000, and sequence length 50.
Trains for 10 epochs with validation data split.

---

## 💻 Usage

After training, the `translate()` function can be used to translate English sentences into Spanish.

---

## 📊 Example Output

Input: I like cars
Output: me gustan los coches

Input: I like soccer
Output: me gusta el fútbol

Note: The translations may vary slightly depending on training randomness.

---

## 🚀 Future Improvements

* Add attention mechanisms (Bahdanau or Luong)
* Replace LSTM with Transformer blocks
* Train with larger vocabulary and dataset
* Deploy with Streamlit or Gradio

---

## 📜 License

This project is licensed under the MIT License.
You can freely use and modify it for educational purposes.

---
