# Watsonx.ai Gradio Chatbot

A conversational Q&A chatbot built with **IBM Watsonx.ai** and **Gradio**, powered by Meta's Llama 3.2 and Mistral AI's Mistral Small models. Users can interact with large language models through a clean web interface, without any technical setup beyond cloning the repo.

---

## Demo

> Type any question into the input field and get an LLM-generated response in real time.

![Chatbot UI](assets/demo.png)

---

## Tech Stack

| Layer | Technology |
|---|---|
| LLM Backend | IBM Watsonx.ai (Llama 3.2 / Mistral Small) |
| Orchestration | LangChain + langchain-ibm |
| Frontend | Gradio 4.44 |
| API | IBM Watsonx AI SDK |
| Environment | Python 3.11, python-dotenv |

---

## Prerequisites

Before running this project locally, you need:

- Python 3.11+
- An **IBM Cloud account** (free Lite plan works)
- An **IBM Watsonx.ai project** with Watson Machine Learning enabled

### Set up IBM Watsonx.ai

1. Create a free account at [cloud.ibm.com](https://cloud.ibm.com)
2. Go to [watsonx.ai](https://dataplatform.cloud.ibm.com/wx/home) and create a new project
3. In your project, go to **Manage > General** and copy your **Project ID**
4. Go to **IBM Cloud > Manage > Access (IAM) > API keys** and generate an **API key**

---

## Quickstart

### 1. Clone the repo

```bash
git clone https://github.com/Jridi1/watsonx-gradio-chatbot.git
cd watsonx-gradio-chatbot
```

### 2. Create a virtual environment

```bash
python -m venv .venv

# Windows
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure environment variables

```bash
cp .env.example .env
```

Then edit `.env` and fill in your credentials:

```env
IBM_API_KEY=your_ibm_api_key_here
IBM_PROJECT_ID=your_project_id_here
```

### 5. Run the chatbot

```bash
python llm_chat.py
```

Open your browser at `http://127.0.0.1:7860` and start chatting.

---

## Switching Models

In `llm_chat.py`, you can switch between models by commenting/uncommenting:

```python
# Mistral Small
model_id = 'mistralai/mistral-small-3-1-24b-instruct-2503'

# Llama 3.2
# model_id = 'meta-llama/llama-3-2-11b-vision-instruct'
```

---

## Key Parameters

| Parameter | Default | Description |
|---|---|---|
| `MAX_NEW_TOKENS` | 256 | Maximum length of the generated response |
| `TEMPERATURE` | 0.5 | Controls creativity (0 = deterministic, 1 = creative) |

To get longer responses, increase `MAX_NEW_TOKENS` in the `parameters` dict.

---
