---
title: Calcolo della resistenza equivalente
description: Resistenza equivalente in circuiti
---

# Attività Pratica: Calcolo e Misura della Resistenza Equivalente

## Introduzione
Questa attività laboratoriale ha lo scopo di tradurre in pratica i concetti teorici relativi ai circuiti in serie e in parallelo. L'obiettivo è duplice: calcolare matematicamente la resistenza equivalente di due circuiti misti e, successivamente, verificare l'esattezza dei propri calcoli confrontandoli con le misurazioni strumentali ottenute sia in un ambiente di simulazione virtuale sia su un circuito fisico reale.

---

## Sviluppo dell'Argomento

### 1. Fase Teorica: Il Calcolo Matematico
Il primo passo consiste nell'analizzare gli schemi dei due circuiti proposti e calcolare teoricamente la resistenza equivalente. Per farlo, è necessario scomporre i circuiti identificando quali resistori sono collegati in serie e quali in parallelo, semplificando la rete passo dopo passo.

![Circuito Misto 1 per calcolo Req](/appunti_sta/immagini/circuito_misto_1.png)
*Figura 1: Circuito Misto 1 da analizzare per il calcolo della Resistenza Equivalente.*

![Circuito Misto 2 per calcolo Req](/appunti_sta/immagini/circuito_misto_2.png)
*Figura 2: Circuito Misto 2 da analizzare per il calcolo della Resistenza Equivalente.*

Per ciascun circuito, dopo aver trovato la Resistenza Equivalente (R<sub>eq</sub>), calcolate la Corrente Totale (I) attesa utilizzando la Prima Legge di Ohm:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  I = V<sub>generatore</sub> / R<sub>eq</sub>
</div>

### 2. Fase di Simulazione: Verifica su Tinkercad
Una volta ottenuti i valori teorici, procedete alla verifica virtuale. Riproducete fedelmente i due circuiti sulla piattaforma Tinkercad. 

In particolare su Tinkercad:
*   **Misura della Resistenza:** Verificate il valore della resistenza equivalente (ai capi del generatore) tramite l'uso di un multimetro impostato su Resistenza. Assicuratevi di fare questa misurazione a batteria scollegata. Confrontate il dato letto con il valore di resistenza equivalente che vi siete calcolati teoricamente.
*   **Misura della Corrente:** Alimentando il circuito con la relativa batteria, verificate anche il valore di corrente totale erogata. La misurazione della corrente dovrà essere effettuata inserendo il multimetro (impostato su Amperaggio) in serie e nelle immediate vicinanze del generatore, in modo da misurare il flusso prima che si dirami.

### 3. Fase Pratica: Realizzazione del Circuito Fisico
Le stesse operazioni svolte su Tinkercad devono essere effettuate anche su un circuito fisico reale. 

Cablate i componenti sulla vostra breadboard. Utilizzate un multimetro reale per misurare prima la resistenza equivalente a circuito disalimentato, e poi la corrente totale erogata dalla batteria a circuito acceso. Confrontate i risultati fisici con quelli teorici e simulati, tenendo presente che lievi discrepanze sono normali a causa della tolleranza costruttiva dei componenti reali.

---

## Sintesi
*   **Calcolo Teorico:** Scomposizione dei circuiti in blocchi serie/parallelo per determinare la R<sub>eq</sub> e la Corrente Totale.
*   **Simulazione (Tinkercad):** Uso del multimetro virtuale per misurare la R<sub>eq</sub> a vuoto (senza batteria) e la corrente totale sotto carico.
*   **Laboratorio Fisico:** Cablaggio su breadboard e utilizzo del multimetro reale per replicare le misurazioni effettuate in simulazione.
*   **Analisi Critica:** Confronto tra dati calcolati, simulati e misurati fisicamente per convalidare l'apprendimento pratico.

---

## Glossario Finale
*   **Amperometro:** Strumento (o modalità del multimetro) collegato in serie per misurare l'intensità del flusso di corrente che attraversa un tratto di circuito.
*   **Ohmmetro:** Strumento (o modalità del multimetro) utilizzato per misurare la resistenza elettrica. Si collega in parallelo al componente o all'intero circuito scollegato dall'alimentazione.
*   **Resistenza Equivalente (R<sub>eq</sub>):** Il valore di un singolo resistore ideale che, se sostituisse l'intera rete di resistenze, assorbirebbe la stessa quantità di corrente dal generatore.
*   **Tolleranza:** La variazione massima (espressa in percentuale) accettabile tra il valore nominale di un componente fisico e il suo valore misurato effettivo.