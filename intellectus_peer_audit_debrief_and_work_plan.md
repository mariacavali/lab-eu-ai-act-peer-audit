Intellectus — Peer-Audit Debrief and Remediation Work Plan

Auditors: Marija Kavaliauskaite and Elza Paegle
Builders: Gretel and Paola
Project: Intellectus — Social Impact Intelligence

Part A — Required debrief record

Status: Complete — based on the real builder debrief response.

1. Auditor presentation

Marija Kavaliauskaite and Elza Paegle presented the independent audit findings:

- Independent classification: limited risk / transparency
- Role map: provider, deployer, and unidentified third-party vendors
- Key findings: AI transparency/provenance, GDPR/data governance, production security boundary, and auditable human review
- Overall recommendation: proceed with conditions

2. Builder response

The builder agreed with the overall direction of the audit and described the limited-risk / transparency classification as conditional on the production system using an AI component to generate substantive diagnostic text, hypotheses, or recommendations. Because the prototype contains substantial deterministic logic and no final AI-model provider has been identified, the builder noted that legal review may conclude that an entirely deterministic deployed version falls outside the Article 3(1) definition of an AI system. This is a legal boundary requiring confirmation, not a definitive conclusion.

The builder also clarified that Article 14 human-oversight duties do not directly apply unless Intellectus is classified as high-risk. Human review remains an important professional and governance control supporting responsible use, transparency, GDPR compliance, and protection against automation bias. Article 50 output-marking duties likewise depend on whether the production AI component generates substantive content and how that content is used or published.

The builder confirmed these current gaps:

- The intended purpose, AI components, and third-party providers are not recorded in a complete system inventory; the final AI-model provider remains unidentified.
- The interface lacks a sufficiently explicit and accessible notice about AI-generated or AI-transformed content, and outputs lack machine-readable provenance or AI-generation markers.
- Human review is designed into the workflow but is not enforceable through an authenticated reviewer, mandatory approval gate, durable correction history, or override log.
- GDPR controls for incidental personal data and future uploads—including lawful basis, minimisation, retention, deletion, and vendor agreements—are not defined.
- Formal AI-literacy training and a documented appropriate-use policy for consultants are absent.

3. Classification comparison

| Assessment | Tier | Basis |
| --- | --- | --- |
| Marija and Elza's independent peer audit | Limited risk / transparency | Outside Article 5 and Annex III; Article 50 transparency duties may apply to AI interaction and generated content. |
| Builder's self-audit | Limited risk / transparency, conditional | The classification assumes that the production system qualifies as an AI system under Article 3(1) and generates substantive content. |

Areas of agreement:

Both reviews reached substantially the same first-pass classification and agreed that the documented system is not prohibited under Article 5 and does not currently fall within a documented Annex III high-risk use.

Important qualification rather than a substantive disagreement:

The builder emphasized that, if the deployed implementation remains entirely deterministic, legal review may conclude that it falls outside the AI Act's Article 3(1) definition rather than being a limited-risk AI system. The builder also refined the analysis by noting that Article 14 does not directly apply without a high-risk classification and that Article 50 output-marking duties depend on the production AI functionality and how outputs are used or published.

4. Gap-list comparison

Findings identified by both reviews:

- transparency and disclosure for AI-generated or AI-transformed content
- provenance and machine-readable output marking
- human review, approval controls, and auditability
- GDPR and personal-data governance
- production governance, vendor identification, and documentation

Builder emphases that were less explicit in the external audit:

- a complete system inventory covering intended purpose, AI components, and third-party providers
- formal AI-literacy training
- a documented appropriate-use policy for consultants
- uncertainty about whether an entirely deterministic implementation meets the Article 3(1) AI-system definition

Substantive refinements from the builder:

- Article 14 human-oversight duties should not be treated as directly applicable while the system is not classified as high-risk; human review remains an important professional and governance control.
- Article 50 output-marking duties are conditional on the production AI functionality and the use or publication of outputs.
- The limited-risk classification depends on the production implementation qualifying as an AI system.

5. Joint closing note

The comparison showed that the internal and external audits reached broadly the same risk classification and identified many of the same governance gaps, but approached them from different angles. The external audit surfaced operational controls and assumptions that may be less visible to the builder, while the builder's technical context clarified where specific AI Act obligations are conditional rather than directly applicable. Together, the two perspectives produced a more precise assessment than either review alone.

Part B — Stretch: work plan for the production-security finding

Gap selected

The browser currently calls an n8n webhook directly. The documentation states that this cannot protect a secret and that production still needs authentication, gateway controls, restricted CORS, rate limits, request-size enforcement, redacted logs, idempotency, and retention/deletion controls.

Deliverable that closes the gap

An authenticated backend-for-frontend or equivalent API gateway, accompanied by a short security and data-retention standard.

The gateway must authenticate the consultant, authorize access, store secrets server-side, restrict CORS, enforce per-user and per-IP rate limits, reject bodies above 256 KiB, generate correlation IDs, redact logs, prevent unintended retries, and support run deletion or cancellation.

Responsibility

Technical owner: full-stack or platform engineer

Workflow owner: n8n administrator

Assurance: security reviewer

Privacy requirements: DPO or privacy counsel

Acceptance: Intellectus product owner

Realistic timeline

Period

Work

Days 1–2

Confirm data flow, threat model, authentication method, and retention requirements

Days 3–7

Implement gateway, authorization, secret management, CORS, rate limits, size limits, and redacted logging

Days 8–10

Add idempotency, run cancellation/deletion, monitoring, and automated security tests

Days 11–12

Independent review, remediation, documented release decision

Closure evidence

Architecture diagram showing that browsers cannot reach n8n directly

Authentication and authorization test results

CORS, rate-limit, and oversized-request rejection tests

Proof that secrets never reach browser code or public error responses

Sample redacted logs and verified correlation-ID tracing

Demonstrated run deletion across gateway and n8n execution data

Approved retention schedule and processor/vendor record

Signed security acceptance stating that no critical or high-severity findings remain
