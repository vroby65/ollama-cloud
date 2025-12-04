# Ollama Cloud Interactive CLI

A lightweight Python command-line client for **Ollama Cloud**, supporting:

* Interactive chat mode
* Direct one-shot mode: `ollama-cloud <model> "prompt"`
* API key storage in `~/.config/ollama-cloud/env`
* Model discovery
* Streaming chat responses
* Animated spinner while waiting
* Automatic suppression of “thinking” tokens
* Conversation history

This tool provides a simple terminal interface to chat with any model hosted on Ollama Cloud.

---

## Features

* 🔑 Automatic API key loading and persistence
* 📦 Fetch available models from Ollama Cloud
* 🌀 Animated spinner during response generation
* 💬 Streaming replies using `application/x-ndjson`
* 🚫 Reasoning tokens are automatically filtered out
* 🧵 Smooth, thread-based spinner
* ⚡ **One-shot command mode** for direct usage
* 💬 Interactive persistent conversation mode

---

## Installation

### 1. Clone the repository

```sh
git clone https://github.com/vroby65/ollama-cloud.git
cd ollama-cloud
```

### 2. Install dependencies

Using a virtual environment is recommended:

```sh
python3 -m venv venv
source venv/bin/activate
```

Then install requirements:

```sh
pip install -r requirements.txt
chmod +x ollama-cloud
```

---

## Usage

### Interactive Mode

Start the chat interface:

```sh
./ollama-cloud
```

On the first run, the script will request your API key:

```
No API key found.
Enter your Ollama API key:
```

It will be stored automatically in:

```
~/.config/ollama-cloud/env
```

The tool will:

1. Retrieve the list of available models
2. Allow you to select one by number
3. Start an interactive streaming chat session

Quit anytime with:

```
exit
```

---

### One-Shot Command Mode

You can invoke the AI with a single terminal command:

```sh
./ollama-cloud <model> "your prompt here"
```

Examples:

```sh
./ollama-cloud gpt-oss:20b-cloud "Translate this sentence to Italian"
./ollama-cloud ministral-3:8b "Explain the concept of entropy"
```

This prints the streamed response directly to stdout without entering interactive mode.

---

## Folder Structure

```
.
├── ollama_cloud_cli.py
├── ollama-cloud
├── README.md
└── requirements.txt
```

The `ollama-cloud` file is the executable wrapper that runs the Python client.

---

## Requirements

Python ≥ 3.8
See [`requirements.txt`](./requirements.txt) for details.

---

## Notes

* This client communicates with **Ollama Cloud**, not a local Ollama instance.
* Responses are streamed token-by-token with minimal latency.
* The spinner stops automatically when the first actual token arrives.
* One-shot mode does not preserve conversation history.
* Interactive mode maintains chat history across requests in the session.

---

## License

MIT License.
You are free to use, modify, and integrate this CLI into other workflows.

