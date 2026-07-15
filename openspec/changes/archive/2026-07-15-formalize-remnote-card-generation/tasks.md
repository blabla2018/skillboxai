## 1. Define Project Boundary and Sources

- [x] 1.1 Update `memory/workflow.md` to state that this project only curates and formats cards, while RemNote owns assessment, recall checking, repetition scheduling, and progress.
- [x] 1.2 Update `memory/english-skillbox.md` with the required source priority: current lesson, linked practice, natural original translations, recent weak spots, and project memory.
- [x] 1.3 Document the failure behavior for unavailable or unauthenticated Skillbox content so the workflow reports the limitation instead of inventing lesson material.

## 2. Implement Phrase Curation Rules

- [x] 2.1 Add an explicit phrase-selection checklist covering contemporary usage, real-world usefulness, reuse potential, learner level, lesson relevance, and personal relevance.
- [x] 2.2 Add hard exclusion rules for rare, bookish, awkward, overly exercise-specific, level-inappropriate, and low-value phrases.
- [x] 2.3 Clarify that weak spots are included only when they fit the lesson naturally and that recorded user rejections or preferred alternatives override vocabulary coverage.
- [x] 2.4 Add exact, key-phrase, and near-duplicate checks against `memory/used-english-cards.md` before card composition.
- [x] 2.5 Make quality-over-coverage explicit: do not require a fixed card count and omit uncertain candidates rather than padding a set.

## 3. Standardize Card Composition and Output

- [x] 3.1 Update `memory/remnote-format.md` so each card normally tests one primary phrase or construction in a natural, meaning-aligned Russian-to-English pair.
- [x] 3.2 Document the controlled exception for dense vocabulary cards and require that supporting vocabulary not obscure the intended recall target.
- [x] 3.3 Require one compact `markdown` code block, clean headings, the `Russian sentence==English translation` delimiter, no tables, and no process commentary inside the paste-ready material.
- [x] 3.4 Clarify that theory and formulas are omitted by default and included only when they materially help interpret the cards.
- [x] 3.5 Preserve natural original Skillbox translations while allowing idiomatic correction when a literal source translation is unnatural.

## 4. Align Project Instructions and Verify Behavior

- [x] 4.1 Align `AGENTS.md` with the clarified project boundary, phrase-selection criteria, and manual-paste output contract.
- [x] 4.2 Review `memory/useful-phrases.md`, `memory/weak-spots.md`, and `memory/used-english-cards.md` guidance so each file has a clear role without introducing mastery tracking.
- [x] 4.3 Run a representative card-generation review using a Skillbox lesson and verify source grounding, preference handling, duplicate avoidance, card focus, bilingual naturalness, and RemNote-ready formatting.
- [x] 4.4 Confirm the workflow does not require a RemNote API, direct synchronization, automated import, spaced repetition, or learning-progress state.
