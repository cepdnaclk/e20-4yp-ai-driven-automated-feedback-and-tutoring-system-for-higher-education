# AI-Driven Automated Feedback & Tutoring System (Moodle Integrated)

An end-to-end automated pipeline for **assignment ingestion, plagiarism detection, multi-agent AI grading, and personalized feedback**, integrated with **Moodle**.  
Built for CO425 Final Year Project (University of Peradeniya).

---

## Key Features

- **Moodle Integration (REST APIs)**  
  Fetch courses, assignments, submissions using a service user + token.

- **Deadline-Aware Automation (Fair Grading)**  
  - Before deadline: ingest + plagiarism check only  
  - After deadline: multi-agent grading + feedback generation

- **Multi-Agent AI Feedback Engine**
  - Correctness Agent (scores per question)
  - Misconception Agent (missing concepts)
  - Clarity Agent (writing quality)
  - Personalization Agent (student history + trends)
  - Synthesizer (final rubric-aligned feedback)
  - QA Agent (checks contradictions/length)

- **Plagiarism Detection (Vector Similarity)**
  - Split answers by question (Q1/Q2/Q3…)
  - Create embeddings and compare with cosine similarity
  - Store similarity score + evidence + matched submission

- **Personalization / Learning History**
  - Tracks concept-level performance over time
  - Maintains student profile: weak concepts + improving/declining trends

- **Backend + Storage**
  - FastAPI backend
  - PostgreSQL for submissions/results
  - `pgvector` for embedding search
  - Redis caching

---

## Architecture (High Level)

**Moodle → Scheduler → Backend (FastAPI) → DB (PostgreSQL + pgvector) → LLM Engine → Feedback back to Moodle**

- **Moodle**: assignments + submissions  
- **Scheduler**: periodic checks, deadline monitoring, orchestration  
- **Backend**: ingestion, chunking, plagiarism, grading, feedback synthesis  
- **DB**: stores submissions, similarity results, grades, feedback, profiles  
- **LLM**: Gemini / Bedrock (configurable)

---

## Current Progress

- Moodle local deployment + REST services enabled
- Token-based auth + service user configured
- Stable API connectivity verified
- Scheduler pipeline running (deadline-aware)
- Submission ingestion + file handling working
- Plagiarism vector similarity pipeline implemented
- Multi-agent grading architecture implemented (agents + synthesis + QA)
- Structured AI feedback output generation demonstrated

---

## Evaluation Plan

- **Dataset**: anonymized real Moodle submissions
- **Metrics**:
  - Instructor-rated feedback quality
  - Student usefulness survey
  - Consistency across students
  - Latency (time to produce feedback)
- **Experiments**:
  - AI vs Human feedback comparison
  - Rubric-based vs non-rubric prompting
  - Prompt structure optimization

---

## Quick Start (Local)

> Update URLs and tokens based on your setup.

### 1) Requirements
- Python 3.10+
- Docker + Docker Compose
- Moodle with REST enabled (local or hosted)

### 2) Environment Variables

Create a `.env` (or export in your shell):

```bash
MOODLE_URL="http://localhost:8080/moodle"
MOODLE_TOKEN="YOUR_MOODLE_TOKEN"
BACKEND_URL="http://127.0.0.1:8000"
COURSE_ID="2"
ASSIGNMENT_ID="1"
```

### 3) Start Services (DB/Cache)

If you use Docker for DB/Redis:

```bash
docker compose up -d
```

### 4) Run Backend

```bash
cd backend
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

### 5) Run Scheduler (Deadline Pipeline)

```bash
cd scheduler
python scheduler_deadline_pipeline.py
```

---

## API Endpoints (Example)

- `POST /ingest/submission`  
  Ingest cleaned text / extracted text and store in DB

- `POST /plagiarism/check/{submission_id}`  
  Run embedding similarity and store results

- `POST /llm/multi-agent-grade/{submission_id}`  
  Run multi-agent grading workflow and store feedback

> Exact paths may differ depending on your repo structure.

---

## Suggested Repository Structure

```
.
├── backend/                 # FastAPI backend + AI engine
├── scheduler/               # deadline-based scheduler scripts
├── moodle_api/              # API wrapper utilities
├── file_processor/          # PDF/text extraction, chunking by question
├── db/                      # migrations, schemas, seed scripts
├── data/                    # sample anonymized submissions (optional)
├── docs/                    # diagrams, evaluation notes, screenshots
└── README.md
```

---

## Notes on Privacy & Ethics

- Use anonymized student submissions for experiments.
- Store only necessary evidence for plagiarism checks.
- Do not expose tokens/credentials in commits.

---

## Team

CO425 Final Year Project – Department of Computer Engineering, University of Peradeniya

---

## License

Add your license here (e.g., MIT) or keep it private for university submission.
