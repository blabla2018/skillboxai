## ADDED Requirements

### Requirement: Ground candidate phrases in supported sources
The system SHALL derive candidate phrases from the requested Skillbox lesson, related exercises, original Skillbox examples or translations, recent weak spots, and applicable project memory. The current lesson SHALL remain the primary source unless the user requests another scope.

#### Scenario: Generate from a named lesson
- **WHEN** the user requests cards for a specific Skillbox lesson
- **THEN** the system reads the lesson and relevant linked practice before selecting candidate phrases
- **THEN** recent weak spots and project memory influence the selection only where they fit the lesson naturally

#### Scenario: Skillbox source is unavailable
- **WHEN** the requested lesson cannot be read because the site is unavailable or authentication is missing
- **THEN** the system reports the limitation instead of inventing lesson content

### Requirement: Prioritize useful and natural phrases
The system SHALL prioritize phrases that are common in contemporary English, reusable in realistic situations, appropriate for the learner's requested level, and valuable beyond a single exercise.

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
- **WHEN** a candidate phrase and meaning already appear in `used-english-cards.md`
- **THEN** the system does not generate another equivalent card

#### Scenario: Near-duplicate wording exists
- **WHEN** a candidate differs only by a minor wording variant such as `listen to reason` versus `listen to the voice of reason`
- **THEN** the system treats the variants as one learning target unless the distinction itself is useful

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
