## Why

The project needs a precise contract for turning Skillbox lesson material into a small set of useful English phrase cards. RemNote owns knowledge assessment and spaced repetition; this project should focus only on selecting high-value phrases and producing paste-ready cards with minimal manual correction.

## What Changes

- Define Skillbox lessons, related exercises, recent weak spots, and project memory as the supported sources for card generation.
- Establish selection criteria that prioritize common, natural, reusable, level-appropriate phrases and reject rare, awkward, overly specific, or duplicate material.
- Require cards to test one primary phrase or construction in a natural context, with controlled exceptions for intentionally dense vocabulary practice.
- Standardize RemNote-ready output as compact Markdown using `Russian sentence==English translation` cards in a single fenced block.
- Keep manual paste into RemNote as the delivery boundary; exclude learning assessment, repetition scheduling, progress tracking, and direct RemNote integration from scope.
- Use existing project memory to avoid duplicate and near-duplicate cards and to apply recorded user preferences and corrections.

## Capabilities

### New Capabilities

- `phrase-curation`: Collect and rank candidate phrases from Skillbox and project memory, then filter them for usefulness, naturalness, relevance, level, and duplication.
- `remnote-card-output`: Turn selected phrases into natural, focused translation cards and return them in the project's required paste-ready Markdown format.

### Modified Capabilities

None.

## Impact

- Affects the English Skillbox workflow and RemNote formatting guidance in `memory/`.
- Affects how project memory for weak spots, useful phrases, used cards, and user corrections is consulted during generation.
- Does not require a RemNote API, browser automation beyond reading source material, or any learning-progress subsystem.
