# Phrase Curation Specification

## Purpose

TBD: Define how useful, natural, lesson-grounded phrases are selected for language-learning cards.

## Requirements

### Requirement: Ground candidate phrases in supported sources
The system SHALL derive candidate phrases from the requested lesson, related exercises, original examples or translations, the matching language's teacher-feedback registry, and applicable project memory. The current lesson SHALL remain the primary source unless the user requests another scope.

#### Scenario: Generate from a named lesson
- **WHEN** the user requests cards for a specific Skillbox lesson
- **THEN** the system reads the lesson and relevant linked practice before selecting candidate phrases
- **THEN** recent weak spots and project memory influence the selection only where they fit the lesson naturally

#### Scenario: New teacher feedback is observed
- **WHEN** a lesson page, dashboard, teacher note, website, or user-provided teacher list exposes recommended phrases
- **THEN** every observed phrase is appended to the matching language's teacher-feedback registry before selection
- **THEN** each new phrase starts with an explicit unused status even when it is not selected for the current batch

#### Scenario: Skillbox source is unavailable
- **WHEN** the requested lesson cannot be read because the site is unavailable or authentication is missing
- **THEN** the system reports the limitation instead of inventing lesson content

### Requirement: Prioritize useful and natural phrases
The system SHALL prioritize phrases that are common in the requested target language, reusable in realistic situations, appropriate for the learner's requested level, and valuable beyond a single exercise.

#### Scenario: Choose between a reusable and an isolated phrase
- **WHEN** two candidates teach comparable language but one is broadly reusable and the other only fits an isolated exercise
- **THEN** the system selects the broadly reusable candidate

#### Scenario: Candidate value is uncertain
- **WHEN** a candidate appears rare, bookish, awkward, or insufficiently useful and the lesson does not require it
- **THEN** the system omits the candidate rather than padding the card set

### Requirement: Apply user preferences and corrections
The system MUST consult recorded preferences, useful-phrase notes, and prior corrections when curating candidates. An explicit recorded rejection or preferred alternative MUST override a generic vocabulary-coverage goal.

#### Scenario: Previously rejected phrase appears again
- **WHEN** a candidate is marked as awkward or low priority in project memory
- **THEN** the system excludes it unless the current lesson explicitly requires it or the user asks for it

#### Scenario: Preferred expression is recorded
- **WHEN** project memory records a preferred natural alternative for a candidate
- **THEN** the system uses the preferred expression when it preserves the lesson's intended meaning

### Requirement: Avoid duplicate learning targets
The system MUST compare candidates with previously used cards and exclude exact duplicates, near-duplicate phrases, and cards that test substantially the same expression in substantially the same context.

#### Scenario: Exact duplicate exists
- **WHEN** a candidate phrase and meaning already appear in the matching language's used-card history
- **THEN** the system does not generate another equivalent card

#### Scenario: Near-duplicate wording exists
- **WHEN** a candidate differs only by a minor wording variant such as `listen to reason` versus `listen to the voice of reason`
- **THEN** the system treats the variants as one learning target unless the distinction itself is useful

### Requirement: Keep language-specific teacher feedback separate
The system MUST store English teacher feedback in `teacher-feedback-english.md` and Spanish teacher feedback in `teacher-feedback-spanish.md`. It MUST NOT merge, compare, or copy entries across these registries.

#### Scenario: Spanish teacher feedback is captured
- **WHEN** the user supplies Spanish teacher feedback
- **THEN** only the Spanish registry is updated

#### Scenario: Skillbox English feedback is captured
- **WHEN** the English Skillbox dashboard exposes `Проблемные места в уже пройденном`
- **THEN** only the English registry is updated

### Requirement: Track card use without tracking mastery
The system MUST retain every teacher-feedback phrase with an explicit used/unused card status. A phrase SHALL be marked used only when the phrase or construction appears in a recorded approved or reusable card, and the entry SHALL name the corresponding card-set heading.

#### Scenario: Feedback phrase is used in an approved card
- **WHEN** an approved or reusable batch containing the phrase is added to the matching used-card history
- **THEN** the feedback entry is checked and includes `used in` evidence naming that batch

#### Scenario: Construction is adapted to the card context
- **WHEN** a recorded card uses the same teacher-feedback construction with normal inflection or a contextual determiner or pronoun in the same slot
- **THEN** the feedback entry is treated as used when the learning target remains unchanged

#### Scenario: Feedback phrase is not selected
- **WHEN** a captured phrase does not fit the current lesson or card set
- **THEN** it remains unchecked and available for future use

#### Scenario: Usage status is reviewed
- **WHEN** a feedback entry is checked or unchecked
- **THEN** the status is interpreted only as card-source usage and never as mastery, recall, repetition, or progress

### Requirement: Prefer quality over exhaustive coverage
The system SHALL produce only candidates that pass the selection criteria and SHALL NOT require a fixed number of cards unless the user specifies one.

#### Scenario: Lesson has few high-value phrases
- **WHEN** only a small number of lesson phrases are natural, useful, and non-duplicate
- **THEN** the system returns a smaller high-quality set instead of filling a quota with weaker material

### Requirement: Exclude learning assessment from curation
The system SHALL NOT infer mastery, schedule repetition, score recall, or maintain learning-progress state as part of phrase curation.

#### Scenario: Previously used card is encountered
- **WHEN** a phrase already has a generated card
- **THEN** the system uses that fact only for duplicate avoidance and does not infer whether the learner knows the phrase
