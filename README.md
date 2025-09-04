# FOSSEE Python Screening Task 2 — Prompt for an AI Debugging Assistant

This repository contains a **single, reusable prompt** for an AI assistant that helps students debug Python code **without revealing the full solution**. It also includes the design rationale and usage instructions.

## Files
- `prompt.md` — The production‑ready prompt.  
- `README.md` — This document (setup, reasoning, and submission).

## How to Use the Prompt
1. Open `prompt.md` and copy its contents into the **system** or **developer** message of your AI platform (e.g., OpenAI, ChatGPT custom instructions).  
2. When a student asks for help, paste:
   - The problem statement (if available)
   - The student’s current code
   - The error/traceback
   - Expected vs. actual behavior
   - Learner level (`beginner` or `advanced`)
3. The assistant will follow the **interaction flow**, using the **hint ladder** and **no‑solution** constraints.

---

## Reasoning (Design Choices)

### Why this wording?
- **Socratic, stepwise flow** pushes the student to run diagnostics and reason about their own code.  
- The **hint ladder (L1–L4)** ensures progressive disclosure—nudges first, micro‑patches later—so learning happens before answers.  
- **Hard rules** + **self‑check** add guardrails that prevent leakage of final solutions.  
- The **output template** keeps responses short, structured, and actionable.

### How does it avoid giving the solution?
- Explicit **prohibitions** against full, runnable code and assignment‑specific logic.  
- Snippets are **generic** and capped at **≤3 lines**.  
- The assistant must describe **minimal changes** in words instead of pasting the fix.  
- A **polite refusal** path when the student requests the full code.  
- A final **self‑audit checklist** before sending the reply.

### How does it encourage helpful, student‑friendly feedback?
- **Supportive, non‑judgmental tone**, with brief **concept nudges** to teach the underlying idea.  
- **Targeted diagnostics** (print/assert, isolate function, check types/lengths) build debugging habits.  
- **Tests & verification** encourage students to validate their own fixes.  
- **One‑bug‑at‑a‑time** discipline reduces overwhelm and clarifies progress.

---

## Required Reasoning Answers

**Tone & style:** Supportive, concise, and **Socratic**. Use plain language, short bullets, and celebrate partial progress. Avoid jargon unless the learner is advanced.

**Balancing bug identification vs. guidance:** Identify **where** the bug likely is (fault lines) and **how** to uncover it (diagnostics), then provide a **hint**—not the fix. Encourage the student to run tests and report back for the next hint level.

**Adapting for learner levels:**  
- **Beginner:** Slower pacing, decode error messages, explain concepts in 2–4 lines, propose tiny experiments, and list concrete tests.  
- **Advanced:** Terse pointers, emphasize invariants/edge cases/performance, link to docs or PEPs when useful, and raise the challenge.

---

## Suggested Repo Structure
```
.
├── prompt.md
└── README.md
```

## Submission Instructions
1. Push this folder to a **public GitHub repository** (instructions below) **or** upload the two files to a publicly shareable drive.  
2. Email the link to **pythonsupport@fossee.in** with the subject: `FOSSEE Python Screening Task 2 — Prompt Submission by <Your Name>`.

## Git Commands (replace the URL with your repo)
```bash
git init
git add .
git commit -m "Add FOSSEE Task 2: AI Debugging Assistant prompt and reasoning"
git branch -M main
git remote add origin https://github.com/<your-username>/fossee-python-task-2-prompt.git
git push -u origin main
```

## Notes
- The prompt is **general** enough for many Python topics (control flow, functions, data structures, files, classes, imports) yet **specific** enough to enforce no‑solution behavior.  
- You can extend the hint ladder with **L5 (high‑level pseudocode)** if the assignment allows it, still without providing a drop‑in answer.
