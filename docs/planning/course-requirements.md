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

Staff should not need to compile code manually (slide set 3 p 20). Plan an installable demo or accessible deployment and staff test accounts where needed. Official templates, roster and staff assignments remain open.

## Spotted research notes

Checked 17 September 2026. Source availability is not proof that our chosen species, licenses, phone or compute budget work.

| Assumption | Finding and consequence |
| --- | --- |
| Camera identification and badges differentiate us | [Seek already provides both](https://help.inaturalist.org/en/support/solutions/articles/151000169914-what-is-the-difference-between-inaturalist-and-seek-by-inaturalist-), including offline identification. iNaturalist provides shared observations and community identification. Validate a more specific local user experience. |
| Local discovery is entirely new | [Seek shows commonly recorded organisms nearby](https://www.inaturalist.org/pages/seek_app). [Merlin supports identification and location/date-based exploration](https://www.allaboutbirds.org/news/get-more-from-merlin-bird-id-with-these-powerful-features/). Treat differentiation as a tested design goal, not an exclusive feature claim. |
| iNat2021 has 2.7M images and a 500K mini set | [TensorFlow Datasets confirms these approximate counts and 10,000 species](https://www.tensorflow.org/datasets/catalog/i_naturalist2021). Mini overlaps the full training set. Its documented features do not include latitude/longitude/date; do not assume that metadata comes through this loader. The catalog lists a roughly 316 GiB download, so audit subset acquisition before downloading. A manageable GPU budget is unverified. |
| GBIF supplies licensed photos and current local content | [iNaturalist's export guidance](https://help.inaturalist.org/en/support/solutions/articles/151000170346-which-inaturalist-observations-are-exported-for-gbif-and-how-often-does-this-export-happen-) distinguishes observation licenses from photo/sound licenses. Check media rights separately. Query and count usable Hamilton records before promising coverage; no global record count establishes local recency. |
| Snapshot Serengeti has millions of labeled bounding boxes | [LILA lists 7.1M images but about 150,000 boxes on 78,000 images](https://lila.science/datasets/snapshot-serengeti). African camera-trap scenes are a different setting from Ontario phone photos. Exclude this dataset initially unless a detection need justifies it. |
| Google Maps means no map costs | [Current pricing lists the Maps SDK SKU as unlimited no-cost usage](https://developers.google.com/maps/billing-and-pricing/pricing), but web Dynamic Maps and other services have separate charges. [Android usage documentation requires billing setup and distinguishes SKUs](https://developers.google.com/maps/documentation/android-sdk/usage-and-billing). Choose actual services, restrict keys and set quotas before promising a free deployment. |

### Data plan before committing

Select common local species, audit permitted images and class counts, then obtain a small sample. Preserve creator, source, license and permitted uses for training and display separately. Use a pretrained model only after checking its license too. Do not download the full datasets merely because they are available.

Hold out independent observations/photographers where possible and collect a separate phone-photo field test set. Include unsupported species, poor photos and no-animal scenes. Team sightings supplement evaluation and demo content; they cannot supply a large training set by themselves.

Imported records must be labeled historical with original dates and provenance. Preserve source obscuration and uncertainty. An observed-sighting density map is not an animal-population estimate. Ask local walkers whether the proposed experience is useful; the original claim that trail groups rely on outdated forums has not been validated.

Version 0.3 replaces previous technical references with Spotted research. User supplied the idea; Codex checked sources and drafted notes. Human verification pending. SRS means software requirements specification; V&V means verification and validation; ML means machine learning.


## Expo and Google Maps

Checked 17 September 2026. Proposed development path, not tested compatibility:

- [Expo Camera](https://docs.expo.dev/versions/latest/sdk/camera/) is included in Expo Go and supports photo capture.
- [react-native-maps](https://docs.expo.dev/versions/latest/sdk/map-view/) is included in Expo Go. It supports Google Maps on Android and Apple or Google Maps on iOS; deployed Google Maps needs platform-specific keys/configuration and a rebuilt app. Test the chosen provider on each target phone.
- [Development builds](https://docs.expo.dev/develop/development-builds/introduction/) allow native libraries/configuration beyond Expo Go's fixed runtime. Plan this transition when integrating the selected ML runtime; prove offline inference separately.
- [expo-maps](https://docs.expo.dev/versions/latest/sdk/maps/) is a different library, using Google Maps on Android and Apple Maps on iOS, and is not a drop-in Expo Go alternative for this plan.

Use restricted mobile API keys and enable only needed Google services. The base map does not provide our sightings backend. No cloud account, billing service or dependency has been configured in this planning work.
