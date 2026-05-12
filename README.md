# Custom GPT Content Pipeline

A governed AI content operations system for technical and marketing content.

This project demonstrates how custom GPTs can be used as workflow infrastructure instead of one-off drafting tools. The pipeline moves content from rough intake through routing, technical drafting, marketing drafting, editorial QA, approval, and repurposing.

## What This Project Demonstrates

This package is designed as an interview-ready example of practical AI enablement for content teams. It shows how AI can support content strategy, technical accuracy, marketing alignment, review discipline, and reuse without reducing the work to generic copy generation.

The core principle is simple: AI drafts are pre-review artifacts. The system is built to create structured work, expose uncertainty, force verification, and preserve narrative consistency across technical, marketing, and enablement assets.

## Why This Exists

Most content problems start before drafting:

* The request is vague.
* The audience is unclear.
* The business goal is missing.
* Product claims are unsupported.
* SMEs receive unfocused drafts.
* Marketing language outruns technical truth.
* Approved content is not reused consistently.

This pipeline addresses those problems by assigning each stage of content work to a specific GPT role with defined inputs, outputs, constraints, and quality gates.

## Pipeline Overview

| Stage              | Owner GPT                        | Purpose                                                                                                                                 |
| ------------------ | -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Intake             | Content strategy intake GPT      | Turns vague requests into structured briefs tied to audience, business problem, technical truth, proof, constraints, and review path.   |
| Routing            | Pipeline orchestrator GPT        | Selects the right workflow, assigns asset type, enforces handoff contracts, and prevents skipped review gates.                          |
| Technical drafting | Technical content builder GPT    | Drafts explainers, documentation, tutorials, solution briefs, and technical enablement content with assumptions and verification flags. |
| Marketing drafting | Marketing content builder GPT    | Creates messaging, thought leadership, web copy, campaign content, and sales enablement material grounded in buyer pain and proof.      |
| Editorial QA       | Editorial QA and governance GPT  | Scores clarity, claim support, technical accuracy, buyer relevance, consistency, and publication readiness.                             |
| Repurposing        | Repurposing and distribution GPT | Turns approved source assets into channel-specific derivatives while preserving claims, caveats, and narrative spine.                   |

## Repository Contents

```text
.
├── 00_master_pipeline_manifest.json
├── 01_pipeline_orchestrator_gpt.json
├── 02_content_strategy_intake_gpt.json
├── 03_technical_content_builder_gpt.json
├── 04_marketing_content_builder_gpt.json
├── 05_editorial_qa_governance_gpt.json
├── 06_repurposing_distribution_gpt.json
├── 07_pipeline_actions_openapi_stub.json
├── 08_interview_talk_track.json
└── README.md
```

## File Descriptions

### `00_master_pipeline_manifest.json`

Defines the full content pipeline package, including the overall positioning, pipeline principle, stages, owner GPTs, and interview angle.

### `01_pipeline_orchest
