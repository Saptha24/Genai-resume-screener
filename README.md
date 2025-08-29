# 📄 GenAI Resume Screener (n8n + OpenAI)

AI-powered workflow to parse PDF resumes, summarise experience/skills, match against a Job Description, and output a 0–100 fit score. Built with **n8n** automation and **OpenAI**.

## ✨ What it does
- Extracts text from PDF resumes
- Normalises Job Description (JD) into structured requirements
- Summarises resume into consistent JSON
- Computes a candidate fit score (skills, experience, projects, education, soft skills)
- Writes results to Google Sheets and notifies via email/Slack

## 🏗️ Architecture
```
Trigger → Read File (PDF) → PDF Extract → OpenAI (JD normalize) → OpenAI (Resume summarise)
→ OpenAI (Keywords) → OpenAI (Scoring) → Function (validate + enrich) → Google Sheets
→ Email/Slack (notify) → IF (score ≥ threshold) → Shortlist sheet
```

## 🚀 Quick start
1) **Clone**
```bash
git clone https://github.com/<your-username>/genai-resume-screener.git
cd genai-resume-screener
```

2) **Set env**
Copy `.env.example` to `.env` and fill values (OpenAI key, Google creds path, SMTP config).

3) **n8n**
- Start n8n (local or Docker)
- Import `workflows/resume_screener_workflow.json`
- Update node credentials:
  - OpenAI HTTP node (bearer key)
  - Google Sheets node (service account JSON)
  - Email/Slack node (optional)

4) **Test**
- Put a test JD into `data/job_description.txt`
- Put one anonymised resume PDF into `data/sample_resumes/`
- Run the workflow (Manual Trigger)
- Check your Google Sheet for results and your email/Slack for notifications

## 🧪 Output schema (Google Sheets)
| timestamp | job_id | candidate_name | overall | skills_sub | exp_sub | edu_sub | proj_sub | soft_sub | top_keywords | missing_must_haves | summary | file_url |

## 📦 Repo contents
- `workflows/` → n8n workflow export
- `prompts/` → all LLM prompts (versioned outside the workflow)
- `data/` → example inputs (anonymised)
- `notebooks/` → optional analysis on results
- `SECURITY.md` → privacy & PII handling
- `requirements.txt` → notebook deps

## 🔒 Privacy
- Avoid committing real resumes.
- Use anonymised samples for demos.
- See `SECURITY.md` for PII handling.

## 📝 License
MIT — see `LICENSE`.
