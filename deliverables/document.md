# Prova asincrona - Deployment Strategist DualOS

## 1. Primo incontro con il cliente

### Risposta all'email del cliente

**Oggetto: Re: Primo confronto su DualOS e priorità di lavoro**

Buongiorno,

grazie per aver condiviso i casi e le priorità. Vi propongo un incontro di **60 minuti** per individuare un primo processo su cui ottenere un beneficio verificabile, conciliando la riduzione del lavoro operativo con le esigenze di servizio e vendita e chiarendo l'impegno richiesto a IT.

Coinvolgerei voi, il responsabile Operations/gestione ordini, un operatore, un rappresentante del Commerciale e il referente IT/ERP. Da parte nostra parteciperanno un Deployment Strategist (DS) e un Forward Deployed Engineer (FDE).

Come prima ipotesi valuterei **UC01, acquisizione degli ordini cliente**: estrarre i dati, controllare la configurazione e inserirli nell'ERP dopo revisione e approvazione umana. Partirei da una sola unità operativa e da prodotti e formati circoscritti. Nel confronto verificheremo se questa scelta risponde anche alla priorità più urgente del Commerciale e quali effetti sul servizio al cliente misurare, oltre al risparmio di lavoro.

Il DS guiderà priorità, criteri di valore e adozione con i vostri referenti; l'FDE verificherà le integrazioni e configurerà agenti, workflow e controlli di validazione e approvazione. Useremo DualOS per provare il processo su esempi reali e analizzare risultati ed errori. Con IT chiariremo il percorso ERP e il lavoro necessario prima di impegnarci sull'implementazione.

Per prepararci, vi chiederei alcuni ordini rappresentativi, comprese le eccezioni, le regole di configurazione disponibili e informazioni sulle modalità di accesso e inserimento nell'ERP. Le domande prioritarie saranno:

1. Quale risultato deve guidare la scelta del primo pilota e chi approva questa priorità?
2. Dove si concentra oggi il tempo di lavorazione degli ordini e quali esempi, comprese le eccezioni, possiamo esaminare?
3. Chi valida le regole di configurazione e quali dati di riferimento affidabili sostengono i controlli?
4. Quali modalità di inserimento/import nell'ERP sono disponibili e quali vincoli tecnici o di accesso dobbiamo considerare?
5. Che cosa considerereste un utilizzo utile e verificabile entro sei settimane e quale disponibilità possono garantire i referenti per discovery e revisione?

Al termine concorderei una breve discovery e verifica di fattibilità: esaminare ordini storici e verificare in parallelo il percorso ERP, definendo perimetro, criteri di successo e revisori. L'obiettivo è un primo utilizzo verificato entro **sei settimane**, subordinato a dati, accessi e disponibilità delle persone.

Valuteremo anche il riuso verso **UC03, aggiornamento dei listini fornitori**: connessione e accessi ERP, anagrafiche, estrazione e meccanismi di approvazione e gestione degli errori, dove compatibili. Corrispondenze dei codici fornitore, regole sui prezzi e azione ERP di aggiornamento richiederanno verifiche specifiche.

Potete indicarci le disponibilità per il confronto e i referenti da coinvolgere?

Grazie,  
Taro Casalino

## 2. Scelta delle priorità

La proposta iniziale è partire da UC01, proseguire con UC03 e rimandare UC02, subordinando la scelta definitiva alle verifiche di discovery. Per la classificazione dei dieci casi, la matrice decisionale ponderata e il confronto dei cinque approfonditi, si veda l'allegato.

**Primo pilota — UC01, acquisizione degli ordini cliente.** Risponde direttamente alla richiesta di Operations su un processo centrale e offre un possibile riuso verso UC03. Lo preferisco a UC05 per questa rilevanza operativa, accettando maggiori verifiche su documenti, regole di configurazione e scrittura ERP. Il beneficio va misurato sul tempo complessivo, includendo revisione, correzioni e inserimento: la sola velocità di estrazione non dimostra un risparmio.

**Secondo caso — UC03, aggiornamento dei listini fornitori.** Potrebbe riutilizzare configurazione e accessi ERP, anagrafiche pertinenti, componenti di estrazione compatibili e meccanismi di revisione, approvazione e tracciamento. Restano specifiche le mappature dei codici fornitore, l'interpretazione e le regole dei prezzi e l'azione ERP di aggiornamento. Con Acquisti e IT confronterei sistemi, dati, formati e operazioni prima di stimare il riuso: se l'integrazione di scrittura di UC01 non viene realizzata, non può essere considerata disponibile per UC03.

**Da rimandare — UC02, configurazione in realtà aumentata.** L'interfaccia e il rendering dedicati, gli asset 3D non confermati e il beneficio commerciale da verificare rendono meno credibile un primo utilizzo nel periodo iniziale. Riconsidererei la priorità in presenza di componenti e asset già utilizzabili e di un'esigenza commerciale validata.

**Verifiche decisive e alternativa.** Osserverei ordini rappresentativi con Operations per raccogliere volumi, tempi e correzioni; business e FDE verificherebbero documenti e regole, FDE e IT azione e permessi ERP e controllo dell'approvazione. Concorderei inoltre responsabili e disponibilità dei revisori. Se l'inserimento automatico è bloccato, verificherei prima un import ERP esistente; manterrei l'inserimento manuale solo con beneficio netto concordato, perimetro esplicitamente ridotto e target temporale rivalutato. Se nessun perimetro UC01 resta utile e fattibile, valuterei **UC05, reporting direzionale**, verificando su report storici il lavoro residuo oltre gli strumenti BI, accesso/export e formati finali. Questo cambio richiederebbe di rivalutare anche il secondo caso e la roadmap.

## 3. Definizione del pilota

### Risultato e perimetro

- **UC01:** ridurre il lavoro per trasformare un ordine ricevuto in un ordine controllato, approvato e inserito nell'ERP.
- Gli operatori riceveranno dati strutturati, esiti dei controlli di configurazione e segnalazioni di informazioni mancanti o ambigue da correggere prima dell'inserimento.
- Avvio su **una unità operativa e un ambiente ERP**, con prodotti/configurazioni e formati scelti con Operations per volumi significativi, regole chiare e varietà rappresentativa.
- Esclusi inizialmente estensione a tutte le unità, copertura universale dei formati e inserimento senza approvazione umana; gli ordini fuori perimetro seguono il processo esistente.

### Dati e dipendenze

- Operations fornirà email e allegati storici, corrispondenti ordini ERP controllati ed esempi incompleti, ambigui o con configurazioni non valide.
- Gli esperti valideranno risposte di riferimento, regole ed eccezioni; le anagrafiche di prodotti/componenti dovranno essere affidabili dove necessarie ai controlli.
- IT e FDE verificheranno campi, mappature, permessi e percorso di inserimento, in parallelo all'analisi dei file storici.
- Prima della configurazione servono esempi sufficienti, regole e riferimenti validati, percorso concordato e revisori disponibili.
- L'acquisizione live richiede verifiche separate di accessi e trigger.
- Nessun input o accesso è assunto pronto.

### Lavoro necessario

- Configurare agente, output strutturato e workflow: AI per estrazione/interpretazione, regole esplicite per i controlli esprimibili, revisione e inserimento controllato.
- Agenti, condizioni, attese di approvazione e trace sono documentati; estrazione dai formati selezionati, esecuzione delle regole, correzione/approvazione e specifica azione ERP restano **verifiche necessarie**.
- I **guardrails** comprendono validazione di campi/formati, controlli di configurazione, segnalazione delle ambiguità, permessi limitati e approvazione obbligatoria prima della scrittura.
- Se servono OCR/conversione, componenti per le regole o integrazione ERP aggiuntiva, valutarne impegno e impatto prima di includerli, rivedendo la classe tecnica se emerge **sviluppo aggiuntivo significativo**.
- Applicare il fallback della sezione 2.

### Valore e qualità

Target proposti da validare con il cliente:

- **≥50% di riduzione del tempo medio di lavoro per ordine**, includendo revisione, correzioni e inserimento/import.
- **>95% di ordini corretti prima della correzione umana**, con tutti i campi critici e gli esiti dei controlli corretti.

**Verifica e condizioni:**

- Output falliti o incompleti restano nel denominatore; riconoscere una configurazione non valida è un esito corretto.
- Raccogliere la baseline osservando il processo attuale su lavoro comparabile.
- Concordare dimensione/copertura degli esempi rappresentativi e confrontare gli output con riferimenti validati dagli esperti.
- Riservare esempi distinti da quelli di configurazione/affinamento; se poi usati per migliorare il workflow, sostituirli per la valutazione successiva.
- Rivalutare il target temporale nel fallback manuale.
- I guardrails sono controlli, non misure di valore o garanzie di correttezza.

### Responsabilità

- Il **DS** guida perimetro, criteri, stakeholder, baseline, adozione e roadmap.
- L'**FDE** configura e mantiene soluzione, integrazioni e guardrails, verificando il comportamento e analizzando gli errori.
- Il **responsabile gestione ordini** valida regole, riferimenti e campi critici, rende disponibili i revisori e accetta valore/qualità.
- Gli **operatori** forniscono esempi, valutano, correggono e approvano.
- **IT/responsabile ERP** abilita gli accessi e verifica con FDE mappature, permessi, inserimento e rilascio.
- Il **referente trasformazione/processi** coordina funzioni e risorse e identifica il decisore autorizzato per cambi di perimetro ed estensione.
- Il DS riunisce evidenze business e tecniche per la decisione di prosecuzione.
- Confermare nomi, disponibilità e autorità in discovery.

### Controlli e revisione

- Rischio principale: inserire un ordine plausibile ma errato, anche con configurazione non valida.
- **Revisione di ogni ordine**, risolvendo dati critici mancanti/ambigui e configurazioni non valide; altrimenti usare il processo esistente.
- Approvazione sui dati finali, da rinnovare se cambiano.
- Verificare prevenzione dei duplicati e controllare l'ERP prima di ritentare una scrittura dall'esito incerto.
- Operatori e FDE indagano gli errori, con IT ove necessario, e rivalutano le correzioni su esempi indipendenti.
- Rivedere perimetro/approccio prima dell'estensione se valore o qualità non soddisfano i criteri; sospendere le scritture automatiche se l'approvazione è aggirabile o gli esiti non sono controllabili, applicando il fallback della sezione 2.
- Verificare i revisori autorizzati: i nomi degli Approvers sono descrittivi.
- Concordare test ERP sicuri: possono scrivere realmente e cancellare una run non annulla scritture accettate.

## 4. Roadmap

### Prime sei settimane: milestone, responsabili e condizioni per proseguire

Le settimane decorrono dalla discovery. Il piano punta a un workflow verificato entro la settimana 4, uso operativo controllato nelle settimane 5–6 e decisione finale sui risultati. È un orizzonte condizionato a dati, accessi, capacità DS/FDE e disponibilità cliente da concordare.

| Periodo | Lavoro e risultato osservabile | Responsabile e contributo cliente | Condizione per proseguire |
| --- | --- | --- | --- |
| **1 — Discovery e perimetro** | Scegliere unità, ERP, prodotti e formati; raccogliere esempi e regole validate, avviare la baseline e riservare esempi di valutazione. **Esito:** perimetro, criteri e dipendenze concordati. | **DS**, con FDE, responsabile di processo, operatori e IT. Il cliente conferma revisori e autorità decisionale. | Esempi/regole sufficienti, revisori disponibili e percorso di inserimento plausibile da verificare; altrimenti risolvere le dipendenze o rivedere il perimetro. |
| **2 — Fattibilità e percorso ERP** | Provare estrazione/controlli, anche sui casi difficili; verificare azione ERP, permessi e test sicuri. Scegliere il percorso della sezione 2, completare la baseline e stimare il lavoro aggiuntivo. **Esito:** percorso completo fattibile e lavoro residuo esplicito. | **FDE e IT** per le verifiche tecniche; **DS/responsabile di processo** per utilità e perimetro. | Percorso fattibile, beneficio potenziale sostenuto dalle evidenze e lavoro compatibile con il tempo residuo; altrimenti restringere/ripianificare UC01 o valutare UC05. |
| **3 — Workflow completo** | Configurare estrazione, regole, correzione, approvazione e inserimento; provare guardrails, dati mancanti/non validi, duplicati e recupero da scritture incerte. Gli operatori provano la revisione sugli esempi di sviluppo. **Esito:** versione candidata alla valutazione. | **FDE**, con operatori, responsabile e IT; DS verifica adozione e lavoro di revisione. | Percorso completo funzionante nei test concordati, dati critici gestiti e controlli di approvazione/scrittura dimostrati. Problemi di sicurezza irrisolti bloccano il rilascio. |
| **4 — Valutazione e rilascio** | Valutare sugli esempi riservati correttezza prima delle correzioni e tempo totale, includendo fallimenti e confronto con baseline. **Esito:** rapporto di accettazione; se accettata, pubblicazione/attivazione della versione valutata e preparazione degli operatori. | **DS** coordina; **FDE/operatori** verificano. Il responsabile accetta i risultati business; IT/FDE verificano il rilascio tecnico. | Criteri di qualità/tempo della sezione 3 concordati e soddisfatti, guardrails dimostrati, copertura sufficiente e utenti preparati. Altrimenti correggere e rivalutare su nuovi esempi indipendenti o ripianificare. |
| **5 — Uso operativo controllato** | Lavorare un volume limitato di ordini reali in perimetro, con revisione di ogni ordine; registrare tempi, correzioni, fallimenti, esiti ERP e feedback. **Esito:** utilizzo effettivo da parte degli operatori. | **Operatori/responsabile di processo** per l'uso; FDE per gli errori; DS per beneficio e adozione. | Controlli efficaci e risultati che sostengono la prosecuzione. Sospendere subito le scritture automatiche se approvazione/esiti non sono controllabili; applicare il fallback concordato ove utile. |
| **6 — Risultati e prosecuzione** | Consolidare evidenze, quota di lavoro coperta e attività manuali residue; concordare supporto e verificare riuso UC03. **Esito:** decisione motivata di prosecuzione, revisione, ulteriore valutazione o arresto e condizioni di estensione. | **DS e FDE** presentano evidenze business/tecniche con responsabile e IT; il decisore cliente autorizzato approva prosecuzione/estensione. | Estensione con evidenze adeguate, valore/qualità accettati, operatività controllata e responsabili/risorse impegnati. Volume reale insufficiente richiede ulteriore valutazione circoscritta. |

### Verifica con gli utenti ed eventuale estensione

- **Verifica:** gli operatori provano la revisione in settimana 3, valutano la candidata in settimana 4 e misurano l'uso reale nelle settimane 5–6. Mantengo l'approvazione umana anche dopo una valutazione positiva. Se cambia il perimetro, concordo il target applicabile prima della valutazione. Non ricreare ordini storici in produzione per testarli.
- **Ritardi ERP:** verifico gli accessi in parallelo ai file storici, ma scelgo il percorso di inserimento entro fine settimana 2 per conservare tempo per verifica completa e uso reale. Se serve più tempo, rivedo le date; nel fallback manuale misuro anche l'inserimento.
- **Dipendenze mancanti:** riduco il perimetro solo se conserva lavoro significativo, mantenendo i casi difficili al suo interno; se dati, regole o revisori restano indisponibili, sposto le milestone. Passare a UC05 richiede verificarne le dipendenze e ripianificare il tempo residuo.
- **Estensione e UC03:** la settimana 6 può stabilire riuso e condizioni di avvio, senza promettere un secondo pilota consegnato. Verifico componenti effettivamente realizzati, lavoro specifico e nuove risorse. Ogni ampliamento di prodotti, formati o unità richiede verifiche nel nuovo contesto.

**Trade-off:** fisso una decisione sul percorso ERP entro la settimana 2 e subordino l'uso operativo ai criteri concordati. Se le condizioni non maturano, modifico esplicitamente perimetro o date, preservando controlli ed evidenze; il cambio di caso non garantisce il rispetto delle sei settimane originarie.

## 5. Esperienze professionali rilevanti

### Gestione di stakeholder con priorità in conflitto

- **Contesto:** per Samsung ho sviluppato un agente AI per interrogare dati CRM in linguaggio naturale. Durante una demo, gli analisti chiedevano di mantenere risposte approfondite con testo, grafici e tabelle; la responsabile CRM, acquirente del progetto, voleva una sintesi dei messaggi principali da presentare al management.
- **Mia responsabilità:** gestione del progetto, dalla raccolta dei requisiti e dal confronto con gli stakeholder allo sviluppo tecnico.
- **Azione concreta:** ho chiarito che potevamo mantenere l'analisi e offrire due modalità di restituzione. Ho proposto e implementato un toggle: una modalità conservava l'output analitico; l'altra usava una skill per riformulare gli stessi risultati in una sintesi executive. Ho spiegato e dimostrato la soluzione a entrambe le parti.
- **Risultato:** entrambe le parti hanno accettato le due modalità e dato feedback positivo durante la prova.
- **Che cosa cambierei oggi:** anticiperei le demo con la responsabile CRM per capire come avrebbe usato e presentato i risultati. Tradurre la richiesta di un output «presentabile» in un requisito concreto ha richiesto tempo: confrontare prima le esigenze dei due pubblici avrebbe accelerato questa definizione.

### Gestione di un ostacolo tecnico importante

- **Contesto:** per il team CRM di Samsung ho sviluppato un agente AI che verifica bozze di email marketing rispetto a brief e template: layout, refusi, link fino alla landing effettiva e promozioni. Produce una sintesi e un report annotato. Il progetto, parte di una gara AI vinta, prevedeva l'uso in Teams, strumento quotidiano del team.
- **Mia responsabilità:** progettazione e sviluppo dell'agente e dell'integrazione Teams; referente tecnico verso l'IT cliente per il rilascio.
- **Ostacolo:** dopo il rifiuto di un plugin ChatGPT, una risposta dell'IT sulla possibilità di usare Teams era stata interpretata come apertura a un bot. A bot pronto e testato è emerso che il tenant, governato dalla casa madre estera, vietava app e personalizzazioni: Teams era stato indicato solo per scambiare file. Il rilascio era bloccato.
- **Azione concreta:** avevo testato il bot su un tenant Microsoft 365 dedicato, predisposto con l'IT interno. Ho chiarito all'IT locale i passaggi amministrativi necessari e preparato un'interfaccia web alternativa. Poiché le email non risolvevano il blocco, ho chiesto un incontro di persona con sponsor e responsabile IT. Abbiamo concordato di ospitare il bot sul nostro tenant, con accesso autorizzato dal proxy cliente e utenti invitati come ospiti, mantenendo Teams come interfaccia attraverso il cambio di tenant. L'IT ha approvato la soluzione.
- **Risultato:** il cliente ha avviato lo sblocco del proxy il giorno stesso; ho fornito i dettagli del tenant e attivato le licenze. Gli utenti accedono ora al bot come ospiti e il servizio funziona senza deroghe alla policy della casa madre. L'interfaccia web non è servita come canale utente.
- **Che cosa cambierei oggi:** prima dello sviluppo verificherei per iscritto con IT e security il meccanismo di rilascio e chi controlla il tenant. Coinvolgerei prima il decisore IT in un confronto diretto e concorderei un'alternativa di hosting, senza assumere la fattibilità da una risposta ambigua.

## Tempo effettivo impiegato

Il tempo impiegato finora è stimato in circa 3 ore e 44 minuti sulla base dei timestamp delle sessioni di lavoro con l’AI, escludendo le pause superiori a 5 minuti; la stima include l’attesa delle risposte e non comprende eventuali attività svolte fuori dalla chat.

## Allegato - Valutazione dei casi d'uso

### Classificazione dei dieci casi

Le classi distinguono supporto documentato, verifiche ancora necessarie e lavoro aggiuntivo identificabile. Anche le **capability documentate** richiedono controlli su dati, accessi e configurazione del cliente; il supporto non documentato non è prova di indisponibilità. Componenti esistenti possono modificare la valutazione dello **sviluppo aggiuntivo significativo**. UC10a e UC10b restano componenti di un unico caso, in una sola riga.

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

*UC01: l'inserimento ERP è il perimetro proposto interpretando il requisito di accesso/scrittura, da confermare con il cliente. La prima versione mantiene la revisione di ogni ordine; una revisione limitata alle eccezioni richiederebbe qualità dimostrata. Fonti: Caso aziendale, pp.2–3; Capabilities della piattaforma, pp.2–5.*

### Matrice decisionale ponderata

Ho utilizzato la matrice per selezionare cinque casi da approfondire, bilanciando rilevanza per il business, fattibilità, verifica nel periodo iniziale e riuso. Pesi e punteggi esprimono un giudizio comparativo da rivedere in discovery: non misurano ROI, disponibilità effettiva degli input o probabilità di consegna. Mancano volumi, tempi, costi degli errori e disponibilità del team; solo UC05 dispone esplicitamente di dati consolidati.

#### Criteri e pesi

Scala **1–5**, con valori più alti sempre favorevoli; 2 e 4 indicano valutazioni intermedie. Per L, un punteggio alto significa meno lavoro e dipendenze. Sono valutati i perimetri completi della classificazione, incluse scritture ERP in UC01/UC03, presentazioni in UC05 ed entrambe le componenti di UC10.

| Criterio | Peso | 1 | 3 | 5 |
| --- | --- | --- | --- | --- |
| **I — Impatto potenziale** | 25% | Comodità limitata | Beneficio circoscritto di produttività/qualità | Incidenza su più decisioni operative o commerciali centrali |
| **S — Rilevanza per gli stakeholder** | 20% | Nessuna richiesta identificabile | Esigenza di una funzione nel catalogo | Risposta diretta a una priorità dell'email |
| **F — Compatibilità tecnica** | 15% | Soluzione dedicata oltre i workflow documentati | Workflow plausibile, componenti essenziali da verificare | Risultato completo sostenuto da capability documentate |
| **L — Lavoro e dipendenze favorevoli** | 15% | Sviluppo significativo o dipendenze strutturali | Configurazione/integrazione circoscritta plausibile, impegno da verificare | Input, accessi e regole disponibili; poco lavoro aggiuntivo |
| **V — Valore verificabile in sei settimane** | 15% | Percorso lungo o indiretto | Prime evidenze possibili, con condizioni importanti | Miglioramento utile facilmente osservabile nel periodo |
| **R — Riuso ed estensione** | 10% | Poco lavoro condiviso identificato | Componenti o ampliamenti plausibili | Base diretta per un altro caso e un uso più ampio |

Impatto e stakeholder ricevono insieme il **45%**, compatibilità e lavoro il **30%**; verifica nelle sei settimane e riuso completano il quadro. La ponderazione privilegia le ragioni di business senza perdere i vincoli temporali e tecnici. I pesi sono proposti, non concordati con il cliente.

#### Punteggi e selezione

**Totale = 0,25I + 0,20S + 0,15F + 0,15L + 0,15V + 0,10R**, su scala 1–5.

| Caso | I | S | F | L | V | R | Totale / 5 | Posizione |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| UC01 — Ordini | 4 | 5 | 3 | 3 | 4 | 4 | **3,90** | 1 |
| UC05 — Reporting | 3 | 4 | 4 | 4 | 4 | 3 | **3,65** | 2 |
| UC04 — Assistenza | 4 | 5 | 3 | 2 | 3 | 3 | **3,50** | 3 |
| UC03 — Listini fornitori | 3 | 4 | 3 | 3 | 4 | 4 | **3,45** | 4 |
| UC09 — Prefatture trasporto | 4 | 4 | 3 | 2 | 4 | 3 | **3,45** | 4 |
| UC07 — Gare | 3 | 3 | 3 | 3 | 4 | 3 | 3,15 | 6 |
| UC10 — Previsioni / bassa rotazione | 5 | 3 | 2 | 1 | 2 | 3 | 2,90 | 7 |
| UC06 — Riconciliazione | 4 | 3 | 2 | 1 | 2 | 5 | 2,85 | 8 |
| UC02 — Configurazione AR | 3 | 5 | 1 | 1 | 2 | 2 | 2,55 | 9 |
| UC08 — Conoscenza aziendale | 3 | 2 | 2 | 2 | 2 | 3 | 2,35 | 10 |

I primi cinque sono **UC01, UC05, UC04, UC03 e UC09**. Il pari merito UC03/UC09 non richiede uno spareggio: entrambi rientrano nella selezione. La graduatoria orienta l'approfondimento; la sequenza UC01→UC03 considera poi il riuso effettivo, come spiegato nella sezione 2.

#### Ragioni dei punteggi

- **UC01:** processo centrale richiesto da Operations, beneficio misurabile e possibile riuso UC03; estrazione, regole e ERP da verificare.
- **UC05:** richiesta direzionale, dati consolidati e sintesi documentata; verificare export, presentazioni e beneficio oltre il BI esistente.
- **UC04:** priorità di servizio esplicita, ma dipendenza dal profilo UC06; migliore preparazione non dimostra risoluzione più rapida o fidelizzazione.
- **UC03:** beneficio circoscritto su lavoro e correttezza dei listini, possibile riuso UC01; mappature e aggiornamento ERP specifici.
- **UC09:** possibili benefici su lavoro e addebiti; spesa/anomalie ignote, collegamenti alle spedizioni ed eccezioni tariffarie aumentano le dipendenze.
- **UC07:** preparazione e omissioni verificabili con esperti; criticità commerciale e collegamento alle priorità dell'email meno evidenti.
- **UC10:** alto impatto potenziale su pianificazione/assortimento, non ritorni dimostrati; storico incerto e sviluppo previsionale rallentano le evidenze. Bassa rotazione valutata separatamente.
- **UC06:** fondazione utile a UC04, ma riconciliazione fra unità, responsabilità e integrazioni comportano lavoro strutturale.
- **UC02:** allineamento alla vendita, penalizzato da sviluppo AR dedicato, asset incerti e beneficio commerciale da validare.
- **UC08:** mancano un responsabile identificato e un'attività onerosa specifica; recupero, permessi e immagini da verificare. Supporto non documentato non implica sviluppo significativo.

#### Sensibilità e condizioni di revisione

La selezione può cambiare con nuove evidenze:

- Se le gare risultano commercialmente critiche e prioritarie, aumentare I e S di UC07 di un punto porta il totale da **3,15 a 3,60**, sopra la soglia attuale di 3,45.
- Se UC04 richiede costruire tutta la fondazione UC06, ridurre F da 3 a 2, L da 2 a 1 e V da 3 a 1 porta il totale da **3,50 a 2,90**.

Sono scenari illustrativi, non fatti acquisiti. Prima dell'impegno raccoglierei baseline, conseguenze degli errori, input/accessi utilizzabili, responsabili e disponibilità dei revisori, aggiornando punteggi e selezione se necessario.

*Base informativa: Caso aziendale, pp.1–3; Guida essenziale a DualOS, p.1; Capabilities della piattaforma, pp.2–5. Criteri, pesi e punteggi sono valutazioni proposte sul materiale disponibile.*

### Approfondimento di cinque casi

I cinque casi derivano dalla matrice precedente; la loro posizione nello screening è distinta dalla sequenza pilota/successore. Tutte le soglie sono **target proposti da validare con il cliente**, non risultati misurati. Raccogliere la baseline e confrontare lavoro equivalente, includendo le attività di revisione, correzione e completamento indicate. I controlli umani sono parte del metodo, non metriche di qualità.

| ID | valore atteso e come verificarlo | compatibilità con DualOS | dati e dipendenze | complessità e incertezza motivate | priorità e motivazione |
| --- | --- | --- | --- | --- | --- |
| UC01 | Ridurre di **almeno il 50%** il tempo di lavorazione per ordine rispetto al processo attuale, come target proposto da validare con il cliente. Raccogliere una baseline su ordini rappresentativi e confrontare il processo assistito, includendo revisione, correzioni e inserimento ERP. Accuratezza come requisito di qualità: proposta >95% degli ordini corretti su tutti i campi critici e sugli esiti dei controlli prima della revisione, da validare con il cliente su risposte di riferimento verificate dagli esperti. | **verifiche necessarie**: agenti, output strutturati, workflow e attese di approvazione sono documentati; estrazione dai documenti reali, applicazione delle regole e specifica azione ERP richiedono verifica. Approvazione umana di ogni ordine prima della scrittura. | Esempi rappresentativi, campi richiesti dall'ERP, regole di configurazione/validazione definite con il business, anagrafiche utili ai controlli, azione e permessi ERP verificati, operatori disponibili per baseline e revisione. | Varietà dei documenti, completezza delle regole, errori sui campi critici e affidabilità della scrittura possono aumentare il lavoro. Il tempo di revisione può annullare il beneficio; verificare che l'approvazione sia obbligatoria e riferita ai dati effettivamente scritti. HITL riduce il rischio ma non elimina gli errori approvati per svista. | **Pilota proposto; primo nello screening (3,90/5).** Risposta diretta a Operations su un processo centrale e possibile riuso verso UC03. Preferito a UC05 per rilevanza operativa, accettando maggiori verifiche; subordinato a beneficio netto, qualità e fattibilità. |
| UC05 | Ridurre di **almeno il 60%** il tempo complessivo di preparazione per ciclo rispetto al processo attuale, includendo export, report/presentazioni, revisione e correzioni. Confrontare almeno **3 fascicoli storici rappresentativi** con gli stessi dati e output richiesti. Qualità della bozza: **100%** dei valori numerici riconciliati e **almeno il 90%** dei commenti accettati senza modifiche sostanziali. Prima della diffusione: **0** affermazioni causali prive di riscontro. Target proposti, non risultati misurati. | **capability documentate** per sintesi da dati preparati e report strutturati/HTML; **verifiche necessarie** per accesso/export BI, formati finali incluse presentazioni, coerenza numerica e commenti. Revisione e approvazione del responsabile reporting prima della diffusione. | Export BI autorizzato, definizioni degli indicatori e regole di calcolo/arrotondamento, struttura concordata, report/presentazioni storiche, regole di commento, formati richiesti e responsabile reporting disponibile. I dati consolidati sono dichiarati; accesso e utilizzabilità restano da verificare. | Gli strumenti BI esistenti possono già coprire parte della richiesta. Verificare il lavoro residuo e il beneficio incrementale; export manuali, formattazione e revisioni possono assorbire il risparmio. Interpretazioni causali e produzione delle presentazioni richiedono controlli specifici. | **Alternativa a UC01; secondo nello screening (3,65/5).** Domanda direzionale e dati consolidati favoriscono la verifica. Valutarlo se nessun perimetro UC01 resta utile e fattibile, accertando beneficio oltre il BI esistente. Possibile riuso verso UC10, senza presumere storico o forecasting pronti. |
| UC04 | Ridurre di **almeno il 40%** il tempo operativo per ricostruire il contesto, classificare e preparare l'assegnazione, includendo revisione e correzioni. Confrontare richieste storiche rappresentative con baseline e risposte validate dagli esperti. Target prima delle correzioni: **almeno il 95%** delle richieste con classificazione e team proposto corretti; **0** associazioni errate cliente/ordine nei casi valutati. Target proposti da validare con il cliente. | **verifiche necessarie**: agenti, workflow e output strutturati sostengono l'approccio; accesso al contesto corretto, copertura dello storico e regole di assegnazione richiedono verifica. Il profilo unificato necessario è trattato in UC06. La decisione finale di assegnazione resta all'operatore. | Richieste in ingresso, profilo cliente unificato utilizzabile, ordini e storico di interazioni/pratiche, accessi verificati e regole di classificazione/instradamento; operatori ed esperti disponibili per baseline, verifica e decisione finale. | La dipendenza da UC06 può aumentare sensibilmente il lavoro se il profilo deve essere costruito. Identità ambigue, storico incompleto e revisioni possono compromettere qualità o risparmio; segnalare il contesto mancante senza inventarlo. Miglioramenti nella preparazione non dimostrano tempi di risoluzione inferiori o maggiore fidelizzazione. | **Terzo nello screening (3,50/5).** Risponde alla priorità commerciale di servizio; candidato subordinato a profilo utilizzabile e beneficio netto. Se il profilo manca, valutare prima il lavoro UC06. Estensione ad altri team/unità con nuove verifiche di dati e regole. |
| UC03 | Ridurre di **almeno il 55%** il tempo complessivo per lotto di aggiornamento rispetto al processo attuale, includendo revisione, correzioni e applicazione ERP. Confrontare listini rappresentativi con dimensioni/varietà comparabili e aggiornamenti di riferimento validati dagli esperti. Prima delle correzioni: **almeno il 98%** delle righe di aggiornamento con articolo e prezzo applicabile corretti; **100%** delle corrispondenze note ambigue o mancanti segnalate nel campione valutato. Target proposti da validare con il cliente. | **verifiche necessarie**: output strutturati, workflow e attese di approvazione sono documentati; estrazione, corrispondenze, interpretazione dei prezzi e specifica azione ERP richiedono verifica. Nella prima versione, revisione di tutte le modifiche e approvazione del lotto prima della scrittura. | Listini rappresentativi dei fornitori, anagrafica articoli/componenti, mappature codici fornitore, dati ERP correnti e regole di validazione; specifica azione e permessi di aggiornamento verificati, responsabili disponibili per baseline e revisione. | Formati/strutture eterogenei, mappature insufficienti e significato dei prezzi possono aumentare il lavoro. Usare corrispondenze esatte/regole ove possibile e AI per interpretazione; verificare errori apparentemente validi e costo della revisione. Il riuso UC01 dipende da ERP, formati e anagrafiche effettivamente condivisi; scrittura prezzi e creazione ordini sono azioni distinte. | **Secondo caso proposto; quarto nello screening, a pari merito con UC09 (3,45/5).** La sequenza deriva dal possibile riuso concreto da UC01, da verificare insieme al beneficio netto e alle operazioni specifiche. Effetti più ampi su costi e margini non sono dimostrati. |
| UC09 | Ridurre di **almeno il 45%** il tempo complessivo di controllo rispetto al processo attuale, includendo indagine, revisione e correzioni. Su prefatture storiche rappresentative, validate dagli esperti: rilevare **almeno il 95%** delle anomalie note nei casi con dati sufficienti; **almeno il 90%** delle anomalie segnalate confermate come reali; **100%** dei casi noti con dati insufficienti classificati come non verificabili. Misurare separatamente addebiti ingiustificati confermati in euro e rettifiche effettivamente ottenute. Target proposti da validare con il cliente. | **verifiche necessarie**: workflow e output strutturati sono documentati; estrazione, collegamenti addebito/spedizione/tariffa e calcoli richiedono verifica. Regole e calcoli espliciti per tariffe definite; AI per estrazione e interpretazione delle clausole, con regole validate dal business. Esame umano prima dell'approvazione della fattura come controllo del metodo. | Prefatture PDF/fogli/EDI, contratti e tariffe con eccezioni, registrazioni di spedizioni, volumi, tratte e consegne; collegamenti affidabili e accessi verificati, referenti Logistica/Amministrazione per baseline e validazione dei casi. | Collegamenti mancanti, eccezioni e ambiguità contrattuali possono impedire il controllo o aumentare il lavoro. Dati insufficienti producono uno stato non verificabile, non un esito conforme. Integrazioni o logiche tariffarie estese possono richiedere sviluppo significativo; falsi allarmi e indagini manuali possono assorbire il risparmio. | **Quarto nello screening, a pari merito con UC03 (3,45/5).** Alternativa di controllo finanziario, con beneficio operativo e addebiti evitabili da misurare. Possibile riuso di estrazione/revisione da UC03 e analisi di clausole da UC07; collegamenti e regole tariffarie restano specifici. |

#### Definizioni delle misure

- **Tempo:** riduzione = 1 − tempo del processo assistito / tempo del processo attuale, su lavoro rappresentativo comparabile. Includere tutte le attività indicate nella tabella, anche inserimento manuale/import o indagine. Il target UC01 va rivalutato se cambia il perimetro, come nella sezione 2.
- **UC01:** ordini con tutti i campi critici e gli esiti dei controlli corretti / tutti gli ordini valutati, prima della correzione umana. Output falliti/incompleti restano nel denominatore; una media fra campi non deve nascondere errori critici. Valutazione e controlli sono descritti nella sezione 3.
- **UC05:** riconciliare ogni valore con l'export BI approvato o con calcoli/arrotondamenti concordati; un valore obbligatorio mancante impedisce di considerare completo il fascicolo. Commenti accettati senza modifiche sostanziali a fatto, interpretazione o utilità / tutti i commenti richiesti, prima delle correzioni: le omissioni sono fallimenti, le sole modifiche stilistiche non lo sono. Prima della diffusione, approvare il fascicolo e correggere/rimuovere affermazioni causali prive di riscontro, distinguendo le ipotesi. Tre fascicoli storici danno evidenza iniziale, non certezza statistica né obbligo di tre cicli mensili live nelle sei settimane.
- **UC04:** richieste con classificazione e team entrambi corretti / tutte le richieste valutate, prima delle correzioni; output mancanti/falliti non sono corretti. Segnalare contesto mancante o ambiguo all'operatore. Zero associazioni errate è un criterio del campione, non una garanzia sui casi futuri.
- **UC03:** righe con articolo interno e prezzo applicabile corretti / tutte le righe di aggiornamento richieste; omissioni e output falliti contano come errori. Rilevazione delle ambiguità = righe ambigue/non abbinate segnalate / tutte quelle note nel campione validato dagli esperti. Misurare prima della correzione umana; resta obbligatoria l'approvazione del lotto.
- **UC09:** rilevazione = anomalie reali segnalate / anomalie reali note nei casi con dati sufficienti; precisione = anomalie reali confermate / tutte le segnalazioni di anomalia. Rilevazione dei non verificabili = casi correttamente identificati / tutti quelli noti con evidenza insufficiente. Includere tutti gli addebiti campionati, riportando quanti sono verificabili/non verificabili; questi ultimi restano separati dagli allarmi e non sono conformi. Distinguere addebiti ingiustificati confermati in euro da rettifiche effettivamente ottenute.

*Fonti: Caso aziendale, pp.2–3; Capabilities della piattaforma, pp.2–5. Metriche, soglie e priorità sono la proposta valutata sul materiale disponibile; non sono disponibili risparmi o accuratezze misurati.*
