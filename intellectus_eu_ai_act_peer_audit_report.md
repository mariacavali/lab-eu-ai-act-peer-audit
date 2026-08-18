Intellectus — Independent EU AI Act Peer-Audit Report

Auditors: Marija Kavaliauskaite and Elza Paegle
Project builders: Gretel and Paola
Date: 18 August 2026
Recommendation: Proceed with conditions

1. System summary

Intellectus researches public information about an organisation and prepares a starting point for a consultant's next client conversation. The consultant enters the organisation, website, country, current challenge, and research period. The workflow returns evidence, findings, uncertainties, questions, recommendations, KPIs, and a roadmap. The consultant selects what to use, adds notes, and marks the final brief Draft or Ready; the current interface is session-only and a live n8n webhook performs research and transformation.

2. Risk classification

First-pass tier: limited risk / transparency.

Article 5: no prohibited practice is evidenced in the documented consulting workflow.

Annex III: no listed high-risk area is evidenced. The system prepares organisation-level consulting analysis and does not decide a natural person's access to employment, education, credit, benefits, law enforcement treatment, migration status, justice, or democratic participation. The consultant retains judgment over whether and how to use the generated material, and the documented system does not itself determine individual eligibility, access, employment, credit, or other Annex III consequential outcomes.

Article 50: potentially relevant if the production system uses an AI component to generate or transform substantive content. The applicable disclosure or output-marking duties depend on that functionality and on how generated material is used or published.

Boundary / uncertainty: this conclusion assumes that the production implementation qualifies as an AI system under Article 3(1). If it remains entirely deterministic, legal review may conclude that it falls outside that definition; if its output is repurposed for consequential individual decisions, the tier must be reassessed.

Based on the documented current use, the high-risk provider checklist and related conformity-assessment, CE-marking, and Annex III registration requirements do not appear to apply; this must be reassessed if the intended use changes.

3. Role map

| Role | Entity | Key obligations / considerations |
| --- | --- | --- |
| Provider / downstream provider | Gretel and Paola's team; any future Intellectus entity that materially repackages or redistributes the system would need to re-check downstream provider duties | If the production implementation qualifies as an AI system, implement applicable Article 50 disclosure and output marking; document purpose, limits, and vendors; ensure AI literacy under Article 4. |
| Deployer | Consulting firm or professional consultant | Follow instructions, review client-facing content, ensure AI literacy, and disclose in-scope published AI text under Article 50(4). |
| AI/model and research vendors | Not identified / unconfirmed | Meet duties applying to their systems and provide downstream technical and provenance information. |
| Infrastructure vendors | n8n and future hosting, gateway, logging, and storage providers | May be GDPR processors or sub-processors requiring contracts and security controls. |

Impacted stakeholders: the client, consultant, and identifiable people mentioned in inputs or research may be affected by unsupported, confidential, or misleading claims.

4. Compliance findings

Finding 1 — AI transparency and output provenance

Severity: Significant
Description: The interface shows a Demo indicator but no verified AI notice. If the production AI component generates or transforms substantive analytical text, the applicable Article 50 disclosure duties, responsible provider, and machine-readable provenance mechanism must be established. Article 50(4) may apply to published public-interest text without qualifying human editorial review.
Recommended action: Disclose AI use before submission and on reports. Identify the model/provider, test machine-readable marking through the workflow, and define a publication-disclosure rule.
Escalation needed? Yes — AI regulatory counsel and the model vendor.

Finding 2 — Personal-data governance and retention

Severity: Significant
Description: current_challenge is free text, public research may collect information about identifiable people, and n8n may retain execution data. No lawful-basis analysis, privacy notice, processor/transfer assessment, deletion schedule, or rights process is evidenced. Session-only browser state does not remove upstream copies.
Recommended action: Map data and vendors; constrain free text; warn against unnecessary personal or confidential information; define lawful bases, retention, deletion, and access; review processors and transfers; and screen for a DPIA.
Escalation needed? Yes — DPO or privacy counsel and the n8n administrator.

Finding 3 — Production security boundary

Severity: Significant
Description: The project acknowledges that its browser-to-n8n webhook cannot protect a secret. Authentication, a gateway, restricted CORS, rate and size limits, redacted logs, idempotency, and deletion/cancellation controls remain unimplemented. Public release in this architecture would expose the workflow to misuse.
Recommended action: Put n8n behind an authenticated backend or gateway and complete abuse, authorization, logging, secret-management, and deletion tests before release.
Escalation needed? Yes — security engineer and platform owner.

Finding 4 — Human review is well designed but not auditable

Severity: Minor for the MVP; Significant before persistent production use
Description: Evidence links, unknowns, contradictions, validation questions, consultant-controlled notes, and Draft/Ready review are strong safeguards. However, review status exists only in session memory and is not a durable gate. The MVP cannot prove who approved a brief or what AI suggestions were changed.
Recommended action: Add a mandatory export/delivery gate, reviewer, timestamp, version, override reason, and durable review event while keeping private notes excluded.
Escalation needed? No for design; involve privacy/security leads when defining the production log.

5. Overall recommendation

Proceed with conditions. No prohibited or Annex III use is evidenced, and the design clearly separates facts, inferences, hypotheses, unknowns, contradictions, and human decisions. The controlled demo may continue. Before production, implement the authenticated gateway, identify AI/research vendors and Article 50 controls, complete GDPR governance, and make consultant approval mandatory and auditable. Prohibit consequential individual eligibility or worker-evaluation use without reclassification and legal review.

6. What this report is not

This report is a first-pass educational assessment based on the system description and selected technical documentation supplied by the builders. It is not a legal opinion, conformity assessment, certification, penetration test, or guarantee of compliance. The conclusions should be verified with qualified legal counsel before EU market placement or production deployment.
