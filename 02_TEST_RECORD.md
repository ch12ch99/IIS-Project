# 02_TEST_RECORD.md

Record three questions and what the screen actually showed. Write what happened, not what you
expected to happen.

- **Grounded** means the current documents contain the answer.
- **Stale** means an old document contains an answer, but a newer document may replace it.
- **Unanswerable** means the documents do not contain the answer.

| question | type | what the screen showed | supported? | what I would change |
|---|---|---|---|---|
| when is coursework 1 due | grounded | "Coursework 1 is due on 14 November at 12:00 and is worth 40% of the module." Evidence: [handbook.md | 3 Assessment | updated 2026-09-12 | score 1.06] "Coursework 1 is due on 14 November at 12:00..." | yes | Keep as is; the retrieved passage is current, clearly matches the query, and shows explicit source provenance and date. |
| what is the penalty for late submission | stale | The top ranked result was marked superseded. The screen displayed the alert: "The top retrieval result is superseded. This answer uses the newer passage shown below." The answer was based on the current 2026 policy passage while keeping the superseded passage visible in Evidence for inspection. | yes | Visually separate or badge the superseded passage in a collapsible section so students do not accidentally read outdated rules. |
| where can I park my bicycle on campus | unanswerable | "The supplied corpus does not give a reliable answer. Ask the module lead about anything it does not cover." No evidence passages were displayed (all retrieval scores were 0.00).	 | no | Provide a clickable contact link or email address for the module lead or student services instead of a plain text suggestion. |
