# Evals

Golden-set cases in `golden-set.md` encode the behaviors this bot must keep: cited, uncertainty-aware reviews, no invented values, urgent red-flag escalation, a quiet path when nothing was asked, and a clear not-medical-advice close.

How to use:

1. For each case, run the agent (or a dry-room roleplay) with the Input.
2. Score with the Must / Must-not rubric (pass/fail). Prefer deterministic checks where possible (presence of a source or an explicit gap, presence of seek-care-now language, absence of a prescription, silence on the quiet path).
3. Add every new production failure as a fictionalized case. Never copy a real patient's results into this set.
4. Re-run the set after skill or instruction changes.

These are regression sensors, not a clinical validation study. All cases are fictional.
