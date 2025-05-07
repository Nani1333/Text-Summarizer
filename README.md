# 📝 Text Summarizer

A Python-based text summarization tool that uses transformer models like BART or T5 to generate concise summaries from longer input text. It leverages the Hugging Face Transformers library for state-of-the-art natural language processing.

---

## 🚀 Features

- Automatically generates short summaries of long passages.
- Supports both online model loading and local saved models.
- Clean and modular Python code.
- Easily extendable or integrable with other applications (like chatbots, document processing tools, etc.).

---

## 🧠 Model Information

This project uses a **transformer-based summarization model** such as:

- `facebook/bart-large-cnn`
- `t5-base`

You can either:
- Load the model dynamically from Hugging Face (recommended).
- Or use a locally saved model inside the `saved_summarization_model/` directory (if available).

---

## 📦 Installation

1. **Clone the repository**

```bash
git clone https://github.com/Nani1333/Text-Summarizer.git
cd Text-Summarizer
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

If `requirements.txt` is missing, you can install manually:

```bash
pip install torch transformers sentencepiece
```

---

## 📁 Project Structure

```bash
Text-Summarizer/
│
├── main.py                     # Entry point to run summarization
├── summarizer.py               # Core summarization logic
├── sample_input.txt            # Sample input file to test summarization
├── saved_summarization_model/ # (Optional) directory to hold a saved model
└── README.md                   # Project documentation
```

---

## 🛠️ How to Use

### 🔹 Option 1: Load Model from Hugging Face (Recommen. Open `summarizer.py` and use the following code:

```python
from transformers import pipeline

summarizer = pipeline("summarization", model="facebook/bart-large-cnn")
```

2. Run the summarizer:

```bash
python main.py
```

3. The input will be read from `sample_input.txt` and the summary will be printed to the terminal.

---

### 🔹 Option 2: Use Local Saved Model

If you've trained or downloaded a model and placed it in `saved_summarization_model/`, modify `summarizer.py` like this:

```python
from transformers import BartTokenizer, BartForConditionalGeneration

tokenizer = BartTokenizer.from_pretrained("saved_summarization_model/")
model = BartForConditionalGeneration.from_pretrained("saved_summarization_model/")
```

Then run:

```bash
python main.py
```

> ⚠️ Note: The saved model is **not pushed** to this repository due to size constraints. You must manually place your model files inside the `saved_summarization_model/` directory.

---

## 📌 Sample Output

### Input:
```
Text summarization is the task of shortening a set of data computationally to create a subset that represents the most important or relevant information```

### Output:
```
Text summarization shortens large content to key points using machine learning models.
```

---

## 📈 Future Enhancements

- Add a web-based interface using Streamlit or Flask.
- Support summarization for PDFs or web pages.
- Add option for extractive summarization alongside abstractive.
- Batch summarization of multiple documents.

---

## 🧑‍💻 Author

- GitHub: [Nani1333](https://github.com/Nani1333)

---
