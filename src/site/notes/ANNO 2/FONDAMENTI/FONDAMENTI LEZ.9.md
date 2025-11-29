---
{"dg-publish":true,"permalink":"/anno-2/fondamenti/fondamenti-lez-9/"}
---

## Descrizione dell'halting problem 
![Pasted image 20250324182059.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324182059.png)
### Dimostrazione per assurdo TEOREMA 5.5
mettiamo per assurdo che $L_H$ è decidibile ricordiamo che per essere decidibile esiste una macchina T per cui per ogni $(i,x)$ la macchina:
- $T(i,x)$ accetta se $(i,x)$ ∈ LH 
- $T(i,x)$ rigetta se $(i,x)$ ∉ LH
##### Creazione di una macchina $T'$ che sarebbe il complementare
- $T’(i,x)$ accetta se (i,x) ∉ LH 
- $T’(i,x)$ rigetta se (i,x) ∈ LH
$T'$ viene creata a scatola chiusa perché semplicemente prende l'output di $T$ e lo cambia
##### Creazione macchina $T''$
![Pasted image 20250324184055.png|600](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324184055.png)
Creiamo una macchina che sostanzialmente accetta il linguaggio ma non lo decide
#### In teoria dovrebbe funzionare anche con la diagonale
![Pasted image 20250324184614.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324184614.png)
##### Creazione macchina $T^*$
Creiamo una macchina $T*(i)$ che lavora con un solo input in modo che il risultato sia uguale a $T''(i,i)$ 
Ossia, se $i$ è la codifica di una macchina di Turing, allora
-  $T*( i )$ accetta se ( i, i ) ∉ LH , ossia se Ti ( i ) non termina 
- $T*( i )$ non termina se ( i, i ) ∈ LH , ossia se Ti ( i ) termina
tanto con solo $i$ era la stessa cosa
#### Creiamo $T_k$ che è uguale a $T*$ ma
è la macchina con una codifica $k$ della macchina $T^*$ (trasformiamo tutti gli stati e le quintuple in interi) 
abbiamo quindi che $T_k=T^*$
##### Nocciolo della questione
Visto che $T_k$ è una macchina vera e propria possiamo dargli un input $k$ e quindi avremo $T_k(k)$ 
Facciamo chiarezza passo per passo.

---
### 1. **Cos’è T*?**

T* è una **macchina di Turing costruita** nel corso della dimostrazione, tale che:

- prende un intero `i` come input,
    
- e fa **la stessa computazione** che farebbe `T''(i, i)` (cioè una macchina che si comporta diversamente se `(i, i)` ∈ LH o no).

In simboli:

> **T*(i)** = risultato della computazione di **T''(i, i)**
---

### 2. **Cos’è k?**

k è il **codice** (cioè l’indice numerico) della macchina **T***.  
Visto che ogni macchina di Turing può essere codificata con un numero, allora anche **T*** può — e il numero che la rappresenta è **k**.

Quindi:

> **T*** = **Tₖ**  
> (cioè la macchina con codice `k` _è_ proprio la macchina T*)

---

### 3. **T*(k) = Tₖ(k)**

Qui si arriva al paradosso!

Poiché T* = Tₖ, allora fare la computazione **T*(k)** (cioè dare `k` come input alla macchina T*)  
è **la stessa cosa** che fare la computazione **Tₖ(k)**  
(la macchina numero `k`, che si chiama T*, riceve il suo stesso codice `k` come input).

---

### 📉 E cosa succede quando fai Tₖ(k)?

La macchina **si interroga su se stessa**.  
Proprio come una persona che si chiede: _"Non mi fido di me stesso... ma posso fidarmi di questa affermazione?"_ 😵‍💫

E questo porta al paradosso:

- Se Tₖ(k) **accetta**, allora significa che **non dovrebbe accettare** (perché dovrebbe accettare solo se _non_ termina),
    
- Se Tₖ(k) **non termina**, allora significa che **dovrebbe terminare** (perché dovrebbe non terminare solo se _termina_).
    

E quindi… ❌ **Contraddizione!**

<font color="#00b0f0">Così facendo abbiamo visto che esiste un caso in cui non è decidibile e quindi $L_H$ non è decidibile</font>

### SIMULARE A SCATOLA CHIUSA
Sostanzialmente posso sempre modificare l'input per facilitare le cose senza fare scatola aperta
se ho una macchina che vuole vedere Palindromia per 1 e 2 posso sfruttare quella di ab semplicemente mettendo che una volta ricevuto l'input ab esso viene modificato in 12 direttamente sul nastro
![Pasted image 20250324193309.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324193309.png)

## RIDUZIONI MANY-to-ONE(Da sapere a memoria)
Abbiamo progettato una funzione $f : \{1,2\}^* → \{a,b\}^*$ tale che
### 1) **f è totale e calcolabile** – ossia:

▪ è definita per ogni parola **x ∈ {1,2}*** e, inoltre,

▪ esiste una macchina di Turing di tipo trasduttore $T_f$ tale che, per ogni parola **x ∈ {1,2}***,  
la computazione $T_f(x)$ termina con la parola f(x) ∈ {a,b} scritta sul nastro di output.

---

### 2) Per ogni **x ∈ {1,2}*** vale che:

**x ∈ L_P12 se e solo se f(x) ∈ L_PPAL**

▪ che in matematichese si scrive:  
$∀ x ∈ {1,2}* [ x ∈ L_{P12} ⟷ f(x) ∈ L_{PPAL} ]$

---

🔸 La funzione **f** si chiama **riduzione** da $L_{P12}$ a $L_{PPAL}$.

🔸 E si dice che $L_{P12}$ è riducibile a $L_{PPAL}$ e si scrive:  $L_{P12}$ ≼ $L_{PPAL}$

#### Generalizzazione della riducibilità
![Pasted image 20250324195226.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324195226.png)
### Come possiamo sfruttarla
possiamo sfruttare la cosa della riduzione per dire che un linguaggio è decidibile o accettabile basta solo dimostrare la riducibilità tra due linguaggi
poi dice che due linguaggi hanno praticamente stesso input e stesso output solo con indici diversi
![Pasted image 20250324200913.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324200913.png)
![Pasted image 20250324211313.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324211313.png)
![Pasted image 20250324211325.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324211325.png)
![Pasted image 20250324211419.png](/img/user/ANNO%202/FONDAMENTI/fotofond/Pasted%20image%2020250324211419.png)