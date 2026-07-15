# English / Skillbox Workflow

Use this workflow for Skillbox English lessons.

1. Open the requested lesson in the in-app browser.
2. Use the Skillbox page itself as the primary source. Do not replace it with web search or generic grammar explanations when the lesson page is available.
3. If authentication is required, ask the user to log in in the in-app browser and stop source-dependent work until access is restored. Never guess missing lesson content.
4. Read the lesson theory and identify the main grammar or lexical topic.
5. Read related exercises from the lesson menu:
   - `Тренировка «Только новое»`
   - `Техника речи 1`
   - `Техника речи 2`
   - `Техника речи 3`
   - `Техника речи 4`
   - `Техника речи 5`
   - additional `Техника речи` sections when present;
   - `Тренировка «Старое + новое»`
   - other linked practice if relevant.
6. For phrase choice, use this source priority:
   - phrases and examples from the lesson theory;
   - Russian prompts from the linked exercises;
   - original Skillbox translations when they are visible and natural;
   - the user's recent weak/problem phrases from the dashboard;
   - the user's personal preferences and corrections from this project memory.
7. Open `https://eng.skillbox.ru/lms/dashboard`.
8. Read several recent `Проблемные места в уже пройденном` blocks. They can be inside collapsed lesson blocks, so do not rely only on the first visible block.
9. Use weak/problem phrases as priority vocabulary only when they fit the current lesson or a realistic card context naturally. Do not force them into unrelated grammar or vocabulary.
10. Build the answer as compact RemNote-ready Markdown:
   - cards are the default content;
   - short theory or a formula is included only when it materially helps interpret the cards;
   - optional extra cards are included only when they pass the same quality bar.
11. Cards should:
   - train the current grammar;
   - reuse weak phrases naturally;
   - prioritize common, contemporary, reusable language;
   - be useful in real speech;
   - avoid duplicates and near-duplicates;
   - normally test one primary phrase or construction;
   - stay around B1/B1+ unless the user asks otherwise.
12. When a batch is approved or likely to be reused, append it to `used-english-cards.md` so future batches avoid duplicates.

Browser notes:

- Work through the in-app browser when reading Skillbox.
- If the page content is collapsed, scroll and open/read several recent blocks rather than using only the first visible block.
- If exercise content is not exposed cleanly, use the visible page text and the user's quoted examples as source material.
- If Skillbox is logged out, ask the user to log in and wait instead of guessing the lesson content.
- If Skillbox is unavailable, report which source could not be read. Continue only from material the user has already supplied, clearly limiting the scope; otherwise stop rather than inventing content.

Card format:

```text
русское предложение==English translation
```
