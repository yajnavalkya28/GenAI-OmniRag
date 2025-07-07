# ⚡ OmniRAG: Multilingual AI Document Assistant

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

> **Chat with any document in multiple languages** - Upload PDFs, images, web pages, or YouTube videos and get instant AI-powered insights with multilingual support.

## View Steamlit APP
<p align="left">
  <a href="https://genai-omnirag.streamlit.app/?embed_options=show_colored_line,show_toolbar,show_padding,dark_theme,show_footer">
    <img src="https://img.shields.io/badge/Launch%20OmniRAG-Streamlit-darkgreen?style=for-the-badge&logo=streamlit" alt="Launch App">
  </a>
</p>

## 🌟 Features

- **📄 Multi-format Support**: PDF, DOCX, Images (PNG, JPG), Web URLs, YouTube videos
- **🌍 Multilingual**: Support for English, Spanish, Hindi, Telugu, and Tamil
- **🔊 Text-to-Speech**: Hear summaries in your preferred language
- **💬 Interactive Chat**: RAG-powered conversations with your documents
- **📊 Smart Summarization**: Adjustable summary length with Markdown formatting
- **📥 Export Options**: Download session reports as DOCX or JSON
- **⚡ Lightning Fast**: Powered by Groq LPU™ inference engine
- **🔍 OCR Support**: Extract text from images using Tesseract

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Tesseract OCR installed on your system
- Groq API key

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yajnavalkya28/GenAI-OmniRag.git
   cd GenAI-OmniRag
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Install Tesseract OCR**

   **Ubuntu/Debian:**
   ```bash
   sudo apt-get update
   sudo apt-get install tesseract-ocr tesseract-ocr-eng libtesseract-dev
   ```

   **macOS:**
   ```bash
   brew install tesseract
   ```

   **Windows:**
   Download and install from [Tesseract GitHub releases](https://github.com/UB-Mannheim/tesseract/wiki)

4. **Set up environment variables**
   
   Create a `.streamlit/secrets.toml` file:
   ```toml
   GROQ_API_KEY = "your_groq_api_key_here"
   ```

   Or set environment variable:
   ```bash
   export GROQ_API_KEY="your_groq_api_key_here"
   ```

5. **Run the application**
   ```bash
   streamlit run app.py
   ```

## 🎯 Usage

### 1. **Add Content**
   - Upload files: PDF, DOCX, or image files
   - Paste URLs: Web pages or YouTube video links
   - Multiple files supported simultaneously

### 2. **Configure Settings**
   - Select your preferred language
   - Adjust summary length (100-1000 words)

### 3. **Process & Interact**
   - Click "Process Content" to analyze your documents
   - Review the AI-generated summary
   - Chat with your content using natural language
   - Listen to summaries with text-to-speech

### 4. **Export Results**
   - Download session reports as DOCX or JSON
   - Share insights with your team

## 🛠️ Technical Architecture

### Core Components

- **Document Processing**: Multi-format loaders with OCR support
- **Embedding Model**: HuggingFace `all-MiniLM-L6-v2` for semantic search
- **Vector Store**: FAISS for efficient similarity search
- **Language Model**: Groq's Llama 3 (8B parameters) for chat and summarization
- **Translation**: AI-powered translation for multilingual support
- **Caching**: Streamlit's built-in caching for performance optimization

### Supported Languages

| Language | Code | UI Support | TTS Support |
|----------|------|------------|-------------|
| English  | en   | ✅         | ✅          |
| Spanish  | es   | ✅         | ✅          |
| Hindi    | hi   | ✅         | ✅          |
| Telugu   | te   | ✅         | ✅          |
| Tamil    | ta   | ✅         | ✅          |

## 📋 Requirements

### Python Dependencies
```
streamlit
langchain
langchain-groq
langchain-community
langchain-huggingface
faiss-cpu
pypdf
python-docx
youtube-transcript-api
pillow
pytesseract
beautifulsoup4
requests
sentence-transformers
gTTS
Markdown
```

### System Dependencies
```
tesseract-ocr
tesseract-ocr-eng
libtesseract-dev
```

## 🔧 Configuration

### Environment Variables

- `GROQ_API_KEY`: Your Groq API key (required)

### Streamlit Configuration

Create `.streamlit/config.toml` for custom settings:
```toml
[theme]
primaryColor = "#FF6B6B"
backgroundColor = "#FFFFFF"
secondaryBackgroundColor = "#F0F2F6"
textColor = "#262730"

[server]
maxUploadSize = 200
```

## 🚀 Deployment

### Streamlit Cloud

1. Fork this repository
2. Connect your GitHub account to [Streamlit Cloud](https://streamlit.io/cloud)
3. Deploy your app
4. Add your `GROQ_API_KEY` in the app settings

### Docker

```dockerfile
FROM python:3.9-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    tesseract-ocr \
    tesseract-ocr-eng \
    libtesseract-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

EXPOSE 8501

CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup

```bash
# Clone your fork
git clone https://github.com/yourusername/GenAI-OmniRag.git

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run tests (if available)
python -m pytest tests/
```

## 🙏 Acknowledgments

- **Groq** for the blazing-fast LPU™ inference engine
- **Langchain** for the RAG framework
- **Streamlit** for the beautiful web interface
- **HuggingFace** for embedding models
- **Tesseract** for OCR capabilities

## 📞 Support

- 🐛 **Bug Reports**: [Create an issue](https://github.com/yajnavalkya28/GenAI-OmniRag/issues)
- 📧 **Contact**: [yajnavalkyamaddi2006@gmail.com](mailto:yajnavalkyamaddi2006@gmail.com)

## 🗺️ Roadmap

- [ ] Add more language support
- [ ] Implement document comparison features
- [ ] Add support for audio files
- [ ] Integrate with cloud storage services
- [ ] Add user authentication
- [ ] Implement collaborative features

---

<div align="center">
  <strong>Made with ❤️ by Yajnavalkya</strong>
</div>
