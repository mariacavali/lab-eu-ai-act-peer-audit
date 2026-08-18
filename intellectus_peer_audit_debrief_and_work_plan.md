Intellectus — Peer-Audit Debrief and Remediation Work Plan

Auditor: Elza Paegle
Builders: Gretel and Paola
Project: Intellectus — Social Impact Intelligence

Part A — Required debrief record

Status: Complete this section only after the live debrief with Gretel and Paola. Do not submit it as completed before that conversation.

[TO COMPLETE AFTER LIVE DEBRIEF]

Use the template below to capture the real conversation with Gretel and Paola. Do not replace these placeholders with invented facts.

1. Auditor presentation

Auditor findings to present:

- Independent classification: limited risk / transparency
- Role map: provider, deployer, and unidentified third-party vendors
- Key findings: AI transparency/provenance, GDPR/data governance, production security boundary, and auditable human review

2. Builder response

Record any missing context or corrections supplied by Gretel and Paola:

- Exact AI/model and research providers: [TO COMPLETE AFTER LIVE DEBRIEF]

- Whether personal data is expected or prohibited: [TO COMPLETE AFTER LIVE DEBRIEF]

- Whether Ready is a mandatory gate: [TO COMPLETE AFTER LIVE DEBRIEF]

- Intended production users and prohibited uses: [TO COMPLETE AFTER LIVE DEBRIEF]

- Existing AI disclosure or provenance controls not visible in the reviewed files: [TO COMPLETE AFTER LIVE DEBRIEF]

3. Classification comparison

Assessment

Tier

Basis

Elza's independent peer audit

Limited risk / transparency

Outside Article 5 and Annex III; Article 50 applies to AI interaction and generated content

Gretel and Paola's self-audit

[TO COMPLETE AFTER LIVE DEBRIEF]

[TO COMPLETE AFTER LIVE DEBRIEF]

Agreement or disagreement and reason:

[TO COMPLETE AFTER LIVE DEBRIEF] State whether any difference resulted from legal interpretation or missing information in the system brief.

4. Gap-list comparison

Finding both audits identified:

[TO COMPLETE AFTER LIVE DEBRIEF]

[TO COMPLETE AFTER LIVE DEBRIEF]

[TO COMPLETE AFTER LIVE DEBRIEF]

[TO COMPLETE AFTER LIVE DEBRIEF]

5. Joint closing note

Discuss and edit the following draft together. Keep the final version to two or three sentences.

[TO COMPLETE AFTER LIVE DEBRIEF]

Draft only, not factual until revised jointly:

Comparing the two audits showed that familiarity helped the builders explain Intellectus's evidence controls and intended human-review process, while the external review focused more quickly on what the documentation did not establish, especially vendor identity, AI disclosure, production security, and data retention. The exercise demonstrated that a strong technical safeguard is not enough unless an outside reviewer can see how it operates and who is accountable for it. Independent review therefore improved both the compliance analysis and the clarity of the system documentation.

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
