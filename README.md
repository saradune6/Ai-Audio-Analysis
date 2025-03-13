# AI Audio Analysis

## Overview
AI Audio Analysis is a FastAPI-based application that processes audio files, transcribes speech, translates it into English, and performs AI-powered analysis using Whisper and Ollama. The project leverages machine learning models to extract insights from conversations and generate meaningful summaries.

## Features
- **Speech-to-Text:** Uses Whisper to transcribe audio files accurately.
- **Translation:** Converts transcribed text from Hindi to English using Google Translator.
- **AI Analysis:** Utilizes Ollama (Mistral model) to analyze conversations and generate summaries.
- **FastAPI Backend:** Provides an easy-to-use API for uploading and processing audio files.
- **MPS Acceleration:** Optimized for Apple Silicon (M1/M2) using Metal Performance Shaders (MPS).

## Installation
### Prerequisites
- Python 3.10+
- Anaconda (recommended)
- FastAPI
- Uvicorn
- Torch with MPS support
- WhisperX
- Deep Translator
- Ollama

### Setup Instructions
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ai-audio-analysis.git
   cd ai-audio-analysis
   ```
2. Create and activate a virtual environment:
   ```bash
   conda create --name ai-audio python=3.10
   conda activate ai-audio
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Install PyTorch with MPS support (for Apple Silicon):
   ```bash
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/mps
   ```

## Usage
### Running the FastAPI Server
Start the FastAPI server using Uvicorn:
```bash
uvicorn main:app --reload
```

### API Endpoints
#### 1. Analyze Audio
**Endpoint:** `/analyze-audio`
- **Method:** `POST`
- **Parameters:**
  - `file`: Audio file (UploadFile)
  - `analysis_type`: Type of analysis (default: "Summary of Call")
- **Response:**
  ```json
  {
    "transcription": "Transcribed text",
    "translated": "Translated text",
    "analysis": "AI-powered analysis"
  }
  ```

### Example API Call (cURL)
```bash
curl -X 'POST' \
  'http://127.0.0.1:8000/analyze-audio' \
  -H 'accept: application/json' \
  -H 'Content-Type: multipart/form-data' \
  -F 'file=@audio_sample.wav' \
  -F 'analysis_type=Summary of Call'
```

## Project Structure
```
├── main.py              # FastAPI application
├── requirements.txt     # Required dependencies
├── static/audio_files   # Directory for storing uploaded audio files
└── README.md            # Project documentation
```

## Contributing
Contributions are welcome! Feel free to fork the repository, submit pull requests, or report issues.

