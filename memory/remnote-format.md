# RemNote Formatting Rules

Output should be easy to paste into RemNote manually. This project produces text only; it does not import, synchronize, schedule, or assess cards in RemNote.

## Card Quality

- Each card normally tests one primary phrase or grammatical construction.
- The Russian prompt and English answer must express the same meaning and sound natural in their respective languages.
- Keep supporting vocabulary familiar enough that it does not obscure the intended recall target.
- A vocabulary-dense card is a controlled exception: use it only when the expressions belong together and the full sentence remains natural and memorable.
- Preserve an original Skillbox translation when it is natural and accurate. If a literal source translation is unnatural, use an idiomatic meaning-aligned version.

Use Markdown:

- Wrap all paste-ready material in exactly one `markdown` code block.
- Keep headings clean: no backticks in headings.
- Use short headings, for example:
  - `Главная идея`
  - `Формула`
  - `Просьбы и команды`
  - `Слова со скрытым отрицанием`
- Put important formulas and phrases in backticks inside normal text, for example:
  - `should have V3`
  - `Let's ..., shall we?`
  - `will you?`
- Do not add too many blank lines.
- Do not use tables.
- Do not include process commentary, source-analysis notes, or operational instructions inside the paste-ready block.
- Cards are the default content. Omit theory when the cards are self-explanatory.
- Include a short formula or explanation only when it materially helps interpret the cards, and place it next to the relevant cards.
- Use exactly one `==` delimiter per card: `русское предложение==English translation`.

Embedded-card style:

```markdown
### Let's
После `Let's` используется хвостик `shall we?`
Давайте посмотрим правде в глаза, хорошо?==Let's face the truth, shall we?
```
