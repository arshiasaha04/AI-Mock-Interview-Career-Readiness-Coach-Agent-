# AI Mock Interview & Career-Readiness Coach Agent

An autonomous multi-agent interview coaching system that gives freshers realistic, personalized, and adaptive mock-interview practice.

## The Real Problem It Solves

Freshers—especially students from Tier-3 colleges—often rely on static question banks and YouTube videos for interview prep.  
Those resources do not adapt to a candidate’s responses, weak areas, or communication style.

This project solves that by running a dynamic interview loop where:
- questions are tailored by role and difficulty,
- answers are evaluated against a structured rubric,
- and follow-up questions adapt in real time based on performance.

---

## Resume Bullet (ATS-Optimized)

Built an autonomous multi-agent interview coaching system using **LangGraph/CrewAI** that dynamically generates role-specific questions, evaluates candidate responses across rubric dimensions (technical accuracy, communication, STAR structure), and adapts question difficulty in real time—improving mock-interview completion rate by **X%** in user testing.

**Keywords:** multi-agent systems, LLM evaluation, adaptive systems, RAG, rubric-based scoring, state management.

---

## Tech Stack

- **Orchestration:** LangGraph or CrewAI (multi-agent state machine)
- **LLM:** Claude/GPT via API for question generation + evaluation
- **Speech (optional):** Whisper for speech-to-text (voice interview mode)
- **Backend:** FastAPI
- **Database:** PostgreSQL for session history and score tracking
- **Frontend:** React dashboard for score trends over multiple sessions

---

## How to Build It

### 1) Question Agent
- Generate the next question from:
  - target role,
  - current difficulty level,
  - coverage history (to avoid repeats).
- Ensure topic diversity and progressive interview flow.

### 2) Evaluation Agent
- Score each response with a **structured rubric** instead of a single raw rating.
- Use sub-scores such as:
  - technical correctness,
  - clarity of explanation,
  - structure (including STAR where relevant).
- Return justification for each sub-score to keep feedback actionable.

### 3) Adaptation Loop (Core Agentic Behavior)
- If candidate performs well → increase difficulty or move to advanced variants.
- If candidate struggles → probe deeper on the same concept before switching topics.
- Keep adaptation stateful to make each session genuinely personalized.

### 4) Memory Layer
- Store interview sessions, question/answer logs, and rubric scores in PostgreSQL.
- Track week-over-week progress across roles and skill dimensions.
- Feed historical performance back into question selection for smarter adaptation.

### 5) Feedback Transparency
- Include a **“why this feedback”** explanation for every score.
- Show evidence-linked feedback so users understand exactly what to improve.
- Avoid black-box scoring behavior.

---

## Demo Direction (Suggested)

- Text interview mode (baseline)
- Voice interview mode with Whisper STT (wow factor)
- React dashboard with:
  - per-session score,
  - rubric-wise trends,
  - improvement trajectory over time

---

## Why This Project Stands Out

- Goes beyond static Q&A into adaptive, stateful interviewing
- Demonstrates practical multi-agent orchestration
- Combines LLM evaluation with transparent rubric design
- Produces portfolio-ready outcomes (backend, memory, frontend, AI logic)
