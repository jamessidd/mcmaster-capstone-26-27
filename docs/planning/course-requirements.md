# Course reference

Supporting notes for the [project overview](high-level-design.md). Page references use PDF page numbers. The course outline governs conflicting slide content; check Teams/Avenue for later announcements and official templates.

## Dates and submissions

| Due | Deliverable | Weight |
| --- | --- | --- |
| Sep 21, 2026 | Team/project selection; GitHub with staff access | 5% |
| Sep 28 | Topic freeze | — |
| Oct 9 | Unified requirements and project plan, maximum 15 pages | 15% |
| Nov 23 | Two-minute proof-of-concept video and presentation | 10% |
| Jan 25, 2027 | Design and verification/validation document | 10% |
| Apr 5 | Final two-minute video | 5% |
| Apr 5 | Working system, code, final documents, user guide and poster | 50% |
| TBD | EXPO demonstration and poster | 5% |

Source: [outline pp 4–6](../../course_docs/COMP%20SCI%204ZP6%20Course%20Outline%202026-20271.pdf). Final grading emphasizes complexity, completeness and professionalism. Staff must independently run the system, and AI performance needs sound metrics.

## Requirements to retain

- Seven students are allowed. Everyone, including the coordinator, contributes technically. Book at least two instructor reviews and one TA deep dive per semester. [Slide set 1 pp 7, 9, 14](../../course_docs/slide_set_1.pdf).
- Use the posted project form; each member submits the identical PDF. Later documents are team submissions. Include contributors, revision history and a glossary. The October plan needs roles, tools, data/compute, workflow and a Gantt chart. [Slide set 2 pp 4–14](../../course_docs/slide_set_2.pdf).
- The November video must show working code. January’s design explains components, interfaces, UI and failure behavior, with a 2–3-page testing section. Final documents add test results and a one-page requirement completion report. [Slide set 3 pp 4–20](../../course_docs/slide_set_3.pdf).
- Store implementation in `src/`, deliverables in `docs/`, and actual attendee/agenda records in `meetings/`. Documents go to Avenue as PDFs; videos follow their upload instructions. Cite AI assistance accurately. Outline pp 3, 9.

## Conflicts and open questions

Plan PoC upload for **Nov 22** under slide set 3 p 4, with presentation Nov 23. Ignore its obsolete April 2026 dates; the outline says **Apr 5, 2027**. Use the outline’s **$125** expense limit, subject to prior written TA approval, rather than the slides’ $150. Confirm Avenue’s displayed deadline/timezone.

Staff should not need to compile code manually (slide set 3 p 20). Agree how automated local game preparation and staff ROM access meet that requirement. Official templates, roster and staff assignments are still missing.

## Technical references

Reviewed September 16, 2026; these are source checks, not local test results.

- [N64Recomp](https://github.com/N64Recomp/N64Recomp): translates game instructions; runtime and training integration remain our work.
- [mk64 decompilation](https://github.com/n64decomp/mk64): game structure/build reference. Its completion status alone does not establish native compatibility.
- [Existing MK64 native port](https://github.com/arefdsg/MK64Recomp): prior art to assess before choosing a base.
- [gym-mupen64plus](https://github.com/bzier/gym-mupen64plus): existing emulator-based RL. Measure differences rather than claiming emulator training is impossible.
- [Gymnasium](https://gymnasium.farama.org/api/env/): a standard interface through which training code observes and controls an environment.

Version 0.2 condenses the original source review. Codex extracted sources and drafted these notes; human verification is pending. RL means reinforcement learning; SRS means software requirements specification; V&V means verification and validation.
