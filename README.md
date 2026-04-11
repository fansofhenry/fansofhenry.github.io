# fansofhenry.github.io

A personal operating system and research hub for **Henry Fan** — CVC-OEI Application Support Analyst at the Foothill–De Anza Community College District, undergraduate researcher, and PhD aspirant in CS Education / Learning Sciences.

Live site: <https://fansofhenry.github.io>

This repository is intentionally two things at once:

1. **A daily-driver productivity system** for the work of becoming a researcher — schedule, focus blocks, mastery queue, and habit tracking.
2. **A public research lab** at [`/research-lab/`](https://fansofhenry.github.io/research-lab/), where a three-paper first-author program with Prof. Jeff Anderson (Foothill College) is planned, executed, and made visible.

The site is static HTML, hand-written, and deployed straight from `main` via GitHub Pages. No build step, no framework, no tracking.

---

## Why this site exists

Most research careers begin behind closed doors: scattered notebooks, private Notion pages, Dropbox folders full of half-draft PDFs. That opacity makes it hard for mentors to give fast feedback and hard for admissions committees to see how a student actually works.

This site takes the opposite bet. Everything a mentor would want to see — the plan, the constraints, the templates, the weekly log, the failure modes each paper might hit — lives at a stable URL that Jeff Anderson can open in 30 seconds from his phone. Everything a PhD admissions committee would want to verify — "is this person capable of shipping a paper, or just of planning one?" — accumulates in public as the work happens.

The habit-tracker side of the repo (`index.html`, `focus.html`, `dream-binder.html`) is the cost of producing that research on top of a full-time job. It is explicitly the private back of the house, not the research itself.

---

## Site map

| Path | Purpose | Primary audience |
| --- | --- | --- |
| [`/`](https://fansofhenry.github.io/) — `index.html` | **Compound** — dashboard, schedule, playbook. Henry's daily operating system. | Henry (daily), mentor (read-only via `?mentor=1`) |
| [`/research-lab/`](https://fansofhenry.github.io/research-lab/) | **The Modeling Bench** — three-paper research program with Jeff Anderson. Mission, mentor lineage, per-paper cards, workflow, PhD targets. | Jeff, PhD admissions committees, Henry |
| [`/focus.html`](https://fansofhenry.github.io/focus.html) | **Focus Blocks** — mentor-voiced execution surface for margin-time blocks. | Henry |
| [`/projects.html`](https://fansofhenry.github.io/projects.html) | **Project Launchpad** — the active portfolio of side projects. | Henry, visitors |
| [`/mscs-tools.html`](https://fansofhenry.github.io/mscs-tools.html) | **MS CS Tools** — roadmap + textbook library for the CS graduate-readiness path. | Henry |
| [`/dream-binder.html`](https://fansofhenry.github.io/dream-binder.html) | **Dream Binder** — printable GTD horizons-of-focus workbook. | Henry (annual review) |

---

## The research program (in one paragraph)

Three first-author papers at the intersection of applied linear algebra, hands-on lab pedagogy, and CS education in the age of AI. Each paper extends a specific, written invitation from Jeff Anderson's published work or his Math 2BL deliverables document. Venues: PRIMUS (Problems, Resources, and Issues in Mathematics Undergraduate Studies), College Math Journal, and Journal of Computing in Higher Education.

| # | Working title | Venue | Status |
| --- | --- | --- | --- |
| **P01** | *MER 2.0 — Open-Hardware, Computer-Vision Lab Kit for Coupled-Oscillator Modeling in Lower-Division Linear Algebra* | PRIMUS | Backlog |
| **P02** | *From Matrices to Networks — A Linear-Algebra-First, Hands-On Introduction to Neural Networks for Community College Students* | PRIMUS | Backlog |
| **P03** | *Anti-Racist AI Tutoring in the Applied Modeling Classroom — A Design and Evaluation Framework* | JCHE / PRIMUS | Backlog |

Full abstracts, research questions, 12-week execution plans, and risk analyses live at [`/research-lab/`](https://fansofhenry.github.io/research-lab/).

### Mentor context

Prof. Jeff Anderson (Foothill College) is Henry's research mentor and the second author on every paper in this program. This is a **mentee-led research program, not a funded academic lab** — Jeff provides domain heritage, journal taste, and corrective feedback; Henry drives scoping, experiments, drafting, code, hardware, video, and submission. The "Modeling Bench" is a working metaphor for the bench where Jeff's hands-on verification ethos gets practiced, not an institutional claim.

---

## Operating principle

> Every week, two things must move forward: (a) a measurable artifact in at least one paper (data, code, hardware photo, draft section), and (b) a five-minute mentor-ready update. If neither moved, the week is a regression — diagnose why before doing anything else.

This principle is visible in the weekly-review template at [`research-lab/templates/weekly-review.md`](research-lab/templates/weekly-review.md) and in the research log on the lab page itself.

---

## Running locally

No build step. Clone and serve the directory with any static server:

```bash
git clone https://github.com/fansofhenry/fansofhenry.github.io.git
cd fansofhenry.github.io
python3 -m http.server 8000
# open http://localhost:8000/
```

The research-lab page uses `localStorage` for the research-log and theme preference; clearing site data resets both. Nothing is sent to any server.

---

## Repository conventions

- **One file per page.** Each entry point is a self-contained HTML file with inline CSS and JS. This is a deliberate choice — the site is small, personal, and should stay legible at a glance. No bundler, no shared component framework.
- **Commits carry the "why."** Commit messages explain motivation, not just what changed. See `git log` for the habit.
- **No tracking.** No analytics, no third-party scripts beyond Google Fonts. All state is local.
- **Accessibility matters.** Every page supports keyboard navigation, `prefers-reduced-motion`, and sufficient color contrast. The research-lab page is the reference implementation.

---

## Citing this work

If you reference the research program or its artifacts, see [`CITATION.cff`](CITATION.cff) for structured citation metadata. GitHub renders a "Cite this repository" button from that file.

## License

Content (writing, plans, prose): **CC BY 4.0** — attribute to Henry Fan.
Code (HTML, CSS, JavaScript in this repo): **MIT** — see `LICENSE` if present, otherwise assume MIT with attribution.
