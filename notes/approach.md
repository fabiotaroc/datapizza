# Initial approach and brainstorming

Status: AI-assisted starting hypotheses for discussion, 10 October 2026. No pilot decision has been recorded. Consequential user choices live in ../decision-record.md. This is a working note, not the final submission.

## What the sources establish

The client is an industrial group with configurable products and multiple operating units. Operations wants less data entry/checking, Commercial wants better customer service/sales, and IT needs a credible systems/effort picture. A first verifiable use in six weeks is conditional. (02 p.1)

Only UC05 explicitly has consolidated BI indicators and aggregated data. Other case descriptions identify required inputs, not confirmed data readiness. Volumes, handling times, error rates, budget and team availability are unknown. (02 pp.1-3)

DualOS combines a platform with DS/FDE delivery. The DS owns problem selection, value, stakeholders, adoption and roadmap; the FDE designs/builds integrations and workflows, verifies and maintains behavior. Discovery and adoption are shared, and the client supplies people, examples, access and trial time. (03 p.1)

The technical sheet documents workflow logic, agents, structured outputs, optional result HTML pages, supported triggers, human waits and run inspection. It does not guarantee every connector action, OCR, semantic retrieval/RAG, native Office generation, forecasting, AR, or enterprise governance requirement. Absence of documentation leaves a check, not proof of absence. (04 pp.1-5)

## Proposed decision method

First define a useful bounded output. Then check source readiness, available actions, process owner/reviewer, error consequences and measurable value. Rank on evidence and explicitly stated assumptions. Avoid invented scores, savings or an implied precision unsupported by the case.

Distinguish the complete requested outcome from the narrow pilot. A reduced pilot can be viable without proving feasibility of every component of the full case. An export/manual input is a possible first-stage choice only if it still produces a useful recurring workflow and its manual effort is included in the value assessment.

## Initial classification of all ten cases

These are provisional classifications of the stated scopes, not claims that capabilities have been tested. Use 04 pp.2-5 to check the proposed boundaries.

| ID | Perimetro valutato | Classe tecnica | Motivazione | Condizione principale |
| --- | --- | --- | --- | --- |
| UC01 | Order extraction, configuration checks and structured proposal; ERP insertion considered separately. | verifiche necessarie | Agents and structured workflow outputs are documented. Mixed PDF/email ingestion, extraction fidelity, business-rule implementation and ERP operations need checks. | Representative orders, explicit configuration rules, catalog quality and an agreed human review path; verify each required ERP action separately. |
| UC02 | Full interactive, real-time AR product configuration. | sviluppo aggiuntivo significativo | Workflow/agent orchestration does not establish a 3D/AR sales interface. This requires a separate application/asset pipeline unless an existing solution covers it. | Suitable 3D assets, configuration logic, device/interface requirements and an existing component or separately estimated development. |
| UC03 | Proposed supplier-price updates with ambiguous matches reviewed; application to ERP assessed separately. | verifiche necessarie | Structured proposals and human waits fit documented primitives. Document extraction, supplier-to-item matching and ERP updates are not validated. | Reliable supplier/item mappings, representative price lists and authorized approval/update path. |
| UC04 | Request classification, customer/order/history context and proposed assignment. | verifiche necessarie | Classification and structured output can use agents. Required context depends on unification in UC06 and actual system coverage. | Confirm access and whether a usable customer view exists; a smaller classification-only pilot would explicitly omit context enrichment. |
| UC05 | Commentary and structured report from prepared BI data; presentations and BI ingestion checked separately. | capability documentate for prepared-data synthesis; verifiche necessarie for full requested outcome | Text/CSV/JSON reading, agents and structured/optional HTML outputs are documented. Consolidated BI data are stated. Native presentation creation/export and actual BI operations need verification. | Obtain a BI export, indicator definitions, historical reports and review rules; establish what existing BI tools already cover. |
| UC06 | Persistent unified customer/order view, cross-system normalization and data-quality improvement. | sviluppo aggiuntivo significativo | Multi-system reconciliation, durable data model, ambiguity handling and ownership are a substantive integration/data project beyond a bounded workflow. Existing tooling might reduce that work. | IDs and match rules, data stewardship, source access, persistence and exception-resolution ownership. |
| UC07 | Tender synthesis and requirements checklist with human validation. | verifiche necessarie | AI-assisted analysis and structured output are supported at primitive level. Mixed Office/PDF ingestion, exhaustive coverage and traceable source locations require checks. | Representative complete document packs, extraction/citations, completeness criteria and a named expert reviewer. |
| UC08 | Source-referenced document answers under access permissions; image product recognition separated. | verifiche necessarie for bounded explicit-source Q&A; sviluppo aggiuntivo significativo provisionally for full cross-system permission-aware retrieval | A KB is not documented as automatic semantic search/RAG. Full archive retrieval, permission propagation and image recognition need separate capability/design checks. | Validate searchable/extractable sources, document access enforcement, freshness and answer evidence; separately validate vision/product-reference data before committing that component. |
| UC09 | Proposed freight-charge discrepancies against shipments and tariffs, before invoice approval. | verifiche necessarie | Workflow can coordinate data and review, but extraction, joins and tariff/exception calculations must be verified and may require custom logic. | Link each charge to shipment and applicable tariff; validate contract exceptions with Logistics/Administration on labeled examples. |
| UC10 | Refreshable sales forecasts and low-rotation analysis at requested granularity. | sviluppo aggiuntivo significativo | Workflow orchestration can schedule a model, but the sheet does not establish a forecasting pipeline, model training or backtesting. Existing BI forecasting should be investigated. | Suitable history, stable product IDs, forecast grain/horizon and time-based comparison against a simple agreed baseline. |

Source for case-specific inputs and outcomes: 02 pp.2-3. Classifications above are judgments about proposed implementation scope. In UC08, full retrieval could move to verifiche necessarie if existing capabilities and permissions are demonstrated. UC09 could move to sviluppo aggiuntivo significativo if integrations/contract logic prove extensive.

## Compare two credible starting paths

### Path A: UC05, reporting from consolidated BI data

Strongest explicit readiness evidence. Start with one report, one approved BI extract and an existing reporting cycle: produce a structured commentary/report draft, preserve every number's lineage, flag missing explanations and require owner review. Keep native PowerPoint/PDF generation as a separate verification, not a built-in promise. (02 p.2; 04 pp.2-3)

Potential measurements: total preparation plus review time, numeric consistency, unsupported commentary and reviewer corrections against a historical cycle. Baselines and thresholds must be gathered/agreed, not invented.

Main counterargument: existing BI may already do most of this. Data readiness alone does not prove meaningful incremental value or satisfy Operations' strongest priority. Check current preparation bottlenecks and existing tool coverage before recommending it.

Potential successor: a bounded UC10 analysis could reuse BI access, reporting structure and some definitions, but sales-grain data/history are not confirmed by UC05. Forecasting would still need distinct data and model validation. Do not claim UC05 prepares order ingestion simply because both use workflows.

### Path B: UC01, reviewed order preparation

Closer to Operations' stated problem. Bound the pilot to one unit, a small agreed order-format set and product family. Produce a structured draft order plus validation/exception evidence for an operator. Proposed initial exclusion: automatic ERP writing. The full client case remains broader, and the value of this narrower output must be confirmed. (02 pp.1-2)

Potential measurements: preparation plus review/re-entry time per order, critical-field correctness, configuration violations caught, and failures/ambiguities correctly surfaced. Include manual handoffs in the comparison.

Main dependency: reliable extraction from real PDFs/documents and explicit product configuration rules. DualOS upload support is not evidence of automatic extraction. A text-prepared trial can isolate reasoning from ingestion, but is not by itself proof of production value. (04 p.3)

Potential successor: UC03 can reuse parts of the product/component master, document-ingestion approach, review/error patterns and verified ERP connection. Supplier-code matching, price semantics, permissions and approval controls remain new work. Reuse is partial, conditional and concrete.

Recommendation for discussion: keep UC05 as the evidence-led reference option; challenge it with UC01's operational relevance and UC03 reuse. Choose UC01 only if order examples, rules, owner availability and the input path can be validated within discovery. Choose UC05 only if the incremental reporting benefit survives comparison with existing tools. Neither is selected yet.

## Five cases to deepen

Proposed set: UC01, UC03, UC05, UC07 and UC09. This compares reporting readiness with operational/document workflows and supports a plausible UC01-to-UC03 sequence. UC02 is a clear initial defer candidate because of AR application/assets. Defer the full UC06 unification program as a first six-week pilot unless existing foundations substantially change the effort. Mention UC04's dependency on UC06 in the all-case table.

## First meeting: five things to establish

Proposed participants: transformation/process sponsor, the relevant Operations process owner and an actual operator, BI/reporting owner, Commercial/Customer Service representative and IT integration/security lead. Adapt attendance to the shortlisted scopes; do not make every business unit a prerequisite.

1. Which result matters most, who will use/own it, and which function has available users to test it?
2. What does the current process look like, including handoffs, volumes, time and costly errors? Ask for real examples.
3. Which inputs, rules, BI exports and system actions are accessible now, and what already works in current tools?
4. Who can authorize data/system access and validate exceptions/results; how much time can they commit?
5. What evidence will count as a useful six-week outcome, and which dependency would cause a scope reduction or stop?

## Roadmap skeleton to tailor after pilot choice

| Window | Observable result | Owner | Condition to proceed |
| --- | --- | --- | --- |
| Week 1 | Agreed process boundary, representative examples, baseline collection plan and documented access/owner checks. | DS leads; FDE and client process/IT owners contribute. | Useful output and feasible input/access path demonstrated; otherwise narrow or switch the pilot. |
| Week 2 | Validated input path and first reviewed output from real or safely prepared examples; list of critical failure types. | FDE with process expert; DS validates relevance. | Inputs are usable and expected output/acceptance rules are agreed. |
| Weeks 3-4 | Versioned bounded workflow, evidence-linked outputs and human review operating on representative cases. | FDE builds/verifies; process owner checks; DS resolves scope and adoption. | Critical errors are surfaced and review does not erase the benefit; verify permissions before real actions. |
| Week 5 | Small supervised user trial, comparable end-to-end timings and correction/error evidence. | Client operators/process owner with DS; FDE monitors and fixes. | Reviewers can use the result safely and measured quality/value meets agreed criteria. |
| Week 6 | Pilot readout with evidence, remaining limitations, operational owner and continue/change/stop decision. | DS plus sponsor; FDE provides technical evidence. | Extend only if benefit, quality and maintainability are supported; otherwise revise or stop. |

These are planning hypotheses contingent on access and availability, not committed delivery dates. More specific thresholds should come from discovery. Do not use readiness status alone as proof of functional quality. (04 p.5)

## Technical details that should affect the proposal

- PDF/Office upload does not establish extraction, OCR or RAG. (04 p.3)
- Catalog actions, authorized account and per-step connection binding are three separate checks. (04 p.4)
- An agent instruction not to write does not replace restricted tools/accounts. Draft tests can perform real actions. (04 pp.2-3)
- Named Approvers are metadata, not an enforced exclusive approval list. Do not promise segregation of duties from that field. (04 p.4)
- Public result links allow unauthenticated access; they are distinct from team-visible resources, and individual link revocation is not documented. (04 p.4)
- Run history supports inspection; Tests is not a documented automated assertion/eval framework. Define representative quality checks separately. (04 p.5)
- Cancelling a run does not reverse external effects. Plan duplicate prevention, exception handling and recovery before writes. (04 p.5)

Use only the details material to the selected pilot in the final document; avoid turning it into a platform audit.

## Proposed working sequence and effort budget

1. Source review and requirements: 35 minutes.
2. Discuss UC05 versus UC01; finalize ten-case classification and five deeper rows: 50 minutes.
3. Pilot, discovery questions and milestone gates: 45 minutes.
4. Gather two real candidate episodes and draft the 4-5 page document plus appendix: 60 minutes.
5. Source/requirement review and ten-minute video outline/rehearsal/recording: 65 minutes.
6. Export relevant assignment sessions raw at the end, check the delivery requirement, verify files/video accessibility and package: 15 minutes. Do not maintain a separate AI work log.

Total proposed budget: 270 minutes (4.5 hours), including the video. These are targets, not actual elapsed effort. Update remaining budget based on candidate time already spent.

User-confirmed schedule: target Monday 12 October 2026, absolute final deadline Wednesday 14 October 2026 (Europe/Rome).

## Proposed final document shape

- Page 1: brief client reply, participants, up to five questions and decision framing.
- Page 2: recommended pilot, second case/defer rationale and six-field pilot summary.
- Page 3: six-week milestones, observable outputs, owners and gates.
- Page 4: two verified professional episodes.
- Page 5 if needed: compact trade-offs, dependencies and change/stop criteria; avoid duplicating page 2.
- Appendix: ten-case classification and five-case deep dive with exact required columns.

Draft in Italian unless the candidate prefers another language: all supplied materials and the simulated client exchange are Italian. Candidate experience details, preferred pilot and actual time spent remain open.
