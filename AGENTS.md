# COMP SCI 4ZP6 Capstone Repository Guide

These instructions apply to every agent working in this repository.

## Working style

Read and follow [.codex/skills/ponytail/SKILL.md](.codex/skills/ponytail/SKILL.md) for every coding task. Default to its `full` intensity: understand the affected flow, then make the smallest safe change. Do not add dependencies, abstractions, scaffolding, or speculative features without a demonstrated need.

## Course context

Treat `course_docs/` as the project’s course source material. Read the relevant document before preparing or changing a course deliverable:

- `COMP SCI 4ZP6 Course Outline 2026-20271.pdf` is authoritative for grading, deadlines, repository rules, and policy.
- `slide_set_1.pdf` covers project selection and AI-project expectations.
- `slide_set_2.pdf` covers the SRS and project development plan.
- `slide_set_3.pdf` covers proof of concept, design/V&V, final submission, hazards, and licensing.

Keep course artifacts in their expected locations: implementation under `src/`, submitted/revisable documents under `docs/`, and one brief attendee-and-agenda record per team meeting under `meetings/`. Preserve contributor lists, version history, glossaries, requirement priorities, and measurable validation evidence in deliverables when applicable. Do not invent submission templates; use the course-provided template when available.

The final system must be runnable and independently testable by the course staff. For ML/RL work, define and report sound performance metrics; a model alone is not the product.

## Project direction: Mario Kart 64 RL environment

The selected capstone direction is **“Mario Kart 64 as a Reinforcement Learning Environment.”** The contribution is not simply training a racer. It is a deterministic, headless, native high-throughput environment based on static recompilation, exposed through a standard RL interface, with single- and multi-agent racing evaluation and a human-vs-agent demo.

Keep the scope evidence-driven:

1. The September feasibility gate is a working, deterministic headless stepping path that runs meaningfully faster than real time. Measure and record throughput, determinism/replay behavior, and the test configuration before committing to broader RL work.
2. Make the environment, training/evaluation pipeline, metrics, and demo separately usable. Prioritize the feasibility gate and a clean single-agent baseline before multi-agent items, large-scale parallelism, and leaderboard polish.
3. Treat the public demo as a product surface: visitors should be able to race an agent, and the project should visibly show training progress. A dashboard/UI is justified only when it materially supports this demonstration or evaluation.
4. Never commit, distribute, download, or embed Nintendo/Mario Kart 64 ROMs, extracted assets, or derived game data. Design for users to provide a legally obtained ROM locally and generate any required artifacts locally. Flag licensing, redistribution, and publication decisions for the team/advisor rather than making legal conclusions.
5. Keep provenance for third-party tools, ROM-handling boundaries, experiments, seeds/configurations, and results. Verify claims such as performance gains and compatibility with reproducible commands or tests.

## Capstone decisions

When choosing work, favor requirements that demonstrate course-scale complexity and completeness: deterministic native execution, a stable RL API, reproducible evaluation, credible metrics, and a usable demo. Track work by P0–P4 priority. P0/P1 scope must be sufficient for a working final system; P2+ work must not endanger it.

Before drafting a proposal, SRS, plan, proof-of-concept video, design/V&V document, poster, or user guide, extract the applicable requirements from the course PDFs and state assumptions explicitly. Cite generative-AI use in course submissions as required by the course outline; do not present generated text, code, or claims as unverified team work.


## Team and documentation

Use [the project overview](docs/planning/high-level-design.md) as the single high-level plan, with [course reference](docs/planning/course-requirements.md) for sources. Do not recreate separate team plans or presentation decks unless requested.

- Three people, including the user, own the environment, agent training and evaluation. Four own the website, results display, playable demo, setup/testing and videos. Everyone has technical ownership. The user is scrum master and also works on training; Codex assists rather than acting as a team member.
- Write for developers and nontechnical readers. Explain terms such as reinforcement learning, native recompilation and headless execution at first use. Describe what each component does and how they connect. Keep API details, task IDs and test matrices out of this overview; add them to course deliverables or implementation tasks when needed.
- The public website explains the project, displays verified training/evaluation results and guides local use. The human-versus-agent game runs locally. Remote gameplay and live training control are not assumed features.
- Decide feasibility by September 27, 2026, before the September 28 topic freeze. Numerical performance targets remain proposals until established from initial evidence and ratified for the SRS.
- Follow course priorities: P0 blocking failure, P1 required prerequisite, P2 ordinary work, P3 optional improvement, P4 informational. Keep multi-agent item learning and presentation polish from delaying the core system.
- Do not claim unmeasured speedups, impossibility of emulator training or novelty of native MK64 ports. Never fabricate results, attendance, contributions or bookings. Cite AI use and retain source provenance.
