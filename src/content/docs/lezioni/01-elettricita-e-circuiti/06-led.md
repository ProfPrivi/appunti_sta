---
title: Il diodo LED
description: Struttura e caratteristiche del LED
---

# Capitolo 6: Il Diodo e il Diodo LED

## Introduzione
Fino ad ora abbiamo studiato componenti come i resistori, che si comportano allo stesso modo indipendentemente dal verso in cui scorre la corrente. In questa lezione facciamo un salto di livello introducendo i **semiconduttori** e, in particolare, il **diodo**. L'obiettivo è comprendere come questo componente agisca da "valvola a senso unico" per l'elettricità e come la sua variante più celebre, il **LED**, debba essere inserita correttamente all'interno di un circuito per emettere luce senza bruciarsi.

---

## Sviluppo dell'Argomento

### 1. Cos'è un Diodo? La Valvola a Senso Unico
Un diodo è un componente elettronico a due terminali realizzato con materiali semiconduttori (solitamente silicio). La sua funzione principale è facilissima da visualizzare: **permette alla corrente elettrica di scorrere in una sola direzione**, bloccandola quasi completamente nella direzione opposta.

I due terminali del diodo hanno nomi specifici:
*   **Anodo (A):** Il polo positivo.
*   **Catodo (K):** Il polo negativo (spesso contrassegnato fisicamente da una fascetta argentata o nera sul componente).

![Simbolo circuitale e aspetto fisico del Diodo](/appunti_sta/immagini/struttura_diodo.jpg)
*Figura 1: Aspetto fisico di un diodo al silicio e suo simbolo nel circuito (la freccia indica la direzione consentita per la corrente).*

**Analogia Pratica:** Immagina il diodo come una valvola di non ritorno in un tubo dell'acqua. L'acqua (la corrente) può spingere lo sportello e passare in un senso. Se l'acqua prova a scorrere al contrario, lo sportello sbatte contro la guarnizione e blocca totalmente il flusso.

### 2. Le due condizioni: Polarizzazione Diretta e Inversa
Il comportamento del diodo dipende da come colleghiamo i terminali della batteria:

1.  **Polarizzazione Diretta:** Colleghiamo il polo positivo della batteria all'Anodo e il negativo al Catodo. La "valvola" si apre e la corrente scorre liberamente. Il diodo si comporta quasi come un filo conduttore chiuso.
2.  **Polarizzazione Inversa:** Invertiamo i collegamenti (positivo al Catodo, negativo all'Anodo). La valvola si chiude ermeticamente e nel circuito non passa corrente (circuito aperto).

*Nota fondamentale:* Quando il diodo è in polarizzazione diretta e conduce corrente, "ruba" una piccola quantità di tensione per funzionare. Questa si chiama **Caduta di Tensione** e per i diodi al silicio è fissa a circa **0,7 V**.

### 3. Il Diodo LED (Light Emitting Diode)
Il LED (Diodo a Emissione di Luce) è un diodo speciale che, quando viene attraversato dalla corrente in polarizzazione diretta, trasforma l'energia elettrica in particelle di luce (fotoni).

Come riconoscere i terminali di un LED fisico?
*   Il "gambetto" (reoforo) più **lungo** è l'**Anodo** (+).
*   Il gambetto più **corto** (o la parte piatta sul bordo della lente in plastica) è il **Catodo** (-).

![Come riconoscere Anodo e Catodo in un LED](/appunti_sta/immagini/riconoscere_led.jpg)
*Figura 2: Identificazione dei terminali di un LED tramite la lunghezza dei reofori e la smussatura del contenitore.*

### 4. Come usare un LED in un circuito (Il calcolo della Resistenza)
I LED sono componenti molto delicati. Se li colleghiamo direttamente a una batteria (ad esempio da 9V), la corrente li attraverserà senza ostacoli, bruciandoli in una frazione di secondo. 
Per questo motivo, **un LED deve SEMPRE essere accompagnato da un resistore collegato in serie**, che faccia da "freno" per limitare la corrente.

Ma come scegliamo il resistore giusto? Utilizziamo la Prima Legge di Ohm (vista nel Capitolo 2). Dobbiamo conoscere due dati tecnici del LED (forniti dal produttore):
1.  **V<sub>LED</sub>**: La caduta di tensione del LED (solitamente circa 2V per i LED rossi o verdi).
2.  **I<sub>LED</sub>**: La corrente ottimale per farlo brillare (solitamente 20 mA, ovvero 0,02 A).

La formula per calcolare il resistore di limitazione è:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R = (V<sub>batteria</sub> - V<sub>LED</sub>) / I<sub>LED</sub>
</div>

> **Esempio Pratico:** Vogliamo accendere un LED rosso (V<sub>LED</sub> = 2V, I<sub>LED</sub> = 0,02A) usando una batteria da 9V. 
> Calcolo: R = (9 - 2) / 0,02 = 7 / 0,02 = **350 &Omega;**.
> Sceglieremo il resistore commerciale più vicino a questo valore (es. 330 &Omega;).

![Circuito con batteria, resistenza e LED](/appunti_sta/immagini/circuito_resistenza_led.jpg)
*Figura 3: Circuito standard per l'accensione di un LED in sicurezza.*

---

## Sintesi
*   Il **Diodo** è un semiconduttore che fa passare la corrente in un solo verso (dall'Anodo al Catodo).
*   Funziona in **Polarizzazione Diretta** (conduce) o **Inversa** (blocca).
*   Il **LED** è un diodo che emette luce quando polarizzato direttamente.
*   Per usare un LED senza bruciarlo è obbligatorio inserire un **resistore in serie** per limitare la corrente.
*   Il resistore si calcola sottraendo la tensione del LED da quella dell'alimentazione e dividendo il risultato per la corrente desiderata.

---

## Glossario Finale
*   **Anodo (A):** Il terminale positivo di un diodo.
*   **Caduta di Tensione:** La quantità di tensione (misurata in Volt) che un componente assorbe per funzionare (es. 0,7V per un diodo al silicio).
*   **Catodo (K):** Il terminale negativo di un diodo.
*   **LED (Light Emitting Diode):** Specifico tipo di diodo progettato per emettere luce quando attraversato da corrente.
*   **Polarizzazione Diretta:** Collegamento elettrico che permette al diodo di condurre corrente.
*   **Polarizzazione Inversa:** Collegamento elettrico che porta il diodo a bloccare il passaggio della corrente.