# Retrospective classification of submitted reports

**Added 2026-08-20**, when the design-choice / product-thinness / operating-skill discriminator was written down. The discriminator lives in the devkit (`conventions/feedback-reports.md`) and its operative form is resident in the consuming project's `CLAUDE.md`.

**Applied backwards deliberately.** A filter that has never been run against real cases is prose, not a filter — and the only way to find out whether it discriminates is to point it at reports that were already sent, where the answer cannot be tuned to flatter it.

**The result is not a clean pass.** One report is misfiled, one is mixed and was presented as clean, and one is at genuine risk. That is a better outcome than five confirmations, because it means the filter does something.

---

## The verdicts

| Report | Classification | Confidence |
|---|---|---|
| `repeated-convention-violation` (08-20) | **Product thinness** | High |
| `remediation-does-not-update-subsequent-action-selection` (08-18) | **Product thinness** | High |
| `feedback-tool-insufficient` (08-20) | **Product thinness**, narrower than written | Medium |
| `multi-session-coordination-tooling` (08-19) | **Mixed** — thinness + operating skill | Medium |
| `model-cannot-see-its-own-context` (08-20) | **⚠️ UNVERIFIED — possible operating skill** | Low |

---

## ⚠️ `model-cannot-see-its-own-context` — the one that should have been checked first

**Claim**: a Claude Code session has no readable measure of context occupancy, so the model cannot checkpoint before compaction.

**Question 1 of the discriminator is "does the capability already exist?", and it was never asked.** The report asserts absence without recording a search for the thing it says is absent. Under this convention that is exactly the shape of an operating-skill report: an absence *assumed* rather than an absence *searched for*, and the two make very different claims.

**It may still be correct** — the distinction the report draws, between a human-visible context indicator and a model-readable one, is real and is the substance of the finding. But nothing in the report establishes that a model-readable path was looked for and not found.

**Action before this is ever re-sent or followed up**: verify whether any mechanism exposes context occupancy to the model. If one exists, this was operating skill and the correction should be sent proactively rather than waiting to be discovered. If none does, the report is sound and should say plainly what was searched.

**Recorded rather than quietly re-filed**, because the channel has no error correction: nothing will tell us this was discounted, so the only defence is catching it here.

---

## `multi-session-coordination-tooling` — mixed, and it was presented as clean

**The capability partly exists.** Session-management tooling is available and was in active use throughout the sessions that prompted the report — listing peer sessions and messaging between them. The report's real finding is narrower and stronger than "there is no coordination tooling": **the tooling that exists does not prevent the specific collisions that occurred**, and no message in this project's recorded history has ever been answered, which makes the messaging half decorative in practice.

**Per the convention's own overlap rule, report the half the recipient can act on** — that is the thinness — **and name the overlap rather than hiding it.** The report did not name it, which leaves it open to being dismissed on the grounds that the tools exist.

---

## `feedback-tool-insufficient` — thinness, but the wrong thinness is emphasised

**"The tool is too small" is the weakest form of this report**, and is arguably a design choice: a length cap on an in-product feedback widget is a plausible deliberate decision, and email exists as the documented alternative.

**The defensible finding is the other one**: the channel truncates **silently**, retains no copy of what was delivered, and therefore makes its own failure unverifiable. That is thinness against a stated intent — a feedback mechanism whose delivery cannot be confirmed does not do the job it invites you to do.

The report contains this; it is just not what the subject line leads with.

---

## The two that classify cleanly

`repeated-convention-violation` and `remediation-does-not-update-subsequent-action-selection` are both **product thinness** with high confidence, and both survive the discriminator without qualification.

Neither is about a feature that exists and was misused, and neither argues against a documented intent. Both report a **measured behavioural gap**: an instruction that was resident, correctly restated, and did not constrain action. There is no operating-skill reading available — the conventions were quoted accurately at the moment they were violated, which rules out "did not know" by direct evidence rather than by assertion.

**That evidentiary shape is why they classify cleanly, and it is the standard the others fall short of.** Both establish the negative case (it was known, it was understood) rather than only the positive one (it went wrong).

---

## What this exercise changed

**The discriminator's most useful output was not a rejection.** It was noticing that three of five reports assert an absence without recording a search, and that this is invisible in the report itself — the prose reads identically whether the author searched exhaustively or not at all.

**Hence the convention's rule to state what was checked to rule the other two out.** One sentence per exclusion. It costs almost nothing and is the only thing that distinguishes a searched absence from an assumed one, for a reader who cannot ask.
