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

### `01_pipeline_orchestrator_gpt.json`

Defines the orchestration layer that routes content requests into the right workflow and prevents skipped review gates.

### `02_content_strategy_intake_gpt.json`

Defines the intake layer. This GPT turns rough content asks into structured briefs by clarifying the audience, business goal, reader problem, technical truths, required proof, missing inputs, and review path.

### `03_technical_content_builder_gpt.json`

Defines the technical drafting layer. This GPT creates technical explainers, architecture overviews, implementation guides, tutorials, FAQs, solution briefs, and technical enablement assets while separating verified facts from assumptions.

### `04_marketing_content_builder_gpt.json`

Defines the marketing drafting layer. This GPT turns approved briefs and technical truths into buyer-facing content such as messaging frameworks, landing pages, campaign briefs, sales one-pagers, executive POVs, and answer-engine-ready FAQs.

### `05_editorial_qa_governance_gpt.json`

Defines the quality gate. This GPT reviews drafts for clarity, technical accuracy, claim support, audience fit, risk, differentiation, and publication readiness.

### `06_repurposing_distribution_gpt.json`

Defines the repurposing layer. This GPT turns approved source assets into derivative content for channels such as LinkedIn, email, sales enablement, FAQs, executive summaries, and web sections without introducing new unsupported claims.

### `07_pipeline_actions_openapi_stub.json`

Provides an OpenAPI-style schema stub for connecting the pipeline to workflow systems such as Notion, Google Drive, Jira, Asana, or a CMS. It is a placeholder and requires real endpoints, authentication, and security review before production use.

### `08_interview_talk_track.json`

Provides a concise interview narrative for explaining the project, including a core pitch, thirty-second version, why the system matters, and likely follow-up questions.

## Core Design Principles

### 1. Intake before drafting

The system does not treat a topic as a complete request. It first clarifies the audience, reader problem, business goal, technical truths, claims requiring validation, and review path.

### 2. AI drafts are not automatically publishable

Drafts are treated as structured pre-review artifacts. The pipeline is designed to help humans review faster and more accurately, not bypass human judgment.

### 3. Claims must be traceable

The system flags unsupported claims, missing proof, ambiguous technical assertions, and review blockers before content reaches publication.

### 4. Technical truth controls marketing language

Marketing assets must stay grounded in verified technical facts, buyer pain, and proof. The system prevents vague or inflated claims from becoming final messaging.

### 5. Repurposing happens only after approval

Derivative assets should come from approved source content. The repurposing layer preserves the narrative spine, caveats, and claims library across channels.

## Example Workflow

1. A stakeholder submits a rough content request.
2. The intake GPT converts the request into a structured brief.
3. The orchestrator routes the brief into a technical, marketing, enablement, thought leadership, or hybrid workflow.
4. The technical or marketing builder creates a draft package with assumptions, verification flags, and review questions.
5. The QA governance GPT scores the draft and identifies blockers.
6. Human reviewers validate technical claims, positioning, legal risk, and publication readiness.
7. Once approved, the repurposing GPT creates channel-specific derivative assets.

## Example Use Cases

* Turning feature-first product notes into a reader-centered content brief
* Creating technical explainers that are easier for SMEs to review
* Drafting buyer-facing messaging without inventing proof
* Running editorial QA before content reaches legal, SMEs, or publication
* Repurposing approved technical content into sales enablement and social content
* Demonstrating AI workflow design in a job interview or portfolio review

## Quality Gates

The pipeline includes explicit checks for:

* Intake completeness
* Audience clarity
* Reader problem definition
* Technical accuracy
* Claim support
* SME review needs
* Legal or compliance risk
* Message consistency
* Publication readiness
* Reuse suitability

## How to Use This in an Interview

A strong way to present this project:

1. Start with the orchestrator to show systems thinking.
2. Show the intake GPT to explain why good content starts before drafting.
3. Show the technical and marketing builders to demonstrate workflow-specific drafting.
4. Show the QA governance GPT to explain how trust and risk are managed.
5. Close with the repurposing GPT to show how approved content becomes reusable infrastructure.

Suggested framing:

> The mistake teams make with AI content is treating the model like a faster writer. This project treats AI as a governed content operating system. It starts with intake, routes work based on asset type and risk, creates drafts with verification flags, runs QA before publication, and repurposes only approved material. The goal is not just more content. The goal is less chaos, fewer unsupported claims, and more reusable content infrastructure.

## What Makes This Different from a Prompt Library

A prompt library gives users isolated instructions.

This project defines a workflow system with:

* Role-specific GPTs
* Input schemas
* Output contracts
* Handoff rules
* Quality gates
* Review blockers
* Approval paths
* Repurposing controls

That makes it closer to a lightweight content operating model than a collection of drafting prompts.

## Suggested Success Metrics

Teams could evaluate the pipeline using:

* Intake completeness score
* Review cycle time
* Number of unsupported claims caught before publication
* SME review churn
* Draft readiness score
* Content reuse rate
* Percentage of derivative assets traced to approved source content

## Production Notes

This package is a portfolio-ready prototype. Before using it in a production content workflow, teams should:

* Add real source-of-truth repositories
* Define reviewer permissions
* Connect approved claims libraries
* Add authentication and security review for workflow integrations
* Validate any OpenAPI actions against real systems
* Define ownership for final editorial, product, legal, and compliance approval

## License

Add the appropriate license for your intended use.

## Author

Will Kelly
