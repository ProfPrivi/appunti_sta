---
title: Attività Legge di Ohm
description: Work in Progress.
---

# Lezione Pratica: La Legge di Ohm e le Caratteristiche del LED

## Introduzione
L'obiettivo di questa attività è osservare come si comportano le grandezze elettriche in base alla legge di Ohm. Per farlo, utilizzeremo principalmente resistori e LED, concentrandoci sull'analisi delle caratteristiche essenziali di questi ultimi. I Diodi a Emissione Luminosa (LED) sono componenti semiconduttori polarizzati che emettono luce quando attraversati da corrente; a differenza delle lampadine a incandescenza, la loro luminosità e durata dipendono strettamente dal controllo di tale corrente.

---

## Sviluppo dell'Argomento

### 1. Tensione di Soglia (Forward Voltage, V<sub>f</sub>)
Essendo un diodo, un LED ha bisogno di una tensione minima per iniziare a condurre e quindi ad accendersi, definita Tensione di Soglia o Tensione di Caduta Diretta (V<sub>f</sub>).
*   Quando la tensione applicata è inferiore a V<sub>f</sub>, il LED rimane spento.
*   Quando la tensione supera V<sub>f</sub>, il LED inizia a condurre.

La V<sub>f</sub> non è un valore fisso, ma dipende dal materiale semiconduttore utilizzato, il quale determina a sua volta il colore della luce emessa. È fondamentale conoscere la V<sub>f</sub> del LED specifico per progettare correttamente il circuito.

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
La corrente che attraversa il LED, nota come Corrente Diretta (I<sub>f</sub>), è il fattore principale che ne determina la luminosità.
La maggior parte dei LED standard (da 5mm, usati nei kit didattici) è progettata per operare con una corrente nominale di circa 15 mA - 20 mA. È cruciale non superare la corrente massima specificata dal produttore, poiché una corrente troppo alta può danneggiare permanentemente il LED o ridurne drasticamente la vita operativa.

### 3. Il Ruolo della Resistenza di Limitazione
Poiché la corrente aumenta molto rapidamente una volta superata la V<sub>f</sub>, un LED non può mai essere collegato direttamente a una sorgente di tensione superiore alla sua V<sub>f</sub>. È sempre necessario inserire una resistenza in serie per limitare la corrente a un livello sicuro (I<sub>f_desiderata</sub>).

Il valore di questa resistenza (R<sub>lim</sub>) si calcola applicando in modo specifico la Prima Legge di Ohm (R = V/I):

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R<sub>lim</sub> = (V<sub>sorgente</sub> - V<sub>f</sub>) / I<sub>f_desiderata</sub>
</div>
<br>

Dove V<sub>sorgente</sub> è la tensione dell'alimentatore, V<sub>f</sub> è la tensione di soglia del LED e I<sub>f_desiderata</sub> è la corrente target.

> **Esempio Pratico di Calcolo:** Ipotizziamo di utilizzare un LED Rosso (V<sub>f</sub> = 2.0 V) con una corrente desiderata di 15 mA (0.015 A) e una sorgente a 5 V DC.
> R<sub>lim</sub> = (5 V - 2.0 V) / 0.015 A = 3 V / 0.015 A = **200 &Omega;**.
> Poiché 200 &Omega; non è un valore standard, si sceglierebbe il valore standard superiore successivo, ad esempio 220 &Omega;, per garantire che la corrente non superi il limite massimo.

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R<sub>lim</sub> = (5 V - 2.0 V) / 0.015 A = 3 V / 0.015 A = 200 &Omega;
</div>

### 4. Attività Pratica: Misura della tensione e della corrente su circuito semplice

![Schema del circuito da realizzare](/appunti_sta/immagini/schema_circuito_led.png)
*Figura 1: Schema del circuito con generatore, voltmetro, amperometro, resistenza e LED.*

L'attività si divide nelle seguenti fasi operative:

*   **Fase 1: Uso di un generatore**
    *   Realizzare con Tinkercad il circuito riportato in figura.
    *   Assegnare un valore a scelta alla resistenza e cominciare con il generatore a 9V.
    *   Eseguire la simulazione e preparare una tabella annotando: tensione del generatore, resistenza, lettura del voltmetro e lettura dell'amperometro. Ripetere cambiando due volte il valore del generatore.
    *   Cambiare due volte il valore della resistenza e ripetere le misurazioni creando due ulteriori tabelle.
    *   Preparare un grafico per ogni tabella (Volt in ascissa, Ampere in ordinata) tracciando una retta passante per tre punti; riportare le tre rette insieme in colori diversi.
*   **Fase 2: Uso di una batteria**
    *   Sostituire il generatore con una batteria a 3V.
    *   Effettuare le stesse misurazioni della fase 1, con gli stessi valori di resistenza; ogni tabella avrà una sola riga.
    *   Preparare lo stesso grafico precedente tracciando un punto per ogni resistenza.
*   **Fase 3: Realizzazione del circuito su breadboard**
    *   Effettuare le misurazioni della fase 2 su un circuito reale montato su breadboard.
*   **Fase 4: Analisi dei dati e Relazione**
    *   Stabilire la relazione che lega tensione, corrente e resistenza dai dati della fase 1 e confrontarla con la legge di Ohm.
    *   Calcolare il rapporto fra la caduta di tensione (differenza fra tensione nominale e misurata a circuito funzionante) e la corrente nelle fasi 2 e 3.
    *   Creare una relazione descrivendo l'esperimento, riportando dati, grafici, foto dei circuiti reali e le immagini di Tinkercad.
    *   Rispondere alla riflessione finale: ai fini del funzionamento, quanto è rilevante la direzione (+/-) della corrente? Esiste un modo per far funzionare il circuito invertendo il verso?.

---

## Sintesi
*   I **LED** sono diodi polarizzati che necessitano di una Tensione di Soglia (V<sub>f</sub>) per accendersi, la quale varia in base al colore emesso.
*   La luminosità è determinata dalla **Corrente Diretta (I<sub>f</sub>)**, che per i LED da 5mm si attesta solitamente tra i 15 mA e i 20 mA.
*   Per non bruciare il LED è obbligatorio calcolare e inserire una **resistenza di limitazione (R<sub>lim</sub>)** in serie.
*   L'**esperimento in 4 fasi** permette di verificare strumentalmente la Legge di Ohm (tramite simulazione e breadboard) e misurare le grandezze all'interno di un circuito reale.

---

## Glossario Finale
*   **Corrente Diretta (I<sub>f</sub>):** La corrente operativa raccomandata che deve fluire attraverso il LED per garantirne un'illuminazione sicura e ottimale.
*   **Resistenza di Limitazione (R<sub>lim</sub>):** Componente inserito in serie in un circuito per abbassare la tensione e mantenere la corrente entro limiti sicuri per i componenti sensibili (come i LED).
*   **Tensione di Soglia (V<sub>f</sub>):** La caduta di tensione minima diretta necessaria affinché il materiale semiconduttore del LED inizi a condurre e produca luce.