---
title: Circuiti Elettrici
description: Work in Progress.
---

# Capitolo 4: Circuiti Elettrici: Struttura e Configurazione

## Introduzione
Questo capitolo fornisce una panoramica fondamentale dei circuiti elettrici. L'obiettivo della lezione è definire le componenti di base di un circuito, introdurre il vocabolario tecnico per analizzarne la struttura (la topologia) e studiare le due configurazioni di collegamento più comuni: in serie e in parallelo.

---

## Sviluppo dell'Argomento

### 4.1 Generalità sui Circuiti
Un circuito elettrico è, nella sua definizione più semplice, un percorso completo e chiuso che permette il flusso di corrente, includendo un generatore di tensione come una batteria. I componenti fondamentali di un circuito base includono:
* Un **generatore** (es. una pila, che fornisce l'energia).
* Un **utilizzatore** (es. una lampadina, che trasforma l'energia elettrica in altra forma).
* Dei **conduttori** (i fili che collegano il tutto).

Possiamo distinguere due stati principali in cui può trovarsi un circuito:
* **Circuito chiuso**: È un percorso completo in cui la corrente può fluire liberamente, permettendo all'utilizzatore di funzionare (es. la lampadina si accende).
* **Circuito aperto**: È un percorso interrotto, che ferma istantaneamente il flusso di corrente. Un circuito può aprirsi per diverse ragioni pratiche, come un interruttore lasciato aperto, un filo rotto, o una lampadina fulminata.

![Circuito Chiuso vs Aperto](/appunti_sta/immagini/circuito_chiuso_chiuso.jpg)
![Circuito Chiuso vs Aperto](/appunti_sta/immagini/circuito_chiuso_aperto.jpg)
*Figure 1-2: Differenza tra un circuito chiuso (lampadina accesa) e un circuito aperto (interrotto dall'interruttore).*

Per analizzare i circuiti più complessi, è utile definire alcuni concetti topologici:
1. **Nodo**: Un punto in cui convergono almeno tre rami.
2. **Ramo**: Un tratto di circuito senza diramazioni intermedie.
3. **Maglia**: Un qualsiasi percorso chiuso che si ottiene partendo da un nodo e ritornando allo stesso nodo attraversando rami diversi.

![Topologia dei circuiti: Nodi, Rami e Maglie](/appunti_sta/immagini/nodo.jpg)
![Topologia dei circuiti: Nodi, Rami e Maglie](/appunti_sta/immagini/rami.jpg)
![Topologia dei circuiti: Nodi, Rami e Maglie](/appunti_sta/immagini/maglia.jpg)
*Figura 3-4-5: Identificazione visiva di nodi, rami e maglie in un circuito elettrico.*

### 4.2 Collegamenti in Serie
I componenti sono collegati in **serie** quando sono posti letteralmente l'uno dopo l'altro, creando un *unico percorso* per il flusso della corrente. Un classico esempio pratico è una vecchia stringa di luci di Natale, dove ogni lampadina è collegata in serie con le altre.

Le caratteristiche principali di un circuito in serie sono:
* **Corrente**: La corrente che attraversa ogni singolo componente è esattamente la stessa per tutto il circuito.
* **Tensione**: La tensione totale del generatore si divide tra i vari componenti. La somma delle tensioni su ogni componente è uguale alla tensione totale fornita dal generatore.
* **Resistenza Equivalente**: La resistenza totale (o equivalente) del circuito è semplicemente la somma aritmetica delle singole resistenze dei componenti.

La formula per calcolare la resistenza equivalente in serie è:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R<sub>eqs</sub> = R<sub>1</sub> + R<sub>2</sub> + ... + R<sub>n</sub>
</div>

**Esempio pratico (Il problema della serie)**: Un'importante conseguenza di questo tipo di collegamento è che se uno dei componenti si guasta, si crea un circuito aperto (come una lampadina che si fulmina). Il risultato è che il flusso di corrente si interrompe per l'intero circuito, e *tutti* gli altri componenti smettono di funzionare.

![Circuito in Serie](/appunti_sta/immagini/circuito_serie.jpg)
*Figura 6: Circuito con lampadine collegate in serie.*

### 4.3 Collegamenti in Parallelo
I componenti sono collegati in **parallelo** quando sono connessi in modo da fornire *più percorsi* (rami) separati per il flusso di corrente. Le prese di corrente nelle nostre case sono un perfetto esempio di collegamento in parallelo, in quanto ogni apparecchio funziona in modo del tutto indipendente dagli altri.

Le caratteristiche principali di un circuito in parallelo sono:
* **Tensione**: La tensione è la stessa per tutti i componenti collegati in parallelo.
* **Corrente**: La corrente totale si divide tra i vari rami. La somma delle correnti che scorrono in ciascun ramo è uguale alla corrente totale fornita dal generatore.
* **Resistenza Equivalente**: La resistenza totale di un circuito in parallelo è *sempre inferiore* a quella del singolo resistore con il valore più basso presente nel circuito.

**Analogia dell'Autostrada**: L'aggiunta di un percorso in parallelo riduce l'ostacolo complessivo al flusso di corrente, proprio come l'aggiunta di una nuova corsia a un'autostrada aumenta la capacità di flusso del traffico, riducendo di fatto la resistenza totale.

La formula per calcolare la resistenza equivalente in parallelo è:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  1 / R<sub>eqp</sub> = 1/R<sub>1</sub> + 1/R<sub>2</sub> + ... + 1/R<sub>n</sub>
</div>

Per il caso specifico e molto comune di soli due resistori, la formula si semplifica in:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R<sub>eqp</sub> = (R<sub>1</sub> &middot; R<sub>2</sub>) / (R<sub>1</sub> + R<sub>2</sub>)
</div>

![Circuito in Parallelo](/appunti_sta/immagini/circuito_parallelo.jpg)
*Figura 7: Circuito con lampadine collegate in parallelo.*

### 4.4 Circuiti Misti (Serie-Parallelo)
Un circuito misto è una combinazione di collegamenti in serie e in parallelo. 
Per analizzare questo tipo di circuito e calcolare le grandezze elettriche, è necessario procedere per gradi, **semplificandolo progressivamente**. 

**Strategia di risoluzione**: La strategia consiste nel calcolare per prima cosa la resistenza equivalente dei piccoli gruppi di rami in parallelo. Successivamente, si sommano queste resistenze equivalenti appena trovate a quelle dei componenti collegati in serie, trovando infine la resistenza totale del circuito. 
*Esempio*: In un circuito con lampadine L1, L2, L3 e L4, dove L2 e L3 sono in parallelo tra loro e questo gruppo è in serie con L1 e L4, si calcolerà prima l'equivalente di L2||L3 e poi si sommerà in serie a L1 e L4.

---

## Sintesi
* **Topologia di base**: 
  * Il *Nodo* è l'incrocio (almeno 3 rami).
  * Il *Ramo* è il percorso tra due nodi.
  * La *Maglia* è un anello chiuso.
* **Circuito in Serie**: Un solo percorso per la corrente (I costante). Se un componente si guasta, tutto si spegne. La resistenza equivalente è la somma delle singole resistenze.
* **Circuito in Parallelo**: Più percorsi per la corrente (V costante). Se un ramo si guasta, gli altri continuano a funzionare. La resistenza equivalente diminuisce all'aumentare dei rami.
* **Circuiti Misti**: Si risolvono procedendo per step successivi, accorpando prima i paralleli e poi le serie.

---

## Glossario Finale
* **Circuito aperto**: Un percorso interrotto che impedisce il flusso della corrente elettrica.
* **Circuito chiuso**: Un percorso continuo e non interrotto che permette alla corrente di circolare.
* **Maglia**: Un qualsiasi percorso chiuso all'interno di un circuito, che inizia e termina nello stesso nodo.
* **Nodo**: Punto di congiunzione in un circuito elettrico in cui convergono tre o più rami.
* **Ramo**: Qualsiasi tratto di circuito compreso tra due nodi; è attraversato dalla medesima corrente.
* **Resistenza Equivalente (Req)**: Un valore di resistenza teorico che, se sostituito all'intero gruppo di resistori di un circuito, si comporterebbe esattamente allo stesso modo nei confronti del generatore (assorbendo la stessa corrente totale).