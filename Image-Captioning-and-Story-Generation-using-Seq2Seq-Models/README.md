# 🧠 Neural Storyteller – Image Captioning using Seq2Seq

Neural Storyteller is a **multimodal deep learning project** that generates natural language descriptions from images using a **Sequence-to-Sequence (Seq2Seq)** architecture. The system combines **Computer Vision (CNNs)** and **Natural Language Processing (NLP)** to build an end-to-end image captioning pipeline.

---

## 🚀 Features

- ✅ Automatic image caption generation using deep learning
- 🧠 Pre-trained **ResNet50** for feature extraction
- 🔁 Encoder–Decoder **Seq2Seq architecture**
- 🔍 Greedy Search decoding strategy
- 🎯 Beam Search for improved caption quality
- 📊 Evaluation using BLEU, METEOR, Precision, Recall, and F1-score
- 🌐 Interactive **Gradio Web Application**
- 📈 Training & validation loss visualization

---

## 📂 Dataset

The model is trained on the **Flickr30k dataset**, which contains real-world images paired with multiple human-written captions.

🔗 Dataset:  
https://www.kaggle.com/datasets/adityajn105/flickr30k

### Dataset Details

- ~31,000 images
- Each image has multiple descriptive captions
- Covers diverse real-world scenes and objects
- Suitable for multimodal learning tasks

---

## 🏗️ Model Architecture

### 🔹 Feature Extraction (CNN Encoder Backbone)

- Uses **pre-trained ResNet50**
- Removes final classification layer
- Extracts **2048-dimensional feature vectors**
- Captures high-level visual representations
- Features are cached to speed up training

---

### 🔹 Seq2Seq Caption Generator

#### Encoder

- Fully connected linear projection layer
- Maps 2048-dim image features into a dense embedding space
- Produces initial hidden state for the decoder

---

#### Decoder

- **LSTM-based recurrent neural network**
- Uses learned word embeddings as input
- Generates captions sequentially (word-by-word)
- Predicts next token based on previous context and image features

---

## 📊 Evaluation Metrics

The model is evaluated using multiple NLP metrics:

- BLEU-1, BLEU-2, BLEU-3, BLEU-4
- METEOR Score
- Token-level Precision
- Token-level Recall
- F1 Score

These metrics measure both **syntactic accuracy and semantic quality** of generated captions.

---

## 🖼️ Example Output

The model workflow:

1. Input image is passed through CNN (ResNet50)
2. Feature vector is extracted
3. Seq2Seq decoder generates caption
4. Output is compared with ground truth captions

---

## 🌐 Web Application (Gradio)

The project includes a **Gradio-based interface** that allows users to:

- Upload an image
- Generate captions in real time
- Compare Greedy vs Beam Search outputs
- View evaluation results interactively

---

## 🛠️ Tech Stack

- Python
- PyTorch
- Torchvision
- NLTK
- NumPy
- Matplotlib
- Gradio

---
pip install -r requirements.txt
python app.py