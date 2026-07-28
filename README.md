# AI Mock Interview & Career-Readiness Coach Agent

An autonomous multi-agent interview coaching system that gives freshers (especially Tier-3 college students) realistic, personalized interview practice.

## Problem It Solves

Most interview prep tools (YouTube playlists, static question banks, generic mock prompts) do not adapt to a learner’s answers in real time.  
This project solves that by running an adaptive, role-specific interview loop where question generation, response evaluation, and difficulty control are handled by coordinated AI agents.

## ATS-Optimized Resume Bullet

Built an autonomous multi-agent interview coaching system using **LangGraph/CrewAI** that dynamically generates role-specific questions, evaluates candidate responses across rubric dimensions (technical accuracy, communication, STAR structure), and adapts question difficulty in real time—improving mock-interview completion rate by **X%** in user testing.

**Keywords:** multi-agent systems, LLM evaluation, adaptive systems, RAG, rubric-based scoring, state management.

## Tech Stack

- **Orchestration:** LangGraph or CrewAI (multi-agent state machine)
- **LLM:** Claude/GPT API for question generation and evaluation
- **Speech (optional):** Whisper for speech-to-text voice interviews
- **Backend:** FastAPI
- **Database:** PostgreSQL for session history and score tracking
- **Frontend:** React dashboard for score trends across sessions

## System Architecture

### 1) Question Agent
- Inputs: target role, current difficulty, concepts already covered
- Output: next question (non-repetitive, role-relevant, difficulty-aware)

### 2) Evaluation Agent
- Scores each answer against a structured rubric:
  - Technical Correctness
  - Clarity of Communication
  - STAR/structured response quality
- Returns sub-scores + final score + explanation (“why this feedback”)

### 3) Adaptation Loop (Core Agentic Behavior)
- If candidate performs well → increase difficulty.
- If candidate struggles → probe same concept deeper instead of switching topics.

### 4) Memory Layer
- Persist session history and rubric scores in PostgreSQL.
- Enable week-over-week progress tracking and trend visualization.

### 5) Dashboard Layer
- Show per-session scores, rubric breakdown, and improvement trends.
- Provide transparent feedback to avoid “black-box” scoring.

## Build Plan (Implementation Guide)

1. **Define Rubric Schema**
   - Create weighted rubric dimensions and score ranges.
   - Require evaluator outputs in structured JSON for reliable parsing.

2. **Implement Question Agent**
   - Use role + difficulty + asked-question history to generate next prompt.
   - Enforce anti-repetition checks.

3. **Implement Evaluation Agent**
   - Evaluate answers dimension-by-dimension.
   - Return sub-scores, weighted aggregate score, and evidence-backed rationale.

4. **Implement Adaptive Controller**
   - Convert rubric output into next-step policy (harder/deeper/lateral).
   - Maintain interview state with LangGraph/CrewAI.

5. **Add Memory + Analytics**
   - Store transcripts, scores, metadata, and timestamps in PostgreSQL.
   - Expose APIs for historical performance retrieval.

6. **Build Frontend Dashboard**
   - Visualize trends over time.
   - Show interview summaries, weak areas, and improvement signals.

7. **Optional Voice Mode**
   - Add Whisper STT so users can practice spoken interviews.

## Suggested API/Data Contracts

- `InterviewSession`: session_id, user_id, role, difficulty, created_at
- `InterviewTurn`: question, answer, rubric_subscores, total_score, feedback, next_action
- `ProgressSummary`: weekly averages, strongest areas, weakest areas, improvement delta

## Why This Project Stands Out

- Demonstrates practical **multi-agent orchestration** beyond simple chatbot Q&A.
- Uses **rubric-based LLM evaluation** with explainability.
- Includes **stateful adaptation** and **longitudinal memory**, making it production-relevant and resume-strong.
