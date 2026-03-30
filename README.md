# When to Apply — A Bias–Variance Tradeoff

An interactive timing model for job applications, built around the tension between **preparedness** (am I actually ready?) and **timeliness** (do I still have runway?), stress-adjusted for the finals crunch.

Defaults to my own situation as a May 2026 grad student targeting ML/AI research roles — but fully customizable for anyone in a similar position.

## The Idea

The standard advice is high-volume, early, cast a wide net. I'm not doing that — I have the skills for a straightforward data science role but I'm targeting research positions instead, which means I need to convince people doing genuinely top-level work that I'm worth betting on as a fast learner. That's a different optimization problem.

A note on where I'm starting from: my master's is in mathematical sciences, so my background until this year has been almost entirely pure math — analysis, linear algebra, that kind of thing. I've been following AI research conceptually for years, but the applied side (data science coursework, real ML projects) is genuinely recent. The preparedness curve reflects that: a high mathematical foundation, but applied ML fluency that's still compounding.

So I modeled it. The tradeoff looks like a classic bias-variance curve: applying too early = high bias (weak application), applying too late = high variance (running out of runway). Somewhere in the middle is a combined score that peaks at an optimal window — but that window shifts once you factor in the negative impact of finals-season stress on application quality.

## What's in the Model

**Preparedness** — Logistic growth curve starting from a configurable baseline, with discrete jumps at project submission milestones. Calibrated against the average strong grad student, not the ideal candidate — that curve never reaches 100%.

**Timeliness** — Exponential decay with two compounding cliff edges: a step down at graduation as some pipelines close, and a steep drop approaching the financial deadline (insurance, housing, income).

**Stress** — Two-term function: a sharp-onset finals plateau that holds near full intensity until classes end (then drops to zero immediately), plus a financial anxiety wave that builds in the last ~7 weeks before the runway runs out. The combined stress term multiplies down the effective application score.

**Effective score** — The combined preparedness/timeliness score after the stress penalty is applied. The gap between raw optimal and stress-adjusted optimal tells you how much finals are actually costing you — and whether it's worth pushing through or waiting for the cliff to pass.

## Sliders

- **Growth rate** — How fast coding/domain knowledge is compounding. Set higher if you're in an active project sprint.
- **Finals intensity** — How much the crunch degrades your bandwidth. Higher values widen the gap between raw optimal and stress-adjusted optimal, and tend to pull the best window earlier — toward the post-LoRA gap before crunch peaks.

## Customization

Click **"adapt to your situation"** to configure:
- Your own key dates (start, classes end, graduation, financial deadline)
- Project milestones — each one produces a preparedness bump on the curve
- Starting preparedness level

There's a reset button to return to my defaults at any time.

## My Defaults

| Date | Event |
|------|-------|
| Mar 29, 2026 | Starting point |
| Apr 9 | LoRA fine-tuning submission (Kaggle) |
| May 7 | Classes end |
| May 14 | Graduation |
| Aug ~1 | Out of runway (insurance ends) |

## Built With

Vanilla HTML/CSS/JS + [Chart.js](https://www.chartjs.org/). No framework, no build step. Rename to `index.html` for GitHub Pages, or just open the file directly in a browser.

---

*Part of a broader job search that is, perhaps inadvisably, quality over quantity.*
