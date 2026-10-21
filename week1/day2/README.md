# Week 1 — Day 2: LLM System Prompts and API Practice

## Overview

This project explores how to interact with a Large Language Model (LLM) using the Groq API and Python. It builds on Day 1 by experimenting with system prompts, user messages, model selection, and temperature.

The practical example asks an AI model to suggest a one-word name for a clothing company.

## Learning Objectives

- Understand the difference between system and user messages.
- Use the Groq Python SDK to send chat-completion requests.
- Guide model behavior using a system prompt.
- Explore the temperature parameter.
- Load API credentials using environment variables.
- Manage Python dependencies using `uv`.

## Tech Stack

- Python
- Groq API
- Groq Python SDK
- python-dotenv
- uv

## Project Structure

```text
day2/
├── sys_temp.py
├── pyproject.toml
├── uv.lock
└── README.md
```

The virtual environment is local and should not be committed to Git.

## Practical Implementation

The script sends two messages to the model:

### System Message

The system message instructs the model to act as a brand manager and return only one word as a company name.

### User Message

The user prompt asks:

> Suggest a name for my clothing company.

### Temperature

The request uses `temperature=0` to favor more predictable outputs. It does not guarantee identical responses for every request.

## How to Run

### 1. Open the project directory

```powershell
cd week1\day2
```

### 2. Install dependencies

```powershell
uv sync
```

### 3. Configure your API key

Create a local `.env` file containing:

```text
GROQ_API_KEY=your_groq_api_key_here
```

Replace the placeholder with your own API key. Never commit `.env` or publish your API key.

### 4. Run the script

```powershell
uv run python sys_temp.py
```

The model should return a suggested clothing-company name.

## Key Concepts Learned

| Concept | Explanation |
|---|---|
| LLM | A model that generates language based on context. |
| API | An interface that allows software systems to communicate. |
| SDK | A library that simplifies API usage from Python. |
| System message | Instructions that guide the model's behavior. |
| User message | The request or input provided to the model. |
| Temperature | A parameter that influences output variability. |
| Environment variable | A way to provide configuration without hardcoding secrets. |
| Lockfile | Records resolved dependency versions for reproducible installations. |

## Troubleshooting

- **Missing API key:** Confirm that `.env` exists and `GROQ_API_KEY` is set correctly.
- **Model not found:** Check whether the model ID is currently supported by your API provider.
- **Dependency errors:** Run `uv sync` from the Day 2 project directory.
- **Unexpected output:** Review the system prompt, user message, and generation parameters.

## Current Progress

- [x] Initialize the Day 2 Python project.
- [x] Install Groq and python-dotenv.
- [x] Experiment with system and user messages.
- [x] Run the Python script.
- [x] Commit and push the initial Day 2 implementation.
- [ ] Integrate Google Gemini.
- [ ] Compare responses from multiple LLM providers.
- [ ] Complete multi-provider testing and document the results.

## Repository

[AI Engineering Learning — GitHub](https://github.com/Pratik-https/AI-Engineering-Learning)

---

*Part of my hands-on AI Engineering learning journey.*
