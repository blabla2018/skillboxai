# Project Instructions

This project curates useful language-learning phrases and formats them as cards, especially from English Skillbox lessons and for Spanish study. RemNote owns assessment, recall checking, repetition scheduling, mastery, and progress; this project only produces text for manual paste.

Before creating new cards or lesson summaries, read the relevant files in `memory/`:

- `memory/workflow.md`
- `memory/remnote-format.md`
- `memory/english-skillbox.md` for English Skillbox tasks
- `memory/spanish-cards.md` for Spanish tasks
- `memory/teacher-feedback-english.md` for English teacher-recommended phrases and their card-usage status
- `memory/teacher-feedback-spanish.md` for Spanish teacher-recommended phrases and their card-usage status
- `memory/used-english-cards.md` to avoid duplicates in English cards
- `memory/used-spanish-cards.md` to avoid duplicates in Spanish cards
- `memory/useful-phrases.md` when building English cards

Default output style:

- Use compact Markdown.
- For RemNote-ready output, wrap all paste-ready material in exactly one `markdown` code block.
- Keep headings clean, without backticks.
- Cards are the default content. Add a short formula or explanation only when it materially helps interpret them.
- Put any necessary formulas inside normal text using backticks.
- Card format: `русское предложение==translation`.
- Normally test one primary phrase or construction per card, using natural Russian and target-language wording that match as closely as possible in meaning, emphasis, context, and sentence structure.
- Do not add, omit, generalize, specify, or reframe information on either side of a card. The Russian prompt must provide all the information needed to produce the target-language answer without guessing a different intended meaning.
- Keep corresponding details in the same part of both sentences whenever the target language allows it. In particular, temporal, spatial, causal, and other contextual references must belong to the same clause and retain the same relative position (for example, beginning or end) on both sides.
- If a natural translation requires substantially different word order or phrasing, rewrite both sides so they remain natural while their information structure stays maximally aligned; do not preserve a Russian prompt that leads to a materially different target-language sentence.
- Prefer common, contemporary, reusable phrases that fit the lesson and the learner's level.
- Apply recorded preferences and corrections; English weak spots are used only for English cards when they fit naturally.
- Keep English and Spanish histories independent; avoid exact, key-phrase, and near-duplicate learning targets within the target-language history.
- Before selecting cards, record every newly observed teacher-recommended phrase in the matching language's teacher-feedback file, including phrases that are not selected.
- Record a new teacher-feedback phrase as unused. After an approved or reusable batch is added to the matching used-card history, mark each phrase or construction actually present in that batch as used and cite the lesson/card-set heading. Normal inflection and a contextual determiner or pronoun in the same construction slot still count when the learning target is preserved. Leave all other phrases explicitly unused.
- Teacher-feedback usage status means only "used in a generated card"; it must never be treated as mastery, recall, repetition, or learning-progress state.
- Never copy English teacher feedback into the Spanish registry or Spanish teacher feedback into the English registry.
- Prefer quality over coverage: do not pad a set to reach a fixed card count.
- Do not implement or imply RemNote synchronization, automated import, spaced repetition, or learning-progress tracking.
