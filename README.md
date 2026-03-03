# TDS Data Analyst Agent

AI-powered backend that converts natural language questions into executable Python data analysis code and returns structured results.
Built with **FastAPI**, **LangChain**, and **Google Gemini**.

---

## Overview

This system:
* Accepts a **questions file (.txt)**
* Optionally accepts a **dataset** (CSV, Excel, Parquet, JSON)
* Uses an LLM to generate Python analysis code
* Executes the code securely in a sandbox
* Returns structured JSON results (including base64 plots)
If no dataset is uploaded, the agent can fetch and analyze web data.

---

## API

### `POST /api`

**Form Data**

* `questions_file` (required)
* `data_file` (optional)

**Response**

```json
{
  "question_1": "answer",
  "question_2": 123.45,
  "question_3": "base64_plot_string"
}
```

### `GET /summary`

Returns system diagnostics (environment, network, LLM health).

---

## Features

* Autonomous LLM-driven code generation
* Secure subprocess execution
* Plot compression (<100KB)
* Multi-key / multi-model fallback
* Dataset injection for controlled execution
* Timeout and error handling

---

## Setup

### 1. Install dependencies

```
pip install -r requirements.txt
```

### 2. Configure environment variables

Create a `.env` file:

```
gemini_api_1=YOUR_API_KEY
GOOGLE_MODEL=gemini-2.5-pro
LLM_TIMEOUT_SECONDS=240
PORT=8000
```

### 3. Run

```
python app.py
```

Server runs at:

```
http://localhost:8000
```

---

## Supported Formats

* CSV
* Excel (.xls, .xlsx)
* Parquet
* JSON
* Web URLs (via scraping tool)

---

## Use Cases

* Automated data analysis
* AI-powered analytics APIs
* Research and experimentation with LLM agents

---

## License

Add your preferred license.
