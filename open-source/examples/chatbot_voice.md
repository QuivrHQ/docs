# Voice Chatbot Example

This example demonstrates how to create a voice-enabled chatbot using Quivr, Flask, and OpenAI's Whisper model. Users can ask questions via audio input and receive spoken responses.

## Features

- Audio input for asking questions
- Speech transcription using OpenAI's Whisper model
- Integration with Quivr API for intelligent responses
- Speech synthesis for audio playback

## Prerequisites

- Python 3.6+
- Flask
- OpenAI Python package
- Requests package

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/stangirard/quivr-whisper.git
   cd Quivr-talk
   ```

2. Install dependencies:
   ```bash
   pip install flask openai requests python-dotenv
   ```

3. Configure environment variables:
   ```env
   OPENAI_API_KEY='your_openai_api_key'
   QUIVR_API_KEY='your_quivr_api_key'
   QUIVR_CHAT_ID='your_quivr_chat_id'
   QUIVR_BRAIN_ID='your_quivr_brain_id'
   QUIVR_URL='https://api.quivr.app'
   ```

## Usage

1. Start the Flask application:
   ```bash
   flask run
   ```

2. Navigate to `http://localhost:5000`
3. Click "Ask a question to Quivr"
4. Record your question
5. Wait for transcription and response
6. Listen to the synthesized response

For the complete example code, visit our [GitHub repository](https://github.com/QuivrHQ/quivr/tree/main/examples/quivr-whisper).
