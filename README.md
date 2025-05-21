# Text Summarizer 📚

A modern text summarization web application built with Python that leverages the T5 (Text-to-Text Transfer Transformer) model to generate concise, accurate summaries from lengthy text inputs. The application provides both a FastAPI-based web interface and a programmatic API for text summarization.

## Features ✨

- FastAPI-powered web interface for easy interaction
- T5-based text summarization with beam search
- Automatic text cleaning and preprocessing
- Support for both local and online model loading
- GPU acceleration (when available)
- RESTful API endpoints for integration
- Clean, modular, and production-ready codebase

## Quick Start 🚀

1. **Clone the Repository**
```bash
git clone https://github.com/Nani1333/Text-Summarizer.git
cd Text-Summarizer
```

2. **Set Up Virtual Environment (Recommended)**
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. **Install Dependencies**
```bash
pip install -r requirements.txt
```

4. **Run the Application**
```bash
uvicorn app:app --reload
```

The application will be available at `http://localhost:8000`

## Project Structure 📁

```
Text-Summarizer/
├── app.py                     # FastAPI application and core logic
├── requirements.txt          # Project dependencies
├── Template/                # HTML templates for web interface
├── Dataset/                 # Training and testing datasets
├── saved_summarization_model/ # Local model storage (optional)
└── README.md                # Documentation
```

## Technical Details 🔧

### Dependencies

- FastAPI: Web framework for building APIs
- Transformers: Hugging Face's transformer models
- T5Tokenizer & T5ForConditionalGeneration: Core summarization components
- PyTorch: Deep learning framework
- Uvicorn: ASGI server for FastAPI
- Additional utilities: sentencepiece, jinja2

### Model Architecture

The project uses the T5 (Text-to-Text Transfer Transformer) model, which treats all NLP tasks as a text-to-text problem. For summarization:

- Max input length: 512 tokens
- Max summary length: 150 tokens
- Beam search with 4 beams
- Early stopping enabled

## Usage Guide 📖

### Web Interface 🌐

1. Start the server: `uvicorn app:app --reload`
2. Open `http://localhost:8000` in your browser
3. Enter your text and click "Summarize"

### API Endpoint 🔌

```python
import requests

url = "http://localhost:8000/summarize/"
data = {"dialogue": "Your text here..."}
response = requests.post(url, json=data)
summary = response.json()["summary"]
```

### Local Development 💻

The application supports both local and online model loading:

```python
from transformers import T5Tokenizer, T5ForConditionalGeneration

# Local model (if available)
tokenizer = T5Tokenizer.from_pretrained("./saved_summarization_model")
model = T5ForConditionalGeneration.from_pretrained("./saved_summarization_model")

# Or from Hugging Face Hub
tokenizer = T5Tokenizer.from_pretrained("t5-base")
model = T5ForConditionalGeneration.from_pretrained("t5-base")
```

## Performance Optimization 🚀

- GPU acceleration when available
- Efficient text preprocessing
- Configurable beam search parameters
- Truncation and padding for optimal processing

## Roadmap 🗺️

- [ ] Add support for batch processing
- [ ] Implement custom model fine-tuning interface
- [ ] Add support for multiple language models
- [ ] Enhance the web UI with additional features
- [ ] Add API authentication and rate limiting
- [ ] Implement caching for frequent requests

## Contributing 🤝

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch
3. Implement your changes
4. Submit a pull request

Please ensure your code follows the project's coding standards and includes appropriate tests.

## Author 👨‍💻

**Nani1333**
- GitHub: [@Nani1333](https://github.com/Nani1333)

## License 📄

This project is open source and available under the MIT License.

---

Made with ❤️ by Nani1333
