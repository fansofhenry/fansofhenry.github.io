# Reproducibility checklist — <paper-NN slug>

Run this before every draft submission to PRIMUS, the College Math Journal, or any other venue. The rule Jeff taught: **if a figure can't be regenerated from a commit hash and a seed, it doesn't go in the paper.** This checklist enforces that.

Fill in every box. If you can't check it honestly, the paper isn't ready to submit — *not because of the venue's rules, but because you don't yet know what the paper claims.*

---

## 1. Code and data provenance

- [ ] All analysis code lives in a public git repository, linked from the paper.
- [ ] The repository has a `README.md` that names the exact script to run for each figure and table.
- [ ] The commit hash used for the submitted draft is recorded in the paper's methods section (or in a footnote on the first results figure).
- [ ] Raw data is either (a) in the repo under `data/raw/`, (b) mirrored in a permanent archive (Zenodo, OSF, Dataverse) with a DOI, or (c) explicitly marked as restricted with a named institutional contact for access requests.
- [ ] Derived data products (cleaned CSVs, processed arrays) are regeneratable from raw data by a single `make` target or `python scripts/build.py`.

## 2. Randomness and seeds

- [ ] Every stochastic procedure (train/test splits, initial weights, simulated noise, bootstrap samples) uses an explicit seed, recorded in code.
- [ ] The paper states the seed used for the figures shown, OR states that the figures are robust across seeds and gives the range tested.
- [ ] If robustness claims are made, the script that tests multiple seeds is named in the repo.

## 3. Environment

- [ ] A `requirements.txt` / `environment.yml` / `Pipfile.lock` pins exact versions of every Python / R / Julia dependency used.
- [ ] The Python (or other) language version is pinned in the environment file.
- [ ] Non-Python dependencies (ffmpeg, LaTeX packages, Arduino IDE version, hardware firmware versions for MER 2.0) are listed with version numbers in `README.md`.
- [ ] A fresh checkout into a clean virtualenv reproduces every figure. *I have done this in the last two weeks.* Date: __________

## 4. Hardware (P1 MER 2.0 only)

- [ ] Bill of materials is in the repo as `hardware/bom.csv` with part numbers and a typical supplier.
- [ ] Spring constants, mass values, and damping coefficients used in the reference runs are documented to 3 significant figures.
- [ ] The calibration procedure is written up as `hardware/calibration.md`, not just in Henry's head.
- [ ] The open-hardware kit has been built by at least one other person from the BOM + instructions and produced matching results. Name: __________ Date: __________

## 5. Prompts and LLM runs (P3 AI Tutor only)

- [ ] Every LLM prompt used in the evaluation is in the repo verbatim under `prompts/`.
- [ ] The exact model name, version, temperature, top-p, and max tokens are recorded for each run.
- [ ] Model outputs used in figures are cached to `data/llm-outputs/` with a timestamp and the prompt hash, because model endpoints drift.
- [ ] If the paper claims behavior under a specific model version that has since been deprecated, the paper says so in a limitations paragraph.

## 6. Figures and tables

- [ ] Every figure has a script that regenerates it from data. The script filename is named in the figure caption or a supplementary table.
- [ ] No screenshot of a Jupyter cell appears in the paper. All figures are written to disk via code.
- [ ] Every table has its source query / aggregation logic in the repo.
- [ ] Color choices pass a colorblind-safe check (Viridis-family or manually checked against simulated protanopia).
- [ ] Axis labels, legends, and units are complete. "No units" means the figure is wrong.

## 7. Statistical claims

- [ ] Every *p*-value, confidence interval, or effect size in the paper is produced by a named, tested function in the repo.
- [ ] The comparison being tested is pre-registered somewhere, or the paper explicitly says the analysis is exploratory.
- [ ] Sample sizes for every claim are in the paper text (not only in a supplement).
- [ ] Multiple comparisons are corrected for, or the correction is explicitly declined with a reason.

## 8. Students and IRB (P2 and P3)

- [ ] The IRB protocol number is in the methods section.
- [ ] Consent forms used with students are in the repo (redacted of student names) as `irb/consent-form.pdf`.
- [ ] Any identifying information in quoted student work has been checked by a second reader. Name: __________
- [ ] The paper honors any "this student does not want to be quoted" flags from the consent form.

## 9. The honest limitations paragraph

- [ ] The paper has a limitations paragraph (not just a sentence).
- [ ] The limitations paragraph names at least one thing a reviewer could legitimately reject the paper for. *If it doesn't, the authors haven't tried hard enough to find it.*
- [ ] The limitations paragraph is visible in the main text, not buried in a supplement.

## 10. Pre-submission read-through

- [ ] I can run every script in the paper from a fresh clone, in one hour, on my laptop. *I have done this.* Date: __________
- [ ] Jeff has reviewed the draft. Date: __________
- [ ] One person outside the project has read the draft end-to-end. Name: __________ Date: __________
- [ ] I have slept on the final draft for at least one night before submitting.

---

*If any box is unchecked when I hit submit, I am submitting a paper I cannot defend. Come back in a week.*
