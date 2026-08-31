# 🎬 Sentiment Analysis - RNN Text Classification System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue) ![TensorFlow](https://img.shields.io/badge/TensorFlow-2.12-orange) ![Streamlit](https://img.shields.io/badge/Streamlit-1.28-red) ![Live Demo](https://img.shields.io/badge/Live%20Demo-Active-brightgreen)

---

## 🎯 Project Overview

A machine learning-powered **Sentiment Analysis System** that classifies movie reviews as positive or negative using Recurrent Neural Networks (RNN). This full-stack application features a trained SimpleRNN model, Streamlit web interface, and IMDB dataset integration for accurate sentiment classification with **85.8% accuracy**.

**Live Demo:** [https://sentiment-analysis-rnn-lccbnqgswwv7jtccdergwq.streamlit.app/](https://sentiment-analysis-rnn-lccbnqgswwv7jtccdergwq.streamlit.app/)

---

## ✨ Features

- ✅ **Sentiment Classification** - Binary classification of movie reviews (Positive/Negative)
- ✅ **Pre-trained RNN Model** - SimpleRNN with word embeddings achieving 85%+ accuracy
- ✅ **IMDB Dataset** - Trained on 50,000 real movie reviews
- ✅ **Streamlit Web App** - Interactive user interface for real-time predictions
- ✅ **Fast Inference** - Process predictions in <100ms per review
- ✅ **Jupyter Notebooks** - Complete training pipeline and analysis notebooks
- ✅ **Word Embeddings** - 32-dimensional embedding layer for semantic text representation
- ✅ **Production Ready** - Optimized model weights included (2.3 MB)

---

## 🏗️ Architecture

```
Input Text (Review)
    ↓
Embedding Layer (32 dims, 10K vocab)
    ↓
SimpleRNN Layer (128 units, ReLU)
    ↓
Dropout (0.5)
    ↓
Dense Layer (64 units, ReLU)
    ↓
Dropout (0.3)
    ↓
Output Layer (Sigmoid - Binary Classification)
    ↓
Sentiment Label + Confidence Score
```

---

## 📊 Model Performance

| Metric | Value |
|--------|-------|
| **Test Accuracy** | 85.8% |
| **Inference Time** | <100ms |
| **Model Size** | 2.3 MB |
| **Vocabulary** | 10,000 words |
| **Max Sequence** | 500 tokens |
| **Training Time** | ~5 minutes |

---

## 🚀 Quick Start

### Installation

```bash
# Clone repository
git clone https://github.com/Rahul6128/Sentiment-Analysis-RNN.git
cd sentiment-analysis-rnn

# Install dependencies
pip install -r requirements.txt
```

### Run Web Application

```bash
streamlit run main.py
```

Then open: `http://localhost:8501`

### Python Usage

```python
from tensorflow.keras.models import load_model
from tensorflow.keras.preprocessing.sequence import pad_sequences
import pickle

# Load model
model = load_model('simple_rnn_imdb.h5')
tokenizer = pickle.load(open('tokenizer.pkl', 'rb'))

# Predict
text = "This movie was absolutely fantastic!"
sequence = tokenizer.texts_to_sequences([text])
padded = pad_sequences(sequence, maxlen=500)
prediction = model.predict(padded)

sentiment = "Positive 😊" if prediction[0][0] > 0.5 else "Negative 😞"
confidence = prediction[0][0]

print(f"Sentiment: {sentiment}")
print(f"Confidence: {confidence:.2%}")
```

---

## 📁 Project Structure

```
sentiment-analysis-rnn/
│
├── 📄 README.md                    # Project documentation
├── 📄 LICENSE                      # MIT License
├── 📄 requirements.txt             # Python dependencies
│
├── 🐍 main.py                      # Streamlit web application
├── 🤖 simple_rnn_imdb.h5          # Pre-trained model weights
│
├── 📓 simplernn.ipynb              # Model training pipeline
├── 📓 embedding.ipynb              # Word embedding analysis
├── 📓 prediction.ipynb             # Inference examples
│
└── 📁 images/                      # Project images (optional)
```

---

## 📚 Dataset Information

- **Source**: IMDB Movie Reviews
- **Total Reviews**: 50,000
- **Training Set**: 25,000 reviews
- **Test Set**: 25,000 reviews
- **Sentiment Distribution**: 50% Positive, 50% Negative
- **Preprocessing**: Tokenization, padding to 500 tokens, index encoding

---

## 🎮 Usage Examples

### Example 1: Positive Review
```
Input: "Amazing movie! Best film I've seen all year!"
Output: Positive (98% confidence)
```

### Example 2: Negative Review
```
Input: "Worst movie ever made. Total waste of time."
Output: Negative (99% confidence)
```

### Example 3: Mixed Sentiment
```
Input: "It was okay, had some good parts but mostly boring."
Output: Negative (58% confidence)
```

---

## 🛠️ Technology Stack

| Component | Technology |
|-----------|-----------|
| **Deep Learning** | TensorFlow 2.12 / Keras |
| **Web Framework** | Streamlit 1.28 |
| **Data Processing** | NumPy, Pandas |
| **ML Utilities** | Scikit-learn |
| **Visualization** | Matplotlib |
| **Notebooks** | Jupyter |

---

## 📋 Requirements

```
tensorflow==2.12.0
keras==2.12.0
streamlit==1.28.0
numpy==1.24.3
pandas==2.0.3
scikit-learn==1.3.0
matplotlib==3.7.2
```

Install all: `pip install -r requirements.txt`

---

## 🔄 Training Details

**Model Configuration:**
- Optimizer: Adam (lr=0.001)
- Loss: Binary Crossentropy
- Batch Size: 32
- Epochs: 10
- Validation Split: 20%
- Early Stopping: Yes (patience=2)

**Performance Metrics:**
- Training Accuracy: 88.5%
- Validation Accuracy: 86.2%
- Test Accuracy: 85.8%

---

## 📝 Jupyter Notebooks

| Notebook | Purpose | Duration |
|----------|---------|----------|
| **simplernn.ipynb** | Model training & evaluation | 20 min |
| **embedding.ipynb** | Embedding layer analysis | 10 min |
| **prediction.ipynb** | Inference & prediction examples | 15 min |

---

## 🌐 Live Demo

**Try the interactive application:**

👉 [**Sentiment Analysis RNN - Live Demo**](https://sentiment-analysis-rnn-lccbnqgswwv7jtccdergwq.streamlit.app/)

- Enter any movie review
- Get instant sentiment prediction
- See confidence score
- Real-time analysis

---

## 📄 License

**MIT License** - See LICENSE file

This project is free to use, modify, and distribute for commercial and personal projects.

```
Copyright (c) 2024 Rahul Prajapati

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software")...
```

---

## 👤 Author

**Rahul Prajapati**

- GitHub: [@Rahul6128](https://github.com/Rahul6128)
- Repository: [sentiment-analysis-rnn](https://github.com/Rahul6128/Sentiment-Analysis-RNN.git)
- Location: Jaipur, India

---

## 🤝 Contributing

Contributions welcome! Please:

1. Open an issue for bugs or suggestions
2. Fork the repository
3. Create a feature branch
4. Submit a pull request

---

## 📞 Support & Issues

- **Report Bugs**: [GitHub Issues](https://github.com/Rahul6128/Sentiment-Analysis-RNN.git)
- **Questions**: Open an issue with `[question]` tag
- **Suggestions**: Share ideas in GitHub Discussions

---

## 🙏 Acknowledgments

- TensorFlow & Keras teams
- IMDB dataset contributors
- Streamlit for web framework
- Open-source community

---

<div align="center">

**Made with ❤️ by Rahul Prajapati**

⭐ Star this repo if you found it helpful!

[View on GitHub](https://github.com/Rahul6128/Sentiment-Analysis-RNN.git)

</div>
