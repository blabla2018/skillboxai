# Project Boundary

This project has one responsibility: select useful language and turn it into paste-ready cards. RemNote owns knowledge assessment, recall checking, repetition scheduling, mastery, and progress.

The delivery boundary is manual paste. Do not require a RemNote API, direct synchronization, automated import, clipboard automation, spaced repetition, or learning-progress state.

# General Workflow

When creating language-learning material:

1. Identify the target grammar or lexical theme.
2. Read the lesson/theory and related exercises when available.
3. Build a candidate pool before composing cards.
4. Keep a candidate only when it passes the phrase-selection checklist:
   - it is common in the contemporary target language;
   - it is useful in real speech, not only in an abstract textbook example;
   - it can be reused in more than one situation;
   - it fits the learner's requested level, B1/B1+ by default;
   - it is relevant to the current lesson;
   - it is personally relevant or naturally reinforces a recorded weak spot.
5. Exclude candidates that are rare or bookish without a lesson-specific reason, awkward for the learner, overly specific to one exercise, outside the requested level, low-value, or difficult to place in a natural card.
6. Combine the current grammar, weak/problem phrases, and realistic situations only when the combination is natural. Never force an unrelated weak spot into a card.
7. Apply recorded user corrections, rejections, and preferred alternatives before trying to maximize vocabulary coverage.
8. Check the separate used-card history for the target language before composition at three levels:
   - exact card duplication;
   - the same key target-language phrase;
   - near-duplicate meaning and context with only minor wording changes.
9. If the source lesson gives a natural and accurate translation, preserve it. If a literal translation is unnatural, use an idiomatic meaning-aligned version.
10. Build focused cards and keep the output compact and ready to paste into RemNote.
11. After producing an approved or reusable batch, add it to the matching language history when the user wants project memory to stay current:
   - English: `used-english-cards.md`;
   - Spanish: `used-spanish-cards.md`.
12. Update the matching teacher-feedback registry after recording the batch:
   - English: `teacher-feedback-english.md`;
   - Spanish: `teacher-feedback-spanish.md`.

## Teacher Feedback Lifecycle

Teacher feedback is durable source provenance, separate from card history and separate for each language.

1. Before candidate selection, read the matching language registry.
2. When a lesson page, dashboard, teacher note, or user-provided teacher list exposes new recommended phrases, append every phrase to the matching registry before deciding which ones to use.
3. Preserve the source and date when they are available. Keep repeated feedback in its dated source section when the repetition itself is evidence.
4. New entries start as unchecked (`[ ]`), meaning "not used in a recorded card yet."
5. After an approved or reusable card batch is added to the matching used-card history, change an entry to checked (`[x]`) only when that phrase or construction is actually present in a recorded card. Add `used in` evidence naming the card-set heading.
6. Do not check an entry merely because a related idea, translation, or grammatical family appears. The key phrase or construction itself must be present. Normal inflection and contextual replacements inside the same construction slot count as use when the learning target is preserved, for example `medicine for any disorder` → `medicine for this disorder`.
7. Never remove unused feedback to make the registry look complete. Unchecked entries remain available for future lessons.
8. Used/unused is source-usage metadata only. It does not represent knowledge, mastery, recall quality, or scheduling.
9. Never compare or merge teacher-feedback entries across languages.

Quality preferences:

- Prefer quality over coverage. Do not target a fixed card count unless the user requests one, and omit uncertain candidates instead of padding the set.
- Each card should normally test one primary phrase or construction. Supporting vocabulary must not hide the intended recall target.
- When a lesson is vocabulary-heavy rather than grammar-heavy, a denser card is acceptable only when its phrases belong together and the result remains natural and memorable.
- If the user says the first batch is too unnatural or too diffuse, rebuild around the most memorable phrases instead of covering every item from the lesson.
- For compound adjectives, it is acceptable for a card to be slightly "study-like" if it combines several high-value compounds in one sentence.
- When the user provides personal details, make self-description examples that sound roughly like the user, not generic textbook people.

For cards, use:

```text
Russian sentence==English or Spanish translation
```

## Final Review

Before returning a set, verify:

- every target is grounded in the requested lesson, related practice, a naturally relevant weak spot, or an explicit user request;
- every newly observed teacher-feedback item has been captured in the matching language registry, whether selected or not;
- recorded preferences and rejections have been applied;
- exact cards, key phrases, and near-duplicate learning targets have been checked against history;
- each card has a clear primary recall target unless it is an intentional vocabulary-dense exception;
- Russian and the target-language translation express the same meaning naturally;
- the paste-ready material uses one compact `markdown` block and one `==` delimiter per card;
- the response does not depend on RemNote integration or contain learning-progress claims.
- after approval/reuse, the batch is present in the matching used-card history and every teacher-feedback phrase actually used by it has a checked entry with `used in` evidence.
