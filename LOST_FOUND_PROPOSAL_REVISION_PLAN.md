# Revision Plan: Nkumba University Lost and Found Property System

## Purpose and limits

Use this document to revise `Lost_and_Found_AI_Analytics_Project_Proposal.docx` into a research proposal for **Design and Implementation of a Web-Based Lost and Found Property Management System with AI Analytics: A Case Study of Nkumba University**.

The project scope is lost and found property management only. Do not reintroduce theft incident reporting, suspect identification, crime analytics, police investigation, facial recognition, or security case management.

This plan records the requirements already agreed and identifies facts that must be verified. Do not invent university policies, current procedures, student identities, confirmed sample numbers, research dates, or observed results. Where information is not known, retain a clearly marked `[TO CONFIRM WITH NKUMBA UNIVERSITY / SUPERVISOR]` note in the working draft or phrase it as a research question. Before submission, resolve these notes through approved requirements gathering.

## Confirmed project requirements

### Users and access

- The primary end users are Nkumba University students.
- Students must create accounts using their student details to post an item or submit a claim.
- Student details are important for identifying and verifying claimants. Keep student numbers, contact details, account credentials, and claimant evidence private and available only to authorised staff who need them.
- All authenticated university users can view all approved property listings and browse/search them by category. “Everyone” means authenticated university users unless the University explicitly approves public internet access. Do not make listings anonymously accessible on the public internet by assumption.
- Define separate permissions for students, School Administrators/Lost and Found Custodians, and system administrators. One person may hold more than one authorised role, but the system must still enforce each role’s permissions.

### Listing and custody lifecycle

- A student can post a lost-item report.
- A student/finder can post a found-item report, then physically take the object to the School Administrator or other designated custodian for the particular school where the object is held.
- Posting a found-item report does **not** mean the University has received the physical item. The record must distinguish at minimum:
  - reported found / awaiting physical delivery;
  - received and accepted into custody;
  - claimed / claim under review;
  - approved for handover;
  - returned/released;
  - rejected, duplicate, withdrawn, archived, or unclaimed, if those statuses are approved by the University.
- Only an authorised School Administrator/custodian can confirm receipt into physical custody and record the responsible office and restricted storage reference.
- The system must record custody transfers between authorised staff/offices and completed handovers.
- All students can browse listings. Students can post lost/found reports and claim items only after account creation and the approved student identity check.

### Claims and ownership verification

- False claims are a known design risk. Do not expose every identifying detail in a public listing.
- A claimant must be associated with a registered student account. Account identity helps identify who made a claim; it does not establish ownership by itself.
- Keep distinctive proof-of-ownership details private in the listing (examples for requirements discussion: unique marks, serial numbers, contents, or another detail known to the owner). These are examples, not mandatory evidence rules. The University must decide acceptable evidence and procedure.
- A custodian reviews a claim, records the verification outcome and reason, and authorises any handover under an approved University procedure.
- The system must support more than one claim against one item, preserve each claim and decision, and make claim history available only to authorised staff.
- Do not publicly label a claimant dishonest or publish rejected-claim details. A rejection is a recorded administrative decision, not a public accusation.
- AI candidate-match scores must never prove ownership or approve release. Human verification and an authorised custodian’s decision are required.

### Administrator moderation and auditability

- School Administrators/custodians manage physical receipt, storage, custody, claim review, and handover for items assigned to their school/office, subject to the University's confirmed rules.
- Administrators retain authority to edit or hide/remove a listing from ordinary browsing.
- Implement “soft delete” as hide/archive/withdraw from public browsing while retaining the record and its audit trail. Do not permanently erase an item or claim record as an ordinary moderation action.
- Record edits and moderation actions with the account, timestamp, changed field or action, and reason. Preserve prior values for consequential changes where feasible.
- Record who created a report, who accepted physical custody, custody transfers, claim attempts, claim decisions, edits, hiding/archiving, and handover/return.
- System administrators manage accounts and system-level oversight. Do not give every administrator unrestricted access to claimant evidence by assumption; define least-privilege access with the University.

## Decisions and facts that must be established, not guessed

The proposal must explicitly investigate or seek approval for the following:

1. Which specific school offices accept found property, and who is the authorised custodian for each?
2. Whether students must deliver found property to the relevant school office, and how the system identifies the correct office when the finder does not know it.
3. What documentation the custodian records when accepting an item (for example receipt time, condition, storage reference, and accepting staff member).
4. What student identity source or process is authorised for account verification (for example a university system, approved staff check, or another university-approved method). Do not assume access to student databases or integration APIs.
5. What ownership evidence is acceptable, who decides claims, and what happens when multiple claims compete or evidence is inconclusive.
6. Whether claimant and finder contact can be mediated through the system rather than exposed to one another.
7. Custody transfer procedure between staff/schools, access to storage locations, and required audit records.
8. The University's retention period and final disposition process for unclaimed property. Do not invent a time limit or disposal rule.
9. The retention and deletion period for account details, claims, photos, and audit data; who can access each category; and whether any data is processed outside Uganda.
10. Whether listings are visible only to authenticated Nkumba users or to the public internet. Current agreed default is authenticated university users only.
11. Whether the prototype will send email/SMS/push notifications, and what channels are actually available and approved.
12. Whether images are necessary for the initial prototype. Core AI matching is text/metadata based; image-recognition matching is not in scope.
13. The accessible student and staff populations, approved sample size, dates, budget, and deployment environment. All are subject to supervisor and University approval.

Represent these as requirements-gathering topics or `[TO CONFIRM]` items until evidence or approval is obtained.

## Recommended document structure and required content

Retain the proposal’s Chapters One to Three and appendices, but align every section, table, diagram, caption, and reference with the same scope.

### Cover page and front matter

- Use the title above, including Nkumba University as the case study.
- Keep student name, registration number, approved submission date, and any formal cover details as placeholders only if they are not supplied.
- Remove drafting notes and instructions to the author from the submission copy.
- Update the table of contents and page numbers after final formatting.
- Follow the School of Computing and Informatics research guide supplied by the student. Do not claim its formatting/reference rules unless the actual guide has been checked. The current new draft says IEEE style, but its actual contents and final formatting must be reconciled with the guide.

### Chapter One: Introduction

1. **Background:** Explain the campus lost/found service need, cross-school visibility, public listing with restricted identity and ownership evidence, custody at a school office, claim verification, handover, and the bounded role of AI. Use official Nkumba sources for university facts. Do not state unverified local process failures as established facts.
2. **Problem statement:** State the practical information-management problem to be investigated at Nkumba: students need to discover reports campus-wide; the physical custodian and item status need to be clear; claim verification needs to be controlled and traceable; and administrators need a reliable record. Explain that baseline details will be confirmed through requirements research.
3. **General objective:** “To design, implement and evaluate a web-based Lost and Found Property Management System with AI analytics to support reporting, discovery, custody, claim verification and return of property at Nkumba University.”
4. **Specific objectives:**
   - Investigate current lost/found reporting, custody, search, claim-verification, and handover procedures and derive requirements.
   - Design and implement student accounts, searchable campus listings, school-level custody, claim review, administrative moderation, and auditable handover workflows.
   - Develop bounded AI-assisted candidate matching and descriptive analytics for lost/found records.
   - Evaluate functionality, usability, security/privacy controls, auditability, and candidate-match relevance.
5. **Research questions:** Map each question one-to-one to the objectives: current procedures and challenges; system and privacy requirements; design of the account/listing/custody/claim workflow; utility and performance of candidate matching/analytics; and prototype evaluation.
6. **Scope:** Limit to Nkumba University and lost/found property. Specify roles and feature boundaries. State that the prototype does not identify people, make ownership decisions, or automate item release. Image recognition and multi-institution operation are outside core scope.
7. **Justification/significance:** Explain expected value to students, school custodians, university administrators, and computing research without claiming measured benefits before evaluation.

### Chapter Two: Literature Review

Organise the review around:

1. Lost-and-found procedures and custody in shared institutional environments.
2. Web-based item registers, browsing/search/filtering, status tracking, and administration.
3. Claims, ownership verification, privacy-preserving public listings, custody records, and audit trails.
4. AI-assisted text/metadata similarity matching and descriptive analytics; distinguish retrieval suggestions from proof of identity or ownership.
5. Data protection, web security, account verification, least privilege, audit logging, and human review.
6. Related Ugandan university projects and relevant international campus systems.
7. A defensible research gap tied to Nkumba’s confirmed requirements and the specific integration/evaluation proposed.
8. Conceptual framework linking reports and verified accounts; system processing and custodian workflow; outputs such as candidate matches, claim/custody status and aggregate reports; and outcomes such as improved record organisation and recovery support. Identify contextual factors such as access, data quality, user trust, custodian procedures, and privacy.

Do not claim that lost-and-found systems do not exist in Uganda: Makerere and Busitema repositories contain related projects. Compare them fairly and distinguish what repository abstracts say from what full texts establish.

### Chapter Three: Methodology

- Use an applied artefact-development approach. Design Science Research is suitable if retained, and the proposal should explain its stages and link them to problem investigation, design/build, demonstration, evaluation, and communication.
- Use a Nkumba University case study. Mixed methods may be used for user requirements and prototype evaluation if justified.
- Population should include students, School Administrators/designated custodians, and relevant system/ICT administrators. Include other staff only if requirements research identifies them as actual actors.
- Determine final sample with supervisor using the actual accessible population. Existing 30–40 estimate is provisional and must not be presented as confirmed. Explain purposive sampling for role-specific staff and an appropriate student sampling method.
- Instruments: student questionnaire; custodian/admin interview guide; observation checklist for report-to-custody/claim/handover steps; authorised document review checklist; prototype test scenarios.
- Do not copy personal information from real historical records into research data unless necessary, authorised, and protected. Prefer synthetic or anonymised test data.
- Qualitative analysis: thematic analysis of reporting, custody, search, verification, handover, privacy, and usability requirements.
- Quantitative analysis: descriptive statistics and task completion/test results. Do not promise inferential claims without a justified design/sample.
- AI evaluation: define a labelled test set of lost/found pairs and report its size, composition, labelling method, and limitations. Use an appropriate measure such as precision@k, recall, or the share of known matches retrieved in top suggestions. Also inspect false positives/negatives. Do not claim accuracy from illustrative examples alone.
- Functional scenarios must include: account verification; browse/filter by category; lost report; found report before physical hand-in; custodian receipt; custody transfer; valid claim; rejected claim; multiple competing claims; approval and handover; edit/hide/archive with reason and retained history; and audit review.
- Security/privacy evaluation must test role boundaries, private student/claim data, hidden ownership details, storage references, input handling, and audit history.
- Ethics must cover consent, voluntary participation, permission, confidentiality, data minimisation, retention, secure handling, and student power dynamics. Confirm relevant university ethics/administrative approvals.
- Limitations should include prototype scale, small/constructed matching dataset, variable item-description quality, possible limited historical records, and untested production deployment.

### System requirements and workflow specification

Include a requirements table with actor, action, access boundary, data recorded, status transition, and evidence/test case. At minimum:

| Actor | Permitted actions | Restrictions / controls |
|---|---|---|
| Verified student | Browse all approved listings; submit own lost/found reports; submit and track own claims | Must have an approved student account; cannot see other students’ private profile/claim evidence or restricted storage details; cannot approve own claim |
| School Administrator / custodian | Confirm physical receipt, assign/record school custody, manage authorised storage reference, review claims, record decision and handover | Limited to assigned school/items unless a university policy authorises wider access; all consequential actions logged |
| System administrator | Manage accounts and roles, oversee listings, edit or hide/archive with reason, view approved aggregate analytics | No silent/permanent removal of accountability; sensitive claim access only when required by assigned duties |

Status model should separately represent report publication, physical custody, claim state, and item disposition so “posted” is never confused with “held by the University.” Define the exact state transitions after the University confirms its process.

### AI analytics boundary

- Core AI: TF-IDF/cosine similarity over text descriptions; optionally combine category, colour, brand, approximate time/location only after defining a transparent scoring method.
- Show ranked candidate pairs and similarity rationale where practical.
- Descriptive analytics: counts by category, school/location, date range and status; number of claims and returned items; unresolved/awaiting custody records. Clearly label denominator and data period.
- The database calculates exact counts/rates. Generative AI summaries are optional and should not be added unless needed and feasible. If used, summaries must be grounded in database-calculated values and reviewed by a human.
- AI does not assess people, claimant honesty, ownership, or eligibility for release. No facial recognition, suspect identification, or automated release.
- Do not send names, student numbers, contact information, claim evidence, or item-owner proof details to an external AI service. If any external processing is proposed, disclose and assess it under Uganda’s data-protection requirements before inclusion.

### Privacy and security requirements

- Public-to-university listings expose only general descriptions and approximate location/date as approved; do not expose student identities, contact details, exact storage location, or private ownership clues.
- Verify student details through an approved university process. Do not assume integration with an existing student information system.
- Apply authentication, role-based authorization, least privilege, server-side validation, secure password hashing, protected file handling if uploads are included, and audit logging.
- Define retention and deletion/archive rules with the University. “Soft delete” must preserve accountability and access controls.
- Address Uganda’s Data Protection and Privacy Act, 2019 and Data Protection and Privacy Regulations, 2021 as the primary legal framework. GDPR may be a comparative benchmark only, not Ugandan law.
- Use current OWASP references. OWASP Top 10:2025 is current at the time of this plan; OWASP ASVS 5.0.0 can inform testable verification requirements.

## References to add or verify

Use the required style from the actual School guide consistently. The following sources were identified during research; verify bibliographic metadata and consult full texts before relying on detailed claims.

1. Nkumba University, “NU Profile,” https://nkumbauniversity.ac.ug/nu-profile/ — institutional student estimate and schools. Cite only for facts actually shown there.
2. Makerere University repository, “An online lost and found items system,” https://dissertations.mak.ac.ug/handle/20.500.12281/18905 — local related project; consult full record/document for author/date and methods.
3. Makerere University repository, “A mobile application for finding lost items (SearchiT),” https://dissertations.mak.ac.ug/handle/20.500.12281/15582 — local related project; consult full record/document.
4. A. F. Musitwa, “A web-based tool for reporting and recovering lost items for Busitema University students Nagongera,” Busitema University Digital Repository, https://bdears.busitema.ac.ug/handle/123456789/9296 — 2026 repository record; consult full document and verify final citation details.
5. N. M. David et al., “A comparative study on lost and found management systems in academic institutions,” 2024, DOI: https://doi.org/10.1109/WAIE63876.2024.00049.
6. S. Y. Tan and C. R. Chong, “An Effective Lost and Found System in University Campus,” 2023, DOI: https://doi.org/10.35631/JISTM.832007.
7. “FindItHere: Lost and Found Item Matching Web Application,” UTHM journal page, https://periodical.uthm.edu.my/index.php/aitcs/article/view/20420 — verify publication metadata and review full text.
8. Uganda, Data Protection and Privacy Act, 2019 (Act 9 of 2019), revised text: https://ulii.org/en/akn/ug/act/2019/9/eng%402023-12-31.
9. Uganda, Data Protection and Privacy Regulations, 2021: https://ulii.org/en/akn/ug/act/si/2021/21/eng%402021-03-12.
10. Personal Data Protection Office Uganda, registration guidance: https://pdpo.go.ug/media//2022/01/20102021105143-Registration_Classification_and_Guidance_Notes.pdf. Use if discussing controller/processor obligations; verify current PDPO guidance.
11. Scikit-learn, “Pairwise metrics, affinities and kernels” and “TfidfVectorizer”: https://scikit-learn.org/stable/modules/metrics.html and https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html.
12. K. Peffers et al., “A Design Science Research Methodology for Information Systems Research,” 2007, DOI: https://doi.org/10.2753/MIS0742-1222240302.
13. A. R. Hevner et al., “Design Science in Information Systems Research,” 2004, DOI: https://doi.org/10.2307/25148625.
14. National Institute of Standards and Technology, AI Risk Management Framework 1.0, 2023, DOI: https://doi.org/10.6028/NIST.AI.100-1. Use as voluntary risk-management guidance, not Ugandan law.
15. OWASP Foundation, OWASP Top 10:2025, https://owasp.org/Top10/2025/.
16. OWASP Application Security Verification Standard 5.0.0, https://asvs.owasp.org/.

Remove references that only support the abandoned theft/suspect/crime-reporting scope unless they directly support a retained general design or research-method claim. Every in-text citation must resolve to a reference-list entry and every reference must be cited in the body.

## Appendices to update

- **Student questionnaire:** ask about current lost/found reporting, discovery across schools, preferred categories/filters, account verification expectations, found-item hand-in, claim and update preferences, privacy concerns, and usability. Do not solicit student passwords, full ID numbers, item serial numbers, or actual ownership proof in research questionnaires.
- **Staff/custodian interview guide:** ask which office accepts which items; how physical receipt/storage/transfers are recorded; what student verification is authorised; how ownership evidence and competing/rejected claims are handled; who may edit/hide listings; retention/unclaimed-item rules; notification channels; access boundaries; and desired aggregate reports.
- **Observation checklist:** observe only with permission; document process steps and information flow, not unnecessary personal data.
- **Work plan and budget:** label estimates as provisional and replace with supervisor-approved dates/costs. Do not state deployment or hosting commitments that are not approved.

## Final consistency checklist for the model editing the Word file

- [ ] One consistent title and scope across cover page, chapters, headings, tables, diagrams, captions, appendices, and metadata.
- [ ] No theft reporting, suspect-identification, crime hotspot, police case-management, facial-recognition, or accusation functionality remains.
- [ ] Nkumba is the confirmed study site everywhere; local claims are either cited or explicitly identified for requirements research.
- [ ] Student registration/verification, authenticated browsing, school custody, claim verification, competing claims, admin editing/hiding, audit trail, and handover are represented consistently.
- [ ] A posted-found record is distinct from confirmed physical custody.
- [ ] Public listing data is distinct from private student, claimant, ownership-proof, and storage data.
- [ ] Soft deletion means hide/archive with retained history, not silent permanent erasure.
- [ ] AI is a candidate-matching and descriptive-analytics aid only; no AI ownership or release decision.
- [ ] Objectives, questions, scope, framework, methodology, test cases, evaluation criteria, and appendices map to one another.
- [ ] Unknown university procedures, sample size, dates, and retention rules are not fabricated.
- [ ] References are checked for accuracy, relevance, citation-style compliance, and in-text/list consistency.
- [ ] Remove internal drafting notes and refresh the table of contents and page numbers after formatting.
