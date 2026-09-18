---
title: Legge di Ohm
description: Dimostrazione su circuito della Legge di Ohm
---

# Lezione di Laboratorio: La Legge di Ohm e le Caratteristiche del LED

## Introduzione
L'obiettivo di questa attività didattica è osservare come si comportano le grandezze elettriche nella pratica, verificando sperimentalmente la Legge di Ohm. Per raggiungere questo scopo, utilizzeremo resistori e LED, concentrandoci sull'analisi delle caratteristiche essenziali di questi ultimi. I Diodi a Emissione Luminosa (LED) sono componenti semiconduttori polarizzati che emettono luce quando sono attraversati da una corrente elettrica. A differenza delle vecchie lampadine a incandescenza, la loro luminosità e durata dipendono strettamente dal controllo accurato della corrente.

---

## Sviluppo dell'Argomento

### 1. Tensione di Soglia (Forward Voltage, V<sub>f</sub>)
Essendo un diodo, un LED necessita di una tensione minima per poter iniziare a condurre corrente e, di conseguenza, ad accendersi. Questa grandezza è definita **Tensione di Soglia** o **Tensione di Caduta Diretta (V<sub>f</sub>)**.
*   Se la tensione applicata è inferiore alla V<sub>f</sub>, il LED rimane spento.
*   Quando la tensione supera la V<sub>f</sub>, il LED inizia a condurre.

Il valore della V<sub>f</sub> non è fisso, ma varia in base al materiale semiconduttore utilizzato, il quale determina anche il colore della luce emessa dal componente. È fondamentale conoscere la V<sub>f</sub> specifica del LED che si intende usare per poter progettare correttamente il circuito.

| Colore del LED | Intervallo di Tensione di Soglia (V<sub>f</sub>) |
| :--- | :--- |
| **Infrarosso** | < 1.9 V |
| **Rosso** | 1.63 V < V<sub>f</sub> < 2.03 V |
| **Arancione** | 2.03 V < V<sub>f</sub> < 2.10 V |
| **Giallo** | 2.10 V < V<sub>f</sub> < 2.18 V |
| **Verde** | 1.9 V < V<sub>f</sub> < 4.0 V |
| **Blu** | 2.48 V < V<sub>f</sub> < 3.7 V |
| **Bianco** | &approx; 3.5 V |

### 2. Corrente di Funzionamento (Forward Current, I<sub>f</sub>)
La **Corrente Diretta (I<sub>f</sub>)** è la corrente che attraversa il LED ed è il fattore primario che ne determina l'effettiva luminosità. 
La maggior parte dei LED standard (quelli da 5mm comunemente impiegati nei kit didattici) è progettata per lavorare in modo ottimale con una corrente nominale compresa tra 15 mA e 20 mA. È di cruciale importanza non oltrepassare la corrente massima dichiarata dal produttore, altrimenti si rischia di danneggiare permanentemente il LED o di accorciarne drasticamente la vita operativa.

### 3. Il Ruolo della Resistenza di Limitazione
Una volta che la tensione supera il valore di soglia (V<sub>f</sub>), la corrente all'interno del LED tende ad aumentare molto rapidamente. Per questo motivo, un LED non può assolutamente essere collegato in modo diretto a una sorgente di tensione che sia superiore alla sua V<sub>f</sub>. 

È sempre d'obbligo inserire una resistenza in serie al LED con lo scopo di limitare la corrente a un valore di sicurezza (I<sub>f_desiderata</sub>). Il valore di questa resistenza (R<sub>lim</sub>) si calcola sfruttando la Prima Legge di Ohm, adattata per questo scopo:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R<sub>lim</sub> = (V<sub>sorgente</sub> - V<sub>f</sub>) / I<sub>f_desiderata</sub>
</div>
<br>

*Dove:*
*   **V<sub>sorgente</sub>** è la tensione fornita dall'alimentatore (es. 5 V o 12 V).
*   **V<sub>f</sub>** è la tensione di soglia del LED in uso (es. 2 V per un LED Rosso).
*   **I<sub>f_desiderata</sub>** è la corrente di funzionamento che vogliamo ottenere (es. 0.015 A, ovvero 15 mA).

> **Esempio Pratico di Calcolo:** Ipotizziamo di voler alimentare un LED Rosso (V<sub>f</sub> = 2.0 V, I<sub>f_desiderata</sub> = 0.015 A) con una sorgente da 5 V DC. 
> Il calcolo sarà: R<sub>lim</sub> = (5 V - 2.0 V) / 0.015 A = 3 V / 0.015 A = **200 &Omega;**.
> Poiché 200 &Omega; non è un valore commerciale standard, le buone pratiche impongono di scegliere il valore standard immediatamente superiore, come ad esempio un resistore da 220 &Omega;, per essere certi che la corrente non sfori il limite massimo.

### 4. Attività Pratica: Misura della Tensione e della Corrente

![Schema del circuito da realizzare](/appunti_sta/immagini/schema_circuito_laboratorio.png)
*Figura 1: Schema del circuito con generatore, resistenza, LED, voltmetro in parallelo e amperometro in serie.*

L'esperimento si divide in quattro fasi operative:

*   **Fase 1: Uso di un generatore (Simulazione)** 
    *   Realizzare su Tinkercad il circuito riportato in figura.
    *   Assegnare un valore a scelta in Ohm alla resistenza e partire con il generatore a 9V.
    *   Avviare la simulazione e annotare in una tabella: tensione del generatore, valore della resistenza, lettura del voltmetro e lettura dell'amperometro. Cambiare due volte la tensione del generatore per ottenere tre righe di dati.
    *   Ripetere l'intero processo per altre due resistenze di valore diverso.
    *   Disegnare un grafico cartesiano (Volt misurati sulle ascisse, Ampere misurati sulle ordinate) riportando i dati raccolti (tre rette distinte per le tre resistenze usate).
*   **Fase 2: Uso di una batteria (Simulazione)**
    *   Sostituire il generatore regolabile con una batteria fissa da 3V.
    *   Ripetere le misurazioni con gli stessi valori di resistenza scelti nella Fase 1 (questa volta ogni tabella avrà una sola riga dati).
    *   Tracciare i nuovi dati sullo stesso grafico precedente.
*   **Fase 3: Realizzazione del circuito reale**
    *   Riprodurre fisicamente le misurazioni effettuate nella Fase 2 assemblando i componenti su una breadboard reale.
*   **Fase 4: Analisi dei dati e Relazione**
    *   Dedurre la relazione tra tensione, corrente e resistenza partendo dai dati della Fase 1 e confrontare i risultati con l'enunciato teorico della Legge di Ohm.
    *   Calcolare la differenza (caduta di tensione) tra la tensione nominale della batteria e quella effettivamente misurata a circuito in funzione durante le Fasi 2 e 3.
    *   Stendere una relazione finale che descriva lo scopo dell'esperimento, includa i dati, i grafici e le fotografie dei circuiti (reali e simulati).
    *   Rispondere alla domanda di riflessione finale: *Ai fini del funzionamento del circuito, quanto è rilevante la direzione (+/-) della corrente? Esiste un modo per far funzionare il circuito anche invertendo il verso della corrente?*.

---

## Sintesi
*   La **Tensione di Soglia (V<sub>f</sub>)** è la tensione minima necessaria per accendere un LED; dipende dal colore della luce emessa.
*   La **Corrente Diretta (I<sub>f</sub>)** determina la luminosità del LED (solitamente tra 15 mA e 20 mA per LED standard); superare questo limite danneggia il componente.
*   Per evitare guasti, un LED in un circuito deve essere sempre protetto da una **resistenza di limitazione (R<sub>lim</sub>)** posta in serie.
*   La formula per calcolare il resistore di limitazione deriva dalla Legge di Ohm: R = (V<sub>sorgente</sub> - V<sub>f</sub>) / I<sub>f</sub>.

---

## Glossario Finale
*   **Breadboard:** Basetta per la prototipazione rapida che permette di montare componenti elettronici senza l'uso di saldature.
*   **Corrente di Funzionamento (I<sub>f</sub>):** La corrente continua che scorre attraverso un diodo LED, responsabile dell'emissione luminosa.
*   **Resistenza di limitazione:** Componente passivo inserito intenzionalmente in serie a un LED per limitare la quantità di corrente che lo attraversa, proteggendolo da bruciature.
*   **Tensione di Soglia (V<sub>f</sub>):** La tensione minima (forward voltage) che un diodo richiede per iniziare a condurre corrente elettrica.