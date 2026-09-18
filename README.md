# 🧠 Next Word Predictor using LSTM

```{=html}
<p align="center">
```
`<b>`{=html}An NLP-based next-word prediction system powered by Deep
Learning and LSTM`</b>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
Predict the next word in a sentence using a trained LSTM language model
built on a news article dataset.
```{=html}
</p>
```

------------------------------------------------------------------------

## 📌 Overview

This project implements a **Next Word Prediction** system using a **Long
Short-Term Memory (LSTM)** neural network.

The model learns patterns, word sequences, and contextual relationships
from a collection of **news articles**. Given a starting phrase, the
model predicts one or more words that are likely to come next.

The project also includes a **Streamlit web interface** that allows
users to enter text and generate predictions interactively.

### ✨ Example

**Input:**

``` text
The government announced
```

**Possible prediction:**

``` text
a new policy
```

> The exact prediction depends on the trained model and the input
> context.

------------------------------------------------------------------------

## 🚀 Features

-   🧠 LSTM-based language model
-   📰 Trained on news article text
-   🔤 Tokenization and integer sequence generation
-   📏 Sequence padding for consistent model input
-   🔮 Multi-word next-word generation
-   💾 Saved trained model (`.h5`)
-   💾 Saved tokenizer (`.pkl`)
-   🖥️ Interactive Streamlit application
-   🐍 Python-based implementation
-   📓 Jupyter/Kaggle training notebook
-   📦 Requirements file for environment setup

------------------------------------------------------------------------

## 🏗️ Project Architecture

``` text
                 📰 News Articles
                        │
                        ▼
              ┌──────────────────┐
              │ Text Preprocessing│
              └────────┬─────────┘
                       │
                       ▼
                🔤 Tokenization
                       │
                       ▼
             📚 Sequence Generation
                       │
                       ▼
                📏 Padding
                       │
                       ▼
             ┌──────────────────┐
             │   LSTM Network   │
             └────────┬─────────┘
                      │
                      ▼
             🎯 Next Word Prediction
                      │
                      ▼
              🖥️ Streamlit App
```

------------------------------------------------------------------------

## 🛠️ Technologies Used

  Technology              Purpose
  ----------------------- ----------------------------------------
  🐍 Python               Core programming language
  🧠 TensorFlow / Keras   Deep learning model
  🔥 LSTM                 Sequence modeling
  🔤 NLP Tokenization     Convert words into numerical sequences
  📊 NumPy                Numerical operations
  🖥️ Streamlit            Interactive web application
  📓 Jupyter Notebook     Model development and experimentation
  ☁️ Kaggle               Model training environment
  🐙 Git / GitHub         Version control
  📦 Git LFS              Large model file storage

------------------------------------------------------------------------

## 📂 Project Structure

``` text
LSTM-New-Word-Predictor/
│
├── 📁 .vscode/
│
├── 📄 main.py
├── 📄 notebookee6c0554dd.ipynb
├── 📄 requirements.txt
│
├── 📰 News_Category_Dataset_v3.json
│
├── 🧠 nextword_model.h5
├── 🔤 tokenizer.pkl
│
└── 📄 README.md
```

### Important Files

**`main.py`**\
Streamlit application used to generate next-word predictions.

**`nextword_model.h5`**\
Trained LSTM model. Because the model is large, it is stored using **Git
LFS**.

**`tokenizer.pkl`**\
Serialized tokenizer used to convert input text into the same numerical
representation used during training.

**`News_Category_Dataset_v3.json`**\
News article dataset used for training the language model.

**`notebookee6c0554dd.ipynb`**\
Training and experimentation notebook.

------------------------------------------------------------------------

## ⚙️ How It Works

### 1. Text Tokenization

The news article text is converted into numerical tokens using a
tokenizer.

For example:

``` text
"the government announced"
```

may become:

``` text
[5, 27, 143]
```

The exact numbers depend on the trained tokenizer.

### 2. Sequence Creation

Text is converted into sequences where previous words are used to
predict the next word.

For example:

``` text
The
The government
The government announced
The government announced a
```

The model learns relationships between these sequences.

### 3. Padding

Because sequences can have different lengths, they are padded to a fixed
length:

``` python
from tensorflow.keras.preprocessing.sequence import pad_sequences
```

### 4. LSTM Prediction

The padded sequence is passed through the trained LSTM model.

The model outputs probabilities for the vocabulary, and the predicted
word is selected from the output.

### 5. Iterative Generation

For multi-word prediction, the newly predicted word is appended to the
input and the process is repeated.

``` text
Input
  ↓
Predict next word
  ↓
Append predicted word
  ↓
Predict again
  ↓
Repeat
```

------------------------------------------------------------------------

## 🖥️ Run the Application Locally

### 1. Clone the repository

``` bash
git clone https://github.com/kryptoadi/LSTM-New-Word-Predictor.git
cd LSTM-New-Word-Predictor
```

### 2. Create and activate a virtual environment

Using Conda:

``` bash
conda create -n ann python=3.12
conda activate ann
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```

### 4. Make sure Git LFS is installed

The trained model is approximately **240 MB**, so Git LFS is used for
the `.h5` file.

``` bash
git lfs install
git lfs pull
```

### 5. Start the Streamlit application

``` bash
streamlit run main.py
```

The application will open in your browser.

------------------------------------------------------------------------

## 🎯 Using the Application

1.  Enter a starting phrase.
2.  Specify the number of words to generate.
3.  Click **Generate**.
4.  The LSTM model generates the predicted continuation.

Example:

``` text
Input:
"Artificial intelligence"

Number of words:
5

Output:
"Artificial intelligence is changing the way..."
```

> Output will vary depending on the trained model and input.

------------------------------------------------------------------------

## 📊 Model Performance

During experimentation, the model achieved approximately:

``` text
Training Accuracy:    ~49%
Validation Accuracy:  ~13%
```

The training results show a noticeable difference between training and
validation performance, indicating that the model has learned the
training data substantially better than unseen validation data.

For a next-word prediction model, validation performance and predictions
on unseen text are important when evaluating generalization.

------------------------------------------------------------------------

## 🔬 Training

The model was trained using an LSTM architecture with TensorFlow/Keras.

Training was performed using **Kaggle GPU acceleration**, with the final
trained model exported as:

``` text
nextword_model.h5
```

The tokenizer used during training was saved separately:

``` text
tokenizer.pkl
```

Keeping the tokenizer is important because inference must use the same
vocabulary mapping that was used during training.

------------------------------------------------------------------------

## 💾 Large File Storage

The trained model is approximately **240 MB**, which exceeds GitHub's
standard maximum file size for normal Git objects.

Therefore, this project uses:

**Git LFS (Large File Storage)**

The `.gitattributes` file contains the LFS configuration for `.h5` model
files.

------------------------------------------------------------------------

## 🔮 Future Improvements

Potential improvements include:

-   [ ] Improve validation performance
-   [ ] Reduce overfitting using regularization
-   [ ] Experiment with different LSTM architectures
-   [ ] Add Early Stopping
-   [ ] Add Model Checkpointing
-   [ ] Experiment with Bidirectional LSTM
-   [ ] Try GRU and Transformer-based models
-   [ ] Add temperature-based sampling
-   [ ] Add Top-K / Top-P word sampling
-   [ ] Improve text preprocessing
-   [ ] Expand the training dataset
-   [ ] Deploy the Streamlit application online

------------------------------------------------------------------------

## 📚 Learning Outcomes

This project demonstrates practical experience with:

-   Natural Language Processing
-   Text preprocessing
-   Tokenization
-   Sequence generation
-   Padding
-   Recurrent Neural Networks
-   LSTM networks
-   Language modeling
-   Model training and evaluation
-   Model serialization
-   Streamlit deployment
-   GPU-based deep learning
-   Git and GitHub
-   Git LFS

------------------------------------------------------------------------

## 👨‍💻 Author

### Aditya Kumar

**Computer Science & Engineering**

Interested in:

-   🤖 Artificial Intelligence
-   🧠 Generative AI
-   📊 Data Science
-   🛠️ Machine Learning
-   💬 Natural Language Processing
-   🔥 Deep Learning

------------------------------------------------------------------------

## ⭐ If You Found This Project Useful

Feel free to **star ⭐ the repository**, explore the code, and
experiment with the model.

------------------------------------------------------------------------

```{=html}
<p align="center">
```
Built with ❤️ using Python, TensorFlow, Keras, LSTM & Streamlit
```{=html}
</p>
```
