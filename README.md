# feedback-reports

Outbound feedback on **model behaviour, tooling defects, and process findings** — reports written to be read by someone outside this toolchain.

Created 2026-08-20, user-directed, on the same reasoning that moved the growth ledger to its own repo: an artifact that is not about any one project should not live inside one.

## Why this is separate from `personal-growth`

They look adjacent and are not.

| | `personal-growth` | this repo |
|---|---|---|
| subject | the **user** — evaluation histograms, work-time accounting | the **model and its tooling** |
| audience | the user alone | an external dev team |
| sharing posture | private, permanently | private by default, **written to be sent** |

The distinction is load-bearing rather than tidy: a report meant to be shared should not require extracting it from a repo full of personal evaluation data. Mixing them makes the sharing step awkward enough to discourage it, which is how reports stop being sent.

## Why the reports live in git at all

**They were being lost.** A search of the Bitburner repo's full history on 2026-08-20 found **no feedback report of any kind** — only the convention describing how to write them. The reports had been drafted, sent, and never preserved, and nobody noticed, because the convention's own survival made the practice look intact.

That is the same failure the convention was written to fix, one level up. The convention exists because an earlier decision about report *format* was recorded and then lost completely; the reports themselves were being lost the same way.

## Conventions

**Plaintext, always.** `.txt`, plain prose. No tables, no bold, no backticks, no heading syntax. Structure with blank lines, plain headings and indentation.

**The reason is the recipient's ingestion cost.** These are read by someone outside this project and usually outside this toolchain. Markdown that renders for the author arrives as visual noise for the reader — pipes and asterisks between them and the content. Formatting effort the author pays and the reader also pays is negative value on both sides.

**Density beats formatting.** If a table's content matters, write it as sentences. If it does not survive that translation, it was decoration.

Canonical statement: `conventions/feedback-reports.md` in the devkit.

## Submission channels

Established 2026-08-20 by the user, from Anthropic's own documentation and support articles. **There is no dedicated address for Claude Code technical feedback** — recorded here because that absence is itself the answer, and re-deriving it costs a search every time.

| Channel | For | Notes |
|---|---|---|
| **`feedback@anthropic.com`** | **general platform feedback, and incorrect or unexpected model responses** | **The right route for the reports in this repo.** An email leaves a sent copy in the mailbox, which is the one property the in-product tool lacks. |
| `/feedback` or `/bug` in-terminal | product feedback and bug reports | Sends **logs and details** to the product team, so it may carry more than the visible text field. **But it truncates, and retains no local copy** — see `feedback-2026-08-20-feedback-tool-insufficient.txt`. |
| Support Center / in-app messenger | account and technical support | Routes to agents triaging account and billing. A technical report on model behaviour is likely to be closed as out of scope rather than forwarded. |
| `usersafety@anthropic.com` | safety and security concerns | **Do NOT route ordinary behaviour or tooling reports here.** Nothing in this repo belongs on a safety channel; using it for product feedback degrades it for its actual purpose. |

**Before submitting**: `/doctor` or `/debug` check for configuration or runtime issues, which is worth doing first if the report concerns a malfunction rather than a behaviour pattern.

**Recommended practice**: send by email, paste the `-ABSTRACT.txt` as the body or lead, and offer the full report. Then save what was actually sent as `-SUBMITTED.txt` in this repo — **that is the only way the next "was it truncated?" question is answerable with evidence rather than inference.**

## Naming

`feedback-YYYY-MM-DD-<short-subject>.txt`

## Resolving this location

Machine-local, in `~/.claude/devkit.json`:

```json
{ "feedbackReportsPath": "C:/Users/stuar/Documents/Projects/feedback-reports" }
```

Same mechanism as `growthLedgerPath`, and for the same reason: neither repo knows where the other was cloned, and the answer differs per machine.
