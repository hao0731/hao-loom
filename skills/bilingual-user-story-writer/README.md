# Bilingual User Story Writer

A skill for turning rough product requirements into structured **User Stories** or **PBIs** with **Traditional Chinese + English** output.

## What this skill does

This skill helps an AI assistant:

- transform rough ideas, meeting notes, or incomplete requirements into structured backlog-ready content
- decide whether the output should be a **User Story** or a **PBI**
- ask clarification questions when the requirement is ambiguous
- make assumptions explicit before generating final output
- suggest splitting large requirements into multiple stories
- generate bilingual content in **Traditional Chinese** and **English**
- produce testable **Acceptance Criteria** using **Given / When / Then**

## Output structure

The final output follows this structure:

- Story Title
- Background
- Description
- Requirements
- Acceptance Criteria

## Title rules

### User Story
If the requirement is best expressed as a user-centric story, the title must follow:

`As a <role>, I want to ..., so that ...`

Example:

`As a customer support agent, I want to filter tickets by priority, so that I can handle urgent issues first.`

### PBI
If the requirement is more system-oriented or implementation-oriented, the title should be a concise English phrase.

Example:

`Add unread message badge on browser tab`

## Language behavior

### Interaction language
During clarification, assumption listing, or split suggestion, the assistant should follow the user's current conversation language:

- If the user writes in Traditional Chinese, respond in Traditional Chinese.
- If the user writes in English, respond in English.

### Final output language
The final formal output must always include both:

- Traditional Chinese
- English

## Folder structure

Recommended structure:

```text
bilingual-user-story-writer/
  SKILL.md
  README.md
  templates/
    output-template.md
  examples/
    user-story-example.md
    pbi-example.md
```

## Recommended usage

Use this skill when the user wants to:
- write a User Story
- write a PBI
- refine raw requirements
- convert meeting notes into backlog items
- improve acceptance criteria
- split a large feature into smaller stories

## Notes
- Keep requirements concrete and testable.
- Avoid vague wording such as “improve experience” unless it is translated into observable behavior.
- Keep Chinese and English semantically aligned.
- Acceptance Criteria should describe one scenario per item whenever possible.