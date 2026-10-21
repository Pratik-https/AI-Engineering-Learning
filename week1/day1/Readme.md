# Day 1 — Your First LLM API Application

## Objective

Build and run a Python application that sends messages to a Large Language Model (LLM) through the Groq API and prints the generated response.

## Concepts Learned

### 1. Large Language Models (LLMs)

An LLM is a model trained on large amounts of data to understand and generate language. Common applications include chatbots, summarization, question answering, code generation, and information extraction.

An LLM generates output by predicting tokens based on its input and learned parameters. Its output can be incorrect and may require validation.

### 2. API and Groq

An API (Application Programming Interface) allows software systems to communicate through a defined interface.

Groq provides hosted inference for supported models. The Python application sends a request to the Groq API and receives a structured response.

- **LLM:** The model that generates output.
- **Groq:** The inference platform used in this project.
- **API:** The communication interface.
- **SDK:** A software library that simplifies API calls.
- **API key:** A credential used to authenticate requests.

### 3. Chat Completions

The application uses the chat-completions interface:

```python
response = client.chat.completions.create(
    model=model,
    messages=messages
)
```

- `client`: the initialized Groq client.
- `model`: the model ID to request.
- `messages`: an ordered list of conversation messages.
- `response`: the structured object returned by the API.

A message commonly contains `role` and `content`.

Example:

```python
messages = [
    {
        "role": "user",
        "content": "Explain artificial intelligence."
    }
]
```

Common roles include `system`, `user`, `assistant`, and `tool`.

Generated text can be accessed with:

```python
print(response.choices[0].message.content)
```

### 4. Model Configuration

The original model ID in my script was:

`llama-3.3-70b-versatile`

It returned a model-not-found error. I changed the model configuration to:

`openai/gpt-oss-120b`

This resolved the issue in my environment.

**Lesson:** Model IDs and availability can change. Check the provider's current model documentation and account access instead of assuming an old model ID will always work.

### 5. API Keys and Environment Variables

API keys authenticate requests and must be kept secret.

Example `.env` entry:

```dotenv
GROQ_API_KEY=your_actual_key_here
```

Never commit a real key to GitHub. Keep `.env` out of version control using `.gitignore`. If a key is exposed, revoke it and generate a replacement.

### 6. Virtual Environments and Dependencies

A virtual environment isolates a project's Python packages from other projects.

This project includes:
- `pyproject.toml`: project metadata and dependency configuration.
- `uv.lock`: resolved dependency versions for reproducible setup.
- `.venv/`: the local virtual environment, which should not be committed.

### 7. Debugging Experience

**Error:** `groq.NotFoundError`, HTTP 404, `model_not_found`.

**Cause:** The requested model ID was unavailable or inaccessible.

**Solution:** Verified model availability, updated the model ID, and reran the Python script.

**Learning:** Read the complete traceback, identify the failing operation, inspect the API error, and test one targeted fix at a time.

### 8. Git and GitHub

I initialized and verified my Git workflow, checked ignored files, staged the relevant Day 1 files, reviewed the staged changes, committed them, and pushed to my GitHub repository.

Repository: [AI-Engineering-Learning](https://github.com/Pratik-https/AI-Engineering-Learning)

Commit: `a379d9c`

### Interview Revision Questions

1. What is an LLM?
2. What is an API, and why use an SDK?
3. What is the difference between a model and an API?
4. What are `model` and `messages` in a chat-completions request?
5. What is the purpose of message roles?
6. How did I troubleshoot the model-not-found error?
7. Why use a virtual environment?
8. What is the purpose of `pyproject.toml` and `uv.lock`?
9. Why must API keys never be committed?
10. What does `.gitignore` do, and what are its limitations?

## Day 1 Completion Checklist

- [x] Ran a Python application that calls an LLM API.
- [x] Diagnosed and resolved a model configuration error.
- [x] Verified that sensitive environment files were ignored.
- [x] Committed and pushed Day 1 code to GitHub.
- [ ] Review these notes without looking at the answers.
- [ ] Explain the request-response flow independently.
- [ ] Complete an interview checkpoint before moving to Day 2.
