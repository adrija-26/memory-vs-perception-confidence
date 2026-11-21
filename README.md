# Are people more overconfident when remembering than when perceiving?

**...even at the same difficulty?** This project tests whether people's
confidence runs further ahead of their accuracy on memory tasks than on
perception tasks, once task difficulty is taken into account.

Final project for *Probability for AI* (Stanford online course), Fall 2026.
Part of my computational / cognitive neuroscience portfolio.

> Status: **Phase 1, question chosen** (started 2026-11-21)

## The question

**Main question:** Are people more overconfident when remembering than when
perceiving, even at the same difficulty?

1. **Hard–easy effect:** does overconfidence grow as tasks get harder?
2. **Domain difference:** are people more overconfident on memory tasks than on perception tasks?
3. **The real test:** at the same difficulty, does the memory–perception difference remain?

## Pre-registered guess

_Written before looking at any data:_

> I'm __% sure that ____.

## The model (plan)

If people are **calibrated**, then out of all the answers given with
confidence c, a fraction c are correct. I fit a logistic regression that
predicts whether each answer was correct from the stated confidence, the task
difficulty and the domain (memory or perception), and compare its **score**
(log₁₀ likelihood) with and without the domain term. The headline figure is
the **average gap** (confidence − accuracy) against difficulty, one line per
domain.

## Data

The [Confidence Database](https://osf.io/s46pr/) (Rahnev et al., 2020,
*Nature Human Behaviour* 4, 317–325). Raw data is **not** stored in this repo.
See [`data/README.md`](data/README.md) for how to get it and which datasets
are locked away as the test set.

## Repo layout

```
memory-vs-perception-confidence/
├── data/            # README only; the raw data lives in Google Drive
├── notebooks/       # Colab notebooks, numbered in order (01_, 02_, ...)
├── src/             # reusable code: loading, simulation, models
├── results/
│   └── figures/     # final figures for the writeup
├── writeup/         # 2-page writeup (template + drafts)
├── video/           # 60-second video plan
├── docs/
│   └── decision-log.md   # every decision: what, why, alternatives
├── AI-NOTES.md      # what the AI did and what I decided
├── SOURCES.md       # every dataset and outside source
└── README.md
```

## Plan

- [ ] **Phase 0: Setup.** Repo, Colab + Google Drive, decision log
- [x] **Phase 1: Question.** Choose the question
- [ ] **Phase 1: Guess.** Write my guess with a probability in this README
- [ ] **Phase 2: Data.** Survey the datasets (readmes only), set inclusion rules, lock the test datasets
- [ ] **Phase 3: Simulate.** A calibrated simulated observer must come out calibrated at every difficulty
- [ ] **Phase 4: Fit.** Logistic regression on the training datasets
- [ ] **Phase 5: Test.** Open the locked test set once
- [ ] **Phase 6: Communicate.** Writeup, figures, video, thumbnail

## Future directions

- Are wrong memory answers given with high confidence (confident errors, as in false memories)?
- Does a run of correct answers make people overconfident?
- Do animals show the same pattern, using wagering or waiting-time measures of confidence?

## How to run

The notebooks run in Google Colab. numpy, pandas, scipy, statsmodels and
matplotlib are already installed there.

## AI use

I use AI (Claude) as a mentor: to brainstorm, suggest structure and question
my reasoning. The question, the guess, the decisions and the interpretation
are mine. Every decision is logged in [`docs/decision-log.md`](docs/decision-log.md),
and [`AI-NOTES.md`](AI-NOTES.md) lists what the AI did and what I did.
