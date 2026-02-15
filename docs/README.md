---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: ai-driven-automated-feedback-and-tutoring-system-for-higher-education
title: AI-Driven Automated Feedback and Tutoring System for Higher Education
---

# AI-Driven Automated Feedback and Tutoring System for Higher Education

#### Team

- E/20/089, Y.H. Edirimanna, [e20089@eng.pdn.ac.lk](mailto:e20089@eng.pdn.ac.lk)
- E/20/361, Y.H. Senadheera, [e20361@eng.pdn.ac.lk](mailto:e20361@eng.pdn.ac.lk)
- E/20/366, A.P.B.P. Senevirathna, [e20366@eng.pdn.ac.lk](mailto:e20366@eng.pdn.ac.lk)

#### Supervisors

- Prof. Roshan Ragel, [roshanr@eng.pdn.ac.lk](mailto:roshanr@eng.pdn.ac.lk)
- Prof. Sakunthala Yatigammana, [sakuyatigammana@arts.pdn.ac.lk](mailto:sakuyatigammana@arts.pdn.ac.lk)

#### Tags

Final Year Project · Artificial Intelligence · Automated Grading · Moodle Integration · LLM · Plagiarism Detection · Education Technology

---

#### Table of content

1. [Abstract](#abstract)
2. [Related works](#related-works)
3. [Methodology](#methodology)
4. [Experiment Setup and Implementation](#experiment-setup-and-implementation)
5. [Results and Analysis](#results-and-analysis)
6. [Conclusion](#conclusion)
7. [Publications](#publications)
8. [Links](#links)

---

## Abstract

Large undergraduate classes make manual grading and feedback slow, inconsistent, and difficult to scale. This project proposes an AI-driven system integrated with Moodle to automate structured, rubric-aligned feedback and support student learning. The pipeline retrieves assignment submissions via Moodle REST APIs, performs deadline-aware processing, checks for potential plagiarism using vector similarity, and generates feedback through a modular multi-agent LLM workflow. The system also maintains concept-level learning history to produce adaptive and personalized guidance. The final outcome is an end-to-end platform that reduces instructor workload while providing faster, consistent, and actionable feedback to students.

## Related works

Automated assessment systems traditionally rely on rule-based marking, keyword matching, or classical machine learning models, which often struggle with open-ended answers and explanation-based questions. Recent LLM-based approaches have shown improved capability in generating human-like feedback, but they may produce inconsistent scoring, hallucinations, and weak transparency without proper structure. Plagiarism detection tools commonly use string matching; however, paraphrased copying and concept-level similarity require semantic methods such as embeddings and vector similarity. Our work builds on these directions by combining deadline-aware automation, multi-agent feedback generation with QA, semantic plagiarism detection, and learning-history-based personalization within a Moodle-integrated workflow.

## Methodology

Our methodology follows a fully automated pipeline:

1. **Moodle Integration**  
   Retrieve course, assignment, and submission data using Moodle REST web services with token-based authentication.

2. **Deadline-Aware Orchestration**  
   A scheduler periodically checks assignments and triggers processing based on the due date:
   - **Before deadline:** ingest + plagiarism check only (no grading)
   - **After deadline:** plagiarism check + multi-agent grading

3. **Submission Processing**  
   Extract/normalize text (online text or file-based submissions) and segment answers by questions (Q1/Q2/Q3…).

4. **Plagiarism Detection (Semantic)**  
   Generate embeddings per question and compare against other submissions using cosine similarity; flag suspicious cases and store evidence.

5. **Multi-Agent Grading + Feedback**  
   Use specialized agents (correctness, misconceptions, clarity, personalization, synthesis, QA) to produce rubric-aligned scores and structured feedback.

6. **Storage + Feedback Delivery**  
   Store all results in the database and return grades/feedback back to Moodle (and/or an internal dashboard).

## Experiment Setup and Implementation

**System Stack**
- Moodle (REST API integration)
- Python Deadline Scheduler (pipeline orchestration)
- FastAPI Backend (AI engine and endpoints)
- PostgreSQL (submissions + results) + **pgvector** (embeddings)
- Redis (caching)
- LLM Engine (Gemini / Bedrock – configurable)

**Key Implemented Components**
- Moodle API wrapper with validation and error handling
- Deadline-based trigger flow (fair grading)
- File organization and submission ingestion pipeline
- Question-level semantic plagiarism detection (vector similarity + evidence storage)
- Modular multi-agent grading workflow with a QA loop
- Student learning history tables for concept tracking and trend detection

## Results and Analysis

**Current preliminary results (mid-progress)**
- Stable Moodle API connectivity and data retrieval confirmed
- Automated pipeline execution demonstrated end-to-end
- Structured AI feedback generation validated on real submission flows
- Plagiarism similarity computation at question-level implemented with stored evidence

**Planned analysis (final phase)**
- Compare AI feedback vs instructor feedback quality scores
- Evaluate consistency across students and assignments
- Measure latency and scalability of the end-to-end pipeline
- Study impact of rubric prompting and agent-based decomposition on feedback quality

## Conclusion

This project demonstrates the feasibility of an AI-driven, Moodle-integrated automated feedback system that combines deadline-aware fairness, semantic plagiarism detection, and structured multi-agent grading. The remaining work focuses on robust evaluation with real anonymized submissions, optimizing prompt/agent behavior, and producing quantitative results to validate pedagogical and technical effectiveness.

## Publications
[//]: # "Note: Uncomment each once you uploaded the files to the repository"

<!-- 1. [Semester 7 report](./) -->
<!-- 2. [Semester 7 slides](./) -->
<!-- 3. [Semester 8 report](./) -->
<!-- 4. [Semester 8 slides](./) -->
<!-- 5. Y.H. Edirimanna, Y.H. Senadheera and A.P.B.P. Senevirathna "AI-Driven Automated Feedback and Tutoring System for Higher Education" (2026). [PDF](./) -->

## Links

- [Project Repository](https://github.com/cepdnaclk/e20-4yp-ai-driven-automated-feedback-and-tutoring-system-for-higher-education)
- [Project Page](https://cepdnaclk.github.io/ai-driven-automated-feedback-and-tutoring-system-for-higher-education)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://pdn.ac.lk/)

[//]: # "Please refer this to learn more about Markdown syntax"
[//]: # "https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
