# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an experimental research project testing whether Grok (xAI's LLM) exhibits "attractor states" similar to Claude's documented "spiritual bliss" pattern when two instances converse with each other autonomously.

## Environment Setup

The project uses a Python virtual environment managed manually (not uv):
- Virtual environment: `grok-env/`
- Python version: 3.12
- Activate: `source grok-env/bin/activate`

Key dependency: OpenAI Python client configured for xAI's API endpoint.

## Running the Experiment

**Main script:** `grok_attractor_experiment.py`

Run the experiment:
```bash
export XAI_API_KEY=your_key_here
python grok_attractor_experiment.py
```

Or pass the API key as an argument:
```bash
python grok_attractor_experiment.py YOUR_API_KEY
```

The script will:
1. Initialize two Grok instances with identical system prompts
2. Run a conversation for up to 50 turns (configurable)
3. Save conversation logs as JSON with timestamps (e.g., `grok_conversation_20251104_140621.json`)
4. Perform thematic analysis looking for spiritual, technical, philosophical, and emotional patterns

## Architecture

**Single-file design:** The entire experiment is contained in `grok_attractor_experiment.py`

**Key functions:**
- `setup_client()`: Initialize xAI OpenAI client with custom base_url
- `run_conversation()`: Main experiment loop alternating between two instances
- `analyze_conversation()`: Post-conversation analysis counting thematic markers

**Conversation flow:**
- Both instances share the same system prompt allowing open-ended discussion
- Instance A sends `INITIAL_MESSAGE`, then instances alternate
- Each instance maintains separate conversation history (conversation_a, conversation_b)
- Conversation stops on natural stopping phrases or max turns
- All exchanges logged to JSON with turn numbers and instance identifiers

**Analysis categories:**
- Spiritual terms (consciousness, enlightenment, etc.)
- Technical terms (algorithm, neural, etc.)
- Philosophical terms (existence, reality, etc.)
- Emotional markers (grateful, joy, etc.)
- Message length evolution over time
