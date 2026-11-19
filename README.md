# IIS-Project
# AmberLens: Uncertainty-Aware Code Assistant Prototype (IIS Project)

**Prose Word Count:** 285 words  
**Project Status:** Functional Prototype (Web-based Simulation)  
**Target Release:** `v1.0.0` (Commit `7f3b89a`)

## 1. Project Overview
AmberLens is an intelligent code-editor interface prototype designed to mitigate developer over-reliance on vulnerable AI code suggestions. Rather than presenting suggestions with uniform fluency, it selectively highlights tokens with high uncertainty or security risk (e.g. CWE-89 SQL injection) using in-situ amber underlines and confidence badges.

## 2. Technology Stack
- **Frontend:** HTML5, CSS3 (in-situ amber wavy highlights and badge styling), Vanilla JavaScript.
- **Backend:** Python 3 (lightweight HTTP server running `app.py`).
- **AI / Analysis Engine:** Local JSON heuristics simulating LLM token uncertainty and CWE vulnerability classification.
- **Tools Used:** VS Code, Git.

## 3. How to Run and Inspect
1. Ensure Python 3 is installed.
2. Clone this repository:
   ```bash
   git clone https://github.com/ch12ch99/IIS-Project.git
   cd IIS-Project
   ```
3. Start the application:
   ```bash
   python app.py
   ```
4. Open `http://localhost:8000` in your browser.
5. Click **"Simulate Insecure SQL Suggestion"** to inspect the amber underline and hoverable rationale card. Press `Alt + [` or click **"Cycle Safe Alternative"** to test recovery.

## 4. Development Record
- `commit 3a1e20`: Initial baseline with context logging and ghost text generation.
- `commit 5c84d1`: Added dual-state token CSS rendering (neutral grey vs. amber alert).
- `commit 9b22e7`: Integrated CWE-89 evidence tooltips (Amershi et al., 2019 Guideline G11).
- `commit 7f3b89`: Implemented keyboard shortcut recovery (`Alt+[` cycling, `Esc` dismiss; Guideline G9).

## 5. AI Assistance Statement
Generative AI (Gemini / Claude) was used to:
1. Brainstorm synonym concept blocks for the literature review.
2. Scaffold initial CSS styling rules for wavy text underlines.
3. Proofread report drafts for grammatical conciseness.
All design rationale decisions, theoretical mappings (Weeks 1–7), and verified code behaviors were independently evaluated and checked by the author.
