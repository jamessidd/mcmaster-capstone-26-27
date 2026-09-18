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

## Project direction: Fieldnote

The selected direction is **Fieldnote — local wildlife discovery, identification and sightings**. Confirmed choices: camera-first wildlife capture and nearby discovery for McMaster students and casual Hamilton walkers, delivered as an iPhone-first app using Expo/React Native and Google Maps. Defer Android until the iPhone experience is stable. Remaining product choices are being brainstormed. Use [the high-level overview](docs/planning/high-level-design.md) as the single concept document and [course reference](docs/planning/course-requirements.md) for evidence. Do not recreate a separate team plan or presentation unless requested.

- Preserve the agreed personality: playful collecting, a calm map and noncompetitive social sharing. Badges reward personal discovery, including private entries. Do not introduce leaderboards, public scores, rarity incentives, popularity-ranked sightings or punitive streaks. Reactions, comments and following are design choices to scope, not assumed commitments.
- Develop a clear user purpose and compare it honestly with Seek, iNaturalist and Merlin. Do not claim identification, badges, nearby discovery or sighting maps are novel by themselves. Label proposed differentiators and untested user needs as hypotheses.
- Start with a small, data-supported mix of familiar local birds and mammals and one target phone platform. Choose exact species after auditing data; do not fix a species count without evidence. Recent sightings and a personal collection form the core experience; seasonal challenges follow it. Explain machine learning, on-device inference and backend responsibilities in plain language. Keep detailed APIs, task matrices and speculative features out of the overview.
- Use two high-level, self-organizing groups: four people including the user own the app/product/backend/demo; three own identification/data/model evaluation. Groups divide work internally; do not prescribe individual assignments. The user is scrum master within the group of four. Assume equal competence. Both groups contribute to integration, tests, documentation and videos; Codex assists rather than acting as a team member.
- After a short skippable tutorial, open on Camera. Proposed tabs are Feed, Map, Camera and Wildlife (personal collection plus field guide); profile/settings sit behind an avatar. Use Snapchat-like camera immediacy and a VSCO-like photo emphasis as visual references, with no competitive metrics.
- Start prototyping with Expo Go, expo-camera and react-native-maps. Plan a development build for native ML and deployed Google Maps configuration. Verify support on actual devices; Expo Go is not a promise of final native-library compatibility. Do not add a website or choose backend/model dependencies without a small compatibility check.
- Audit image and model licenses, species coverage and a small sample before large downloads. Observation-data licenses do not automatically cover photographs. Record provenance and separate training and evaluation data, avoiding duplicate-observation leakage.
- Treat model outputs as suggestions. Provide an uncertain/unsupported result and user review before sharing. Test unfamiliar species and non-animal images as well as the supported classes. Measure per-species performance and latency on named devices.
- Make sharing opt-in. Protect locations on the server before public delivery, remove embedded photo location metadata, preserve source obscuration, and support deletion/reporting. Sensitive wildlife may require suppression rather than approximate coordinates. Address identifiable bystanders in the capture/upload flow.
- Distinguish recent user sightings, historical imports, seasonal suggestions and demo data. Never publish a printed-photo booth demonstration as a real wildlife sighting. Do not describe observation counts as animal abundance or verified migration trends.
- Keep the first product focused. Phone identification and private drafts can work offline; shared maps need connectivity. Do not add a separate website; provide only the operator tools needed for moderation. Routes, direct messaging, live-video recognition and broad species coverage are not assumed commitments.
- Before the September 28 topic freeze, verify permitted sample data and a small model on a target device. Team/project selection remains due September 21; requirements and plan October 9. Use the course outline for conflicts and confirm later announcements.
- Use P0 for blocking failures, P1 for required prerequisites, P2 ordinary work, P3 optional improvements and P4 information. Ratify measurable targets before the SRS. Never fabricate results, user research, attendance, contributions or bookings. Cite AI assistance accurately.

Keep prose concise and understandable to developers and users. This is a working app with evaluated ML, not a model-only project. Preserve contributor lists, revisions and course-required evidence without duplicating the same plan across files.
