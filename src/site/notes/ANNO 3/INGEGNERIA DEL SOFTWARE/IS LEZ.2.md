---
{"dg-publish":true,"permalink":"/anno-3/ingegneria-del-software/is-lez-2/"}
---

## ⚙️ Il Processo Software

Il **processo software** è definito come la serie di attività necessarie alla realizzazione di un prodotto software che rispetti i tempi, i costi e le caratteristiche di qualità desiderate.

Nel contesto del processo software:

- Si applicano **metodi**, tecniche e strumenti specifici.
    
- Si creano **prodotti**, sia intermedi (documenti di analisi, design) che finali (il codice eseguibile).
    
- Si stabilisce il **controllo gestionale** del progetto per monitorarne l'avanzamento.
    
- Si **garantisce la qualità** del prodotto attraverso attività di verifica e validazione.
    
- Si **governano le modifiche** ai requisiti e al software in modo controllato.
    

### Stadi del Processo

Il ciclo di vita del software si articola in 3 stadi principali:

1. ➡️ **Sviluppo**: La fase di creazione vera e propria del software.
    
2. 🔧 **Manutenzione**: La fase successiva al rilascio, in cui si supporta e si fa evolvere il software.
    
3. 🗑️ **Dismissione**: La fase finale in cui il software viene ritirato dal mercato o dall'uso.
    

Lo stadio di **sviluppo** si suddivide a sua volta in due macro-tipologie di fasi:

- **Fasi di Definizione**: Si occupano del **"cosa"** il software deve fornire. In questa fase si raccolgono i requisiti del cliente e si producono le specifiche formali.
    
- **Fasi di Produzione**: Definiscono il **"come"** realizzare quanto stabilito nelle fasi di definizione. Includono la progettazione dell'architettura, la codifica, l'integrazione dei moduli e il rilascio del prodotto finale al cliente.
    

#### Tipi di Manutenzione 🔧

Lo stadio di manutenzione è cruciale e, a seconda dello scopo, si può classificare in:

- **Correttiva**: Ha lo scopo di eliminare i difetti (fault) che causano guasti (failure) durante l'esecuzione del software.
    
- **Adattativa**: Si occupa di modificare il software per adattarlo a cambiamenti nell'ambiente operativo (es. nuovo sistema operativo, nuove normative).
    
- **Perfettiva** (o **Evolutiva**): È la tipologia più comune. Consiste nell'estendere il software per aggiungere nuove funzionalità o migliorare quelle esistenti in base alle nuove esigenze degli utenti.
    
- **Preventiva** (o **Software Reengineering**): Consiste nell'effettuare modifiche per migliorare la struttura e la qualità interna del software (es. aggiornando la documentazione, migliorando il codice), rendendo più semplici le future attività di manutenzione.
    

### Ciclo di Vita e Modelli

#### Definizione di Ciclo di Vita (IEEE Std 610-12) 📜

Secondo lo standard IEEE, il **ciclo di vita** del software è l'intervallo di tempo che intercorre tra l'istante in cui nasce l'esigenza di un prodotto software e l'istante in cui viene dismesso. Include una serie di fasi in un ordine temporale, ma con una nota fondamentale:

> **Nota del Prof:** Le fasi (requisiti, progetto, codifica, etc.) possono sovrapporsi ed essere eseguite in modo iterativo. Non sono necessariamente una sequenza rigida e lineare. Praticamente, a seconda del modello, puoi tornare indietro o lavorare su più fasi contemporaneamente.

Un **modello di ciclo di vita**, invece, non è solo la definizione temporale, ma rappresenta la **sequenza di fasi e attività** da seguire passo passo per sviluppare il software.

La scelta del modello non è casuale; non esiste un modello "migliore" in assoluto. La scelta deve essere consapevole e si basa su diversi fattori:

- **Tipologia di software** da realizzare.
    
- **Maturità dell'organizzazione**: un team esperto può usare modelli più complessi e agili.
    
- **Metodi e tecnologie** utilizzate.
    
- **Vincoli** dettati dal cliente (es. tempi, budget).
    

#### Modello "Build & Fix" 👎

Se non si adotta alcun modello formale, si finisce per applicare il **Build & Fix**.

- **Come funziona**: Il software viene sviluppato rapidamente e poi modificato ripetutamente ("rilavorato") finché il cliente non è soddisfatto o, più realisticamente, finiscono i soldi.
    
- **Criticità**: Questo approccio è molto costoso e inefficiente. Come sottolineato dal prof, **il cliente non veniva quasi mai soddisfatto**, portando a fallimenti o a software di bassa qualità. Per questo motivo, l'Ingegneria del Software ha introdotto modelli più rigorosi.
    

![Pasted image 20251024164620.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164620.png)

---

## I Modelli di Processo Principali

### Modello a Cascata (Waterfall) 💧

Rappresenta la prima evoluzione strutturata per superare il caos del "Build & Fix". È un modello **sequenziale e rigoroso**. Le fasi sono eseguite una dopo l'altra e, quando una fase è completata e verificata, viene **"congelata"** per non subire modifiche.

**Fasi del Modello a Cascata:**

- **Definizione dei Requisiti**: Si raccolgono i bisogni e le specifiche dell'applicazione. I requisiti vengono documentati in dettaglio per creare una base chiara.
    
- **Progettazione (Design)**: Basandosi sui requisiti, si progetta l'architettura del sistema e si definiscono i dettagli tecnici. Ci si concentra sul "come" il sistema soddisferà i requisiti.
    
- **Sviluppo (Implementation)**: Il codice sorgente viene scritto traducendo il design in codice eseguibile.
    
- **Testing e Integrazione**: I singoli moduli vengono testati e poi integrati. L'intero sistema viene sottoposto a rigorosi test per identificare difetti.
    
- **Consegna e Manutenzione**: Una volta superati i test, il software viene rilasciato. Inizia la fase di manutenzione (correzione bug, implementazione modifiche).
    

![Pasted image 20251024164639.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164639.png)

**Svantaggi del Waterfall:**

- **Poco flessibile**: I requisiti devono essere chiari e stabili fin dall'inizio. Tornare indietro è molto costoso.
    
- **Non "client-friendly"**: Il cliente vede il prodotto solo alla fine. Questa mancanza di comunicazione può creare un divario tra le sue aspettative e il prodotto finale.
    

#### Verifica, Convalida e Certificazione

- **Verifica (Verification)**: "Stiamo costruendo il prodotto nel modo giusto?" Controlla che il prodotto di una fase sia conforme alle specifiche della fase precedente.
    
    - **Nota del Prof**: Si parla di **Static Verification** per i documenti (es. revisione) e **Dynamic Verification** (o Test) per il codice.
        
- **Convalida (Validation)**: "Stiamo costruendo il prodotto giusto?" Controlla che il prodotto finale soddisfi i reali bisogni dell'utente.
    
- **Certificazione**:
    
    - **Nota del Prof**: Non si certifica il prodotto in sé, ma il **processo** o l'**organizzazione** che lo ha sviluppato.
        

![Pasted image 20251024164658.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164658.png)

### Modello a Prototipazione Rapida (Rapid Prototyping) 🚀

Nasce per risolvere il problema principale del Waterfall: il **rischio legato ai requisiti**. L'idea è creare un prototipo, ovvero una versione funzionante ma parziale del sistema, per ottenere un feedback tempestivo dagli **stakeholder** (individui, gruppi o organizzazioni con un interesse nel progetto).

Il prototipo serve per:

- **Elicitation (Elicitazione)**: Aiutare il cliente a scoprire e definire meglio ciò che vuole.
    
- **Validation (Validazione)**: Permettere al cliente di validare i requisiti vedendo qualcosa di concreto.
    

**Vantaggi:**

- Riduce le **incomprensioni** tra cliente e sviluppatori.
    
- Il cliente ha subito un **prototipo da vedere e usare** (es. una GUI), fornendo feedback prezioso.
    

![Pasted image 20251024164716.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164716.png)

![Pasted image 20251024164728.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164728.png)

- **Concetto**: Il prototipo viene creato al solo scopo di definire i requisiti e poi **viene buttato**. Il prodotto finale viene sviluppato da zero.
    
- **Nota del Prof**: Anche se viene buttato, alcune parti (es. una GUI) possono essere riutilizzate.
    
- **Attenzione**: È sconsigliato consegnare un prototipo "throw-away" come prodotto finale per diversi rischi:
    
    - **Requisiti non funzionali**: Il prototipo non è progettato per garantire performance, sicurezza o scalabilità.
        
    - **Mancanza di documentazione**: Rende la manutenzione futura quasi impossibile.
        
    - **Struttura degradata**: Il codice è spesso di bassa qualità, pensato solo per la rappresentazione.
        

![Pasted image 20251024164745.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164745.png)

#### Programmazione Visuale e Prototipazione

Strumenti di programmazione visuale (drag-and-drop) e CASE (Computer-Aided Software Engineering) sono molto usati per creare prototipi velocemente.

![Pasted image 20251024164805.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164805.png)

**Problemi della programmazione visuale:**

- **Difficoltà nel coordinare il team**.
    
- **Mancanza di un'architettura software esplicita**.
    
- **Problemi di manutenzione** a lungo termine.
    

---

## Process Iteration: Sviluppo Incrementale e a Spirale

Poiché i requisiti evolvono quasi sempre, sono nati modelli basati sull'**iterazione**. I due approcci principali sono:

### Sviluppo Incrementale (Incremental Development) 🧱

L'idea è di sviluppare e rilasciare il prodotto in **incrementi successivi** e funzionanti, chiamati **build**.

![Pasted image 20251024164819.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164819.png)

#### Versioni con o senza Architettura Generale (Overall Architecture)

- **Versione con Architettura Generale**:
    
    - **Come funziona**: Prima di iniziare lo sviluppo degli incrementi, si definisce un'architettura software completa del sistema, che funge da guida.
        
    - **Vantaggio**: **Minori rischi di integrazione** tra i vari incrementi, perché tutti seguono una struttura comune.
        
    - **Svantaggio**: Richiede più pianificazione iniziale.
        
    
    ![Pasted image 20251024164959.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024164959.png)
    
- **Versione senza Architettura Generale**:
    
    - **Come funziona**: Si parte direttamente con lo sviluppo dei singoli incrementi, senza una progettazione architetturale preliminare.
        
    - **Vantaggio**: **Risultati iniziali più rapidi** e maggiore flessibilità.
        
    - **Svantaggio (Prof)**: **Molto più rischiosa**. Senza una guida comune, coordinare i team e integrare i moduli diventa complesso e può portare a una struttura finale incoerente.
        
    
    ![Pasted image 20251024165010.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165010.png)
    

#### Impatto sui costi

Il costo totale è la somma del **costo dei build** e del **costo di integrazione**. L'obiettivo è trovare il numero di build che si colloca nella **regione di costo minimo**.

![Pasted image 20251024165021.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165021.png)

#### Confronto: Waterfall vs. Incrementale

![Pasted image 20251024165039.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165039.png)

### Modello a Spirale (Spiral Model) 🌀

È un modello evolutivo che unisce l'iterazione alla gestione sistematica dei rischi. La **dimensione radiale** rappresenta i **costi** accumulati, mentre quella **angolare** il **progresso** del progetto.

Ogni ciclo della spirale attraversa 4 settori:

1. **Determinazione degli Obiettivi**: Si definiscono gli obiettivi dell'iterazione.
    
2. **Analisi dei Rischi (Risk Analysis)**: La fase chiave. Si identificano e risolvono i rischi. Se un rischio è troppo alto, il progetto può essere terminato.
    
3. **Sviluppo e Test (Engineering)**: Si sviluppa la "build" di quel ciclo.
    
4. **Valutazione del Cliente**: Il cliente valuta il risultato e si pianifica il ciclo successivo.
    

![Pasted image 20251024165104.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165104.png)

È molto adatto per progetti grandi e rischiosi, spesso per **software interno**.

![Pasted image 20251024165131.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165131.png)  
![Pasted image 20251024165153.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165153.png)  
![Pasted image 20251024165205.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165205.png)

---

## 🚨 Gestione dei Rischi (Risk Management)

È un processo fondamentale che riguarda **TUTTI I MODELLI E I PROGETTI**.  
Un **rischio** è la probabilità che una circostanza avversa possa avere un impatto negativo sul progetto.

- **Rischi di Progetto (Project Risks)**: Legati a pianificazione, personale e risorse. Es: ritardi, perdita di personale chiave.
    
- **Rischi di Prodotto (Product Risks)**: Legati alla qualità o alle performance del software. Es: modifiche alle specifiche, problemi di prestazioni.
    
- **Rischi di Business (Business Risks)**: Legati a fattori di mercato o tecnologici. Es: un prodotto concorrente esce prima, la tecnologia usata diventa obsoleta.
    

![Pasted image 20251024165217.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165217.png)

Si articola in 4 fasi cicliche:  
![Pasted image 20251024165243.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165243.png)

1. **Identificazione (Risk Identification)**: Si elencano tutti i possibili rischi.  
    ![Pasted image 20251024165258.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165258.png)
    
2. **Analisi (Risk Analysis)**: Si valutano **probabilità** e **impatto** di ogni rischio per dargli una priorità.  
    ![Pasted image 20251024165319.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165319.png)
    
3. **Pianificazione (Risk Planning)**: Si definiscono le strategie per gestire i rischi (Prevenzione, Minimizzazione, Piani di Emergenza).
    
4. **Monitoraggio (Risk Monitoring)**: Si controllano i rischi a intervalli regolari, tipicamente durante le riunioni **SAL (Stato Avanzamento Lavori)**.  
    ![Pasted image 20251024165348.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165348.png)
    

---

## 📚 Altri Modelli di Processo

#### Modello Object-Oriented (a Fontana)

- Le fasi hanno un **overlap**, a significare che si sovrappongono.
    
- **Nota del Prof**: La fase di **Maintenance** ha un diametro inferiore per evidenziare come un buon design OO riduca lo sforzo di manutenzione.
    

![Pasted image 20251024165401.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165401.png)

#### Modello di Ingegneria Concorrente

- Obiettivo: **ridurre tempi e costi**.
    
- Le fasi di sviluppo **coesistono e vengono eseguite in parallelo**.
    

#### Modello basato su Metodi Formali

- Utilizzato per **software critici**.
    
- Le specifiche usano **linguaggi formali basati sulla matematica** per eliminare ambiguità.
    
- Esempio: **Cleanroom Software Engineering**, che mira a software con zero difetti.
    

### Modello Microsoft (Synchronize-and-Stabilize)

È un approccio **iterativo, incrementale e concorrente** basato su:

1. **Sincronizzazione (Synchronize)**: Creazione di una **Daily Build** per integrare il lavoro quotidianamente.
    
2. **Stabilizzazione (Stabilize)**: Rilascio di versioni stabili a intervalli periodici, chiamate **Milestone**.
    

![Pasted image 20251024165452.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165452.png)

#### 3 Fasi di Sviluppo

1. **Planning Phase**: Definizione della visione e del piano.
    
2. **Development Phase**: Sviluppo organizzato in Milestone.
    
3. **Stabilization Phase**: Testing intensivo, bug fixing e preparazione per il rilascio, include il **UI Freeze** (l'interfaccia non può più essere modificata).
    

![Pasted image 20251024165435.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165435.png)  
![Pasted image 20251024165500.png](/img/user/ANNO%203/INGEGNERIA%20DEL%20SOFTWARE/FOTOIS/Pasted%20image%2020251024165500.png)
