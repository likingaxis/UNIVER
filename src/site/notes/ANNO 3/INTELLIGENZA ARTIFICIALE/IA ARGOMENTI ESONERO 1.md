---
{"dg-publish":true,"permalink":"/anno-3/intelligenza-artificiale/ia-argomenti-esonero-1/"}
---

### 🏛️ **Parte 1: Fondamenti dell'Intelligenza Artificiale**

Questa sezione introduce i concetti base, le definizioni e i diversi approcci filosofici all'IA.

- **🧠 Introduzione e Cos'è l'IA (Pag. 1)**
    
    - **Agire Umanamente: L'Approccio del Test di Turing**
        
        - **Test di Turing:** Scopo (una macchina è in grado di pensare?), funzionamento (esaminatore umano che interroga via testo) e criterio di superamento.
            
        - **Capacità richieste:** Interpretazione del linguaggio naturale, rappresentazione della conoscenza, ragionamento automatico, apprendimento automatico (Machine Learning).
            
        - **Test di Turing Totale:** Aggiunge l'interazione con il mondo fisico, richiedendo visione artificiale e robotica.
            
    - **Pensare Umanamente: L'Approccio della Modellazione Cognitiva**
        
        - **Metodi di analisi:** Introspezione, sperimentazione psicologica, imaging cerebrale.
            
        - **Scienze Cognitive:** Campo interdisciplinare che unisce modelli computazionali dell'IA e tecniche psicologiche.
            
    - **Agire Razionalmente: L'Approccio degli Agenti Razionali**
        
        - **Agente:** Qualsiasi cosa che agisce.
            
        - **Agente Razionale:** Agisce per ottenere il miglior risultato possibile, anche in condizioni di incertezza.
            

---

### 🤖 **Parte 2: Agenti Intelligenti**

Qui si definisce il paradigma centrale del corso: l'agente. Si analizza come interagisce con l'ambiente e come si misura la sua efficacia.

- **🌍 Agenti e Ambienti (Pag. 2-6)**
    
    - **Definizione di Agente:** Un sistema che percepisce l'ambiente tramite **sensori** e agisce su di esso tramite **attuatori**.
        
    - **Percezione (Percept) e Sequenza Percettiva:** I dati raccolti dai sensori e la storia completa di tutte le percezioni.
        
    - **Funzione Agente:** La mappatura astratta tra sequenze percettive e azioni.
        
    - **Programma Agente:** L'implementazione concreta della funzione agente.
    - **Il Ciclo dell'Agente (4 fasi):** La scomposizione del ciclo in percepire -> decidere -> agire -> aggiornare è una formalizzazione molto utile.
        
- **👍 Comportarsi Correttamente: Il Concetto di Razionalità (Pag. 3-4)**
    
    - **Misure di Prestazione:** Criterio oggettivo per valutare il successo del comportamento di un agente.
        
    - **Definizione di Razionalità:** Dipende da 4 fattori: misura di prestazione, conoscenza pregressa, azioni possibili, sequenza percettiva corrente.
        
    - **Definizione di Agente Razionale:** Per ogni sequenza di percezioni, sceglie l'azione che massimizza il valore atteso della misura di prestazione.
        
    - **Onniscienza vs Razionalità:** Un agente onnisciente conosce l'esito reale delle azioni, un agente razionale massimizza l'esito atteso.
        
    - **Information Gathering (Raccolta di Informazioni) e Autonomia:** La capacità di apprendere dalle proprie percezioni per diventare indipendente dalla conoscenza iniziale del progettista.
        
- **🔍 La Natura degli Ambienti (Pag. 4-6)**
    
    - **Ambiente Operativo (Task Environment):** La descrizione di un problema attraverso il modello **PEAS**:
        
        - **P**erformance (Prestazione)
            
        - **E**nvironment (Ambiente)
            
        - **A**ctuators (Attuatori)
            
        - **S**ensors (Sensori)
            
        - Esempio: Guidatore di taxi automatizzato.
            
    - **Proprietà degli Ambienti Operativi:**
        
        - **Osservabile (Completamente/Parzialmente):** L'agente ha accesso allo stato completo dell'ambiente?
            
        - **Agenti (Singolo/Multiagente):** Ci sono altri agenti nell'ambiente?
            
        - **Deterministico/Stocastico:** L'esito di un'azione è certo o probabilistico?
            
        - **Episodico/Sequenziale:** La decisione corrente dipende dalle decisioni passate?
            
        - **Statico/Dinamico:** L'ambiente cambia mentre l'agente decide? (Semidinamico se cambia solo la misura di prestazione).
            
        - **Discreto/Continuo:** Lo stato, il tempo e le azioni sono finiti o infiniti?
            
        - **Noto/Ignoto:** Le "leggi fisiche" dell'ambiente sono conosciute dall'agente?
            

---

### ⚙️ **Parte 3: La Struttura degli Agenti**

Questa sezione descrive le "ricette" per costruire programmi agente, dai più semplici ai più complessi.

- **🏗️ Architettura e Programmi Agente (Pag. 8)**
    
    - **Equazione fondamentale:** agente = architettura + programma.
        
    - **Sfida dell'IA:** Creare comportamento razionale con codice compatto, evitando tabelle esplicite (impossibili da gestire per la loro dimensione).
        
- **Tipi di Programmi Agente (Pag. 9-14)**
    
    - **1. Agenti Reattivi Semplici:**
        
        - **Funzionamento:** Basati su regole condizione-azione (if-then).
            
        - **Limiti:** Ignorano la storia percettiva, funzionano solo in ambienti completamente osservabili, possono entrare in cicli infiniti.
            
    - **2. Agenti Reattivi Basati su Modello:**
        
        - **Funzionamento:** Mantengono uno **stato interno** per tener traccia del mondo non osservabile.
            
        - **Componenti chiave:** **Modello di transizione** (come evolve il mondo) e **modello sensoriale** (come le percezioni si legano allo stato).
            
    - **3. Agenti Basati su Obiettivi:**
        
        - **Funzionamento:** Oltre allo stato, hanno informazioni sugli **obiettivi** (goal), ovvero situazioni desiderabili.
            
        - **Capacità:** Prendono decisioni considerando il futuro (**ricerca e pianificazione**). Sono più flessibili degli agenti reattivi.
            
    - **4. Agenti Basati sull'Utilità:**
        
        - **Funzionamento:** Usano una **funzione di utilità** che mappa uno stato in un numero reale (grado di "contentezza").
            
        - **Vantaggi:** Gestiscono obiettivi contrastanti e incertezza, scegliendo l'azione che massimizza l'**utilità attesa**.
            
- **🎓 Agenti Capaci di Apprendere (Pag. 13-14)**
    
    - **Vantaggio:** Possono operare in ambienti sconosciuti e migliorare nel tempo.
        
    - **Componenti Astratti:**
        
        - **Elemento di Apprendimento (Learning Element):** Responsabile dei miglioramenti.
            
        - **Elemento Esecutivo (Performance Element):** Sceglie le azioni (è l'agente visto finora).
            
        - **Elemento Critico (Critic):** Fornisce feedback su come sta andando l'agente.
            
        - **Generatore di Problemi (Problem Generator):** Suggerisce azioni esplorative per acquisire nuove esperienze.
            
    - **Rappresentazioni dello Stato del Mondo:**
        
        - **Atomica:** Lo stato è un blocco unico, senza struttura interna.
            
        - **Fattorizzata:** Lo stato è un insieme di variabili/attributi.
            
        - **Strutturata:** Lo stato descrive oggetti e le loro relazioni.
            

---

### 🗺️ **Parte 4: Risolvere i Problemi con la Ricerca**

Questa è una delle sezioni più corpose. Descrive come un agente può trovare una sequenza di azioni per raggiungere un obiettivo quando la soluzione non è ovvia.

- **🎯 Formulazione dei Problemi di Ricerca (Pag. 15-18)**
    
    - **Agente Risolutore di Problemi:** Trova sequenze di azioni per raggiungere uno stato obiettivo.
        
    - **Processo di Risoluzione:**
        
        1. **Formulazione dell'obiettivo.**
            
        2. **Formulazione del problema** (stati, azioni, ecc.).
            
        3. **Ricerca** di una soluzione (sequenza di azioni).
            
        4. **Esecuzione** della soluzione.
            
    - **Definizione Formale di un Problema:**
        
        - **Spazio degli stati.**
            
        - **Stato iniziale.**
            
        - **Azioni(s):** Azioni possibili in uno stato s.
            
        - **Modello di transizione (Risultato(s, a)):** Lo stato risultante.
            
        - **Test di obiettivo.**
            
        - **Funzione di costo dell'azione.**
            
    - **Astrazione:** Il processo di rimuovere dettagli per creare un modello gestibile.
        
	- **Esempi di problemi:** Aspirapolvere, ricerca di itinerari, commesso viaggiatore (TSP), configurazione VLSI.
        
- **🌲 Algoritmi di Ricerca: Concetti Base (Pag. 18-20)**
    
    - **Albero di Ricerca:** Struttura dati creata dall'algoritmo per esplorare i cammini.
        
    - **Nodo:** Struttura dati che contiene: Stato, Padre, Azione, Costo-Cammino.
        
    - **Frontiera (o Coda):** Insieme dei nodi generati ma non ancora espansi.
        
    - **Criteri di Valutazione degli Algoritmi:**
        
        - **Completezza:** Trova sempre una soluzione se esiste?
            
        - **Ottimalità:** Trova la soluzione a costo minimo?
            
        - **Complessità Temporale:** Quanto tempo ci mette?
            
        - **Complessità Spaziale:** Quanta memoria usa?
            
- **🧭 Strategie di Ricerca Non Informata (Cieca) (Pag. 21-24)**
    
    - **Ricerca in Ampiezza (BFS):**
        
        - Espande il nodo più superficiale.
            
        - Completa e ottimale (se i costi sono uniformi).
            
        - Complessità esponenziale O(b^d).
            
    - **Ricerca a Costo Uniforme (Dijkstra):**
        
        - Espande il nodo con il costo di cammino g(n) più basso.
            
        - Completa e ottimale.
            
    - **Ricerca in Profondità (DFS):**
        
        - Espande il nodo più profondo.
            
        - Non completa e non ottimale.
            
        - Bassa complessità spaziale O(bm).
            
    - **Ricerca a Profondità Limitata:** DFS con un limite di profondità.
        
    - **Ricerca ad Approfondimento Iterativo:** Esegue DFS con limiti di profondità crescenti. Unisce i vantaggi di BFS e DFS.
    
	- **Direzione della Ricerca (Avanti vs. Indietro):**
        
    - **Ricerca Bidirezionale:** Cerca simultaneamente in avanti dallo stato iniziale e all'indietro dall'obiettivo.
        
- **💡 Strategie di Ricerca Informata (Euristica) (Pag. 25-34)**
    
    - **Funzione Euristica h(n):** Stima del costo dal nodo n all'obiettivo.
        
    - **Ricerca Best-First Greedy ("Golosa"):**
        
        - Espande il nodo che sembra più vicino all'obiettivo, f(n) = h(n).
            
        - Non completa e non ottimale.
            
    - **Ricerca A*:**
        
        - **Formula chiave:** f(n) = g(n) + h(n).
            
        - g(n) = costo dal nodo iniziale a n.
            
        - h(n) = costo stimato da n all'obiettivo.
            
        - Combina i vantaggi della ricerca a costo uniforme e della greedy.
            
    - **Proprietà delle Euristiche:**
        
        - **Ammissibilità:** Un'euristica è ammissibile se non sovrastima mai il costo reale (h(n) <= h*(n)). **A* con euristica ammissibile è ottimale.**
            
        - **Consistenza (Monotonicità):** Proprietà più forte, implica l'ammissibilità.
            
    - **Ricerca con Memoria Limitata:**
        
        - **IDA* (A* ad Approfondimento Iterativo):** Usa f(n) come limite.
            
        - **RBFS (Ricerca Best-First Ricorsiva):** Simula A* in spazio lineare.
            
        - **SMA* (Simplified Memory-Bounded A*):** Dimentica i nodi peggiori quando la memoria è piena.
            
    - **Generazione di Euristiche:**
        
        - **Problemi Rilassati:** Rimuovere vincoli dal problema originale.
            
        - **Database di Pattern:** Memorizzare i costi esatti per sottoproblemi.
            

---

### ⛰️ **Parte 5: Altre Tipologie di Ricerca**

Questa parte esplora approcci di ricerca alternativi, adatti a problemi diversi da quelli classici "trova il cammino".

- **🔍 Ricerca Locale e Problemi di Ottimizzazione (Pag. 35-39)**
    
    - **Idea:** Non si tiene traccia del cammino, si lavora su uno stato corrente e si cerca di migliorarlo.
        
    - **Panorama dello Spazio degli Stati:** Metafora della superficie con picchi e valli.
        
    - **Hill Climbing ("Scalata della Collina"):**
        
        - Si muove sempre verso lo stato vicino migliore.
            
        - **Problemi:** Massimi locali, plateau (pianori), creste (ridges).
            
        - **Varianti:** Stocastico, con prima scelta, con riavvio casuale.
            
    - **Simulated Annealing:**
        
        - Permette mosse "peggiori" con una probabilità che diminuisce nel tempo (controllata da una "temperatura").
            
        - Aiuta a sfuggire ai massimi locali.
            
    - **Ricerca Local Beam:** Mantiene k stati invece di uno solo e li espande in parallelo.
        
- **🎲 Ricerca in Ambienti Non Deterministici e Parzialmente Osservabili (Pag. 39-45)**
    
    - **Ricerca con Azioni Non Deterministiche:**
        
        - **Alberi di Ricerca AND-OR:** I nodi OR rappresentano le scelte dell'agente, i nodi AND i possibili esiti dell'ambiente.
            
        - Una **soluzione** è un piano condizionale (o strategia).
            
    - **Ricerca con Osservazioni Parziali:**
        
        - **Stato-Credenza (Belief State):** L'insieme di tutti gli stati fisici in cui l'agente potrebbe trovarsi.
            
        - La ricerca avviene nello spazio degli stati-credenza.
            
- **🏃 Agenti per Ricerca Online (Pag. 45-47)**
    
    - **Caratteristica:** L'agente alterna computazione e azione in un ambiente sconosciuto.
        
    - **Ricerca Locale Online:**
        
        - **Hill Climbing Online:** Soffre dei massimi locali.
            
        - **LRTA* (Learning Real-Time A*):** Apprende e aggiorna i valori dell'euristica mentre esplora.
            

---

### 📚 **Parte 6: Agenti Logici**

L'ultima sezione introduce un modo completamente diverso di costruire agenti, basato sulla rappresentazione esplicita della conoscenza e sul ragionamento logico.

- **🧠 Agenti Basati sulla Conoscenza (Pag. 47-48)**
    
    - **Base di Conoscenza (KB - Knowledge Base):** Un insieme di formule che rappresentano asserzioni sul mondo.
        
    - **Operazioni Fondamentali:**
        
        - **Tell:** Aggiungere una nuova formula alla KB.
            
        - **Ask:** Interrogare la KB.
            
    - **Inferenza:** Il processo di derivare nuove formule da quelle esistenti.
        
    - **Approccio Dichiarativo vs Procedurale.**
        
- **📖 Logica Proposizionale (Pag. 49-52)**
    
    - **Sintassi:**
        
        - **Simboli proposizionali** (P, Q, ...).
            
        - **Connettivi logici** (¬, ∧, ∨, ⇒, ⇔).
            
    - **Semantica:**
        
        - **Modello:** Assegnazione di valori di verità (vero/falso) a ogni simbolo.
            
        - **Tavole di Verità:** Definiscono il significato dei connettivi.
            
    - **Concetti per la Dimostrazione di Teoremi:**
        
        - **Equivalenza Logica:** Due formule sono vere nello stesso insieme di modelli.
            
        - **Validità (Tautologia):** Una formula è vera in tutti i modelli.
            
        - **Soddisfacibilità:** Una formula è vera in almeno un modello.
            
    - **Inferenza e Dimostrazioni:**
        
        - **Regole di Inferenza:** Meccanismi per derivare nuove formule (es. **Modus Ponens**).
            
        - **Dimostrazione per Risoluzione:**
            
            - **Forma Normale Congiuntiva (CNF):** Tutte le formule sono scritte come congiunzioni di clausole (disgiunzioni di letterali).
                
            - L'algoritmo di risoluzione è completo per la logica proposizionale.
