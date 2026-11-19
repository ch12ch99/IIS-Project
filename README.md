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
Development is structured across four progressive milestones:
- **Stage 1 (Baseline Architecture):** Adapted the lightweight Python web server from Lab 4 with request context inspection and user input handling.
- **Stage 2 (Dual-State Visual Styling):** Implemented token-level CSS rendering for code completions (neutral grey ghost text for safe boilerplate vs. amber underlines for flagged tokens).
- **Stage 3 (Interactive Explanations & Rationale):** Designed hoverable evidence cards explaining CWE-89 SQL injection risks, adhering to Amershi et al. (2019) Guideline G11.
- **Stage 4 (Correction & Recovery Controls):** Integrated one-click alternative cycling (`Alt + [` shortcut and button controls) to support efficient correction (Guideline G9).

## 5. AI Assistance Statement
Generative AI (Gemini / Claude) was used to:
1. Brainstorm synonym concept blocks for the literature review.
2. Scaffold initial CSS styling rules for wavy text underlines.
3. Proofread report drafts for grammatical conciseness.
All design rationale decisions, theoretical mappings (Weeks 1–7), and verified code behaviors were independently evaluated and checked by the author.


# Lab 4 app route

If you have a working Lab 3 app, you can extend it with the Lab 4 support files and keep its app files.
Otherwise, copy this whole folder to your working location. Lab 3 is not required for this route.
Open a terminal there, run `python app.py`, then open <http://localhost:8000>. The mock model and sample
files run locally, without a key or network connection. Use the student handout for the task steps.

| file | what it is |
|---|---|
| `retrieve.py` | searches `corpus/`; each result includes its source, section, date, score and superseded status |
| `tools.py` | checks a revision-slot request, asks for confirmation, then logs the result |
| `vlm.py` | returns an answer with a confidence score or refuses with a reason |
| `app.py`, `index.html`, `model.py`, `mock_model.py`, `recorded_runs/` | the runnable app and its mock replies |
| `corpus/` | six sample course documents with source and date information |
| `sample_images/` | `sample_poster.png` supports the deadline answer; for the same question, the app should refuse to answer from `sample_noticeboard.png` |
| `01_CONTEXT_MAP.md` | record what your app sends to the model |
| `02_TEST_RECORD.md` | record the three retrieval cases you test |

## Check the support files

    python retrieve.py --selftest     # expect: ok: 6 documents, 14 passages
    python tools.py --selftest        # expect: valid call accepted, 900-minute call refused
    python vlm.py --selftest          # expect: ok: 2 sample images

The supplied mock is used for the checks in this lab. Do not put API keys in a file, screenshot or
commit. The course documents and sample images are provided for this exercise.

