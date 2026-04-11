# The Modeling Bench

**Live site:** https://fansofhenry.github.io/research-lab/

A working hub for Henry Fan's three-paper research program with
Prof. Jeff Anderson (Foothill College). The site tracks:

- **Paper 01** — MER 2.0: an open-hardware, computer-vision lab kit
  that extends Anderson (2018) *Make Eigenvalues Resonate* to a
  three-mass case. Target venue: *PRIMUS*.
- **Paper 02** — From Matrices to Networks: a linear-algebra-first,
  SVD-centered introduction to neural networks for community-college
  students. Target venue: *PRIMUS*.
- **Paper 03** — Anti-Racist AI Tutoring: a design-and-evaluation
  framework for an LLM modeling co-tutor scoped to Anderson's 8-step
  modeling process and audited against his five anti-racist
  learner-centered objectives. Target venue: *J. Computing in Higher
  Ed* / *PRIMUS*.

Henry is the principal author and driver. Jeff is the research
mentor and second author on every paper. This is a mentee-led
research program; the "lab" naming is a working metaphor for the
bench where Jeff's hands-on verification ethos gets practiced, not
an institutional claim.

## Contents

```
research-lab/
├── index.html       The hub (single-page reference + working dashboard)
├── styles.css       Design tokens, layout, dark mode, print styles
└── templates/       Copy-fill-commit templates for day-to-day work
    ├── research-log.md
    ├── experiment.md
    ├── weekly-review.md
    ├── mentor-update.md
    ├── paper-skeleton.md
    ├── video-script.md
    ├── long-list-of-candidates.md
    ├── phd-targets.md
    ├── reading-notes.md
    └── reproducibility-checklist.md
```

## Tech choices and why

- **No framework, no build step.** The whole site is one HTML file
  and one stylesheet served directly by GitHub Pages. A mentor who
  wants to fix a typo can edit index.html and push.
- **`<details>` over JS accordions.** The paper cards and PI cards
  use the built-in `<details>`/`<summary>` element so the
  non-JavaScript fallback is already the desired behavior. A JS
  enhancement adds an "Expand all / Collapse all" affordance per
  card.
- **`localStorage` research log.** The log entries live on the
  visitor's own device; a JSON export/import button lets Henry
  commit snapshots into git monthly. This avoids a backend and
  keeps the mentor-facing site purely static. The log drives two
  other UI elements on the page: (1) a per-paper "live pulse" block
  inside each paper card that shows the latest entry, the number of
  distinct modeling steps touched, and a timestamp — so the three
  paper cards reflect real state instead of an aspirational Kanban;
  (2) a "Draft mentor update" button that opens a native `<dialog>`
  pre-filled with the last 7 days of log entries grouped by paper
  and tagged with their Anderson step, shaped like
  `templates/mentor-update.md`, ready to copy into email.
- **Live program arc.** A 52-week progress bar at the top of the
  page is computed from the 2026-04-10 start date every page load,
  so the site demonstrates currency (Week N of 52) instead of just
  claiming it.
- **Anderson's 8-step modeling process as a first-class vocabulary.**
  The 8 steps (find → mathematize → state ideal → solve → analyze
  → verify → transfer → iterate) are displayed once as a legend and
  referenced in the research log's step-tag field, so mentor emails
  can cite step numbers unambiguously.

## Accessibility

- WCAG AA contrast across light and dark modes (verified against
  `--bg` / `--bg-2` / `--sb-bg` for every text token).
- Skip-to-main-content link, landmark regions labeled, `:focus-visible`
  ring, and `prefers-reduced-motion` honored.
- Icon buttons have `aria-label`; decorative emoji are
  `aria-hidden="true"`.
- The sidebar drawer closes on Escape and returns focus to the
  menu button.

## License

- Code: MIT
- Prose and figures: CC-BY 4.0

## Related

- Main site: https://fansofhenry.github.io/
- Curriculum project (Teaching Computing Differently):
  https://fansofhenry.github.io/teach_cs/
