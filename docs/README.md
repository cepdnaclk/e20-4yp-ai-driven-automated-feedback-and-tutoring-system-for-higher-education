---
layout: home
permalink: index.html

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

Final Year Project · Artificial Intelligence · Automated Grading · Moodle Integration · Multi-Agent Systems · Educational Technology

---

## Project Summary

The rapid expansion of higher education, combined with increasing adoption of online and hybrid learning environments, has created significant challenges in delivering timely, consistent, and personalized feedback to students. Traditional grading approaches are time-consuming, difficult to scale, and often suffer from inconsistencies due to human limitations, particularly in large classes where instructors handle hundreds of submissions. Delayed feedback reduces students’ ability to improve learning outcomes effectively.

This project addresses these challenges by developing **EduTutor AI**, an AI-driven automated feedback and tutoring system designed for seamless integration into Learning Management Systems (LMS), specifically Moodle. Unlike many existing AI tools that operate as standalone systems, EduTutor AI is designed as a native LMS-integrated solution that works within existing academic workflows.

The proposed system introduces a **multi-agent architecture** to improve the reliability and quality of automated grading and feedback. The system consists of four key components: a rubric generation agent that creates structured grading criteria from assignment descriptions and reference answers, an answer evaluation agent that performs concept-level grading based on the rubric, a feedback generation agent that produces personalized and adaptive feedback, and a validation agent that ensures consistency, correctness, and robustness of outputs. This modular design reduces common limitations of single-model AI systems such as hallucinations, inconsistency, and overgeneralized responses.

The system operates as a fully automated pipeline triggered by assignment deadlines, eliminating manual intervention and enabling scalability across large student cohorts. It also incorporates adaptive learning mechanisms by classifying students into performance levels and generating tailored feedback ranging from guided hints for weaker students to advanced conceptual insights for high-performing learners. Additionally, the system enables the creation of longitudinal learning datasets, supporting future analysis of student progress.

Experimental evaluation using benchmark datasets demonstrates a **47% reduction in grading error** and a **24 percentage point improvement in grading accuracy** compared to baseline approaches. Feedback quality evaluation using semantic similarity and coverage metrics shows strong alignment with instructor feedback, particularly when using OpenAI-based models.

Overall, EduTutor AI provides a scalable, reliable, and practical solution for automated grading and feedback in higher education, reducing instructor workload while improving student learning outcomes and bridging the gap between research prototypes and real-world deployment.

---

## Related Work

Automated feedback systems have evolved from rule-based grading and keyword matching approaches to machine learning and deep learning methods. Traditional systems provide consistent evaluation but lack flexibility in handling open-ended responses. Recent large language model (LLM)-based systems demonstrate improved capability in generating natural language feedback, but they often suffer from limitations such as inconsistent grading, shallow explanations, and lack of pedagogical alignment.

Hybrid human-AI systems have been proposed to improve reliability; however, research indicates that human intervention may introduce variability and reduce consistency. Additionally, most AI-based feedback tools operate outside institutional LMS environments, limiting their practical usability and adoption.

Recent studies highlight the potential of multi-agent architectures, where different AI components handle specialized tasks such as grading, feedback generation, and validation. These approaches improve robustness and reduce systematic errors. However, many existing solutions remain research prototypes and lack real-world LMS integration.

This project addresses these limitations by combining multi-agent AI design, LMS-native integration, adaptive feedback generation, and validation mechanisms into a single deployable system.

---

## Methodology

The system follows a fully automated pipeline:

1. **Moodle Integration**  
   Retrieve assignments and submissions using Moodle Web Services API.

2. **Deadline-Based Processing**  
   Trigger grading pipeline automatically after assignment deadlines.

3. **Rubric Generation (Agent 1)**  
   Generate structured grading criteria from assignment descriptions and reference answers.

4. **Answer Evaluation (Agent 2)**  
   Perform concept-level grading using rubric-based evaluation.

5. **Feedback Generation (Agent 3)**  
   Generate personalized feedback based on student performance and learning patterns.

6. **Validation and Quality Control (Agent 4)**  
   Ensure consistency, detect anomalies, and apply fallback mechanisms.

---

## System Architecture

- Frontend: Moodle LMS
- Backend: FastAPI (Python)
- Database: PostgreSQL
- AI Layer: OpenAI, Gemini, Groq APIs
- Scheduler: Deadline-triggered processing system

---
## System Architecture Diagram

![System Architecture](/images/architecture.png)

The figure illustrates the overall architecture of EduTutor AI, including Moodle integration, backend processing, multi-agent workflow, and database storage.

---

## Workflow Pipeline

![Pipeline](/images/pipeline.png)

The pipeline shows the automated flow from assignment submission to rubric generation, evaluation, feedback generation, and validation.

---

## Performance Results

![Results](/images/results.png)

The graph highlights improvements in grading accuracy and reduction in error compared to baseline methods.

---

## Results and Analysis

### Grading Performance

- **47% reduction in Mean Absolute Error (MAE)**
- **+24 percentage point increase in grading accuracy**
- Improved alignment with instructor grading patterns

### Feedback Quality

- OpenAI models achieved highest semantic similarity and coverage
- Gemini showed strong adaptability in feedback generation
- Groq demonstrated efficient inference performance

### Key Findings

- Rubric-based evaluation significantly improves grading consistency
- Multi-agent architecture reduces hallucinations and errors
- Adaptive feedback enhances student learning support

---

## Impact and Limitations

### Impact

- Enables real-time, scalable feedback for large classes  
- Reduces instructor workload significantly  
- Improves consistency and reliability of grading  
- Supports personalized and adaptive learning  

### Limitations

- Performance depends on prompt design  
- Limited dataset diversity  
- LLM outputs may vary in edge cases  
- Requires further long-term evaluation in real classrooms  

---

## Conclusion

EduTutor AI demonstrates the effectiveness of multi-agent AI systems in delivering scalable and personalized feedback within LMS platforms. The system successfully improves grading accuracy, feedback quality, and adaptability while maintaining practical deployability.

Future work will focus on improving robustness, expanding datasets, and incorporating advanced learning analytics for long-term educational insights.

---

## Links

- [Project Repository](https://github.com/cepdnaclk/e20-4yp-ai-driven-automated-feedback-and-tutoring-system-for-higher-education)
- [Project Page](https://cepdnaclk.github.io/e20-4yp-ai-driven-automated-feedback-and-tutoring-system-for-higher-education/)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://pdn.ac.lk/)