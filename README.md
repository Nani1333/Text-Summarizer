# Text Summarizer 📚

A powerful text summarization tool built with Python that leverages state-of-the-art transformer models (BART and T5) to generate concise, accurate summaries from lengthy text inputs. Built using the Hugging Face Transformers library.

## Features ✨

- Generate concise summaries from long text passages
- Support for multiple transformer models (BART, T5)
- Flexible model loading (online or local)
- Clean, modular, and extensible codebase
- Easy integration with other applications

## Quick Start 🚀

1. **Clone the Repository**
```bash
git clone https://github.com/Nani1333/Text-Summarizer.git
cd Text-Summarizer
```

2. **Install Dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the Summarizer**
```bash
python main.py
```

## Installation Details 🔧

If `requirements.txt` is not available, install the required packages manually:
```bash
pip install torch transformers sentencepiece
```

## Project Structure 📁

```
Text-Summarizer/
├── main.py                      # Application entry point
├── summarizer.py               # Core summarization logic
├── sample_input.txt           # Example text for testing
├── saved_summarization_model/ # Optional local model storage
└── README.md                  # Documentation
```

## Usage Guide 📖

### Option 1: Online Model (Recommended) 🌐

Use models directly from Hugging Face's model hub:

```python
from transformers import pipeline

summarizer = pipeline("summarization", model="facebook/bart-large-cnn")
```

### Option 2: Local Model 💾

For using a locally saved model:

```python
from transformers import BartTokenizer, BartForConditionalGeneration

tokenizer = BartTokenizer.from_pretrained("saved_summarization_model/")
model = BartForConditionalGeneration.from_pretrained("saved_summarization_model/")
```

> **Note**: Local model files must be manually placed in the `saved_summarization_model/` directory.

## Supported Models 🤖

The project currently supports:
- `facebook/bart-large-cnn`
- `t5-base`

## Example Usage 💡

**Input Text:**
```
Text summarization is the task of shortening a set of data computationally to create a subset that represents the most important or relevant information
```

**Generated Summary:**
```
Text summarization shortens large content to key points using machine learning models.
```

## Roadmap 🗺️

- [ ] Web interface implementation (Streamlit/Flask)
- [ ] PDF and webpage summarization support
- [ ] Extractive summarization capabilities
- [ ] Batch document processing
- [ ] Custom model fine-tuning options

## Contributing 🤝

Contributions are welcome! Feel free to:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## Author 👨‍💻

**Nani1333**
- GitHub: [@Nani1333](https://github.com/Nani1333)

## License 📄

This project is open source and available under the MIT License.

---

Made with ❤️ by Nani1333
