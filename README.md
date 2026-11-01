# Subject Checklist Validator

LLM-backed quality gate for **curriculum questions**. Each item is scored against subject-specific JSON checklists (math, physics, chemistry, biology, English, social) so weak or off-curriculum items get caught before they reach students.

## Why it exists

EdTech pipelines generate questions faster than humans can review them. This project turns a teacher checklist into an automated pass/fail signal instead of a free-form chat.

## What it does

- Loads per-subject checklist rules from `checklists/*.json`
- Runs `Main_Validator.py` against candidate questions
- Returns structured validation signals for agents or batch jobs

## Stack

Python · checklist JSON · OpenAI-compatible LLM via env

## Quick start

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # if present; otherwise export OPENAI_API_KEY
python Main_Validator.py
```

## Portfolio note

Companion to `curriculum-qa-agents` (generate → validate). This repo is the **validator** half: deterministic checklists + LLM judgment.
