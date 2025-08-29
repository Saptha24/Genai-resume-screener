# 📄 GenAI Resume Screener (n8n + OpenAI)

AI-powered workflow to parse PDF resumes, summarise experience/skills, match against a Job Description, and output a 0–100 fit score. Built with **n8n** automation and **OpenAI**.

## Features
- Extract resumes (PDF → text)
- Summarise into structured JSON
- Match skills against JD
- Generate candidate fit score
- Store results in Google Sheets
- Notify HR via Email/Slack

## Setup
1. Import `workflows/resume_screener_workflow.json` into n8n
2. Add your OpenAI + Google Sheets credentials
3. Run with a sample resume in `data/sample_resumes/`

## Repo Contents
- `workflows/` → n8n workflow export
- `prompts/` → all LLM prompts
- `data/` → example inputs
- `notebooks/` → optional analysis
- `SECURITY.md` → privacy & PII handling
