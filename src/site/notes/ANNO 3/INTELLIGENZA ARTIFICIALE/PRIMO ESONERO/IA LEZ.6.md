---
{"dg-publish":true,"permalink":"/anno-3/intelligenza-artificiale/primo-esonero/ia-lez-6/"}
---

# 🧠 Agenti basati sulla conoscenza

Gli **agenti basati sulla conoscenza (Knowledge-Based Agents)** sono sistemi che **ragionano sul mondo attraverso formule logiche**.  
L’elemento fondamentale è la **Base di Conoscenza (KB)**, cioè un insieme di **fatti e regole** che descrivono il mondo in modo simbolico.
### La Base di Conoscenza (KB)
La **KB** contiene un insieme di **formule logiche** (proposizioni o predicati) che rappresentano asserzioni sul mondo.
- Quando una formula è accettata come vera **senza essere derivata**, si chiama **assioma**.
- Le formule possono essere **aggiunte**, **rimosse** o **interrogate** attraverso operazioni logiche.
### Operazioni fondamentali
- **TELL(KB, φ)** → inserisce nella KB una nuova formula (nuovo fatto o regola).
- **ASK(KB, α)** → interroga la KB per verificare se α è una **conseguenza logica** delle informazioni memorizzate.
- (**RETRACT(KB, φ)** → facoltativo, rimuove una formula).
### Requisito fondamentale
> Ogni risposta dell’agente deve essere **una conseguenza logica** di ciò che gli è stato detto in precedenza.  
> In simboli: se **KB ⊨ α**, allora α è logicamente conseguente da KB.
#### Agente basato su conoscenza – ciclo operativo
Un agente di questo tipo alterna **percezione, inferenza e azione**, aggiornando continuamente la KB.
![Pasted image 20251112114302.png](/img/user/ANNO%203/INTELLIGENZA%20ARTIFICIALE/IA%20FOTO/Pasted%20image%2020251112114302.png)
L’agente quindi:
1. **Osserva** l’ambiente (percezioni → formule logiche);
2. **Ragiona** deducendo nuove informazioni (inferenza logica);
3. **Agisce** nel mondo e aggiorna la KB.
## 🧱 Approcci alla costruzione
- **Dichiarativo:** si “dice” all’agente _cosa sapere_ (formule logiche esplicite).  
    ➜ più **modulare**, **manutenibile**, **spiegabile**.
- **Procedurale:** si “programma” direttamente il comportamento con codice.  
    ➜ meno flessibile e più difficile da modificare.
## ⚙️ Componenti fondamentali della rappresentazione logica

|Componente|Descrizione|
|---|---|
|**Sintassi**|Definisce i simboli e le regole per costruire frasi logiche.|
|**Semantica**|Stabilisce la corrispondenza tra formule e fatti del mondo (quando una formula è vera).|
|**Inferenza**|Insieme di regole che permettono di derivare nuove formule vere da quelle note.|

> Una KB può essere vista come l’insieme di formule, oppure come una singola formula che le implica tutte.
### ✅ Proprietà dell’inferenza

- **Correttezza (Soundness):** l’algoritmo genera solo formule che sono conseguenze logiche (preserva la verità).
- **Completezza (Completeness):** l’algoritmo può derivare **tutte** le conseguenze logiche possibili.
### Grounding (Radicamento)

È il legame tra **rappresentazione logica** e **mondo reale**.
- Le **percezioni sensoriali** producono formule vere nella KB (es. “Odore percepito → Odore(2,3)”).
- Le **regole generali** derivano da **apprendimento induttivo**, che può essere fallibile.
> In sostanza, il grounding collega le **formule** (mondo simbolico) con **gli stati reali del mondo** (mondo fisico).
### Rappresentazione e mondo
- La **rappresentazione logica** produce **nuovi fatti** (inferenze) coerenti con la realtà.
- La **semantica** collega formule e mondo:
    - “verso il basso” → formule → fatti reali (interpretazione);
    - “verso l’alto” → nuovi fatti logici → nuovi aspetti veri del mondo.
![Pasted image 20251112112059.png](/img/user/ANNO%203/INTELLIGENZA%20ARTIFICIALE/IA%20FOTO/Pasted%20image%2020251112112059.png)

Un’**interpretazione** I stabilisce la corrispondenza tra simboli e elementi reali.  
Una formula **A** è **conseguenza logica** di KB se:  
$$KB ⊨ A \ \text{⇔}\ M(KB) ⊆ M(A)$$
cioè: tutti i modelli che rendono vera KB rendono vera anche A.
-  per M(qualcosa) si intende **l'insieme di tutti i modelli** (cioè le interpretazioni del mondo) in cui **tutte le formule di quel qualcosa sono vere**.
>[!tip] per capire meglio
>Ora passiamo alla semantica:
>
> - $M(p)$ = tutti i mondi in cui **p è vero**
>     
> - $M(q)$= tutti i mondi in cui **q è vero**
>     
> - $M(KB) = M(p \land q) = M(p) \cap M(q)$
> Cioè: l’insieme dei mondi che rendono **vera la KB** è l’intersezione dei mondi che rendono veri **tutti** i fatti in KB.
> 👉 Quindi **più formule ci sono in KB, meno modelli soddisfano tutto**.  
> KB più grande → M(KB) **più piccolo**.


![Pasted image 20251112124104.png](/img/user/ANNO%203/INTELLIGENZA%20ARTIFICIALE/IA%20FOTO/Pasted%20image%2020251112124104.png)

### Ragionamento non monotono
Nella **logica classica** vale la **monotonia**: se $KB ⊨ α$, allora anche $KB ∪ \{β\} ⊨ α$ 
- Se aggiungo una nuova informazione non modifico ciò che prima era vero
Nel ragionamento umano, invece, **nuove informazioni possono invalidare** conclusioni precedenti → **ragionamento non monotòno**.

> Esempio: “Gli uccelli volano; Tweety è un uccello ⟹ vola.”  
> Aggiungo: “Tweety è un pinguino” ⟹ la conclusione non vale più.  
> È tipico del **ragionamento per default** e dell’**assunzione di mondo chiuso**.

