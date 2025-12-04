# Ollama Cloud Interactive CLI

A lightweight Python command-line client for **Ollama Cloud**, supporting:
- API key storage in `~/.config/ollama-cloud/env`
- Model discovery
- Streaming chat responses
- Animated spinner while waiting
- Automatic suppression of “thinking” tokens
- Conversation history

This tool provides a simple, terminal-based interface to chat with any model available on Ollama Cloud.

---

## Features

- 🔑 Automatic API key loading and persistence  
- 📦 Fetch available models from Ollama Cloud  
- 🌀 Animated spinner during response generation  
- 💬 Streaming replies using `application/x-ndjson`  
- 🚫 Reasoning tokens are automatically skipped  
- 🧵 Multithreaded spinner for smooth output  

---

## Installation

### 1. Clone the repository

```sh
git clone https://github.com/<your-user>/<your-repo>.git
cd <your-repo>
````

### 2. Install dependencies

It is recommended to use a virtual environment:

```sh
python3 -m venv venv
source venv/bin/activate
```

Then install:

```sh
pip install -r requirements.txt
```

---

## Usage

Run the interactive chat tool:

```sh
python3 ollama_cloud_cli.py
```

On the first launch, the script will ask for your **Ollama API Key**:

```
No API key found.
Enter your Ollama API key:
```

It will be saved automatically in:

```
~/.config/ollama-cloud/env
```

Next:

1. The tool downloads the list of available models.
2. You select one by number.
3. Start chatting.

Type:

```
exit
```

to quit the program.

---

## Folder Structure

```
.
├── ollama_cloud_cli.py
├── README.md
└── requirements.txt
```

---

## Requirements

See [`requirements.txt`](./requirements.txt) for full details.

---

## Notes

* This client uses **Ollama Cloud**, not a local Ollama server.
* Responses are streamed for minimal latency.
* The spinner is disabled as soon as the first text token arrives.

---

## License

MIT License.

Feel free to modify or integrate this client into your own workflows.

