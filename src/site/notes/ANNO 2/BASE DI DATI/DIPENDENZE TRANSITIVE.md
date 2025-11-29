---
{"dg-publish":true,"permalink":"/anno-2/base-di-dati/dipendenze-transitive/"}
---

## 🧠 Strategia pratica da usare in esame

1. Trova **le chiavi candidate**
    
2. Trova tutte le **FD**
    
3. Per ogni forma normale:
    
    - 1NF: valori atomici?
        
    - 2NF: ci sono FD su **parte della chiave**?
        
    - 3NF: ci sono FD **transitive**?
        

---
## 🧩 Riepilogo visivo

| Forma Normale | Criterio                          | Obiettivo                              |
| ------------- | --------------------------------- | -------------------------------------- |
| **1NF**       | Nessun attributo multivalore      | Tabelle leggibili e gestibili          |
| **2NF**       | Nessuna dipendenza **parziale**   | Elimina ripetizioni legate alla chiave |
| **3NF**       | Nessuna dipendenza **transitiva** | Elimina duplicazione di dati derivati  |
## 🛠️ Come normalizzare in BCNF

### 1. Identifica la FD che **viola la BCNF**

- Deve essere `X → Y` con `X` **non superchiave**
    

### 2. Decomponi in due relazioni:

- Una con: `X → Y`
    
- L’altra con: gli attributi rimanenti
    

### 🔧 Esempio:

Relazione:

```scss

`Esami(Matricola, CodiceCorso, Aula) 

FD: 
CodiceCorso → Aula Matricola, 
CodiceCorso → tutti`
```

→ `CodiceCorso` **non è una chiave**, ma determina `Aula` ⇒ violazione BCNF
Decomposizione:

1. `Corso(CodiceCorso, Aula)`
    
2. `Esami(Matricola, CodiceCorso)`
    

✅ Ora entrambe sono in BCNF

### 🔷 1. **Lossless join**

> Dopo la decomposizione, se faccio un **join tra le nuove relazioni**, devo ottenere **esattamente i dati originali**.

✅ È **obbligatorio**. Se perdi dati → decomposizione **non accettabile**.

BCNF
## 🧩 La tua situazione:

Hai una tabella con:

`nome, cognome → chiave primaria   telefono → attributo non primo`

Ora immagini una dipendenza:


`telefono → nome`

---

## 🔍 Analisi passo per passo:

### 1. `nome, cognome` è **chiave primaria** ✅

→ quindi è una **superchiave**

### 2. `telefono` **non è superchiave** ❌

→ perché non identifica univocamente le righe (più persone potrebbero avere lo stesso numero, o viceversa)

### 3. `nome` è parte della chiave → **attributo primo** ✅

---

## 🎯 Domanda:

> La dipendenza `telefono → nome` è accettabile in 3NF?  
> È accettabile in BCNF?

---

### ✅ In **3NF**: **SI!**

Perché:

- `telefono → nome`
    
- `telefono` **non è superchiave** ❌
    
- ma `nome` è **attributo primo** ✅  
    ➡️ La **3NF lo accetta**
    

---

### ❌ In **BCNF**: **NO!**

Perché:

- In BCNF, **ogni lato sinistro (`X`)** di una dipendenza deve essere **superchiave**
    
- `telefono` **non è superchiave** ❌  
    ➡️ **Violazione della BCNF**
    

---

## ✅ Conclusione finale

|Forma|La tua dipendenza `telefono → nome` è accettata?|
|---|---|
|3NF|✅ **Sì**, perché `nome` è attributo primo|
|BCNF|❌ **No**, perché `telefono` non è superchiave|

---

### 💡 In pratica:

> La **3NF è più flessibile**, ma può nascondere **anomalie**  
> La **BCNF elimina tutte le dipendenze “sospette”**, anche se servono più tabelle

![Pasted image 20250612154522.png](/img/user/ANNO%202/BASE%20DI%20DATI/fotobasi/Pasted%20image%2020250612154522.png)
