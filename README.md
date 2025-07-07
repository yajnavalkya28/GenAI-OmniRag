# GenAI-OmniRag
# 🌟 GenAI-OmniRAG: Multilingual AI Document Assistant

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://your-app-url.streamlit.app)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)


A powerful multilingual AI assistant that enables you to chat with any document using advanced RAG (Retrieval-Augmented Generation) technology. Upload PDFs, DOCX files, images, or provide web URLs/YouTube links to get instant summaries and engage in intelligent conversations about your content.

## 🚀 Key Features

### 📄 Universal Document Support
- **PDF Files**: Extract and process text from PDF documents
- **DOCX Files**: Parse Microsoft Word documents
- **Images**: OCR support for PNG, JPG, JPEG files using Tesseract
- **Web Pages**: Scrape and process content from any public webpage
- **YouTube Videos**: Automatic transcript extraction and processing

### 🌍 Multilingual Capabilities
- **5 Languages Supported**: English, Spanish, Hindi, Telugu, Tamil
- **Real-time Translation**: Powered by Groq's Llama 3 model
- **Localized UI**: Interface adapts to selected language
- **Text-to-Speech**: Hear summaries in your preferred language

### 🧠 Advanced AI Features
- **Intelligent Summarization**: Generate Markdown-formatted summaries with adjustable length
- **Conversational RAG**: Chat with your documents using context-aware responses
- **Smart Caching**: Streamlit-powered caching for faster processing
- **Vector Search**: FAISS-based semantic search for accurate information retrieval

### 📊 Export & Sharing
- **DOCX Reports**: Professional document reports with summaries and chat history
- **JSON Export**: Structured data export for further processing
- **Audio Summaries**: Text-to-speech functionality for accessibility

## 🛠️ Technology Stack

- **Frontend**: Streamlit
- **LLM**: Groq Llama 3 (8B-8192)
- **Embeddings**: HuggingFace all-MiniLM-L6-v2
- **Vector Store**: FAISS
- **OCR**: Tesseract
- **Document Processing**: LangChain, PyPDF, python-docx
- **Web Scraping**: BeautifulSoup4, WebBaseLoader
- **Audio**: Google Text-to-Speech (gTTS)

## 📸 Screenshots

> **Note**: Add your screenshots in the following locations:
> - `screenshots/main-interface.png` - Main application interface
> - `screenshots/document-upload.png` - Document upload process
> - `screenshots/summary-generation.png` - Summary generation example
> - `screenshots/chat-interface.png` - Chat interface with documents
> - `screenshots/multilingual-support.png` - Different language interfaces

![Main Interface](screenshots/main-interface.png)
*Main application interface with document upload options*

![Document Processing](screenshots/document-upload.png)
*Document upload and processing workflow*

![Summary Generation](screenshots/summary-generation.png)
*AI-generated summary with markdown formatting*

![Chat Interface](screenshots/chat-interface.png)
*Interactive chat interface with document context*

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Groq API key (get one from [Groq Console](https://console.groq.com/))
- Tesseract OCR installed on your system

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/GenAI-OmniRAG.git
   cd GenAI-OmniRAG
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Install system dependencies (for OCR)**
   
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
   Download and install from [GitHub Tesseract releases](https://github.com/UB-Mannheim/tesseract/wiki)

4. **Configure API key**
   
   Create a `.streamlit/secrets.toml` file in your project root:
   ```toml
   GROQ_API_KEY = "your-groq-api-key-here"
   ```

5. **Run the application**
   ```bash
   streamlit run app.py
   ```

6. **Access the application**
   
   Open your browser and navigate to `http://localhost:8501`

## 📋 Requirements

### Python Dependencies (`requirements.txt`)
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

### System Dependencies (`packages.txt`)
```
tesseract-ocr
tesseract-ocr-eng
libtesseract-dev
```

## 🎯 Usage Guide

### 1. Upload Content
- **Files**: Drag and drop PDF, DOCX, or image files
- **URLs**: Paste web page or YouTube video URLs
- **Multiple Sources**: Process multiple documents simultaneously

### 2. Configure Settings
- **Summary Length**: Adjust summary word count (100-1000 words)
- **Language**: Select your preferred language for interface and output

### 3. Process & Interact
- Click "Process Content" to analyze your documents
- Review the AI-generated summary
- Use the chat interface to ask questions about your content
- Listen to audio summaries with text-to-speech

### 4. Export Results
- **DOCX**: Download professional reports with summaries and chat history
- **JSON**: Export structured data for further analysis

## 🔧 Configuration

### Environment Variables
```bash
GROQ_API_KEY=your_groq_api_key_here
```

### Supported File Types
- **Documents**: `.pdf`, `.docx`
- **Images**: `.png`, `.jpg`, `.jpeg`
- **Web Content**: Any public webpage URL
- **Video**: YouTube video URLs

### Language Support
- **English** (en)
- **Spanish** (es) 
- **Hindi** (hi)
- **Telugu** (te)
- **Tamil** (ta)

## 🚀 Deployment

### Streamlit Cloud
1. Fork this repository
2. Connect your GitHub account to [Streamlit Cloud](https://streamlit.io/cloud)
3. Deploy your app
4. Add your `GROQ_API_KEY` in the Streamlit Cloud secrets management

### Docker Deployment
```dockerfile
FROM python:3.9-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    tesseract-ocr \
    tesseract-ocr-eng \
    libtesseract-dev \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy requirements and install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Expose port
EXPOSE 8501

# Run the application
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**
4. **Add tests** (if applicable)
5. **Commit your changes**
   ```bash
   git commit -am 'Add some feature'
   ```
6. **Push to the branch**
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Create a Pull Request**

### Development Guidelines
- Follow PEP 8 style guidelines
- Add docstrings to functions and classes
- Update README.md if needed
- Test your changes thoroughly

## 🐛 Troubleshooting

### Common Issues

**1. Tesseract not found**
```bash
# Make sure Tesseract is installed and in PATH
tesseract --version
```

**2. API Key errors**
- Verify your Groq API key is correctly set in `.streamlit/secrets.toml`
- Check if the API key has proper permissions

**3. Memory issues with large documents**
- Reduce chunk size in the text splitter
- Process documents in smaller batches

**4. OCR accuracy issues**
- Ensure images are clear and high resolution
- Consider preprocessing images for better OCR results

### Getting Help
- **Issues**: Report bugs via [GitHub Issues](https://github.com/yourusername/GenAI-OmniRAG/issues)
- **Discussions**: Join our [GitHub Discussions](https://github.com/yourusername/GenAI-OmniRAG/discussions)
- **Documentation**: Check our [Wiki](https://github.com/yourusername/GenAI-OmniRAG/wiki)



## 🙏 Acknowledgments

- **Groq** for providing high-speed LLM inference
- **Streamlit** for the amazing web framework
- **LangChain** for RAG capabilities
- **HuggingFace** for embeddings models
- **Open Source Community** for various libraries and tools

## 📈 Roadmap

- [ ] Support for more file formats (Excel, PowerPoint, etc.)
- [ ] Advanced chart and graph generation
- [ ] Multi-user collaboration features
- [ ] Custom embedding models
- [ ] Enhanced security features
- [ ] Mobile app development
- [ ] API endpoint creation

### 🌟 Star to Get Updates!
Star this repository to receive notifications about:
- 🚀 New features and updates
- 🐛 Bug fixes and improvements  
- 📚 Documentation updates
- 💡 Usage tips and tricks

[⭐ Star Now!](https://github.com/yourusername/GenAI-OmniRAG)

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/GenAI-OmniRAG&type=Date)](https://star-history.com/#yourusername/GenAI-OmniRAG&Date)

---

**Made with ❤️ by Yajnavalkya**

*If you find this project helpful, please consider giving it a star ⭐*

