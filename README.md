# IIS-Project
# AmberLens: Uncertainty-Aware Code Assistant Prototype (IIS Project)

**Prose Word Count:** 285 words  
**Project Status:** Functional Prototype (Web-based Simulation)  
**Target Release:** v1.0.0

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
Development is documented through progressive commits in the repository:
- `commit 562a168`: Initial repository initialization.
- `commit aa2776e`: Baseline project structuring and documentation setup.
- `commit 51328a3`: Core implementation upload (web UI, in-situ amber highlight styling, and simulation logic).
- `commit acbf894`: Final README revision, test records integration, and submission release freeze.

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

