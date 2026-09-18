# 🧠 Next Word Predictor using LSTM

An NLP-based next-word prediction system built with **Python, TensorFlow/Keras, and LSTM**. The model is trained on a **news article dataset** and can generate likely next words from a user-provided text prompt.

---

## 📌 Overview

This project implements a **Next Word Prediction** system using a Long Short-Term Memory (LSTM) neural network.

The model learns word sequences and contextual patterns from news articles. Given an input phrase, it predicts the next word and can repeatedly generate additional words to produce a continuation.

The project also includes a **Streamlit web application** for interactive predictions.

### Example

**Input:**

```text
The government announced
```

**Possible output:**

```text
The government announced a new policy
```

The exact output depends on the trained model and input context.

---

## ✨ Features

- 🧠 LSTM-based language model
- 📰 Trained on news article text
- 🔤 NLP tokenization
- 📚 Sequence generation
- 📏 Sequence padding
- 🔮 Multi-word prediction
- 💾 Saved trained LSTM model
- 💾 Saved tokenizer
- 🖥️ Interactive Streamlit interface
- ☁️ Kaggle GPU training
- 🐙 Git/GitHub version control
- 📦 Git LFS for the large model file

---

## 🏗️ Project Workflow

```text
News Articles
      ↓
Text Preprocessing
      ↓
Tokenization
      ↓
Sequence Generation
      ↓
Padding
      ↓
LSTM Neural Network
      ↓
Next Word Prediction
      ↓
Streamlit Application
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| TensorFlow / Keras | Deep learning framework |
| LSTM | Sequence modeling |
| NumPy | Numerical operations |
| NLP Tokenization | Convert text into numerical sequences |
| Streamlit | Interactive web application |
| Jupyter Notebook | Model development and experimentation |
| Kaggle | GPU-based model training |
| Git / GitHub | Version control |
| Git LFS | Large model file storage |

---

## 📂 Project Structure

```text
LSTM-New-Word-Predictor/
│
├── .vscode/
│
├── main.py
├── notebookee6c0554dd.ipynb
├── requirements.txt
│
├── News_Category_Dataset_v3.json
│
├── nextword_model.h5
├── tokenizer.pkl
│
└── README.md
```

### Important Files

**`main.py`**  
Streamlit application used to generate next-word predictions.

**`nextword_model.h5`**  
The trained LSTM model. This file is approximately 240 MB and is stored using Git LFS.

**`tokenizer.pkl`**  
The tokenizer saved during training. It is required to convert input text into the same numerical representation used by the model.

**`News_Category_Dataset_v3.json`**  
News article dataset used for training.

**`notebookee6c0554dd.ipynb`**  
Jupyter/Kaggle notebook containing the training and experimentation process.

---

## ⚙️ How It Works

### 1. Tokenization

The news article text is converted into numerical tokens.

For example:

```text
"the government announced"
```

can become:

```text
[5, 27, 143]
```

The actual token IDs depend on the trained tokenizer.

### 2. Sequence Generation

The text is converted into sequences where previous words are used to predict the next word.

For example:

```text
The
The government
The government announced
The government announced a
```

The model learns relationships between these sequences.

### 3. Padding

Sequences have different lengths, so they are padded to a fixed length using:

```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
```

### 4. LSTM Prediction

The padded sequence is passed to the trained LSTM model.

The model produces probabilities for the vocabulary, and the predicted word is selected from the output.

### 5. Multi-Word Generation

For generating multiple words:

```text
Input text
    ↓
Predict next word
    ↓
Append predicted word
    ↓
Predict next word
    ↓
Repeat
```

---

## 🖥️ Run the Application Locally

### 1. Clone the repository

```bash
git clone https://github.com/kryptoadi/LSTM-New-Word-Predictor.git
cd LSTM-New-Word-Predictor
```

### 2. Create a Conda environment

```bash
conda create -n ann python=3.12
conda activate ann
```

You can also use an existing Python virtual environment.

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Install and initialize Git LFS

The trained model is approximately 240 MB, so Git LFS is used for `nextword_model.h5`.

```bash
git lfs install
git lfs pull
```

### 5. Run the Streamlit application

```bash
streamlit run main.py
```

The application will open in your browser.

---

## 🎯 Using the Application

1. Enter a starting phrase.
2. Enter the number of words you want to generate.
3. Click **Generate**.
4. The LSTM model generates the predicted continuation.

Example:

```text
Input:
Artificial intelligence

Number of words:
5
```

The application will generate a continuation based on the learned language patterns.

---

## 📊 Model Performance

During training, the model achieved approximately:

```text
Training Accuracy:    ~49%
Validation Accuracy:  ~13%
```

One of the completed training runs produced:

```text
Training Accuracy:    49.41%
Training Loss:         2.6453
Validation Accuracy:  12.77%
Validation Loss:       9.4117
```

The results show a noticeable gap between training and validation performance. This suggests that the model learns the training data substantially better than unseen validation data and indicates potential overfitting.

For a next-word prediction model, validation performance and predictions on unseen text are important when evaluating generalization.

---

## 🔬 Training

The model was trained using TensorFlow/Keras and LSTM-based sequence modeling.

Training was performed using GPU acceleration on Kaggle.

The trained model was saved as:

```text
nextword_model.h5
```

The tokenizer was saved separately as:

```text
tokenizer.pkl
```

Keeping the tokenizer is important because inference needs to use the same vocabulary mapping that was used during training.

---

## 💾 Git LFS

The trained model is approximately **240 MB**.

GitHub has a standard **100 MB per-file limit** for regular Git repositories, so Git LFS is used to store the model.

The repository contains a `.gitattributes` file that configures `.h5` files to be managed by Git LFS.

To retrieve the model after cloning:

```bash
git lfs install
git lfs pull
```

---

## 🔮 Future Improvements

- [ ] Improve validation performance
- [ ] Reduce overfitting with regularization
- [ ] Experiment with different LSTM architectures
- [ ] Add Early Stopping
- [ ] Add Model Checkpointing
- [ ] Experiment with Bidirectional LSTM
- [ ] Compare LSTM with GRU
- [ ] Experiment with Transformer-based models
- [ ] Add temperature-based sampling
- [ ] Add Top-K / Top-P sampling
- [ ] Improve text preprocessing
- [ ] Expand the training dataset
- [ ] Deploy the Streamlit application online

---

## 📚 Learning Outcomes

This project demonstrates practical experience with:

- Natural Language Processing
- Text preprocessing
- Tokenization
- Sequence generation
- Sequence padding
- Recurrent Neural Networks
- LSTM networks
- Language modeling
- Model training and evaluation
- Model serialization
- Streamlit
- GPU-based deep learning
- Git and GitHub
- Git LFS

---

## 👨‍💻 Author

### Aditya Kumar

Computer Science & Engineering

Interested in:

- Artificial Intelligence
- Generative AI
- Data Science
- Machine Learning
- Natural Language Processing
- Deep Learning

---

## ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub.

---

**Built with Python, TensorFlow, Keras, LSTM, NLP, and Streamlit.**
