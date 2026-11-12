# esci-review

![esci-review icon](assets/icon.png)

An Agent Skill that pre-screens a journal's website and published articles from the standpoint of the Web of Science Emerging Sources Citation Index (ESCI) evaluation, and predicts the likely outcome.

## What it does

- Evaluates the journal against the 24 Web of Science quality criteria (C1–C24), stage by stage: initial triage, editorial triage, and editorial evaluation (quality)
- Applies 44 specific checks (S1–S44) compiled from the reasons real journals were rejected in ESCI evaluations, each mapped to the official criteria
- Reviews the journal website (identification, policies, editorial board, publication record, website function, broken links) and a sample of articles (metadata, declarations, reporting guidelines, scientific rigour, citations with live DOI verification, presentation, scope fit)
- Aggregates author distribution, board-authored content, and policy compliance across the sample
- Predicts the outcome by stage (e.g., "would fail initial triage", "low/moderate/high likelihood of acceptance"), with the resubmission embargo that each stage carries
- Produces a prioritized markdown report with must-fix, should-fix, and ongoing-practice recommendations and a full evidence log

The 4 impact criteria, which decide promotion to SCIE/SSCI/AHCI, are out of scope; new submissions to the Web of Science Core Collection are evaluated against the 24 quality criteria only.

## Structure

```
skills/esci-review/
└── SKILL.md      # Criteria C1–C24, checks S1–S44, procedure, prediction rules, report format
```

## Installation

- **Claude Code (plugin)**:

  ```
  /plugin marketplace add huhsoleil/esci-review
  /plugin install esci-review@huhsoleil-esci-review
  ```

- **Any agent (via [skills.sh](https://skills.sh))**:

  ```bash
  npx skills add huhsoleil/esci-review
  ```

- **Claude Code (manual)**: copy the `skills/esci-review` folder to `~/.claude/skills/` (personal) or `.claude/skills/` (project).
- **Claude.ai**: download `esci-review.zip` from the [Releases](https://github.com/huhsoleil/esci-review/releases) page (or zip the `skills/esci-review` folder) and upload it under Settings → Capabilities → Skills.

## Usage

Ask, for example: "Review this journal for an ESCI application: https://example-journal.org," optionally with a list of articles or uploaded article files.

## What the skill runs and fetches

The skill contains only instructions; it bundles no scripts, hooks, or MCP servers. When used, it asks the agent to read the journal website and articles the user specifies, the Clarivate criteria page (to confirm the criteria are current), the ISSN Portal (to verify the ISSN), and Crossref or doi.org (to verify cited DOIs). It sends no data anywhere else.

## Disclaimer

The prediction is a qualitative judgment based on the published Web of Science criteria and known rejection patterns, not a validated statistical prediction. The specific checks (S1–S44) reflect past rejection reasons and are not official Clarivate requirements. The final decision rests with Clarivate. This project is not affiliated with or endorsed by Clarivate.

## License

This work is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). See [LICENSE](LICENSE).

The official criteria are summarized from Clarivate's [Web of Science journal evaluation process and selection criteria](https://clarivate.com/academia-government/scientific-and-academic-research/research-discovery-and-referencing/web-of-science/web-of-science-core-collection/editorial-selection-process/journal-evaluation-process-selection-criteria/); please refer to that page for the authoritative wording.

## Citation

Huh S. esci-review: an Agent Skill for pre-screening journals for Web of Science Emerging Sources Citation Index (ESCI) indexing [software]. 2026. Available from: https://github.com/huhsoleil/esci-review

## Author

Sun Huh, Hallym University College of Medicine
