# Agentic AI Labs

This repository contains my completed foundation labs from the Udemy course **The Complete Agentic AI Engineering Course**.

The original course repository uses separate provider API keys in some places. I adapted these labs to use **OpenRouter** so the same `OPENROUTER_API_KEY` can call multiple LLM providers through one OpenAI-compatible API.

## Included Labs

- `notebooks/1_lab1.ipynb` - Foundation API usage and first LLM calls
- `notebooks/2_lab2.ipynb` - Comparing multiple LLMs and judging their responses

## OpenRouter Adaptation

Lab 2 uses different model IDs through one OpenRouter client, including examples from OpenAI, Anthropic, Google, DeepSeek, and Llama-family models.

Example setup:

```python
from openai import OpenAI

client = OpenAI(
    api_key=openrouter_api_key,
    base_url="https://openrouter.ai/api/v1",
)
```

## Setup

These instructions are for Windows PowerShell. The project is intentionally much smaller than the original course repo, so you only need Python, `uv`, Jupyter, and an OpenRouter key.

1. Install prerequisites if you do not already have them.

- Git: https://git-scm.com/download/win
- Python 3.12 or newer: https://www.python.org/downloads/
- uv: https://docs.astral.sh/uv/getting-started/installation/

2. Clone this standalone showcase repository and enter it.

```bash
git clone <your-repo-url>
cd agentic-ai-labs-showcase
```

3. Install dependencies with `uv`.

```bash
uv sync
```

This creates a local `.venv` folder for the project.

4. Create a `.env` file from `.env.example`.

```env
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

The file must be named exactly `.env` and should live in the project root directory:

```text
agentic-ai-labs-showcase/.env
```

5. Open the notebooks.

```bash
uv run jupyter lab
```

If Jupyter asks you to select a kernel, choose the `.venv` Python environment for this project.

If you prefer activating the environment manually first, you can do this in Windows PowerShell:

```bash
.venv\Scripts\Activate.ps1
jupyter lab
```

Alternatively, use `pip` instead of `uv`:

```bash
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Notes

- Notebook outputs are cleared before publishing so API key prefixes, local paths, and temporary execution output are not committed.
- The real `.env` file is ignored by git.
- This is a standalone showcase repo. The full course repo is not required to run these copied notebooks.
- These notebooks are learning exercises, not production applications.
- I did not include the original `setup/SETUP-PC.md` file because it is specific to the full course repo and includes setup steps that this smaller OpenRouter showcase does not need.

## Attribution

Original lab material is from the Agentic AI Engineering course repository and is licensed under the MIT License. My changes adapt the labs for OpenRouter-based model access and document the setup for my learning portfolio.
