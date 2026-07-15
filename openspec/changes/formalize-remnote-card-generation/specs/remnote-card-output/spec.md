## ADDED Requirements

### Requirement: Create focused translation cards
The system SHALL express each selected phrase as a natural Russian prompt and a meaning-aligned English answer. Each card SHALL normally test one primary phrase or grammatical construction.

#### Scenario: Standard phrase card
- **WHEN** a selected phrase can be tested independently
- **THEN** the system creates a realistic sentence whose main recall target is that phrase

#### Scenario: Supporting vocabulary would obscure the target
- **WHEN** a candidate card requires several additional unfamiliar expressions
- **THEN** the system simplifies or replaces the context so the primary target remains clear

#### Scenario: Dense vocabulary card is useful
- **WHEN** a vocabulary-heavy lesson benefits from combining several closely related expressions and the result remains natural and memorable
- **THEN** the system may create a denser card as an explicit exception to the single-target default

### Requirement: Preserve bilingual meaning and naturalness
The system MUST ensure that the Russian prompt and English answer express the same intended meaning and both sound natural in their respective languages. Original Skillbox translations SHALL be preserved when they are natural and accurate.

#### Scenario: Original translation is natural
- **WHEN** Skillbox provides a natural and accurate source translation
- **THEN** the system retains it unless adaptation is needed for the selected card context

#### Scenario: Literal translation is unnatural
- **WHEN** a literal rendering would sound unnatural in Russian or English
- **THEN** the system uses an idiomatic meaning-aligned formulation

### Requirement: Produce paste-ready RemNote syntax
The system MUST format every card as `Russian sentence==English translation` and return the final RemNote material inside one `markdown` code block.

#### Scenario: Default output
- **WHEN** the system returns a completed English card set
- **THEN** all cards appear in one `markdown` code block using the required `==` delimiter
- **THEN** headings are clean Markdown headings without backticks

### Requirement: Keep the paste-ready block compact
The system SHALL keep the paste-ready block free of tables, process commentary, source-analysis notes, and unnecessary blank lines. It MAY include short formulas or theory only when they materially help the learner interpret the cards.

#### Scenario: Grammar explanation is unnecessary
- **WHEN** the cards are self-explanatory
- **THEN** the paste-ready block contains only a short heading and the cards

#### Scenario: Formula is required
- **WHEN** a concise grammar formula materially clarifies the recall target
- **THEN** the system places the formula near the relevant cards using inline code formatting

### Requirement: Support manual insertion only
The system SHALL deliver text for manual insertion and SHALL NOT require a RemNote API, direct synchronization, automated import, mastery tracking, or repetition scheduling.

#### Scenario: Card set is complete
- **WHEN** the final set has been generated and formatted
- **THEN** the system returns the paste-ready text without attempting to transmit it to RemNote
