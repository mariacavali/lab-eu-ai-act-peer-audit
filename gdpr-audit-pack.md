# GDPR Audit Pack — MIRA

**Student:** Marija Kavaliauskaite

**Purpose:** Educational GDPR consulting audit; not formal legal advice.

## 1. Transition note

This audit continues the MIRA scenario examined in the previous EU AI Act work. That work generally classified MIRA as a limited-risk/transparency use rather than an Annex III high-risk system, subject to implementation details. GDPR is nevertheless central because MIRA processes user-provided identity and birth details, written responses, preference choices, and optional imagery. The two analyses operate in parallel: an AI system may fall outside the AI Act's high-risk category while still requiring a lawful, fair, transparent, and secure basis for processing personal data under GDPR.

## 2. Fact pattern

- MIRA is an AI Creative Director / remote editorial photography product that creates a “Creative DNA” and five-frame visual campaign or moodboard.
- Stated inputs are name and birth details, business and creative free text, visual choices, and optional inspiration and personal reference images.
- The direct data subjects are MIRA users; uploaded images could also depict third parties, but whether this is allowed is **TBD — legal review**.
- The lab concerns an EU/EEA privacy lens; the controller's establishment and exact user geography are **TBD — legal review**.
- AI/model and infrastructure vendors are likely processors, but their identities, locations, roles, and subprocessors are **TBD — legal review**.
- Processing serves personalised creative/editorial direction and campaign generation.
- No employment, credit, health, legal, or other decision producing legal or similarly significant effects is evidenced.

## 3. Audit worksheet

### Section A — Data map

| Categories of personal data | Sources | Purpose(s), one row per purpose | Lawful basis per purpose | One-line lawful-basis justification | Retention period | Recipients / subprocessors | International transfers | Transfer mechanism |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Name; date, city, and time of birth; account/contact data if collected | User directly | Create and administer the user's MIRA session/account and deliver the requested service | Contract | These data may be objectively necessary to provide the personalised service the user requests; necessity of each birth field must be tested. | **TBD — legal review** | MIRA staff; hosting/infrastructure providers: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Business, audience, purpose, and creative-preference free text; visual choices | User directly | Produce the user's internal Creative DNA / creative direction | Contract | Processing is integral to the requested personalised creative direction, provided inputs are limited to what is necessary. | **TBD — legal review** | AI/model and infrastructure providers: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Creative DNA, prompts, generated campaign/moodboard, and associated metadata | Generated or inferred from user inputs | Generate, display, and retain the requested five-frame output | Contract | Generation and delivery are the core contracted service; optional retention beyond delivery requires separate justification. | **TBD — legal review** | AI/model, storage, and delivery providers: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Optional inspiration images and optional personal reference photograph, including metadata | User upload | Use reference material to personalise the requested output | Contract | User-initiated upload can be processed to perform the requested feature; necessity and a non-upload route should be documented. | **TBD — legal review** | AI/model, image-processing, and storage providers: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Service events, security logs, device/network identifiers if collected | Product and infrastructure | Secure the service, prevent misuse, and diagnose faults | Legitimate interests | **Purpose:** service security; **necessity:** proportionate logs may be required to detect and investigate abuse; **balancing:** minimise fields and access, use short retention, and respect users' reasonable expectations. | **TBD — legal review** | Security, logging, and infrastructure providers: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Transaction and statutory records, if MIRA sells the service directly | User and payment provider | Meet applicable accounting, tax, or record-keeping duties | Legal obligation | Retention is justified only to the extent a specific applicable legal duty requires it; the duty is **TBD — legal review**. | **TBD — legal review** | Payment/accounting providers and competent authorities: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Product-use and analytics events, if collected | User interaction, device, or cookies/SDKs | Product analytics or improvement, including model improvement if proposed | **TBD — legal review** | Collection, purpose, necessity, expectations, ePrivacy requirements, and any use for model training are not evidenced. | **TBD — legal review** | Analytics and AI/model vendors: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |
| Contact details and communication preferences, if collected | User directly | Send optional promotional communications | Consent | Consent is appropriate only if marketing is optional, specific, informed, recorded, and as easy to withdraw as to give; local ePrivacy rules remain **TBD — legal review**. | **TBD — legal review** | Email/CRM vendors: **TBD — legal review** | **TBD — legal review** | **TBD — legal review** |

Contract as an Article 6 basis does not resolve incidental Article 9 data. If special-category data are processed, a separate Article 9 condition and appropriate safeguards are required: **TBD — legal review**.

### Section B — Risk and rights

#### 1. Are Article 9 special-category data present or inferable?

MIRA does not collect Article 9 data by design on the available facts. However, free text and photographs can incidentally reveal racial or ethnic origin, health, political or religious beliefs, sexual orientation, or other sensitive circumstances. A Creative DNA or AI output could also infer such information even when the user did not state it explicitly.

A photograph is not automatically biometric data under Article 9; it becomes biometric data in this context only where specific technical processing is used for unique identification. MIRA should warn users not to submit unnecessary sensitive or third-party data, avoid sensitive inference, and establish a handling rule. The applicable Article 9 condition, if such processing occurs, is **TBD — legal review**.

#### 2. Does Article 22 automated decision-making apply?

On the stated facts, Article 22 is unlikely to apply. MIRA automates creative synthesis and image generation, but it does not make employment, credit, healthcare, legal, or comparable decisions, and its output does not appear to produce legal or similarly significant effects on a person.

This conclusion must be revisited if MIRA is later used to rank people, gate services, or make consequential commercial decisions. Profiling can still occur without Article 22 applying and remains subject to transparency, lawful-basis, objection, and fairness duties.

#### 3. Is a DPIA required or strongly recommended?

A DPIA is **strongly recommended before launch**; whether Article 35 makes it strictly mandatory is **TBD — legal review** after confirming scale, geography, model behaviour, and the competent supervisory authority's list. Relevant EDPB high-risk criteria appear to include evaluation/scoring through the Creative DNA, innovative AI use, and data of a highly personal or potentially sensitive nature. Matching datasets may also apply if user data are combined with vendor or external data, but no such combination is evidenced.

There is no evidenced systematic monitoring, vulnerable-subject targeting, large-scale processing, or automated decision with legal/similarly significant effect. Because EDPB guidance indicates that processing meeting two criteria will in most cases merit a DPIA, documenting the assessment is proportionate even if the final conclusion is that residual risk is not high.

#### 4. Likely data-subject friction

**Access:** responsive exports must cover raw inputs, images, Creative DNA/inferences, prompts or relevant metadata, and vendor-held copies without disclosing others' rights or trade secrets. Vendor searchability and output provenance may create practical friction.

**Erasure:** deletion must propagate across primary storage, AI/model vendors, caches, derived profiles, and backup schedules, subject to evidenced exceptions. **Objection/profiling:** users need a clear route to object where legitimate interests support profiling or security/analytics processing; contract-based core generation is not displaced merely by an objection, but fairness and transparency still apply. **Rectification:** users should be able to correct factual profile inputs and misleading inferred attributes; generated artistic outputs may be better handled through regeneration or annotation than treated as objectively correct facts.

#### 5. Controller / processor split

MIRA's product owner is likely the controller where it decides why and how user inputs are used to provide creative direction. AI/model, hosting, storage, logging, support, and communication vendors are processors only where they act on MIRA's documented instructions.

Any vendor using inputs for its own model training, advertising, security purposes beyond instructions, or other independent purposes may be an independent or joint controller for that activity. Exact roles and the identity of the legal entities are **TBD — legal review**.

#### 6. Which vendors require Article 28 DPAs?

Every vendor processing personal data on MIRA's behalf requires an Article 28-compliant DPA: likely AI inference/model APIs, cloud hosting, databases/storage, image delivery, logging/security, customer support, email/CRM, analytics, and payment support where the provider acts as processor. Actual vendors and roles are **TBD — legal review**.

The review should cover instructions, confidentiality, security, subprocessor controls, rights assistance, breach support, deletion/return, audit information, and transfer terms. A vendor acting only as an independent controller needs an appropriate data-sharing assessment rather than being mislabeled as a processor.

#### 7. Retention and deletion concerns

No retention periods are evidenced. MIRA needs purpose-specific schedules for incomplete questionnaires, uploaded originals, generated images, Creative DNA, accounts, security logs, support records, statutory records, and backups. Keeping images or prompts for general model improvement must not be bundled into core service retention.

Deletion needs a traceable workflow and contractually supported propagation to processors/subprocessors. Backup deletion may be delayed under a documented, access-restricted rotation, but the period and restoration controls are **TBD — legal review**.

#### 8. Transparency / privacy-notice concerns

The notice should explain the controller, data categories, each purpose and lawful basis, Creative DNA/inference logic in meaningful plain language, whether provision is required or optional, recipients, transfers, retention criteria, rights, complaint route, and any consequential automation. Optional image uploads, incidental sensitive/third-party content, and whether inputs are used for vendor or MIRA model training require prominent just-in-time explanations.

Vendor identities, transfer locations, retention, training use, cookies/SDKs, and the controller's contact details are **TBD — legal review**. AI disclosure should be coordinated with, but not substituted for, GDPR transparency.

### Section C — Law stacking

#### AI Act cross-check

The prior assessment treated MIRA as limited risk / transparency rather than Annex III high risk because its primary function is creative/editorial direction, not a listed consequential decision. Subject to role and implementation, AI Act transparency may require users to know when they interact with AI and require machine-readable marking of synthetic outputs; disclosure duties may also apply when generated or manipulated imagery qualifies as a deep fake, with a tailored rule for evidently artistic or creative works. AI literacy, output provenance, human oversight, incident handling, and vendor governance are prudent operational controls. These obligations sit alongside—not in place of—GDPR lawful-basis, rights, security, and transparency duties.

#### ePrivacy check

Nothing in the described creative workflow inherently requires non-essential cookies or tracking. Strictly necessary session or security storage may be used, but its implementation is not evidenced. Analytics, advertising cookies, pixels, or SDKs: **TBD — legal review**. If MIRA stores information on or accesses information from a user's device, separate ePrivacy consent requirements may apply unless a valid exemption applies; national implementation must be checked.

#### Data Act check

No connected product, IoT device, or related-service data is evidenced, so those Data Act provisions do not appear materially relevant to MIRA's described service. Cloud/data-processing-service switching rules could affect contracts between MIRA and its infrastructure providers, but whether MIRA itself is a regulated provider or customer for particular services depends on its deployment and contracts: **TBD — legal review**. Applicability should not be inferred merely because MIRA uses cloud infrastructure.

## 4. Client recommendation memo

**To:** MIRA product owner

**From:** Privacy audit team

**Subject:** Pre-launch GDPR recommendation

### Bottom line

**GO WITH CONDITIONS.** MIRA can continue toward launch because its purpose is creative direction rather than consequential decision-making, but the current evidence does not establish the data-governance, vendor, transfer, retention, and rights controls needed for EU/EEA users.

### Top three actions

**1. Fix the processing blueprint before finalising the user journey.** Record every input, inferred Creative DNA element, prompt, output, metadata field, and storage location. For each purpose, confirm whether the field is necessary, assign and document the Article 6 basis, and set a defensible retention/deletion rule. Test whether birth city and exact birth time are genuinely needed. Convert the result into a layered privacy notice with just-in-time explanations beside free-text and image uploads. State that uploads are optional, discourage unnecessary sensitive or third-party content, and clearly disclose any model-training use separately from campaign generation.

**2. Close the vendor and transfer evidence gap.** Inventory the exact legal entity, service, processing location, subprocessor chain, and role for every AI/model, hosting, storage, logging, support, analytics, email, and payment provider. Put an Article 28 DPA in place wherever a vendor acts on MIRA's instructions. Verify whether data leave the EEA and document the valid transfer mechanism and supplementary assessment rather than relying on a vendor's marketing statement. Ensure contracts support access, deletion, incident notification, audit evidence, subprocessor-change notice, and a prohibition or clear governance for vendor training on MIRA data.

**3. Run and operationalise a DPIA before launch.** Assess the Creative DNA inference, innovative AI processing, optional photographs, incidental Article 9 data, third-party images, and any dataset matching against the actual scale and architecture. Record whether Article 35 legally requires the DPIA and consult the relevant supervisory-authority list. Then test an access export and end-to-end deletion across primary systems, vendors, caches, derived profiles, and backup rotation. Assign owners and response deadlines for access, rectification, erasure, objection, breaches, and vendor escalation.

### Residual risks

Even after mitigation, free text or photographs may reveal sensitive facts and AI outputs may make unwanted inferences. Deletion may propagate imperfectly or slowly through subprocessors and backups. International-transfer arrangements and vendor subprocessor chains may change, requiring ongoing monitoring rather than a one-time check.

## 5. Overall conclusion

MIRA's earlier limited-risk/transparency AI Act assessment is compatible with a conditional path forward, but it does not mean low privacy risk. GDPR work should focus on minimisation, lawful and transparent inference, processor and transfer assurance, retention, and usable rights workflows. With those conditions evidenced and the DPIA decision documented, MIRA can pursue its creative purpose without overstating compliance or risk.

## Reference points

- GDPR, especially Articles 5, 6, 9, 13–22, 28, 32, 35, and 44–49.
- EDPB-endorsed WP29 Guidelines WP248 rev.01 on DPIAs and WP251 rev.01 on automated decision-making and profiling.
- EU AI Act, especially Article 4 and Article 50, subject to the applicable dates and MIRA's role.
- EU Data Act, especially its connected-product scope and data-processing-service switching provisions.
