Intellectus — Peer-Audit Evidence and Clarifying-Questions Log

Auditor: Elza Paegle
Project builders: Gretel and Paola
Project audited: Intellectus — Social Impact Intelligence
Review date: 18 August 2026
Review basis: System description and technical documentation only; the builders' self-audit conclusions were not reviewed.

Evidence reviewed

apps/intellectus-web/README.md

apps/intellectus-web/docs/INFORMATION_ARCHITECTURE.md

apps/intellectus-web/docs/N8N_INTEGRATION_CONTRACT.md

apps/intellectus-web/docs/REPORT_MAPPING.md

apps/intellectus-web/src/app/initialIntake.ts

apps/intellectus-web/src/schemas/diagnosticTransport.ts

apps/intellectus-web/src/fixtures/demoDiagnostic.ts

fixtures/intellectus_71_live_request.json

docs/ARCHITECTURE_FREEZE.md

workflows/WORKFLOW_MAP.md

docs/INTELLECTUS_AUDIT_GUIDE.md was deliberately not reviewed because it could contain the builders' own audit conclusions or live-audit interpretation.

Independent-review statement

This evidence log was prepared as an independent audit. The builders' self-audit conclusions were not used to form the first-pass classification or the findings below.

Phase 1 — Annotated evidence

The labels below replace handwritten annotations: Risk tier marks facts affecting classification, Clarify marks unresolved facts, and Obligation marks evidence relevant to a legal or governance requirement.

Evidence

Annotation

Audit significance

Intellectus turns public organisational information into a consultant-reviewed starting point for a client conversation.

Risk tier

The intended purpose is professional decision support and conversation preparation, not an individual eligibility or access decision.

Intake includes organisation name, website, country, current challenge, research dates, and an empty document-reference array.

Clarify / Obligation

There are no dedicated name or email fields, but free text and public research can still contain personal data. GDPR cannot be ruled out.

The live workflow performs public research, evidence assembly, transformation, and final-response preparation.

Risk tier / Obligation

The system generates findings and recommendations rather than merely storing information. AI transparency and output-quality controls are relevant.

Outputs preserve sources, evidence, findings, unknowns, contradictions, confidence, and validation questions.

Obligation

Traceability and uncertainty controls are meaningful safeguards, although the system is not high-risk.

Inferred, hypothetical, and unknown findings require validation; unsupported values are not synthesized to fill gaps.

Obligation

This reduces hallucination and overclaiming risk and supports meaningful human review.

The consultant chooses questions and next steps, can add notes, and makes the Draft/Ready decision. Workflow results cannot overwrite human notes or review status.

Risk tier / Obligation

The output is advisory and human-controlled. The current evidence supports classification outside Annex III.

Review status and notes exist only in React session memory; no remote or browser persistence is used.

Clarify / Obligation

The MVP protects private notes from export, but cannot retain a durable record of review or override.

Direct browser-to-workflow deployment cannot protect a secret; authenticated gateway, CORS, rate limits, redacted logs, and retention rules are still required.

Obligation

This is a material production-readiness and data-security gap explicitly acknowledged by the builders.

The interface shows an Intellectus brand and a Demo indicator.

Clarify / Obligation

A Demo badge is not the same as a clear notice that the user is interacting with AI or receiving AI-generated content.

Exact AI model, model provider, research API, hosting region, and model data-retention terms are not identified in the reviewed materials.

Clarify / Obligation

The vendor role map, Article 50(2) allocation, transfer analysis, and technical provenance controls remain incomplete.

Phase 2 — First-pass classification

Question

Independent answer

Does this system fall under any prohibited category (Article 5)?

No, based on the documented intended purpose. It does not manipulate people into harmful behaviour, conduct social scoring, infer emotions from biometric data, scrape facial images, or perform prohibited biometric identification or categorisation.

Does this system operate in any of the eight Annex III areas?

No. It conducts organisation-level public research and prepares consulting analysis. It is not documented as deciding access to education, employment, essential services, law enforcement, migration, justice, or democratic participation.

If Annex III: does it significantly influence decisions in that area, or is it narrow/preparatory?

Not applicable. A reassessment would be required if Intellectus were used to decide individual grant, benefit, employment, education, or service eligibility.

Does this system interact with end users or generate content requiring disclosure (Article 50)?

Yes. A consultant interacts with the application and receives AI-generated findings, hypotheses, questions, recommendations, KPIs, and roadmap content. Article 50(1) is relevant, and Article 50(2) may apply to the provider of the integrated content-generating system. Article 50(4) would become relevant if generated text were published on a matter of public interest without qualifying human editorial review and responsibility.

First-pass risk tier

Limited risk / transparency

One-sentence justification citing the specific article or Annex entry

Intellectus is outside Article 5 and the Annex III use cases for its documented consulting purpose, but its direct AI-supported interaction and generated content bring Article 50 transparency duties into scope.

Classification boundary

This conclusion depends on Intellectus remaining an advisory tool for organisation-level consulting. It must be reassessed if a public authority or service provider uses its output to determine a natural person's eligibility for public assistance, employment, education, credit, insurance, or another Annex III decision.

Phase 3 — Clarifying-questions log

These questions remain open after reviewing the supplied documentation. They should be sent to the builders in writing before the audit is treated as final. If no response is received, the provisional assumptions below govern the report.

#

Information requested

Why it matters

Provisional assumption without an answer

Status

1

Which language model, model provider, research API, hosting region, and model version are used by DEV_PROJECT3_END_TO_END?

Required to complete the provider/vendor map, assess international data transfers, and determine how Article 50(2) machine-readable marking is implemented.

A third-party generative model and research service are integrated through n8n; their compliance cannot be verified from the current repository evidence.

Open — written response required

2

Can consultants enter names, employee details, beneficiary information, or confidential client information in current_challenge, and can public research collect information about identifiable people?

Determines GDPR scope, lawful basis, privacy notice, minimisation, and DPIA screening.

Personal data may enter through free text or researched sources even though no dedicated personal-data fields exist.

Open — written response required

3

Is the Draft/Ready action a mandatory technical gate before export or client delivery, and will production retain who approved the brief, when, and what was changed?

Confirms whether human review is operationally enforceable and auditable rather than only encouraged by interface copy.

Review is expected and human-controlled, but the session-only MVP does not provide a durable approval log.

Open — written response required

4

Will production be restricted to internal consulting preparation, or could clients use results for grants, public-service eligibility, recruitment, worker evaluation, or other consequential decisions?

A new intended purpose could change the Annex III classification and obligations.

Use is restricted to organisation-level consulting and client-conversation preparation.

Open — written response required

5

Where does the interface disclose AI involvement, and how are generated outputs marked in human-readable and machine-readable form?

Determines compliance with Article 50(1), 50(2), and potentially 50(4).

No adequate AI disclosure or provenance mechanism is evidenced; the Demo indicator is not sufficient.

Open — written response required

Sources for the legal test

Regulation (EU) 2024/1689 — consolidated EU AI Act

Article 3 — provider, deployer, importer, and downstream-provider definitions

Article 5 — prohibited practices

Annex III — high-risk use cases

Article 50 — transparency obligations

General Data Protection Regulation
