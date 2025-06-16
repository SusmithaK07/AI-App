# Concept Explainer

A lightweight web application that provides simple explanations for complex concepts using locally-running Large Language Models (LLMs).


## Overview

Concept Explainer is a privacy-focused tool that leverages the power of local LLMs through [Ollama](https://ollama.ai/) to explain complex topics in simple terms. All processing happens on your machine - no data is sent to external APIs.

## Features

- **Simple Interface**: Clean, intuitive UI for entering concepts to explain
- **Local Processing**: All explanations are generated on your machine
- **Model Selection**: Choose from any model available in your Ollama installation
- **Adjustable Parameters**: Control response creativity with temperature settings
- **Responsive Design**: Works on both desktop and mobile devices
- **Automatic Logging**: All explanations are saved locally for future reference

## Prerequisites

- [Node.js](https://nodejs.org/) v14 or higher
- [npm](https://www.npmjs.com/) v6 or higher
- [Ollama](https://ollama.ai/) installed and running locally

## Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/concept-explainer.git
   cd concept-explainer
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables** (optional)
   ```bash
   cp .env-example .env
   # Edit .env file if you need to change default settings
   ```

4. **Start the application**
   ```bash
   npm start
   ```

5. **Access the app**
   Open your browser and navigate to:
   ```
   http://localhost:3000
   ```

## Using Ollama

### Installing Ollama

1. Visit [https://ollama.ai/](https://ollama.ai/)
2. Download and install the version for your operating system
3. Follow the installation instructions

### Managing Models

After installing Ollama, you'll need to pull at least one model:

```bash
# Pull the default model (recommended for beginners)
ollama pull llama3

# Other popular models
ollama pull mistral
ollama pull gemma
```

## How to Use the App

1. Enter a concept or term you want explained in the text area
2. Adjust the temperature slider:
   - Lower values (0.1-0.3): More focused, deterministic responses
   - Medium values (0.4-0.7): Balanced responses
   - Higher values (0.8-1.0): More creative, varied responses
3. Select your preferred model from the dropdown
4. Click "Explain" and wait for the response
5. The explanation will appear in the output section

## Development

For development with auto-restart on file changes:

```bash
npm run dev
```

## Logs

All explanations are automatically logged to:
```
logs/explanations.log
```

The log includes timestamps, user prompts, generated explanations, and any errors.

## Troubleshooting

### Common Issues

- **Connection Errors**: Ensure Ollama is running before starting the app
- **Model Not Found**: Make sure you've pulled the model you're trying to use
- **Slow Responses**: Response time depends on your hardware and the chosen model size

### Checking Ollama Status

To verify Ollama is running correctly:

```bash
# Check if Ollama is running
curl http://localhost:11434/api/tags

# Should return a JSON response with available models
```

## Tech Stack

- **Backend**: Node.js with Express
- **Frontend**: Vanilla JavaScript, HTML, CSS
- **LLM Integration**: Ollama API
- **Logging**: File-based using Node.js fs module

