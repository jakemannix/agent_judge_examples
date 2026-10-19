# Data dictionary

## `data/transcripts.jsonl`

One JSON object per line. Each line is one grading of one agent transcript by the judge.

| Field | Type | Meaning |
|---|---|---|
| `event_id` | string | Log event identifier |
| `logged_at` | timestamp (UTC) | When the grading was logged |
| `session_id` | string | One user request to the agent. If the user asks again in the same session, the agent produces a new transcript (a new attempt) in the same session. |
| `user_id` | string | Hashed user identifier |
| `transcript_id` | string | One agent attempt |
| `attempt_started_at` | timestamp (UTC) | When the agent attempt started |
| `task_type` | string | `lookup`, `workflow`, `tool`, or `draft` (assigned by the router) |
| `prompt` | string | The user's message that started the attempt |
| `n_turns` | int | Turns in the transcript |
| `n_tokens` | int | Length of the full transcript in tokens |
| `judge_run_id` | string | Identifier of the judging run that produced this verdict |
| `judge_model` | string | Judge model version |
| `judge_input_tokens` | int | Tokens of transcript sent to the judge |
| `judge_verdict` | string | `pass` or `fail` |
| `judge_rationale` | string | The judge's one-line explanation |
| `tool_error_tail` | string, optional | Last error line from a tool call, when one failed |
| `tool_stdout_tail` | string, optional | Last bytes of tool stdout, when a tool crashed |

## `data/gold_labels.csv`

| Field | Meaning |
|---|---|
| `transcript_id` | Matches `transcripts.jsonl` |
| `annotator_id` | Who labeled it |
| `human_label` | `pass` or `fail`, using the same rubric as the judge |

The gold set was drawn by the eval team from graded transcripts.¹ Some items were labeled by two annotators.

---

¹ To make sure there were enough failures to study, the eval team sampled 150 transcripts the judge marked `fail` and 150 it marked `pass` (using each transcript's first grading).
