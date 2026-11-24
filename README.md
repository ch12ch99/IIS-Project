# AmberLens: Uncertainty-Aware Code Assistant Prototype (IIS Project)

**Prose Word Count:** 264 words  
**Project Status:** Functional Prototype (Web-based Simulation)  
**Target Release:** v1.0.0

## 1. Project Overview
AmberLens is an intelligent code-editor interface prototype designed to mitigate developer over-reliance on vulnerable AI code suggestions. Rather than presenting suggestions with uniform fluency, it selectively highlights tokens with high uncertainty or security risk (e.g., CWE-89 SQL injection) using in-situ amber underlines and confidence badges.

## 2. Technology Stack
- **Frontend:** HTML5, CSS3 (in-situ amber wavy highlights and badge styling), Vanilla JavaScript.
- **Backend:** Python 3 (lightweight local HTTP server running `app.py`).
- **AI / Analysis Engine:** Deterministic front-end and JSON heuristics simulating LLM token uncertainty and CWE vulnerability classification.
- **Tools Used:** VS Code, Git.

## 3. How to Run and Inspect
1. Ensure Python 3 is installed.
2. Clone this repository and navigate to the project directory:
   ```bash
   git clone [https://github.com/ch12ch99/IIS-Project.git](https://github.com/ch12ch99/IIS-Project.git)
   cd IIS-Project
   ```
3. Start the local server:
   ```bash
   python app.py
   ```
4. Open `http://localhost:8000` in your browser.
5. Click **"Simulate AmberLens (Insecure SQL)"** to inspect the amber underline, confidence badge (`61% confidence [CWE-89]`), and inline vulnerability alert card. Click **"Cycle Safe Alternative (Alt + [)"** to test parameterised query recovery.

## 4. Development Record
Key development stages, rationale, and verification checks:
- `commit 562a168` & `aa2776e`: Initialised repository and structured baseline files; verified local HTTP routing worked without external API keys.
- `commit 51328a3`: Built the AmberLens UI in `index.html` (amber wavy CSS underline, confidence tag, and G11 explanation card) to address uncalibrated trust; checked visual contrast and button state transitions in browser.
- `commit acbf894`: Finalised documentation, aligned report references, and froze submission release.

## 5. AI Assistance Statement
Generative AI (Gemini / Claude) was used to brainstorm literature search terms, scaffold initial CSS wavy-underline rules, and proofread report drafts for conciseness. All design choices, theoretical mappings (Weeks 1–7), and literature claims were manually checked and corrected (e.g., removing unsupported claims and aligning implementation scope) by the author.

## 6. Additional Files
This repository builds upon the Lab 4 local server environment (`app.py`, `model.py`, `mock_model.py`). Accompanying lab artefacts (`01_CONTEXT_MAP.md`, `02_TEST_RECORD.md`, and `corpus/`) remain in the root directory for reference. No external API keys are required.
