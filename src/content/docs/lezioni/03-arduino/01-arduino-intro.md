---
title: Cos'è Arduino?
description: Introduzione Arduino
---

# Lezione 1: Cos'è Arduino e le Basi del Physical Computing

## Introduzione
Benvenuti nel mondo di Arduino. Questa lezione ha lo scopo di introdurre una piattaforma che ha rivoluzionato il modo in cui studenti, insegnanti, artisti e appassionati si approcciano alla tecnologia e all'elettronica. Impareremo che cos'è esattamente Arduino, da dove nasce la sua filosofia e come interagisce con il mondo fisico attraverso la lettura e l'emissione di segnali elettrici. L'obiettivo è fornire una chiara mappa mentale del sistema prima di iniziare a collegare i componenti fisici.

---

## Sviluppo dell'Argomento

### 1. Cos'è Arduino (e cosa NON è)
Arduino è uno strumento open source che semplifica enormemente la progettazione e la prototipazione elettronica. È una piattaforma composta da due anime inseparabili: una parte hardware (la scheda fisica) e una parte software open source (l'ambiente in cui scriveremo il codice).

È fondamentale chiarire subito un equivoco comune: Arduino NON è un normale computer, né un giocattolo, e non è costoso. È definito come un **physical computer**, ovvero un mini-elaboratore elettronico adibito al controllo di oggetti nel mondo reale. 

### 2. Le Origini e il Maker Movement
Il progetto è nato in Italia presso l'Interaction Design Institute di Ivrea, ereditando gli scopi del progetto "Wiring": rendere l'elettronica accessibile anche a chi non ha un background ingegneristico. Curiosità: il nome della scheda deriva da quello di un bar di Ivrea, frequentato dai fondatori del progetto (Massimo Banzi e il suo team).
Oggi Arduino è il simbolo indiscusso del **Maker Movement**, la "sottocultura" globale di hobbisti tecnologici e inventori che vivono di comunità online e hardware open source, spesso supportati da iniziative come le fiere "Maker Faire" e riviste come "Make".

### 3. L'Hardware: Il Cuore del Sistema
Il cervello pulsante di ogni scheda Arduino è il **microcontrollore**. Un microcontrollore è un dispositivo elettronico integrato su un unico chip, progettato appositamente per interagire con input esterni e restituire output basati sulle operazioni di un programma caricato nella sua memoria.
Prendiamo come riferimento l'**Arduino UNO**: questa scheda è dotata di un microcontrollore a 8-bit (ATmega328) che viaggia a una velocità di 16MHz e possiede 32KB di memoria Flash. Può sembrare poco rispetto a un PC moderno, ma è una potenza di calcolo perfetta per leggere sensori e muovere motori o robot.
Sulla scheda troviamo inoltre dei **pin** (piedini) di input e output, attraverso i quali il microcontrollore scambia informazioni con l'ambiente esterno. Essendo hardware *Open Source* (licenza Creative Commons), chiunque può legalmente scaricare gli schemi elettrici e costruirsi un clone o sviluppare schede compatibili.

### 4. I Segnali: Come Arduino "sente" e "parla"
Per controllare luci o leggere sensori ambientali, Arduino usa l'elettricità sotto forma di **segnali**. I segnali che attraversano i pin si dividono in due grandi famiglie:

*   **Segnali Digitali:** La quantità di energia può assumere SOLO valori specifici e ben distinti. In Arduino, un segnale digitale può essere solo acceso (ON / HIGH / 5V / 1) oppure spento (OFF / LOW / 0V / 0). Un segnale digitale è immediatamente leggibile dal microcontrollore non appena ne viene discriminato il livello alto o basso.
*   **Segnali Analogici:** Un segnale analogico può assumere *qualsiasi valore* all'interno di un range noto e varia in modo continuo nel tempo (come una curva). Poiché il microcontrollore "ragiona" in digitale, per leggere un segnale analogico deve prima "campionarlo", ovvero convertirlo in una sequenza di bit che ne esprima l'ampiezza in un dato momento.

> **Esempio Pratico:** Un normale interruttore della luce della nostra camera che può essere solo "acceso" o "spento" genera un segnale *digitale*. Al contrario, una manopola (potenziometro) che regola gradualmente il volume di uno stereo o l'intensità di una lampada genera un segnale *analogico*.

---

## Sintesi
*   **Definizione:** Arduino è una piattaforma open source (sia hardware che software) nata per facilitare la prototipazione elettronica.
*   **Physical Computing:** Arduino non è un PC tradizionale, ma un dispositivo progettato per leggere sensori e controllare attuatori fisici nel mondo reale.
*   **Hardware:** Il "cervello" è il microcontrollore, che comunica con l'esterno tramite connettori chiamati Pin.
*   **Segnali Digitali:** Possono assumere solo due stati, ovvero HIGH (5V) o LOW (0V).
*   **Segnali Analogici:** Variano in modo continuo e assumono infiniti valori in un range; necessitano di essere campionati per poter essere letti dal microcontrollore.

---

## Glossario Finale
*   **Maker:** Inventori e appassionati che uniscono tecnologia, design e risorse open source per creare dispositivi in totale autonomia.
*   **Microcontrollore:** Circuito integrato programmabile che costituisce il vero e proprio "cervello" elettronico della scheda Arduino, capace di eseguire lo sketch in memoria.
*   **Open Source:** Filosofia in cui le risorse progettuali (schemi hardware o codici software) sono distribuite liberamente in modo che tutti possano studiarle, usarle o modificarle.
*   **Pin:** I connettori (o piedini) femmina presenti sui bordi della scheda Arduino, utilizzati per collegare fisicamente fili, sensori e attuatori.
*   **Prototipo:** Un modello o modulo iniziale funzionante, sviluppato rapidamente per testare un'idea prima della produzione definitiva.

<button onclick="window.print()" style="padding: 10px 15px; background-color: #dbae1a; color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold;">
  🖨️ Stampa / Salva in PDF
</button>