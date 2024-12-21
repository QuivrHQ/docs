# Chatbot Example

This example demonstrates how to create a simple chatbot using Quivr and Chainlit. The chatbot allows users to upload a text file and then ask questions about its content.

## Prerequisites

- Python 3.8 or higher
- [Rye](https://rye.astral.sh/) package manager

## Installation

1. Clone the repository and navigate to the `examples/chatbot` directory.

2. Install the requirements using `rye`:
   ```sh
   rye sync
   ```

3. Activate the venv:
   ```sh
   source ./venv/bin/activate
   ```

## Running the Chatbot

1. Define your API key as environment variable:
   ```sh
   export OPENAI_API_KEY=your-key-here
   ```

2. Start the Chainlit server:
   ```sh
   chainlit run main.py
   ```

3. Open your web browser and go to `http://localhost:8000`.

## Using the Chatbot

1. Upload a text file (max 20MB)
2. Wait for processing
3. Start asking questions about the content
4. The chatbot will respond based on the information in the uploaded file

## How It Works

The chatbot uses Quivr to create a "brain" from the uploaded text file. This brain is then used to answer questions about the file's content. The Chainlit library provides the user interface and handles the chat interactions.

For the complete example code, visit our [GitHub repository](https://github.com/QuivrHQ/quivr/tree/main/examples/chatbot).
