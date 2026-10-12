# Working draft

Concise working notes for [plan.md](plan.md). We discuss choices before drafting; the submission document is filled only when explicitly requested.

## 1. Reading the client's request

*Reviewed together.*

### Core request

An industrial group with configurable products and multiple operating units wants help choosing where to start with DualOS. It asks for a first meeting, including whom to involve and what information to prepare. The objective is a **first verifiable use within six weeks, if conditions permit**, with initial work that can help subsequent initiatives. (02, p.1)

### Priorities

- **Operations:** reduce data-entry and checking work.
- **Commercial:** improve customer service and the sales experience.
- **IT:** understand the systems involved and the effort required.

The source gives these priorities no ranking and describes no actual disagreement. The transformation/process contact can convene the relevant functions, but their responsibilities and availability still need agreement. (02, p.1)

### Constraints and missing information

- **Readiness:** listed inputs and systems are requirements, not confirmation that data, access or integrations are ready. UC05 is the explicit exception for consolidated reporting data; access/export and existing tool coverage still need checking. (02, pp.1-2)
- **Value:** volumes, processing times and error rates are unknown, so there is no basis yet for quantified savings or a confident business ranking. (02, p.1)
- **Resources:** budget and team availability are unknown. Six weeks is a conditional planning horizon. (02, p.1; 01, p.2)
- **Reuse:** the client wants the first initiative to help later ones; what can actually be reused depends on the cases selected. (02, p.1)

### Working interpretation and questions to resolve

We need to identify a useful starting process, establish its feasibility and agree how users will verify the result. Our proposed meaning of “verifiable use” is an output used and assessed by the intended users; the client has not defined acceptance criteria yet.

Before confirming a pilot, clarify:

1. Which outcome takes priority, who decides, and who will use/review the result?
2. What do real examples show about the current work, errors, usable inputs and necessary system access?
3. What evidence would count as a useful six-week result, and what later case could benefit from it?

These are working questions, to refine after the case analysis. No pilot or technical approach has been selected.

Sources: **02** = `source-material/02-caso-aziendale.pdf`; **01** = `source-material/01-prova-asincrona.pdf`.

## 2. DualOS: support and technical boundaries

*Reviewed together; classification boundary approved.*

**Roles:** DS leads priorities, expected value, adoption and roadmap; FDE designs integrations/workflows, verifies behavior and maintains the solution. Discovery is shared; the client contributes examples, access and people. (03, p.1)

| Documented support | Checks still needed |
| --- | --- |
| Agents; workflow conditions, loops, parallel steps; scheduled and supported event triggers. | Exact provider actions/events, client permissions and configuration. (04, pp.2-4) |
| Text/CSV/JSON reading; structured outputs; optional HTML result pages. | PDF/Office extraction, OCR, semantic search/RAG and native presentation generation. (04, pp.2-3, 5) |
| Human approval waits; versioned deployment; execution traces. | Enforced approval responsibilities, functional quality and recovery after external writes. (04, pp.2, 4-5) |

**Important distinctions:** the Knowledge Base is not automatically read; named Approvers do not enforce an exclusive approval list; Tests records executions rather than providing documented automated quality assertions. Draft tests can perform real actions, and cancelling a run does not undo external writes. (04, pp.2-5)

**Approved classification rule:**

- **capability documentate:** the assessed component is supported by the technical reference; client data, access and configuration still require checks.
- **verifiche necessarie:** specific support or suitability remains uncertain, including undocumented extraction or connector actions. Missing documentation alone is not evidence of unavailability.
- **sviluppo aggiuntivo significativo:** we can identify substantial extra work for the assessed scope, such as a dedicated AR interface or a new reconciliation pipeline. Existing components may change that assessment.

Split mixed components explicitly when assessing each case. (01, p.1; 04, pp.1, 5)

Sources: **03** = `source-material/03-guida-essenziale-dualos.pdf`; **04** = `source-material/04-capabilities-dualos.pdf`.

## 3. Case classification

Approved rows: 10 of 10. UC10a and UC10b identify the two components of the original UC10 case.

| ID | perimetro valutato | classe tecnica | motivazione | condizione principale |
| --- | --- | --- | --- | --- |
| UC01 | Estrazione dei dati d'ordine, controllo della configurazione e inserimento nell'ERP tramite workflow; nella prima versione, approvazione umana di ogni ordine prima della scrittura. | verifiche necessarie | Workflow e output strutturati sono documentati; estrazione dai documenti reali, applicazione delle regole e specifica azione di creazione nell'ERP richiedono verifica. | Esempi rappresentativi, regole concordate con il business, percorso di scrittura ERP verificato per campi e permessi e controllo dell'approvazione. |
| UC02 | Configurazione interattiva di varianti, materiali e finiture con visualizzazione del prodotto in realtà aumentata nell'ambiente del cliente, in tempo reale. | sviluppo aggiuntivo significativo | Il perimetro richiede interfaccia AR, rendering e logica di collegamento tra configurazioni e modelli 3D, oltre ai workflow e alle pagine di risultato documentati. | Verificare regole, asset 3D adeguati, requisiti d'uso in vendita ed eventuali configuratori/soluzioni AR esistenti che riducano il lavoro aggiuntivo. |
| UC03 | Estrazione dei listini, corrispondenza dei codici fornitore con gli articoli, proposta delle variazioni e applicazione nell'ERP. Prima valutazione delle modifiche come apparentemente valide o incerte; nella prima versione, revisione di entrambe e approvazione del lotto prima della scrittura. | verifiche necessarie | Output strutturati e attese di approvazione sono documentati; estrazione, corrispondenze, interpretazione dei prezzi e specifica azione ERP restano da verificare. | Listini rappresentativi della varietà dei fornitori, mappature affidabili, regole di validazione e percorso verificato di approvazione/aggiornamento ERP. |
| UC04 | Classificazione delle richieste, ricostruzione del contesto cliente/ordini/interazioni e proposta del team assegnatario; decisione finale all'operatore. La costruzione del profilo unificato è trattata in UC06. | verifiche necessarie | Agenti e workflow sostengono l'approccio; recupero del contesto corretto, copertura dello storico e regole di instradamento richiedono verifica. Il profilo unificato necessario è oggetto di UC06. | Profilo cliente unificato utilizzabile, accessi verificati a ordini e storico, regole concordate di assegnazione e verifica dell'operatore. Se il profilo deve essere costruito, UC06 condiziona l'avvio del perimetro completo. |
| UC05 | Report e presentazioni periodiche con indicatori, sintesi e commenti: distinguere elaborazione di dati BI preparati da accesso/esportazione e produzione nei formati richiesti. | capability documentate (sintesi e report strutturato/HTML da dati preparati); verifiche necessarie (accesso BI e formati finali, incluse presentazioni) | Analisi assistita, lettura testuale/CSV/JSON e output strutturato/HTML sono documentati. Dati aggregati e indicatori sono già consolidati; accessi, esportazione e generazione delle presentazioni restano da verificare. | Export BI utilizzabile, definizioni degli indicatori, struttura e riferimenti storici, regole di commento e verifica della coerenza numerica; accertare formati richiesti e copertura degli strumenti esistenti. |
| UC06 | Vista cliente unificata collegata agli ordini, normalizzazione dei flussi tra CRM/ERP delle unità operative e miglioramento della qualità dei dati. | sviluppo aggiuntivo significativo | Il perimetro richiede modello condiviso cliente/ordini, regole di riconciliazione, gestione delle ambiguità e integrazione dei flussi; l'orchestrazione non risolve da sola queste attività. | Accessi ai sistemi, identificativi e relazioni verificati, regole e responsabilità concordate tra unità; valutare mappature e strumenti esistenti che possano ridurre lo sviluppo e cambiare la classificazione. |
| UC07 | Sintesi strutturata della gara e checklist di requisiti, scadenze, allegati obbligatori e rischi, con riferimenti alle fonti e validazione umana della completezza. | verifiche necessarie | Analisi AI e output strutturati sono documentati; estrazione da PDF/Word/Excel, copertura del fascicolo e tracciabilità dei requisiti restano da verificare. Il rischio principale è omettere un requisito. | Fascicoli rappresentativi e completi, riferimenti a file/pagina o foglio, segnalazione dei materiali illeggibili/incompleti e verifica esperta delle estrazioni e delle omissioni rispetto agli originali. |
| UC08 | Risposte sulla conoscenza aziendale con fonti e rispetto dei permessi; riconoscimento dei prodotti da immagini valutato come componente distinto. | verifiche necessarie | Libreria documentale e analisi assistita non attestano ricerca semantica/RAG automatici. Recupero tra fonti, estrazione, applicazione dei permessi e riconoscimento da immagini richiedono verifiche specifiche; la mancata documentazione non dimostra la necessità di sviluppo significativo. | Fonti accessibili e aggiornate, risposte verificabili tramite riferimenti, rispetto dei permessi dimostrato e riconoscimento testato su immagini di prodotti noti. Rivalutare se occorre sviluppo sostanziale di recupero, controllo degli accessi o riconoscimento. |
| UC09 | Collegamento degli addebiti a spedizioni e tariffe, controllo di scostamenti/difformità/eccezioni ed elenco delle anomalie e dei casi non verificabili per esame umano prima dell'approvazione della fattura. | verifiche necessarie | Workflow e output strutturati sono documentati; estrazione, collegamenti e calcoli tariffari richiedono verifica. Regole/calcoli espliciti per tariffe definite, AI per estrazione e interpretazione delle clausole con regole validate dal business. | Prefatture, spedizioni e contratti rappresentativi, collegamenti affidabili e tariffe/eccezioni validate. Dati insufficienti producono uno stato non verificabile; integrazioni o logiche estese possono cambiare la classificazione. |
| UC10 | UC10a: previsioni aggiornabili per prodotto, variante, mercato e periodo; UC10b: analisi storica, inclusi i prodotti a bassa rotazione. | UC10a: sviluppo aggiuntivo significativo; UC10b: verifiche necessarie | UC10a richiede preparazione dello storico, selezione/validazione del metodo e aggiornamenti ripetibili, salvo soluzioni esistenti riutilizzabili. UC10b richiede definizioni, dati e calcoli verificati; sintesi/reporting da risultati preparati sono documentati. | Storico utilizzabile, identificativi coerenti, granularità/orizzonte e definizione di bassa rotazione concordati. Verificare le previsioni su periodi storici successivi a quelli usati per costruirle e confrontarle con una baseline semplice; controllare eventuali strumenti BI di forecasting esistenti. |

**UC01 scope assumption:** ERP insertion is our approved interpretation of the access/write requirement, to confirm with the client. Exception-only review can be reconsidered after quality is demonstrated; it is not the initial control. (02, p.2; 04, pp.2-5)

**Potential UC01 → UC03 reuse:** ERP integration setup, some product/component data, document-processing components and approval/error-handling patterns. Order creation and supplier-price updates remain distinct actions with separate field, permission and business-rule checks; reuse also depends on whether the cases use the same ERP instance and input formats. No successor has been selected. (02, p.2; 04, p.4; reuse is a hypothesis)

**UC02:** assess the full AR experience; existing solutions/assets may change the development assessment. Product data and configuration rules may be shared with UC01; AR assets and interaction require separate assessment. (02, p.2; 04, p.2; reuse is a hypothesis)

**UC03:** use exact code mappings and explicit validation rules where possible, with AI for document interpretation and uncertain matches. Passing checks means apparently valid, not proven correct. Inspect supplier count and format variation, document structure and any handwriting in representative samples; these input properties are not established yet. Review every proposed change before approving the batch; exception-only review can be reconsidered after quality is demonstrated. (02, p.2; 04, pp.2-5; checks and control are agreed recommendations)

**UC04:** retain the full requested context; classification-only would be a narrower scope. Creating a missing unified profile belongs to UC06 and affects readiness. ERP connectivity may be shared with UC01, but history reads, CRM access and routing rules require separate checks. (02, pp.2-3; 04, pp.2-4; reuse is a hypothesis)

**UC05:** retain both reports and presentations; consolidated data do not establish incremental benefit. Check the current preparation work and existing tool coverage. BI access/definitions could help UC10 where applicable, but sales-history granularity and forecasting require separate checks. (02, pp.2-3; 04, pp.1-4; reuse is a hypothesis)

**UC06:** assess the full reconciliation/data-quality scope, conditional on existing foundations. UC04 directly needs its unified profile; connections and mappings may support other workflows after specific checks. (02, pp.2-3; 04, pp.4-5)

**UC07:** source traceability and expert completeness review are approved conditions; source references are to be verified, not a guaranteed native capability. Ingestion components may be reusable from UC01/UC03 subject to format/layout checks; document processing and source-reference patterns could help UC08, whose retrieval and permissions need separate assessment. (02, p.3; 04, pp.1-3, 5; reuse is a hypothesis)

**UC08:** retain both document Q&A and image recognition under verification initially, revising the earlier `approach.md` hypothesis of significant development for full retrieval. UC07 document/source-reference components may be reusable; retrieval, permissions and image recognition remain separate checks. (02, p.3; 04, pp.3-5)

**UC09:** human examination precedes invoice approval. Missing shipment/tariff/exception data must be flagged as cannot verify. Extraction/review components may transfer from UC03, and contract-analysis patterns from UC07; shipment matching and tariff rules remain specific. (02, p.3; 04, pp.1-5; controls are approved recommendations and reuse is a hypothesis)

**UC10a/UC10b:** preserve both requested outcomes but assess them separately. The source prefers two or three years of sales history; availability is unconfirmed. Existing forecasting tools may reduce UC10a's development assessment. UC05 access, relevant definitions and reporting components may be reusable; consolidated reporting does not establish forecast-ready sales history. (02, pp.2-3; 04, pp.1-5)

## 3a. Weighted decision matrix: narrowing ten cases to five

*Intermediate step between 3 and 4. Shortlist approved on 11 October 2026; weights and scores remain provisional analytical judgments, not client priorities. No pilot is selected. The required appendix tables retain their original schemas.*

### Criteria, weights and scoring scale

Scores use **1–5, with higher always better**. Scores 2 and 4 represent intermediate judgments. For effort/dependencies, a higher score means less work and fewer unresolved dependencies. The matrix assesses the approved scopes in section 3, including ERP writes in UC01/UC03, presentations in UC05 and both components of UC10.

| Criterion | Weight | 1 | 3 | 5 |
| --- | --- | --- | --- | --- |
| **I — Potential business impact** | **25%** | Limited convenience | Focused productivity/quality benefit | Potential to change several core commercial/operational decisions |
| **S — Stakeholder / agenda signal** | **20%** | No identifiable business request | Function-specific request in case catalog | Direct match to a business priority in the client email |
| **F — Technical compatibility** | **15%** | Dedicated solution substantially beyond documented workflows | Workflow approach plausible; essential components need checks | Full assessed outcome supported by documented capabilities |
| **L — Favorable work / dependencies** | **15%** | Significant development or structural dependencies | Bounded configuration/integration approach plausible, effort unverified | Inputs/access/rules available; little additional work identified |
| **V — Value verifiable within six weeks** | **15%** | Long/indirect path to meaningful evidence | Initial evidence possible, with important conditions | Useful business improvement readily observable within the horizon |
| **R — Reuse / expansion potential** | **10%** | Little concrete shared work identified | Some components or wider adoption plausible | Direct foundation for another requested case and wider business use |

**Weight rationale:** business impact and stakeholder relevance together receive 45%; technical compatibility and work 30%; six-week verification 15%; reuse/expansion 10%. This gives business reasons the largest combined influence while retaining the client's time horizon and expansion request. These are our proposed weights, not client-approved priorities.

**Evidence boundary:** scores quantify our comparative judgment, not measured ROI, proven readiness or delivery probability. The client supplies no priority weights, volumes, effort, error costs or confirmed sponsor authority. Only UC05 explicitly has consolidated data. Significant development is scored where identifiable; undocumented support remains a check. (02, pp.1–3; 03, p.1; 04, pp.2–5)

### Scored matrix

**Weighted total = SUMPRODUCT(scores, weights)**, using weights as fractions:  
**Total = 0.25I + 0.20S + 0.15F + 0.15L + 0.15V + 0.10R**, on a 1–5 scale.

| Use case | I (25%) | S (20%) | F (15%) | L (15%) | V (15%) | R (10%) | Weighted total / 5 | Rank |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| UC01 — Orders | 4 | 5 | 3 | 3 | 4 | 4 | 3.90 | 1 |
| UC05 — Reporting | 3 | 4 | 4 | 4 | 4 | 3 | 3.65 | 2 |
| UC04 — Customer service | 4 | 5 | 3 | 2 | 3 | 3 | 3.50 | 3 |
| UC03 — Supplier lists | 3 | 4 | 3 | 3 | 4 | 4 | 3.45 | 4 |
| UC09 — Freight checks | 4 | 4 | 3 | 2 | 4 | 3 | 3.45 | 4 |
| UC07 — Tenders | 3 | 3 | 3 | 3 | 4 | 3 | 3.15 | 6 |
| UC10 — Forecasts / low rotation | 5 | 3 | 2 | 1 | 2 | 3 | 2.90 | 7 |
| UC06 — Reconciliation | 4 | 3 | 2 | 1 | 2 | 5 | 2.85 | 8 |
| UC02 — AR configuration | 3 | 5 | 1 | 1 | 2 | 2 | 2.55 | 9 |
| UC08 — Knowledge | 3 | 2 | 2 | 2 | 2 | 3 | 2.35 | 10 |

Example, **UC01:** (4 × 0.25) + (5 × 0.20) + (3 × 0.15) + (3 × 0.15) + (4 × 0.15) + (4 × 0.10) = **3.90**. UC03 and UC09 tie; no arbitrary tie-break is needed because both fit within the five places.

### Reasons behind the scores

- **UC01:** core order handling and direct Operations alignment; extraction/rules/ERP remain checks. Handling time/errors can be compared, including approval. Concrete UC03 reuse is conditional. (02, p.2; 04, pp.2–5)
- **UC02:** direct sales-experience alignment, but sales benefit requires a real buying obstacle; dedicated AR work/assets and commercial verification weaken the near-term case. (02, p.2; 04, pp.2–3)
- **UC03:** focused price-update productivity/accuracy rather than proven wider savings; fits Operations' data-work agenda. Supplier mappings/ERP updates need checks, with concrete possible UC01 overlap. (02, p.2; 04, pp.2–5)
- **UC04:** direct service priority and core customer-process potential. Unified-profile dependency lowers the work score; preparation/assignment improvements do not establish faster resolution or retention. Reuse beyond service patterns is uncertain. (02, pp.2–3)
- **UC05:** management demand in the case, consolidated data and documented prepared-data synthesis improve its position. Exports/presentations and existing BI coverage remain checks; impact is initially preparation/coherence. (02, p.2; 04, pp.2–4)
- **UC06:** potentially important enabling infrastructure and direct UC04 foundation; cross-unit reconciliation, ownership and integration make the full scope a heavier, less immediately verifiable undertaking. (02, pp.2–3)
- **UC07:** plausible preparation/error benefit and measurable expert-reviewed omissions; tender importance is unconfirmed and the link to the email's service/sales-experience agenda is weaker. (02, p.3; 04, pp.3–5)
- **UC08:** broad potential but no named process owner or costly target task. Retrieval, permissions and image recognition remain separate checks; do not infer significant development from missing documentation. (02, p.3; 04, pp.3–5)
- **UC09:** potential financial exposure plus checking effort; actual spend/overcharges unknown. Shipment links and tariff exceptions create more dependencies than a simple document workflow. (02, p.3; 04, pp.2–5)
- **UC10:** highest potential-impact score reflects its planning/assortment ambition, not proven largest returns. Forecast development, unconfirmed history and slower realized benefits lower its near-term total; UC10b remains a separate verification component. (02, p.3)

### Approved shortlist and sensitivity

**Approved for deeper comparison: UC01, UC05, UC04, UC03 and UC09**, the five highest weighted totals. The order is a screening result, not the final pilot/next-case sequence. The five-case comparison must still use the six columns specified in requirements.md.

The cutoff is provisional: **UC03/UC09 score 3.45; UC07 scores 3.15.** If tenders prove commercially critical and aligned with leadership priorities, increasing UC07's I and S by one point produces **3.60**, changing the shortlist. If UC04 requires building the full UC06 foundation, reducing F from 3 to 2, L from 2 to 1 and V from 3 to 1 produces **2.90**, also changing it. These are illustrative rescoring scenarios, not new facts.

**Step 4 complete:** all five cases and proposed value/quality criteria have been reviewed. The next plan step is pilot/next/defer selection, to begin when the user requests it. Before pilot commitment, collect process baselines, error consequences, named owners/expansion authority, usable inputs/access and reviewer availability. Revisit scores and shortlist if those checks change the assessment.

## 4. Five-case comparison

*Reviewed cases: 5 of 5 (UC01, UC05, UC04, UC03, UC09), including the differentiated time-reduction targets. These remain acceptance proposals for client validation, not measured results. Human approvals and final assignment are method controls, not performance measures. Step 4 is complete; no pilot is selected.*

| ID | valore atteso e come verificarlo | compatibilità con DualOS | dati e dipendenze | complessità e incertezza motivate | priorità e motivazione |
| --- | --- | --- | --- | --- | --- |
| UC01 | Ridurre di **almeno il 50%** il tempo di lavorazione per ordine rispetto al processo attuale, come target proposto da validare con il cliente. Raccogliere una baseline su ordini rappresentativi e confrontare il processo assistito, includendo revisione, correzioni e inserimento ERP. Accuratezza come requisito di qualità: proposta >95% degli ordini corretti su tutti i campi critici e sugli esiti dei controlli prima della revisione, da validare con il cliente su risposte di riferimento verificate dagli esperti. | **verifiche necessarie**: agenti, output strutturati, workflow e attese di approvazione sono documentati; estrazione dai documenti reali, applicazione delle regole e specifica azione ERP richiedono verifica. Approvazione umana di ogni ordine prima della scrittura. | Esempi rappresentativi, campi richiesti dall'ERP, regole di configurazione/validazione definite con il business, anagrafiche utili ai controlli, azione e permessi ERP verificati, operatori disponibili per baseline e revisione. | Varietà dei documenti, completezza delle regole, errori sui campi critici e affidabilità della scrittura possono aumentare il lavoro. Il tempo di revisione può annullare il beneficio; verificare che l'approvazione sia obbligatoria e riferita ai dati effettivamente scritti. HITL riduce il rischio ma non elimina gli errori approvati per svista. | **Prima posizione nello screening (3,90/5)**: risposta diretta a Operations su un processo centrale, con possibili benefici per Commerciale e riuso verso UC03. Candidato al pilota, subordinato a beneficio netto, qualità e fattibilità; la scelta del pilota resta allo step 5. |
| UC05 | Ridurre di **almeno il 60%** il tempo complessivo di preparazione per ciclo rispetto al processo attuale, includendo export, report/presentazioni, revisione e correzioni. Confrontare almeno **3 fascicoli storici rappresentativi** con gli stessi dati e output richiesti. Qualità della bozza: **100%** dei valori numerici riconciliati e **almeno il 90%** dei commenti accettati senza modifiche sostanziali. Prima della diffusione: **0** affermazioni causali prive di riscontro. Target proposti, non risultati misurati. | **capability documentate** per sintesi da dati preparati e report strutturati/HTML; **verifiche necessarie** per accesso/export BI, formati finali incluse presentazioni, coerenza numerica e commenti. Revisione e approvazione del responsabile reporting prima della diffusione. | Export BI autorizzato, definizioni degli indicatori e regole di calcolo/arrotondamento, struttura concordata, report/presentazioni storiche, regole di commento, formati richiesti e responsabile reporting disponibile. I dati consolidati sono dichiarati; accesso e utilizzabilità restano da verificare. | Gli strumenti BI esistenti possono già coprire parte della richiesta. Verificare il lavoro residuo e il beneficio incrementale; export manuali, formattazione e revisioni possono assorbire il risparmio. Interpretazioni causali e produzione delle presentazioni richiedono controlli specifici. | **Seconda posizione nello screening (3,65/5)**: domanda esplicita della direzione e dati consolidati favoriscono una prova verificabile. Candidato alternativo al pilota se emerge beneficio aggiuntivo; accesso BI, definizioni pertinenti e reporting possono aiutare UC10, senza attestare storico o forecasting pronti. |
| UC04 | Ridurre di **almeno il 40%** il tempo operativo per ricostruire il contesto, classificare e preparare l'assegnazione, includendo revisione e correzioni. Confrontare richieste storiche rappresentative con baseline e risposte validate dagli esperti. Target prima delle correzioni: **almeno il 95%** delle richieste con classificazione e team proposto corretti; **0** associazioni errate cliente/ordine nei casi valutati. Target proposti da validare con il cliente. | **verifiche necessarie**: agenti, workflow e output strutturati sostengono l'approccio; accesso al contesto corretto, copertura dello storico e regole di assegnazione richiedono verifica. Il profilo unificato necessario è trattato in UC06. La decisione finale di assegnazione resta all'operatore. | Richieste in ingresso, profilo cliente unificato utilizzabile, ordini e storico di interazioni/pratiche, accessi verificati e regole di classificazione/instradamento; operatori ed esperti disponibili per baseline, verifica e decisione finale. | La dipendenza da UC06 può aumentare sensibilmente il lavoro se il profilo deve essere costruito. Identità ambigue, storico incompleto e revisioni possono compromettere qualità o risparmio; segnalare il contesto mancante senza inventarlo. Miglioramenti nella preparazione non dimostrano tempi di risoluzione inferiori o maggiore fidelizzazione. | **Terza posizione nello screening (3,50/5)**: risponde direttamente alla priorità di servizio della direzione commerciale. Candidato subordinato a un profilo utilizzabile e beneficio netto; se manca, valutare il lavoro UC06 prima di impegnarsi sul perimetro completo. Possibile estensione ad altri team/unità, con nuove verifiche di dati e regole. |
| UC03 | Ridurre di **almeno il 55%** il tempo complessivo per lotto di aggiornamento rispetto al processo attuale, includendo revisione, correzioni e applicazione ERP. Confrontare listini rappresentativi con dimensioni/varietà comparabili e aggiornamenti di riferimento validati dagli esperti. Prima delle correzioni: **almeno il 98%** delle righe di aggiornamento con articolo e prezzo applicabile corretti; **100%** delle corrispondenze note ambigue o mancanti segnalate nel campione valutato. Target proposti da validare con il cliente. | **verifiche necessarie**: output strutturati, workflow e attese di approvazione sono documentati; estrazione, corrispondenze, interpretazione dei prezzi e specifica azione ERP richiedono verifica. Nella prima versione, revisione di tutte le modifiche e approvazione del lotto prima della scrittura. | Listini rappresentativi dei fornitori, anagrafica articoli/componenti, mappature codici fornitore, dati ERP correnti e regole di validazione; specifica azione e permessi di aggiornamento verificati, responsabili disponibili per baseline e revisione. | Formati/strutture eterogenei, mappature insufficienti e significato dei prezzi possono aumentare il lavoro. Usare corrispondenze esatte/regole ove possibile e AI per interpretazione; verificare errori apparentemente validi e costo della revisione. Il riuso UC01 dipende da ERP, formati e anagrafiche effettivamente condivisi; scrittura prezzi e creazione ordini sono azioni distinte. | **Quarta posizione nello screening, a pari merito con UC09 (3,45/5)**: beneficio operativo misurabile e possibile riuso concreto da UC01. Candidato all'espansione, da confermare allo step 5 dopo beneficio netto e verifiche specifiche; effetti più ampi su costi/margini non sono dimostrati. |
| UC09 | Ridurre di **almeno il 45%** il tempo complessivo di controllo rispetto al processo attuale, includendo indagine, revisione e correzioni. Su prefatture storiche rappresentative, validate dagli esperti: rilevare **almeno il 95%** delle anomalie note nei casi con dati sufficienti; **almeno il 90%** delle anomalie segnalate confermate come reali; **100%** dei casi noti con dati insufficienti classificati come non verificabili. Misurare separatamente addebiti ingiustificati confermati in euro e rettifiche effettivamente ottenute. Target proposti da validare con il cliente. | **verifiche necessarie**: workflow e output strutturati sono documentati; estrazione, collegamenti addebito/spedizione/tariffa e calcoli richiedono verifica. Regole e calcoli espliciti per tariffe definite; AI per estrazione e interpretazione delle clausole, con regole validate dal business. Esame umano prima dell'approvazione della fattura come controllo del metodo. | Prefatture PDF/fogli/EDI, contratti e tariffe con eccezioni, registrazioni di spedizioni, volumi, tratte e consegne; collegamenti affidabili e accessi verificati, referenti Logistica/Amministrazione per baseline e validazione dei casi. | Collegamenti mancanti, eccezioni e ambiguità contrattuali possono impedire il controllo o aumentare il lavoro. Dati insufficienti producono uno stato non verificabile, non un esito conforme. Integrazioni o logiche tariffarie estese possono richiedere sviluppo significativo; falsi allarmi e indagini manuali possono assorbire il risparmio. | **Quarta posizione nello screening, a pari merito con UC03 (3,45/5)**: alternativa di controllo finanziario con beneficio operativo e possibili addebiti evitati, la cui entità resta da misurare. Possibile riuso di estrazione/revisione da UC03 e analisi di clausole da UC07; collegamenti e regole tariffarie restano specifici. Candidato da confrontare prima della scelta allo step 5. |

**Sources:** UC01/UC05/UC04/UC03 inputs and outcomes: 02, p.2; UC09 and UC04's UC06 dependency: 02, p.3; technical support and checks: 04, pp.2-5. Metrics, thresholds and priority are proposed assessments; no measured savings or accuracy are available.

**UC01 time target:** proposed ≥50% reduction = 1 − assisted average working time per order / current-process average working time per order, measured on comparable representative orders and including review, corrections and ERP insertion. Validate against the baseline with the client.

**UC01 approved quality proposal:** >95% = orders whose critical fields and configuration-check outcomes are all correct / all representative orders evaluated, measured before human corrections. Do not use an average across fields that could conceal critical order errors or omit failed/incomplete outputs from the sample. Validate the acceptance criterion and agree critical fields/reference answers with the client process owner; this is not a measured result.

**UC01 approval distinction:** the intended control is no ERP write without approval of that order's final data. It is not a guarantee that every approved order is correct. Verify enforcement/authorized roles; the documented Approvers names are descriptive metadata, not an exclusive approval list. (04, pp.2, 4)

**UC05 proposed targets:** numerical thresholds are deliberately chosen working targets, as requested by the user; validate feasibility and business relevance with the client. Time reduction = 1 − assisted preparation time / current-process preparation time, using total working time across the same historical packs, including reviewer/correction effort. Three historical packs provide initial comparative evidence, not statistical certainty or a requirement for three live monthly cycles within six weeks.

**UC05 quality definitions:** numeric reconciliation = all displayed values agreeing with the approved BI extract or agreed calculations/rounding; a missing required value must be flagged and prevents treating the pack as complete. Comment acceptance = comments accepted by the reporting owner without a substantive change to fact, interpretation or usefulness / all required commentary items; missing items count as failures, while style-only edits do not. Measure these on drafts before human corrections. The circulated version must reconcile all figures, label unverified explanations as hypotheses and receive owner approval; unsupported causal assertions must be corrected or removed. These are acceptance criteria, not guarantees of model accuracy.

**UC04 targets:** proposed ≥40% reduction in average operator preparation time per request, including review/corrections, on comparable cases. Classification/team accuracy = requests where both agree with expert-validated reference answers / all representative requests evaluated, before human corrections; missing or failed outputs do not count as correct. Zero incorrect customer/order associations is a criterion for the evaluated sample, not proof of zero future errors. Missing/ambiguous context must be flagged for the operator; do not treat missing context as a complete profile. Final assignment remains human. Validate the targets with the client and retain the full context scope and UC06 dependency.

**UC03 quality definitions:** correct-update rate = required update rows with both the correct internal article and correctly interpreted applicable price / all required update rows in the representative sample, measured before human correction; missing/failed required outputs count as failures. Ambiguity detection = known ambiguous/unmatched rows correctly flagged / all such rows in the expert-labeled sample. Compare total working time for equivalent supplier batches, including full initial review, corrections and ERP application. Batch approval remains a mandatory method control, with enforcement to verify.

**UC09 approved measures:** compare total working time on equivalent historical prefactures, including investigation, review and corrections. Anomaly detection = true anomalies flagged / all expert-confirmed anomalies in cases with sufficient evidence (target ≥95%); alert precision = expert-confirmed true anomalies / all anomaly alerts (target ≥90%). Insufficient-evidence detection = known unverifiable cases correctly identified / all such expert-labeled cases (target 100%); treat these separately from anomaly alerts and do not mark them conforming. Include all sampled charges and report how many are verifiable/unverifiable. Confirmed unjustified charges in euros are potential financial value; record actual invoice corrections separately. Human examination is a method control. No monetary savings threshold is assumed.

## 5. Scelta delle priorità

*Scelte e fallback approvati l'11 ottobre 2026. Step 5 completo; documento di consegna non modificato.*

- **Primo pilota: UC01.** Risponde direttamente a Operations su un processo centrale, con beneficio da misurare sul tempo totale, inclusi revisione, correzioni e inserimento ERP. Preferito a UC05 per rilevanza operativa e possibile riuso verso UC03, accettando maggiori verifiche su documenti, regole e scrittura. Se UC01 nel suo complesso è impraticabile, valutare UC05, successivo nella matrice, verificando beneficio oltre gli strumenti BI, accesso/export e formati finali. (02, pp.1–2)
- **Secondo caso: UC03.** Verificare il riuso di configurazione/accesso ERP, anagrafiche pertinenti, componenti di estrazione compatibili e struttura di revisione/approvazione/tracciamento. Restano specifici mappature fornitore, interpretazione dei prezzi, regole e azione ERP di aggiornamento. Il riuso concreto motiva la sequenza, senza confonderla con la classifica generale; se il pilota diventa UC05, rivalutare il secondo caso. (02, p.2; 04, pp.2–5; riuso condizionato)
- **Da rimandare: UC02.** Interfaccia AR/rendering specifici, asset 3D non confermati e beneficio commerciale da verificare rendono meno credibile il primo utilizzo nel periodo iniziale. Rivalutare con soluzioni/asset già disponibili e priorità commerciale dimostrata. (02, p.2; 04, p.2)

**Prima della scelta definitiva:** osservare ordini rappresentativi con Operations e raccogliere volumi, tempi e correzioni; far verificare documenti/regole a business e FDE e azione/permessi ERP e controllo di approvazione a FDE/IT; concordare responsabili e disponibilità. Per l'alternativa UC05, esaminare fascicoli storici e lavoro residuo oltre il BI. Per UC03, confrontare sistemi, anagrafiche, formati e azioni con Acquisti/IT. Beneficio netto insufficiente o lavoro incompatibile con risorse/orizzonte possono cambiare la scelta. (02, pp.1–2; 04, pp.4–5; verifiche proposte)

**Fallback ERP approvato:** preferire approvazione umana seguita da inserimento automatico; un pulsante che avvia uno script richiede comunque un percorso di scrittura verificato. Se questo è bloccato, verificare prima un import ERP esistente da file strutturato. In assenza anche dell'import, mantenere estrazione e controlli con compilazione/copia manuale dei campi solo se il processo completo offre un beneficio netto concordato: dichiarare il perimetro ridotto e rivalutare con il cliente il target proposto ≥50%, senza fissare qui una soglia sostitutiva. Includere revisione, correzioni e inserimento/import nella misura; mantenere revisione umana e requisito di qualità a livello d'ordine. Se non resta un perimetro UC01 utile e fattibile, valutare UC05. Nessuna modalità ERP è confermata dal materiale: verifica con IT/FDE e responsabile del processo. Se l'integrazione di scrittura non viene realizzata, escluderla dal riuso dichiarato verso UC03 e rivalutarne l'impegno. (02, p.2; 04, pp.2, 4–5; fallback come decisione condizionata)

## 6. Definizione del pilota — UC01

*Step 6 completo: tutti e sei i campi approvati l'11 ottobre 2026; documento di consegna non modificato.*

### 1. Risultato e perimetro

Ridurre il lavoro necessario per trasformare un ordine ricevuto in un ordine controllato, approvato e inserito nell'ERP. Output per gli operatori di gestione ordini: dati strutturati, esiti dei controlli di configurazione e segnalazione delle informazioni mancanti/ambigue, da rivedere e correggere prima dell'inserimento secondo il percorso concordato allo step 5. Avvio su **una unità operativa e un ambiente ERP**, con una famiglia o un insieme circoscritto di prodotti/configurazioni e formati documentali selezionati con Operations in discovery, considerando volumi significativi, regole sufficientemente chiare e varietà rappresentativa. Esclusi inizialmente estensione a tutte le unità/ERP, copertura universale dei formati e inserimento senza approvazione umana; gli ordini fuori perimetro seguono il processo esistente. Errori di estrazione, dati mancanti e configurazioni non valide negli ordini in perimetro restano nella valutazione. (02, pp.1–2: contesto e risultato richiesto; 01, p.2: campo richiesto; delimitazione come decisione approvata)

### 2. Dati e dipendenze

Operations fornisce ordini storici originali (email/allegati) e corrispondenti ordini ERP controllati, includendo casi incompleti, ambigui e configurazioni non valide; gli esperti validano le risposte di riferimento. Il responsabile di processo conferma regole/eccezioni applicabili e dati di prodotto/componenti ove necessari ai controlli, verificandone aggiornamento e identificativi. IT/FDE verificano campi ERP, mappature, permessi e percorso di inserimento/import; prima delle scritture automatiche, anche il controllo obbligatorio dell'approvazione. Concordare responsabile e revisori disponibili; raccogliere volumi, tempi e correzioni osservando il processo, incluso l'inserimento ERP. Avviare discovery su file storici forniti mentre IT/FDE verificano l'ERP in parallelo; l'eventuale acquisizione live richiede controlli separati di accesso/trigger. Prima di configurare il workflow del pilota, confermare esempi sufficienti, regole e riferimenti validati, percorso di inserimento e disponibilità dei revisori. Serve affidabilità nel perimetro scelto, non una bonifica preventiva dell'intero catalogo. Nessun input/accesso è assunto pronto. (02, pp.1–2; 03, p.1; 04, pp.2–4; percorso e condizioni come decisione approvata)

### 3. Lavoro necessario

Configurare agente, output strutturato e workflow: lettura/estrazione dell'ordine con AI, controlli di configurazione tramite regole esplicite ove chiaramente esprimibili, revisione/correzione umana e inserimento ERP come azione controllata dopo approvazione dei dati finali. I **guardrails** comprendono validazione di campi obbligatori/formati, controlli di configurazione, invio dei dati mancanti/ambigui alla revisione, permessi limitati alle azioni necessarie e approvazione obbligatoria prima della scrittura; la loro applicazione va verificata. Agenti, output, condizioni, attese di approvazione e trace sono documentati. Verificare estrazione dai formati scelti, esecuzione delle regole, modalità di correzione/approvazione, azione e permessi ERP ed eventuale acquisizione live. Se il supporto esistente non basta, valutare conversione/OCR, componente di esecuzione delle regole o integrazione ERP, esplicitando lavoro e impatto sul pilota prima di accettarli e applicando il fallback concordato. Classe **verifiche necessarie**, da rivedere se emerge sviluppo aggiuntivo significativo. I guardrails non garantiscono correttezza; i nomi degli Approvers non impongono una lista esclusiva. (04, pp.2–5: capability e limiti; approccio e guardrails come decisione approvata)

### 4. Valore e qualità

Target proposti da validare con il cliente: **≥50% di riduzione del tempo medio di lavoro per ordine**, su attività comparabili includendo revisione, correzioni e inserimento ERP; **>95% di ordini strutturati corretti prima della correzione umana**, con tutti i campi critici e gli esiti dei controlli corretti, includendo output falliti/incompleti nel denominatore. Raccogliere la baseline osservando il processo attuale. Confrontare il processo assistito con risposte validate dagli esperti su ordini rappresentativi di formati/configurazioni e casi mancanti, ambigui o non validi; riconoscere correttamente una configurazione non valida è un esito corretto. Riservare esempi distinti da quelli usati per configurare/affinare il workflow per la valutazione finale, concordando dimensione e copertura con il responsabile: analogia con train–test split, senza implicare training del modello. Se usati poi per affinamento, servono nuovi esempi indipendenti per la successiva valutazione finale. Rivalutare il target temporale nel fallback manuale. I guardrails sono controlli del metodo, non misure di valore/qualità; nessuna soglia è un risultato misurato o un impegno cliente. (02, pp.1–2: dati/baseline da raccogliere; 04, p.5: qualità su esempi e limiti di Tests; criteri e separazione degli esempi come decisione approvata; definizioni già concordate al punto 4)

### 5. Responsabilità

**DS:** perimetro, risultati/criteri, stakeholder, baseline, adozione e roadmap. **FDE:** configurazione/manutenzione di agenti, regole, workflow e integrazioni, verifiche tecniche, guardrails e analisi degli errori. **Responsabile gestione ordini:** regole, riferimenti e campi critici validati, revisori disponibili e accettazione di valore/qualità. **Operatori:** esempi, osservazione del processo, valutazione, correzione/approvazione e feedback. **IT/responsabile ERP:** accessi autorizzati, mappature, permessi, percorso di inserimento e condizioni tecniche di rilascio con FDE. **Referente trasformazione/processi:** coordinamento delle funzioni, priorità/risorse e individuazione di chi autorizza cambi di perimetro ed estensione. DS riunisce accettazione business e verifiche tecniche per la decisione di proseguire con il decisore cliente autorizzato. Confermare nomi, disponibilità e autorità in discovery. (03, p.1: ruoli DS/FDE; 02, p.1: referente e responsabilità da concordare; assegnazioni cliente come proposta approvata)

### 6. Controlli e revisione

Rischio principale: ordine plausibile ma errato inserito nell'ERP, inclusa una configurazione non valida trattata come valida. Applicare i guardrails del campo 3 e revisione di ogni ordine: risolvere dati critici mancanti/ambigui e configurazioni non valide prima dell'inserimento, altrimenti tornare al processo esistente. Approvazione sui dati finali corretti, da rinnovare se cambiano. Verificare prevenzione dei duplicati e, dopo una scrittura dall'esito incerto, controllare l'ERP prima di ritentare; operatore/FDE indagano gli errori con IT ove necessario. Analizzare feedback/errori, correggere estrazione/regole e rivalutare su esempi indipendenti. Se valore/qualità non soddisfano i criteri concordati, rivedere perimetro/approccio prima dell'estensione. Sospendere le scritture automatiche se l'approvazione è aggirabile o gli esiti non sono controllabili; mantenere preparazione assistita solo se utile con il fallback concordato, passando a UC05 se nessun perimetro UC01 resta utile e fattibile. Verificare controllo dei revisori e concordare test ERP sicuri: Approvers è descrittivo, i test possono scrivere realmente e cancellare una run non annulla scritture accettate. (04, pp.2, 4–5; controlli, recupero e condizioni come decisione approvata)

## 7. Roadmap — prime sei settimane

*Roadmap completa e trade-off approvati l'11 ottobre 2026. Step 7 completo; documento di consegna non modificato.*

Obiettivo di pianificazione: workflow verificato entro la settimana 4, uso operativo controllato nelle settimane 5–6 e decisione basata sui risultati alla fine della settimana 6. Le settimane decorrono dalla discovery; capacità DS/FDE e disponibilità cliente vanno concordate, non sono fornite dal materiale. Date indicative e passaggi subordinati alle evidenze, non garanzia di consegna. (01, p.2; 02, p.1; 03, p.1)

| Periodo | Lavoro e risultato osservabile | Responsabile e contributo cliente | Condizione per proseguire |
| --- | --- | --- | --- |
| **Settimana 1 — Discovery e perimetro** | Scegliere unità, ERP, prodotti/configurazioni e formati. Osservare il processo e avviare la baseline temporale; raccogliere esempi, validare regole/riferimenti e riservare esempi di valutazione. Risultato: perimetro, criteri di accettazione e dipendenze concordati. | **DS**, con FDE, responsabile di processo, operatori e IT. Il cliente conferma revisori e autorità decisionale. | Esempi/regole sufficienti, revisori disponibili e percorso di inserimento plausibile da verificare. In caso contrario, risolvere le dipendenze o rivedere il perimetro prima della configurazione. |
| **Settimana 2 — Fattibilità e percorso ERP** | Provare estrazione/controlli su esempi di sviluppo, inclusi quelli difficili. Verificare operazione ERP, permessi e modalità sicura di test. Scegliere inserimento automatico, import esistente o fallback manuale; identificare componenti aggiuntivi e impegno. Completare la baseline iniziale. Risultato: percorso completo fattibile e lavoro residuo esplicito. | **FDE** per le verifiche tecniche, con IT; **DS/responsabile di processo** per utilità e perimetro. | Percorso fattibile, evidenze sufficienti di beneficio potenziale e lavoro compatibile con il tempo residuo. Altrimenti restringere/ripianificare UC01 o valutare UC05. |
| **Settimana 3 — Workflow completo** | Configurare estrazione, regole, output, correzione operatore, approvazione e percorso di inserimento scelto. Provare guardrails, dati mancanti/non validi, prevenzione duplicati e recupero da scritture incerte. Gli operatori provano la revisione sugli esempi di sviluppo. Risultato: versione candidata alla valutazione. | **FDE**, con operatori, responsabile e IT; DS verifica adozione e lavoro di revisione. | Percorso completo funzionante nell'ambiente/modalità di test concordati, gestione dei dati critici e controlli di approvazione/scrittura dimostrati. Problemi di sicurezza irrisolti bloccano il rilascio operativo. |
| **Settimana 4 — Valutazione indipendente e rilascio** | Valutare la candidata sugli esempi riservati; misurare correttezza prima delle correzioni e tempo totale, incluse correzioni/inserimento. Registrare fallimenti e confronto con baseline. Risultato: rapporto di accettazione; se accettata, pubblicazione/attivazione della versione valutata e preparazione degli operatori. | **DS** coordina le evidenze; **FDE/operatori** eseguono la verifica. Il responsabile accetta i risultati business; IT/FDE verificano le condizioni di rilascio. | Criteri concordati di qualità/tempo e guardrails soddisfatti, copertura sufficiente e utenti in grado di operare. Altrimenti correggere e rivalutare su nuovi esempi indipendenti o ripianificare. Non ricreare ordini storici in produzione per testarli. |
| **Settimana 5 — Uso operativo controllato** | Lavorare un volume limitato di ordini reali in perimetro con il percorso scelto e revisione di ogni ordine. Registrare tempi, correzioni, fallimenti, esiti ERP e feedback. Risultato: utilizzo effettivo da parte degli operatori destinatari. | **Operatori/responsabile di processo** per l'uso; FDE per gli errori; DS per beneficio e adozione. | Controlli efficaci e risultati operativi che sostengono la prosecuzione. Sospendere subito le scritture automatiche se approvazione/esiti non sono controllabili; usare il fallback concordato ove utile. |
| **Settimana 6 — Risultati e prosecuzione** | Consolidare evidenze storiche/operative, quota di lavoro coperta e attività manuali residue. Decidere prosecuzione nel perimetro, revisione, ulteriore valutazione o arresto. Concordare supporto continuativo e verificare il riuso concreto verso UC03. Risultato: decisione motivata e condizioni dell'eventuale estensione. | **DS** presenta con FDE; responsabile e IT forniscono evidenze business/tecniche; il decisore cliente autorizzato approva prosecuzione/estensione. | Estensione solo con evidenze adeguate, valore/qualità accettati, operatività controllata e responsabili/risorse impegnati. Volume reale insufficiente richiede ulteriore valutazione circoscritta, non una dichiarazione di successo dimostrato. |

### Verifica con gli utenti, ritardi ed eventuale estensione

- **Criteri e verifica:** validare in discovery i target già proposti (≥50% di riduzione del tempo e >95% di ordini corretti prima delle correzioni); includere output falliti/incompleti e mantenere approvazione umana anche dopo la valutazione positiva. Prima dell'uso operativo, soddisfare i criteri concordati e dimostrare i guardrails. Se il fallback cambia il perimetro, concordare il target applicabile prima della valutazione. Gli operatori provano la revisione in settimana 3, verificano la candidata in settimana 4 e misurano l'uso reale nelle settimane 5–6.
- **Ritardi ERP:** investigare accessi in parallelo ai file storici, ma scegliere un percorso di inserimento credibile entro fine settimana 2, per conservare tempo per verifica completa e uso reale. Se serve più tempo, rivedere le date di utilizzo; nel fallback manuale misurare anche l'inserimento.
- **Dati, regole o revisori mancanti:** ridurre il perimetro solo se copre ancora lavoro significativo, senza eliminare i casi difficili al suo interno. Se le dipendenze restano indisponibili, spostare le milestone. Il passaggio a UC05 richiede verifica delle sue dipendenze e ripianificazione del tempo residuo: non implica la consegna automatica entro le sei settimane originarie.
- **Estensione e UC03:** dopo la verifica di UC01, accertare che cosa è realmente riutilizzabile e concordare nuove verifiche/risorse. La settimana 6 può stabilire riuso e readiness, non promette un secondo pilota consegnato. Mappature fornitore, regole prezzo e azione ERP di aggiornamento restano specifiche; non attribuire al riuso integrazioni non realizzate. Ogni ampliamento di prodotti, formati o unità richiede verifiche nel nuovo contesto.

**Trade-off approvati:** scegliere il percorso ERP entro fine settimana 2 anziché prolungarne indefinitamente la verifica; subordinare l'uso operativo al raggiungimento dei criteri concordati anziché iniziare un trial operativo sotto soglia. Eventuali ritardi richiedono modifica esplicita di perimetro/date, preservando controlli ed evidenze.

**Fonti:** 01, p.2: sei settimane, milestone/condizioni e verifica utenti/estensione; 02, pp.1–2: dipendenze, disponibilità e casi UC01/UC03/UC05; 03, p.1: responsabilità e riuso condizionato; 04, pp.2–5: configurazione/versioni, approvazioni, estrazione, integrazioni e recupero. Sequenza e tempi sono la proposta approvata, non prestazioni garantite dalla piattaforma.

## 8. Primo incontro — risposta all'email del cliente

*Email rivista e approvata il 12 ottobre 2026, inclusa la precisazione del riuso UC01→UC03. Step 8 completo; documento di consegna non modificato.*

**Oggetto: Re: Primo confronto su DualOS e priorità di lavoro**

Buongiorno,

grazie per aver condiviso i casi e le priorità. Il primo confronto servirà a scegliere un processo che riduca il lavoro di inserimento e controllo richiesto da Operations, tenendo conto delle esigenze di servizio e vendita del Commerciale e chiarendo sistemi e impegno per IT.

Proporrei un incontro di **60 minuti** con voi, il responsabile Operations/gestione ordini, un operatore, un rappresentante del Commerciale e il referente IT/ERP. Da parte nostra parteciperanno 1 Deployment Strategist (DS) e 1 Forward Deployed Engineer (FDE).

Come prima ipotesi valuterei **UC01, acquisizione degli ordini**: estrarre i dati, controllare la configurazione e preparare l'inserimento nell'ERP, con revisione e approvazione umana. Partirei da una unità operativa e un insieme circoscritto di prodotti e formati; nel confronto verificheremo se questa scelta risponde alla priorità più urgente anche per il Commerciale. Gli effetti sul servizio al cliente andranno verificati, oltre al risparmio di lavoro.

Useremo DualOS per provare il processo su esempi reali e rendere osservabili risultati ed errori. Il DS guiderà priorità, criteri di valore e adozione con i vostri referenti; l'FDE verificherà integrazioni e configurerà agenti, workflow e guardrails per validazione e approvazione. Con IT chiariremo il percorso ERP e il lavoro necessario prima di impegnarci sull'implementazione.

Per prepararci, vi chiederei di portare alcuni ordini rappresentativi, incluse eccezioni, le regole di configurazione disponibili e informazioni sulle modalità di accesso/inserimento nell'ERP. Le cinque domande prioritarie saranno:

1. Quale risultato deve guidare la scelta del primo pilota e chi approva questa priorità?
2. Dove si concentra oggi il tempo di lavorazione degli ordini e quali esempi, comprese le eccezioni, possiamo esaminare?
3. Chi valida le regole di configurazione e quali dati di riferimento affidabili sostengono i controlli?
4. Quali modalità di inserimento/import nell'ERP sono disponibili e quali vincoli tecnici o di accesso dobbiamo considerare?
5. Che cosa considerereste un utilizzo utile e verificabile entro sei settimane e quale disponibilità possono garantire i referenti per discovery e revisione?

Al termine proporrei di concordare una breve discovery e verifica di fattibilità: esaminare ordini storici mentre verifichiamo l'accesso ERP, definire perimetro, criteri di successo, revisori e percorso di inserimento. L'obiettivo resta un primo utilizzo verificato entro sei settimane, subordinato a dati, accessi e disponibilità delle persone. 

Valuteremo anche il riuso verso **UC03, aggiornamento dei listini fornitori**: connessione e accessi ERP, anagrafiche di articoli/componenti, estrazione dai documenti e meccanismi di approvazione e gestione degli errori, dove compatibili. Resterebbero da verificare le corrispondenze dei codici fornitore, le regole sui prezzi e la specifica azione ERP di aggiornamento.

Potete indicarci le disponibilità per il confronto e i referenti da coinvolgere?

Grazie
Taro Casalino

**Fonti e controllo dei requisiti (fuori dall'email):** 01, p.1, sezione 1: risposta breve, uso della piattaforma da DS/FDE, obiettivo/next step, partecipanti e fino a cinque domande prioritarie; 02, p.1: email simulata e priorità Operations/Commerciale/IT, sei settimane condizionate e riuso; 02, p.2: UC01/UC03 e relative dipendenze; 03, p.1: ruoli DS/FDE; 04, pp.2–5: workflow, controlli e verifiche. Incontro, perimetro iniziale e discovery sono proposte; non si dichiarano verifiche già svolte né benefici o tempi garantiti al cliente.

## 9. Esperienze professionali rilevanti

*Step 9 completo: entrambi gli episodi rivisti con l'utente il 12 ottobre 2026. Samsung nominata su sua richiesta; persone non nominate. Documento di consegna non modificato.*

### 1. Priorità in conflitto — output per analisti e responsabile CRM

**Contesto.** Per Samsung ho sviluppato un agente AI per interrogare dati CRM in linguaggio naturale. Durante una demo emersero due esigenze in tensione: gli analisti volevano mantenere risposte approfondite, con testo, grafici e tabelle; la responsabile CRM, acquirente del progetto, chiedeva una sintesi che potesse presentare al management, centrata sui messaggi principali.

**Mia responsabilità.** Ero responsabile del progetto, dalla raccolta dei requisiti e dal confronto con gli stakeholder allo sviluppo tecnico del prodotto.

**Azione concreta.** Ho chiarito che potevamo mantenere l'analisi e offrire due modalità di restituzione. Ho proposto e implementato un toggle: una modalità conservava l'output analitico esistente; l'altra usava una skill per riformulare gli stessi risultati in una sintesi executive. Ho spiegato la soluzione a entrambe le parti e l'ho dimostrata, preservando il formato richiesto dagli analisti e aggiungendo quello utile alla responsabile CRM.

**Risultato.** Entrambe le parti hanno accettato la soluzione e dato feedback positivo durante la prova. Il risultato osservato è stato l'accordo sulle due modalità di output; non attribuisco a questa modifica miglioramenti quantitativi o adozione continuativa non misurati.

**Che cosa cambierei oggi.** Anticiperei le demo con la responsabile CRM per capire prima come intendeva usare e presentare i risultati. Ho impiegato tempo a tradurre la richiesta di un output «presentabile» in un requisito concreto: confrontare prima le esigenze dei due pubblici avrebbe reso più rapida questa definizione.

**Fonti e confini dell'evidenza (note di lavoro):** racconto e conferme dell'utente in questa sessione, 12 ottobre 2026, per ruolo personale, implementazione, demo successiva, accettazione e riflessione. Contesto progetto: `/Users/taro/Projects/samsung-data-agent/docs/prd.md`, sezione 3 (pubblici diversi), e CV `/Users/taro/Library/CloudStorage/OneDrive-AlkemySpa/Desktop/Personal/CV/2026/FTC CV Datapizza.pdf`, p.1. SAM Brainstorming part 2 — trascrizione Wispr Flow (link privato conservato localmente), tratto finale: discussione di due tone of voice, dettaglio per day-by-day e key message per leadership. La call sostiene il confronto sui bisogni e la proposta di due modalità, non documenta il successivo toggle implementato o il suo esito; l'attribuzione personale si basa sulla conferma dell'utente, non sulle etichette generiche dei parlanti. La riunione affronta anche dati e valore analitico: questo episodio riguarda la specifica tensione sul formato di restituzione. Samsung nominata su richiesta dell’utente; persone non nominate nel testo; i dati complessivi del CV non sono attribuiti alla modifica.

### 2. Ostacolo tecnico — rilascio di un agente nel canale Teams

**Contesto.** Per il team CRM di Samsung ho sviluppato un agente AI che verifica le bozze delle email marketing rispetto a brief e template: layout, refusi, link fino alla landing effettiva e promozioni. Produce una sintesi e un report annotato. Il progetto, parte di una gara AI vinta, prevedeva l'utilizzo in Teams, strumento quotidiano del team.

**Mia responsabilità.** Progettazione e sviluppo dell'agente e dell'integrazione Teams; referente tecnico verso l'IT del cliente per il rilascio.

**Ostacolo.** Dopo il rifiuto di un plugin ChatGPT, una risposta dell'IT sulla possibilità di usare Teams era stata interpretata come apertura a un bot. A bot pronto e testato è emerso che il tenant era governato dalla casa madre estera, che vietava app e personalizzazioni: Teams era stato indicato soltanto come canale per scambiare file. Il rilascio era bloccato.

**Azione concreta.** Avevo già testato il bot su un tenant Microsoft 365 dedicato, predisposto con l'IT interno senza intervenire sull'ambiente cliente. Ho esplicitato all'IT locale i passaggi amministrativi necessari, chiedendo se fossero esclusi dalla policy, e preparato un'interfaccia web alternativa. Poiché lo scambio di email non risolveva il blocco, ho chiesto un incontro di persona con sponsor e responsabile IT. Abbiamo concordato di ospitare il bot sul nostro tenant: accesso autorizzato dal proxy cliente e utenti invitati come ospiti, mantenendo Teams come interfaccia attraverso il cambio di tenant. L'IT ha approvato la soluzione.

**Risultato.** Il cliente ha avviato lo sblocco del proxy il giorno stesso; ho fornito i dettagli del tenant e attivato le licenze. Gli utenti accedono ora al bot come ospiti e il servizio funziona, senza richiedere deroghe alla policy della casa madre. L'interfaccia web non è servita come canale utente.

**Che cosa cambierei oggi.** Prima dello sviluppo verificherei per iscritto con IT e security il meccanismo di rilascio e chi controlla il tenant. Coinvolgerei prima il decisore IT in un confronto diretto e concorderei un'alternativa di hosting: una frase ambigua non basta a confermare la fattibilità del rilascio.

**Fonte (nota di lavoro):** racconto completo fornito dall'utente in questa sessione, 12 ottobre 2026; nessuna verifica esterna o metrica aggiunta. Samsung nominata su richiesta dell’utente; persone non nominate. Omesse cifre delle licenze e dettagli non necessari al nesso ostacolo–azione–risultato; il piano web resta distinto dal canale Teams effettivamente utilizzato.
