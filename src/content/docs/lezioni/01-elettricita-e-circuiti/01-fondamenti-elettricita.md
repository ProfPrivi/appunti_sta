---
title: Fondamenti di Elettricità
description: Work in Progress.
---

# Capitolo 1: Fondamenti di Elettricità: Carica, Tensione e Corrente

## Introduzione
Questo capitolo introduce i concetti fondamentali che costituiscono la base di ogni fenomeno elettrico . L'obiettivo di questa lezione è fornire una comprensione chiara delle grandezze fisiche di carica, tensione e corrente, utilizzando efficaci analogie pratiche per rendere i concetti teorici molto più accessibili e intuitivi .

---

## Sviluppo dell'Argomento

### 1.1 La Carica Elettrica: il Movimento degli Elettroni
L'elettricità, nel senso più elementare del termine, è il movimento di cariche elettriche . In un conduttore metallico, come può essere un comune filo di rame, il flusso elettrico è costituito da un movimento ordinato di elettroni liberi . 
A livello microscopico, ogni atomo è composto da un nucleo centrale contenente protoni (che hanno carica positiva) e neutroni (neutri), il tutto circondato da elettroni (che hanno carica negativa) . Nei metalli, alcuni degli elettroni più esterni sono definiti "liberi" poiché possono muoversi casualmente in tutte le direzioni . Quando viene applicato un campo elettrico, questi elettroni iniziano a muoversi in modo ordinato, generando di fatto una corrente elettrica .

![Rappresentazione di un elettrone libero e di un atomo in un conduttore](/appunti_sta/immagini/Immagine1.jpg)
*Figura 1: Flusso di elettroni all'interno di un conduttore *

![Struttura dell'atomo di rame](/appunti_sta/immagini/Immagine2.jpg)
*Figura 2: Atomo di rame con nucleo ed elettrone libero *

L'unità di misura della carica elettrica è il Coulomb (C) . Per comprenderne la grandezza, si consideri che la carica di un singolo elettrone (carica elementare) è piccolissima:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  Carica elementare (e) = 1.60 &times; 10&minus;19 C
</div>

Questo significa che per ottenere una carica totale di 1 C, sono necessari circa 6,25 × 10¹⁸ elettroni . 
**Esempio pratico**: La carica può essere paragonata all'acqua all'interno di un serbatoio, dove la quantità totale di acqua rappresenta esattamente la carica elettrica accumulata .

### 1.2 La Tensione (o Differenza di Potenziale): L'Energia che Spinge
La tensione è la grandezza che determina e forza il movimento delle cariche elettriche . Viene definita rigorosamente come la quantità di energia potenziale presente tra due punti di un circuito . Una differenza di carica tra due punti genera la "pressione" necessaria per spingere gli elettroni a muoversi .

La tensione si misura in Volt (V), in onore del fisico italiano Alessandro Volta (inventore della prima batteria chimica) . Il Volt è definito come la differenza di potenziale tra due punti che impartisce un Joule (J) di energia per ogni Coulomb di carica che lo attraversa :

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  1 V = 1 J / 1 C
</div>

![Analogia Idraulica: Tensione come pressione dell'acqua](/appunti_sta/immagini/Immagine3.jpg)
*Figura 3: L'altezza dell'acqua genera la pressione (Tensione) *

**Esempio pratico**: Utilizzando l'analogia idraulica, la tensione è paragonabile alla pressione dell'acqua alla base di un serbatoio o al dislivello tra due serbatoi . Più alta è la pressione, maggiore è l'energia potenziale disponibile, e maggiore sarà il flusso d'acqua una volta aperto il tubo . Senza questa differenza (o "dislivello"), non c'è movimento: l'acqua non scorre se i punti sono allo stesso livello . I generatori (es. pile) mantengono questo dislivello fornendo energia al circuito .

### 1.3 La Corrente Elettrica: Flusso e Intensità
La corrente elettrica è il flusso effettivo di cariche che si muove in un circuito chiuso . Se la tensione è la causa, la corrente è l'effetto . L'intensità di corrente (I) misura quantitativamente questo flusso ed è il rapporto tra la quantità di carica (Q) e l'intervallo di tempo (Δt) in cui fluisce :

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  I = Q / &Delta;t
</div>

L'unità di misura della corrente è l'Ampere (A), dove un Ampere equivale al passaggio di un Coulomb al secondo :

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  1 A = 1 C / 1 s
</div>

![Analogia Idraulica: Corrente come flusso d'acqua](/appunti_sta/immagini/Immagine4.jpg)
*Figura 4: L'Ampere rappresenta il volume d'acqua in transito nel tubo *

![Analogia Idraulica: Corrente come flusso d'acqua](/appunti_sta/immagini/Immagine5.jpg)
*Figura 5: L'Ampere rappresenta il volume d'acqua in transito nel tubo *

Esiste una distinzione tra il moto reale degli elettroni (dal polo negativo al polo positivo) e la **corrente convenzionale**, che per ragioni storiche è stabilita scorrere dal polo positivo al polo negativo . I risultati dell'analisi dei circuiti rimangono identici a prescindere dalla convenzione adottata .

![Flusso convenzionale vs reale](/appunti_sta/immagini/Immagine6.jpg)
*Figura 6: Flusso convenzionale della corrente rispetto al moto degli elettroni*

### 1.4 Corrente Continua vs. Alternata: Due Modalità di Flusso
Il flusso di elettroni può comportarsi in due modi differenti nel tempo:

1. **Corrente Continua (CC)**: L'intensità rimane costante nel tempo . È tipica di pile, batterie, smartphone e computer .
2. **Corrente Alternata (CA)**: L'intensità varia in modo sinusoidale nel tempo, cambiando direzione di moto decine di volte al secondo . Viene usata nella rete domestica e per gli elettrodomestici .

![Grafico CC vs CA](/appunti_sta/immagini/Immagine7.jpg)
*Figura 7: Grafico di tensione nel tempo per CC*

![Grafico CC vs CA](/appunti_sta/immagini/Immagine8.jpg)
*Figura 8: Grafico di tensione nel tempo per CA*

**Esempio Storico (La battaglia delle correnti)**: La corrente alternata, sostenuta da Nikola Tesla, ha prevalso per la distribuzione su larga scala contro la corrente continua di Thomas Edison . Il motivo risiede nell'efficienza: la CA può essere facilmente elevata o abbassata di tensione tramite trasformatori, permettendo il trasporto a lunghe distanze con perdite minime di energia . 

---

## Sintesi
* **Carica Elettrica**: È alla base dell'elettricità, misurata in Coulomb (C). Rappresenta il serbatoio dell'energia .
* **Tensione**: Misurata in Volt (V), è la "pressione" o il dislivello di potenziale che costringe gli elettroni a muoversi nel circuito .
* **Corrente Elettrica**: Misurata in Ampere (A), è la quantità di carica che attraversa il conduttore in un dato lasso di tempo (il flusso) .
* **Tipi di Corrente**: Esistono due tipologie principali, la Corrente Continua (costante) e la Corrente Alternata (variabile e invertibile), ciascuna con applicazioni specifiche .

---

## Glossario Finale
* **Ampere (A)**: Unità di misura della corrente elettrica. Corrisponde a un flusso di 1 Coulomb al secondo .
* **Corrente Alternata (CA)**: Tipo di corrente la cui intensità e direzione variano in modo sinusoidale nel tempo .
* **Corrente Continua (CC)**: Tipo di corrente la cui intensità e direzione rimangono costanti nel tempo .
* **Coulomb (C)**: Unità di misura della carica elettrica .
* **Elettrone libero**: Elettrone situato negli strati più esterni dell'atomo di un metallo, in grado di staccarsi e muoversi generando corrente .
* **Generatore di tensione**: Dispositivo (come una pila) che mantiene una differenza di potenziale in un circuito, fornendo l'energia per muovere le cariche .
* **Volt (V)**: Unità di misura della tensione (o differenza di potenziale). Un Volt equivale a un Joule per Coulomb .
