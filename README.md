# Agent pilot: how good is it, really?

## Context

For 14 days, about 1,200 associates piloted an internal assistant agent. They used it for quick lookups, multi-step workflows (tickets, PTO, scheduling), tool-heavy data tasks (reports, reconciliations), and drafting.

Every agent transcript was graded automatically by an LLM judge (`judge_config.yaml`). The eval team also hand-labeled a sample of transcripts (`data/gold_labels.csv`).

The pilot dashboard currently shows the judge's pass rate: **79%**.

Leadership's question, verbatim:

> "If we roll this out, when an associate asks the agent to do something, how often do they end up getting it done? Our bar for rollout is 75%."

## What we'd like from you

These are in priority order. We don't expect you to finish everything; we care much more about your reasoning than about getting to the end.

1. **Define** the success rate you'll estimate, and why. Please talk this through with us before writing code.
2. **Estimate** it, with an honest statement of uncertainty.
3. **Recommend**: does the agent clear the bar?
4. **Plan**: the eval team can fund **200 more human labels**. Which transcripts should they label, and how much would that improve your estimate?

## Ground rules

- Use any tools you like, including AI assistants. We expect you to.
- Please share your screen and narrate your decisions as you go.
- We'll occasionally ask you to predict a result before you run it. Rough guesses are fine.
- If you'd normally ask a colleague a question about the data, ask us.

## Files

| Path | What it is |
|---|---|
| `data/transcripts.jsonl` | Pilot log: one line per judge grading of an agent transcript |
| `data/gold_labels.csv` | Human labels for a sample of transcripts |
| `DATA_DICTIONARY.md` | Field definitions |
| `judge_config.yaml` | How the judge was configured |
| `requirements.txt` | Suggested Python packages |
