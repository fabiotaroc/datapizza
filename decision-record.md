# Decision record

## 2026-10-10 — Boundary between verification and significant development

**Decision:** initially classify uncertain or undocumented components as **verifiche necessarie**. Use **sviluppo aggiuntivo significativo** when substantial additional work can be identified for the assessed scope.

**Alternative considered:** classify undocumented components as significant development from the outset. Rejected because missing documentation does not establish that a capability is unavailable or requires substantial custom work.

**Consequence:** reassess after checking existing support and client conditions; distinguish components within mixed cases. This does not select a pilot or guarantee feasibility.

## 2026-10-11 — Include ERP insertion in UC01's assessed scope

**Decision:** assess UC01 through workflow-driven ERP insertion, including extraction and configuration checks. Human control was left open at this point; the subsequent decision below resolves it.

**Alternative considered:** assess preparation of a structured, checked order, with ERP insertion outside the core scope. Rejected because the reference to ERP access and writing is interpreted as an intended part of the actual workflow.

**Condition:** confirm this scope with the client and verify the specific ERP write action. Consider integration reuse for UC03, while checking price-update actions separately; no pilot or successor is selected.

## 2026-10-11 — UC01 classification and first-version review

**Decision:** classify UC01 as **verifiche necessarie**, with human approval of every order before workflow-driven ERP insertion in the first version.

**Alternatives considered:** documented support for the whole case is not established; significant development is not yet demonstrated. Exception-only review is deferred until quality is demonstrated because extraction, configuration validation and ERP writing remain to be verified.

**Condition:** verify functional quality, ERP access/actions and enforcement of the approval control. Reconsider review scope based on evidence; this does not select UC01 as the pilot.

## 2026-10-11 — UC02 full AR scope and classification

**Decision:** classify the full interactive AR configuration experience as **sviluppo aggiuntivo significativo**.

**Alternative considered:** classify the whole case as **verifiche necessarie**. Rejected because the scope entails a dedicated AR interface, rendering and configuration-to-3D logic beyond the documented workflow/result-page capabilities.

**Condition:** check suitable 3D assets and existing configurators/AR solutions; these could reduce the additional work and change the classification. Product/configuration data may be reusable from UC01, subject to checks; no pilot priority is selected.

## 2026-10-11 — UC03 classification and review before ERP updates

**Decision:** classify the workflow through ERP price updates as **verifiche necessarie**. Initially mark proposed changes as apparently valid or uncertain using exact mappings/rules where possible and AI for interpretation. In the first version, a person reviews both groups and approves the batch before writing.

**Alternatives considered:** review only ambiguous matches, as the source minimally requires, versus reviewing all proposed changes. Choose all initially because extraction and matching reliability are unverified; confidently wrong changes could escape exception-only review. Neither full documented support nor substantial additional development is established yet.

**Condition:** inspect representative supplier formats, validate mappings and price interpretation, and verify ERP update actions and approval enforcement. Reconsider exception-only review after demonstrated quality. UC01 integration reuse remains conditional; no successor is selected.

## 2026-10-11 — UC04 full context and UC06 dependency

**Decision:** classify UC04 as **verifiche necessarie**, retaining classification, customer/order/history context and suggested assignment, with the final decision left to the operator. Make the unified customer profile dependency on UC06 explicit.

**Alternative considered:** reduce the assessed scope to classification alone. Rejected because it would omit the context required in the stated outcome.

**Condition:** verify a usable unified profile, history coverage, access and routing rules. If the profile must be built, assess that work under UC06 and reflect its effect on UC04 readiness. No pilot is selected.

## 2026-10-11 — UC05 component classification and full reporting scope

**Decision:** retain reports and presentations. Classify synthesis and structured/HTML reporting from prepared data as **capability documentate**, with BI access/export and required final formats, including presentations, as **verifiche necessarie**.

**Alternatives considered:** treat the full case as documented, or narrow it to commentary/HTML alone. Reject both: final-format support remains unverified, while narrowing would omit requested presentations.

**Condition:** verify exports, definitions, historical references, commentary/quality rules and output formats. Check existing tool coverage and remaining manual work before inferring value. Potential UC10 reuse does not establish forecast-data readiness or select a successor.

## 2026-10-11 — UC06 full reconciliation scope and classification

**Decision:** classify UC06's unified customer/order view, flow normalization and data-quality work as **sviluppo aggiuntivo significativo**.

**Alternative considered:** treat the full scope as verification/configuration alone. Rejected because the shared data model, cross-system reconciliation, ambiguity resolution and ownership require identifiable design and integration work.

**Condition:** inspect existing mappings, matching rules and data-management tools; these may reduce effort and change the assessment. UC04 depends on the resulting usable profile. No pilot or implementation architecture is selected.

## 2026-10-11 — UC07 completeness and source traceability

**Decision:** classify tender analysis and its requirements checklist as **verifiche necessarie**, with source traceability and expert completeness review as the main conditions.

**Alternatives considered:** treat generic AI synthesis support as evidence that the whole case is documented, or accept a plausible summary without checking omissions. Rejected because extraction and full requirement coverage are unverified, and an omitted requirement is the main proposed failure to control.

**Condition:** check representative complete packs, reference each item to its source, flag unreadable/incomplete material and have an expert verify extracted requirements and omissions against originals. Shared ingestion components require format/layout checks.

## 2026-10-11 — UC08 full scope with separate component checks

**Decision:** retain document Q&A with source references/access permissions and product recognition from images. Initially classify both components as **verifiche necessarie**.

**Alternatives considered:** the initial brainstorming classified full cross-system retrieval provisionally as significant development; a narrower document-only scope would omit image recognition. Reject these as the starting assessment because support remains uncertain and the full requested scope should be preserved.

**Condition:** verify retrieval/extraction, source accuracy and freshness, access enforcement and recognition against known products. Reclassify if substantial retrieval, permission-control or recognition development is identified. Document-processing/source-reference reuse from UC07 is conditional.

## 2026-10-11 — UC09 tariff checks and unverifiable cases

**Decision:** classify UC09 as **verifiche necessarie**. Use explicit rules/calculations for defined tariffs and AI for extraction/clause interpretation, with resulting rules validated by the business. Flag insufficient inputs as cannot verify; findings are examined by people before invoice approval.

**Alternatives considered:** infer successful verification from absence of anomalies, or assume generic workflow support proves tariff control. Rejected because missing links or tariff exceptions can prevent a valid comparison.

**Condition:** validate charge-to-shipment/tariff links and exceptions on representative inputs. Extensive integration or tariff logic may warrant significant development. UC03/UC07 component reuse remains conditional.

## 2026-10-11 — Separate UC10a forecasting from UC10b historical analysis

**Decision:** assess UC10a (refreshable forecasts) as **sviluppo aggiuntivo significativo** and UC10b (historical/low-rotation analysis) as **verifiche necessarie**, retaining both outcomes.

**Alternative considered:** assign one class to the whole case. Rejected because forecasting requires a validated, repeatable forecasting process, while historical analysis has different data, definition and calculation checks; synthesis/reporting from prepared results are documented.

**Condition:** verify usable history, consistent identifiers, horizon/granularity and low-rotation definitions. Evaluate forecasts on later historical periods against a simple agreed baseline. Existing BI forecasting may reduce development and change UC10a's assessment; UC05 data readiness is not sufficient evidence.

## 2026-10-11 — Five-case shortlist for deeper comparison

**Decision:** deepen UC01, UC05, UC04, UC03 and UC09, the five highest totals in the provisional weighted matrix. Together they compare Operations' core order workflow, management reporting with stronger data-readiness evidence, Commercial's service priority, a concrete operational reuse candidate and financial control.

**Alternatives considered:** UC07 could be material if tenders drive substantial business, but that importance is unconfirmed and its email-agenda alignment is weaker. UC10 has strategic planning potential but identifiable forecasting work and less immediate business verification; UC02 has direct sales-experience alignment but dedicated AR work and unproven commercial benefit. UC06 is an important UC04 dependency with broader reconciliation work; UC08 lacks a defined priority workflow/owner and needs separate retrieval, permission and image checks.

**Condition:** this selects comparison candidates, not a pilot or implementation sequence. Baselines, sponsor authority, inputs/access and user availability can change the ranking. In particular, investigate UC04's UC06 dependency and UC05's incremental benefit beyond existing BI before committing.

## 2026-10-11 — UC01 primary value measure

**Decision:** make time reduction the primary UC01 outcome, with accuracy as a quality requirement. Include human review, corrections and ERP insertion in the time comparison.

**Alternative considered:** give error reduction equal priority or make it the primary outcome. Not chosen because the user favors time reduction as the main benefit while retaining a quality requirement.

**Condition:** collect a representative current-process baseline and establish net benefit after review. The user's >95% accuracy example is not yet a defined acceptance criterion; its denominator, critical fields and threshold remain to be agreed. The previously approved human approval before every ERP write still applies; no pilot is selected.

## 2026-10-11 — UC01 order-level quality criterion

**Decision:** approve the UC01 comparison row and propose >95% correct draft orders before human correction: every critical field and configuration-check outcome must be correct for an order to count as correct. Include failed/incomplete outputs in the evaluation. Maintain approval of each order's final data before ERP writing.

**Alternative considered:** average correctness across individual fields. Rejected because it can conceal critical errors within orders. Human approval prevents unapproved writes when enforced, but does not guarantee that every approved order is correct.

**Condition:** this resolves the earlier open accuracy definition as our proposal, not client acceptance or measured performance. Agree critical fields/reference answers and validate the threshold with the process owner; verify approval enforcement. No pilot is selected.

## 2026-10-11 — UC05 value and quality approach

**Decision:** make total reporting-cycle preparation time the primary UC05 outcome, including report/presentation assembly, review and corrections. Require numerical reconciliation to approved BI data/calculation rules, evidence-supported commentary with hypotheses identified, and reporting-owner approval before circulation. Assess additional benefit over existing BI tools.

**Alternative considered:** a generic accuracy percentage or treating management visibility/data readiness as sufficient proof of value. Not chosen: numerical correctness and commentary usefulness require distinct measures, while existing tools may already meet much of the need.

**Condition:** the user authorized proposing specific numerical targets; those targets are in draft.md for review and client validation, not measured results. Baseline, exports, final formats and reviewer availability remain checks. No pilot is selected.

## 2026-10-11 — Numerical value targets for UC01 and UC05

**Decision:** retain UC05's proposed targets and add a matching **≥30% time-reduction target** to UC01, including review, corrections and ERP insertion; retain UC01's >95% correct-order requirement. UC05 targets are ≥30% lower total preparation time, 100% numerical reconciliation, ≥90% commentary acceptance without substantive edits, zero unsupported causal assertions in circulated outputs and owner approval of every output, initially compared on at least three historical packs.

**Alternative considered:** leave UC01's time benefit unquantified while specifying UC05's. Not chosen because a numerical acceptance proposal makes both primary outcomes assessable.

**Condition:** all thresholds are proposed targets, not measured results or client commitments. Validate them against representative baselines and required quality; a common time percentage does not establish equal business value. No pilot is selected.

## 2026-10-11 — UC04 preparation-time outcome and quality targets

**Decision:** propose ≥30% less operator time to reconstruct context, classify and prepare assignment, including review/corrections; ≥95% of requests with both classification and proposed team correct before human correction; zero incorrect customer/order associations in evaluated cases; final assignment decisions remain with the operator in 100% of cases.

**Alternative considered:** use resolution time or customer retention as the primary outcome. Not chosen because UC04 directly prepares/classifies/assigns requests; those downstream outcomes require separate causal evidence.

**Condition:** validate targets against representative historical requests and expert reference answers. Retain the full context scope: verify a usable unified profile and history; if the profile must be built, assess UC06 work before committing. Thresholds are proposed acceptance criteria, not measured performance or guarantees. No pilot is selected.

## 2026-10-11 — UC03 quality and distinction between measures and controls

**Decision:** retain time reduction as UC03's primary outcome; propose ≥98% correct article/price update rows before human correction and detection of 100% of known ambiguous/unmatched rows in evaluated examples. Keep full initial review and batch approval before ERP writing as method controls, not performance measures. Apply the same distinction to UC04's final operator assignment and other human approval controls.

**Alternative considered:** list the percentage of human-approved actions alongside business/quality measures. Rejected because approval is a required characteristic of the method and does not itself demonstrate business value or correct output.

**Condition:** the earlier common ≥30% time targets are superseded by the user's instruction to propose more ambitious, differentiated targets; revised numerical proposals are in draft.md pending review/client validation. Preserve the earlier decisions as history. Baselines, mappings, price interpretation, ERP actions and approval enforcement remain checks; no pilot is selected.

## 2026-10-11 — Differentiated time-reduction targets

**Decision:** adopt proposed reductions of ≥50% for UC01, ≥60% for UC05, ≥40% for UC04 and ≥55% for UC03, measured on comparable work and including review/corrections and the required final output/action. Retain their agreed quality criteria and human controls.

**Alternative considered:** the earlier common ≥30% threshold. Superseded in favor of more ambitious, differentiated targets appropriate to the proposed workflows.

**Condition:** these are chosen acceptance proposals, not forecasts, measured savings or client commitments. Validate against process baselines, reviewer effort, input quality and verified output/integration paths. Earlier target decisions remain as history; no pilot is selected.

## 2026-10-11 — UC09 checking-time, quality and financial measures

**Decision:** propose ≥45% less total checking time including investigation, review and corrections; detection of ≥95% of known anomalies where evidence is sufficient; ≥90% of anomaly alerts confirmed genuine; identification of 100% of known insufficient-evidence cases in evaluation. Track confirmed unjustified charges in euros separately from actual invoice corrections obtained. Human examination before approval is a method control.

**Alternative considered:** invent a monetary savings percentage or count identified charges as realized savings. Not chosen because freight expenditure, overcharge prevalence and actual corrections are unknown; quality also requires both missed-anomaly and false-alert measures.

**Condition:** validate proposed criteria on representative historical prefactures with expert labels for anomalies, valid charges and unverifiable cases. Check charge/shipment/tariff links and contractual exceptions. Insufficient evidence must not produce a conforming result. No pilot is selected.

## 2026-10-11 — UC01 pilot, UC03 successor and UC05 alternative

**Decision:** choose UC01 as the proposed first pilot and UC03 as the proposed second case, conditional on useful results and verified reuse. If UC01 as a whole proves infeasible, choose UC05 as the next candidate from the decision matrix, subject to its own feasibility and incremental-value checks.

**Alternatives considered:** start with UC05 because its reporting data are consolidated. Not chosen initially because UC01 directly addresses Operations' core order process and offers concrete potential reuse toward UC03. UC05's higher screening position than UC03 does not determine the successor: that choice considers actual reuse from UC01.

**Condition:** verify net benefit, representative inputs/rules, ERP actions, approval enforcement and client availability. UC03 reuse depends on shared ERP access, relevant master data, compatible extraction components and workflow controls; supplier mappings, price rules and the ERP update action need separate work. Retaining a reduced UC01 scope if automated ERP insertion is blocked remains under discussion; no manual/import fallback is approved yet. If UC05 replaces UC01, reassess the successor and its reuse rationale.

## 2026-10-11 — Defer UC02

**Decision:** defer the full AR configuration experience in UC02, given identifiable dedicated interface/rendering work, unverified 3D assets and unproven commercial benefit within the initial planning horizon.

**Alternative considered:** prioritize UC02 for its direct alignment with the sales-experience request. Not chosen because the additional work and asset dependencies make a first verifiable use less credible than the proposed UC01 route on current evidence.

**Condition:** reconsider if existing configurator/AR components, suitable assets and validated commercial priority materially reduce the work or change the business trade-off.

## 2026-10-11 — UC01 ERP insertion fallback

**Decision:** prefer human approval followed by automated ERP insertion. If that path is blocked, first check an existing ERP file-import route. If neither is feasible, retain extraction and configuration checks with manual field entry only if the complete process still delivers an agreed net benefit. Explicitly narrow the pilot scope and revisit the proposed ≥50% time-reduction target with the client. Choose UC05 if no useful, feasible UC01 scope remains.

**Alternatives considered:** abandon UC01 whenever automated writing is unavailable, or retain it regardless of the remaining manual work. Neither is chosen: extraction and checks may still be valuable, but review and field entry can absorb the savings. A button invoking a script remains automated insertion and still requires a verified ERP write path.

**Condition:** no ERP write/import route is confirmed by the supplied material. Verify with IT/FDE and the process owner; include review, corrections, import handling or manual field entry in the time comparison. Preserve human review before insertion and the order-level quality requirement. If the write integration is not built, remove it from the claimed UC03 reuse and reassess the successor's effort. This resolves the fallback question left open in the pilot-selection entry; the full UC01 scope remains preferred.

## 2026-10-11 — UC01 bounded pilot scope

**Decision:** start with one operating unit and one ERP environment, covering a coherent product family or bounded set of products/configurations and selected incoming document formats. Produce structured orders with configuration-check results and missing/ambiguous information for order-processing operators to review/correct before insertion through the agreed route.

**Alternatives considered:** cover all units/ERPs, or retain broader product coverage while limiting only document formats. Not chosen because both leave more system or configuration complexity in the initial pilot; the chosen boundary permits verification of the complete workflow within a manageable context.

**Condition:** select the exact unit, products and formats with Operations during discovery, using meaningful volume, clear enough rules and representative variation. Keep missing data, invalid configurations and extraction failures within the selected scope in the evaluation. Other orders retain the existing process; group-wide rollout, universal format coverage and insertion without human approval are excluded initially. The ERP fallback decision remains applicable.

## 2026-10-11 — UC01 discovery inputs and readiness dependencies

**Decision:** begin discovery with historical original emails/attachments and checked ERP orders supplied by Operations while IT/FDE investigate ERP access in parallel. Require representative examples and expert-validated reference answers, applicable configuration rules and relevant current reference data, verified ERP fields/mappings/permissions and an agreed insertion route, plus a process owner and available reviewers. Gather baseline volumes, working time and corrections through process observation.

**Alternatives considered:** wait for a live mailbox connection before assessing inputs, or require company-wide master-data cleanup first. Neither is chosen: supplied historical files permit early assessment, and the bounded pilot needs reliable references for its selected rules rather than a complete group-wide data program.

**Condition:** include incomplete, ambiguous and invalid examples. Product/component master data are required where needed for the selected checks, not assumed universally necessary. Before configuring the pilot workflow, confirm sufficient examples, rules/reference answers, the insertion route and reviewer availability; verify approval enforcement before automated writing. Live intake, if used, needs separate access/trigger checks. No client inputs or access are assumed ready.

## 2026-10-11 — UC01 implementation approach and guardrails

**Decision:** use AI for order extraction/interpretation, explicit business rules for configuration checks wherever clearly expressible, and a controlled workflow action for ERP insertion after approval of the final corrected data. Configure documented agents, structured outputs, workflow branches, approval waits and execution traces. Use the term **guardrails** for required-field/format validation, explicit configuration checks, routing missing/ambiguous information to human review, restricted action permissions and enforced approval before writing.

**Alternatives considered:** rely on AI judgment alone for clearly defined configuration rules, or allow the interpretation agent to write independently of the approval path. Not chosen because explicit checks are easier to explain/verify and insertion must remain tied to approved final data.

**Condition:** verify extraction for selected formats, rule execution, correction/approval behavior and exact ERP actions/permissions; live intake needs separate checks. Assess conversion/OCR, rule-execution or ERP integration components only where existing support is insufficient, making actual effort visible before accepting it in the pilot. Retain **verifiche necessarie**, revising if substantial additional development is identified, and use the agreed insertion fallback where appropriate. Guardrails are controls to configure and verify, not a documented turnkey package or a guarantee of correctness; approval names alone do not enforce an exclusive approver list.

## 2026-10-11 — UC01 value/quality verification and separate evaluation examples

**Decision:** retain the proposed ≥50% reduction in average order-processing working time, including review, corrections and ERP insertion, and >95% correct draft orders before human correction, requiring all critical fields and configuration-check outcomes to be correct. Reserve representative orders for final evaluation separately from examples used to configure/refine the workflow: a train–test split analogy for workflow development, not a requirement to train a model.

**Alternative considered:** evaluate only on examples already used during configuration. Not chosen because that can overstate behavior on new orders.

**Condition:** agree evaluation size/coverage, critical fields and expert reference answers with the process owner. Include failed/incomplete outputs and missing/ambiguous data or invalid configurations; correctly identifying an invalid configuration is a correct check outcome. Gather the current-process baseline through observation on comparable work. Revisit the time target with the client if using the manual-entry fallback. Targets remain acceptance proposals, not measured results or commitments; guardrails remain method controls. If evaluation examples are subsequently used for refinement, use new independent examples for the next final assessment.

## 2026-10-11 — UC01 responsibilities and acceptance

**Decision:** DS leads scope, outcomes/criteria, stakeholder coordination, baseline/adoption and roadmap; FDE configures and maintains the solution, integrations, technical checks and guardrails. The client order-process owner validates rules/reference answers, provides reviewers and accepts business usefulness/quality; operators demonstrate/evaluate the process and correct/approve orders. Client IT/ERP owner enables authorized access and validates mappings, permissions, insertion routes and release conditions. The transformation/process contact convenes functions and helps resolve priorities/resources, identifying the authorized decision-maker for scope changes and extension.

**Rationale:** business acceptance belongs with the process owner, while IT/FDE verify technical release conditions. DS brings both sets of evidence to the continuation decision with the authorized client decision-maker; neither technical readiness alone nor the contact's convening role establishes business acceptance or decision authority.

**Condition:** confirm named owners, availability and authority in discovery. DS/FDE collaboration continues across discovery, verification and adoption; the allocation does not assume client resources are already committed.

## 2026-10-11 — UC01 controls, recovery and change/stop conditions

**Decision:** review every order; resolve critical missing/ambiguous information and invalid configurations before insertion, otherwise use the existing process. Bind approval to the final corrected data and require renewed approval after changes. Verify duplicate prevention; after uncertain ERP write outcomes, check whether the order exists before retrying. Investigate errors/feedback and reassess revisions on independent examples. Revise scope/approach before extension if agreed quality or time criteria are unmet.

**Alternatives considered:** abandon UC01 entirely when automated writing cannot be controlled, versus suspend writing and retain useful assisted preparation through the agreed fallback. Choose the latter where preparation remains useful; move to UC05 if no useful, feasible UC01 scope remains. Blind retries after uncertain writes are rejected because they can create duplicate orders.

**Condition:** suspend automated writing if approval can be bypassed or write outcomes cannot be controlled. FDE and responsible operators investigate/reconcile errors, with IT where needed. Verify enforcement rather than relying on descriptive Approvers names; agree a safe ERP write-testing arrangement because draft tests perform real actions. Cancelling a run does not undo accepted ERP writes. These are proposed controls/recovery behavior to verify, not automatic platform guarantees.

## 2026-10-11 — Six-week roadmap and release gates

**Decision:** plan discovery/scope/baseline in week 1; feasibility and selection of the complete insertion route by end of week 2; candidate workflow with verified guardrails in week 3; independent evaluation and conditional release in week 4; controlled real use in week 5; consolidated evidence, continuation/support decision and UC03 reuse assessment in week 6. Meet agreed value/quality criteria and control requirements before operational use. Week 6 does not promise delivery of UC03.

**Alternatives considered:** allow ERP-route investigation to run longer without changing the live-use dates, or start a supervised operational trial while still below agreed criteria. Not chosen because early route selection preserves time for complete-process verification/real use, and the release gate preserves the accepted quality/value and control boundary.

**Condition:** weeks run from discovery and depend on agreed capacity, client inputs/access and reviewer availability. Replan scope/dates when dependencies slip; include manual entry in benefit measurement and agree any revised target before evaluation. If no useful UC01 scope remains, verify UC05 dependencies and replan remaining time rather than assuming the original deadline holds. Insufficient live evidence means continued bounded evaluation; extension requires accepted evidence, controlled operation and committed resources. Preserve safe historical testing, every-order approval and the previously agreed suspension/recovery conditions.
