## Context

The repository currently uses human-readable Markdown memory files to guide English card creation. The workflow reads a Skillbox lesson, related exercises, recent dashboard weak spots, useful-phrase notes, and previously used cards, then produces material for manual paste into RemNote. The boundary between this project and RemNote has been unclear: RemNote evaluates recall and schedules repetition, while this project is only responsible for source reading, editorial selection, card composition, and formatting.

The primary stakeholder is the learner who wants a small set of cards that are worth keeping and require little or no editing. Existing project instructions favor B1/B1+ language, original Skillbox wording when natural, realistic situations, compact Markdown, and avoidance of duplicate or near-duplicate cards.

## Goals / Non-Goals

**Goals:**

- Make phrase usefulness, naturalness, popularity, relevance, and non-duplication the core selection criteria.
- Produce focused Russian-to-English cards that are convenient to paste into RemNote manually.
- Reuse current lesson content, exercise prompts, weak spots, and recorded user preferences without forcing unrelated vocabulary into a card.
- Preserve a lightweight, human-editable workflow based on the existing Markdown memory files.
- Make the output contract predictable enough to verify mechanically and review quickly.

**Non-Goals:**

- Assess whether the learner knows a phrase.
- Schedule repetition, track mastery, or reproduce RemNote functionality.
- Send cards to RemNote through an API or automate clipboard insertion.
- Build a general-purpose vocabulary database or a full Skillbox client.
- Maximize the number of cards created from every lesson.

## Decisions

### Use a source-priority pipeline

Generation will consult sources in this order: current lesson theory and examples, related exercises and technique-of-speech sections, original Skillbox translations, recent weak spots, and project preference/history files. This keeps the result grounded in the requested lesson while allowing personal weak vocabulary to influence cards when it fits naturally.

Alternative considered: treat all collected phrases equally. Rejected because weak spots or isolated exercise vocabulary can overwhelm the current lesson and produce incoherent sets.

### Apply hard filters before composing cards

Candidate phrases will be excluded when they are rare or bookish without a lesson-specific reason, awkward for the learner, too specific to one exercise, outside the requested level, already represented by an existing card, or difficult to use in a natural example. Preference notes such as the rejection of `to gobble up` override generic attempts to maximize vocabulary coverage.

Alternative considered: generate cards first and filter the completed set. Rejected because composition effort encourages retaining low-value cards and makes artificial combinations more likely.

### Optimize for acceptance, not coverage

The default result will be a small focused set rather than exhaustive coverage. A phrase is valuable when the learner is likely to paste and reuse the card without rewriting it. When quality is uncertain, the system will omit the candidate instead of padding the set.

Alternative considered: require a fixed card count for every lesson. Rejected because lessons vary in density and a fixed quota lowers quality.

### Keep cards focused

Each card will normally test one primary phrase or grammatical construction in a realistic context. Multiple target expressions may appear together only when the lesson is vocabulary-dense and the combined sentence remains natural and memorable. Supporting vocabulary must not obscure the intended recall target.

Alternative considered: combine grammar, several weak spots, and multiple new phrases in each card to increase density. Rejected because such cards are hard to recall and diagnose.

### Retain Markdown as editable project memory

The existing `memory/` files remain the source of project preferences, weak spots, useful phrases, formatting rules, and used cards. No learning state or mastery model will be added. Implementation may clarify file responsibilities and add validation guidance, but must keep the content easy for the user to inspect and edit.

Alternative considered: migrate memory to a structured database. Rejected as unnecessary for the current project size and scope.

### Treat manual paste as the output boundary

The final response will contain one `markdown` code block with clean headings and `Russian sentence==English translation` cards. Short theory or formulas may be embedded only when they materially help interpret the cards. Explanatory analysis, tables, and operational notes stay outside the paste-ready block.

Alternative considered: direct RemNote integration. Rejected because the user explicitly wants manual insertion and RemNote already owns the learning workflow.

## Risks / Trade-offs

- [Usefulness and popularity require editorial judgment] → Use explicit selection questions, prefer contemporary reusable language, and omit uncertain candidates.
- [Markdown history becomes harder to search as it grows] → Keep predictable headings and perform exact plus phrase-level duplicate checks before generation.
- [Weak spots may be forced into unrelated lessons] → Include them only when they fit the current grammar or context naturally.
- [Dense cards can hide multiple recall failures] → Make single-target cards the default and document vocabulary-dense cards as a controlled exception.
- [Original Skillbox translations may sound unnatural] → Preserve them only when natural; otherwise prefer meaning-aligned idiomatic translations.
- [A small set may omit lesson coverage] → Favor cards the learner will actually keep; allow the user to request a larger or exhaustive set explicitly.
