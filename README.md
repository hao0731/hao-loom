# HAO Loom

HAO Loom is an open source skills library for AI Agents. It collects reusable
Skills that improve developer workflows, from shaping requirements to checking
whether design documents still match the implementation.

The name **Loom** comes from the weaving machine. This repository is meant to
weave together the recurring actions developers perform while planning,
building, reviewing, documenting, and collaborating, so AI Agents can support
those workflows with clearer context and more reliable execution.

## Purpose

HAO Loom provides practical Agent Skills for software development work. Each
Skill is designed to be:

- reusable across repositories, products, and teams
- explicit about when it should be used
- structured enough for AI Agents to follow consistently
- documented with examples, templates, or usage notes when useful
- focused on real developer workflows, not only text generation

This project is intended for developers, product teams, technical writers, and
AI Agent users who want their agents to follow repeatable workflows instead of
starting from scratch on every task.

## Available Skills

| Skill | Purpose |
| --- | --- |
| `checking-design-doc-drift` | Reviews whether design documents, plans, ADRs, specs, README files, and other agent-facing docs still match the current implementation. |
| `bilingual-user-story-writer` | Turns rough product requirements into structured User Stories or PBIs with Traditional Chinese and English output. |
| `design-document-creator` | Creates, updates, reviews, or normalizes engineering design documents with consistent frontmatter, scope, decisions, alternatives, invariants, and testing strategy. |
| `design-document-index-creator` | Creates or updates `index.yaml` for engineering design documents by reading Markdown frontmatter and using the bundled index script. |
| `design-document-searcher` | Finds relevant engineering design documents for a request, code path, tag, feature, component, PR, issue, or implementation question. |
| `design-document-re-index` | Checks whether design-document `index.yaml` files match Markdown frontmatter, then rebuilds stale indexes through the index creator workflow. |

More Skills can be added over time as reusable development workflows emerge.

## Repository Structure

```text
hao-loom/
  skills/
    checking-design-doc-drift/
      SKILL.md
      README.md
    bilingual-user-story-writer/
      SKILL.md
      README.md
      templates/
      examples/
    design-document-creator/
      SKILL.md
      agents/
      references/
    design-document-index-creator/
      SKILL.md
      agents/
      references/
      scripts/
    design-document-searcher/
      SKILL.md
      agents/
    design-document-re-index/
      SKILL.md
      agents/
```

Each Skill lives in its own directory under `skills/`.

Common files:

- `SKILL.md`: the main instruction file consumed by an AI Agent
- `README.md`: optional human-facing documentation for the Skill
- `templates/`: reusable output formats or document templates
- `examples/`: example prompts, inputs, or expected outputs
- `references/`: canonical reference materials or templates used by the Skill
- `scripts/`: executable helpers used by the Skill workflow
- `agents/`: agent-specific configuration or adapter files

## Usage

Browse the `skills/` directory and choose the Skill that matches your workflow.
Each Skill includes a `SKILL.md` file with trigger metadata and workflow
instructions. Some Skills also include a README with recommended prompts and
usage notes.

Example prompts:

```text
Use $checking-design-doc-drift to review this repository for stale design documents.
```

```text
Use $bilingual-user-story-writer to turn this requirement into a bilingual PBI.
```

```text
Use $design-document-creator to draft a design document for this feature.
```

```text
Use $design-document-index-creator to update docs/designs/index.yaml.
```

```text
Use $design-document-searcher to find the design docs related to this code path.
```

```text
Use $design-document-re-index to check whether the design document index is stale.
```

The exact installation and invocation flow depends on the AI Agent or tool
environment you use. In general, copy or install the Skill directory into the
custom Skills path used by your Agent, then invoke the Skill by name.

## Skill Design Principles

Skills in HAO Loom should follow these principles:

- **Workflow first**: describe how the Agent should work, not just what it
  should output.
- **Clear trigger**: make it obvious when the Skill should be used.
- **Practical structure**: include checklists, examples, or templates when they
  reduce ambiguity.
- **Evidence over assumption**: encourage Agents to inspect source material and
  cite concrete evidence when reviewing or transforming work.
- **Open collaboration**: make the Skill understandable to humans so it can be
  reviewed, improved, and adapted by the community.

## Contributing

Contributions are welcome. A good contribution should add or improve a Skill
that captures a repeatable development workflow.

When adding a Skill, please include:

1. A dedicated directory under `skills/`
2. A `SKILL.md` file with clear trigger metadata and workflow instructions
3. Human-facing documentation, such as `README.md`, when additional usage notes
   or examples would help readers
4. Templates or examples if the Skill produces structured output
5. Concise wording that helps both humans and AI Agents understand the intent

Before opening a pull request, review the Skill from two perspectives:

- Would a developer understand when and why to use it?
- Would an AI Agent have enough structure to execute it reliably?

## Roadmap Ideas

Possible future directions:

- more Skills for code review, planning, testing, and release workflows
- shared contribution guidelines for Skill quality
- example integrations with common AI Agent environments
- a catalog or index for discovering Skills by workflow category

## License

HAO Loom is licensed under the MIT License. See [LICENSE](LICENSE) for details.
