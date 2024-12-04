# ChatGPT with Ollama

## About

ChatGPT with Ollama is an open source chat UI for Ollama.

Demo project. (https://chatgpt.ipv64.net)   (hosted localy with 100Mbit's)

## Updates

ChatGPT with Ollama will be updated over time.

### Pull ollama models

```shell
ollama pull ollama2
```


## Docker

Build locally:

```shell
docker build -t chatbot-ollama .
docker run -p 3000:3000 chatbot-ollama
```

Pull from ghcr:

```bash
docker run -p 3000:3000 ghcr.io/ivanfioravanti/chatbot-ollama:main
```

## Running Locally

### 1. Clone Repo

```bash
git clone https://github.com/BalkanCloud/chatgpt-ollama.git
```

### 2. Move to folder

```bash
cd chatbot-ollama
```

### 3. Install Dependencies

```bash
npm ci
```

### 4. Run Ollama server

Either via the cli:

```bash
ollama serve
```

or via the [desktop client](https://ollama.ai/download)

### 5. Run App

change the .env.local file

```bash
.env.local
```
```bash
DEFAULT_MODEL="Mistral-7B:latest"
NEXT_PUBLIC_DEFAULT_SYSTEM_PROMPT="You are a helpful, respectful and honest assistant.Help humman as much as you can."
```
and run the script with:
```bash
OLLAMA_HOST="http://0.0.0.0:11434" DEFAULT_MODEL='Mistral-7B:latest'  HOST=0.0.0.0 PORT=80 npm run dev
```
or:
```bash
npm run dev
```

### 6. Use It

You should be able to start chatting.

## Configuration

When deploying the application, the following environment variables can be set:

| Environment Variable              | Default value                  | Description                                                                                                                               |
| --------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| DEFAULT_MODEL                     | `ollama2`                | The default model to use on new conversations                                                                                             |
| NEXT_PUBLIC_DEFAULT_SYSTEM_PROMPT | [see here](utils/app/const.ts) | The default system prompt to use on new conversations                                                                                     |
| NEXT_PUBLIC_DEFAULT_TEMPERATURE   | 1                              | The default temperature to use on new conversations                                                                                       |

