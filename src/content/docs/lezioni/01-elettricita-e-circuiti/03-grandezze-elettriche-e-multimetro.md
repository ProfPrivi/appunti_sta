---
title: Grandezze Elettriche
description: Work in Progress.
---

# Capitolo 3: Grandezze Elettriche e Misurazioni con il Multimetro

## Introduzione
Questo capitolo si concentra sull'aspetto pratico della misurazione delle grandezze elettriche. L'obiettivo è presentare lo strumento più comune per questo scopo, il multimetro, analizzandone le caratteristiche metrologiche e illustrando i metodi corretti per utilizzarlo in sicurezza all'interno di un circuito.

---

## Sviluppo dell'Argomento

### 3.1 Introduzione ai Resistori: Tipi e Identificazione
In elettronica, un "resistore" è un componente passivo la cui funzione specifica è quella di fornire un valore di resistenza predefinito e controllato in un circuito. Ne esistono di diversi tipi:
* **A filo**: realizzati avvolgendo filo resistivo su un supporto.
* **A impasto**: formati da un impasto di carbone e resina.
* **A strato**: caratterizzati da una sottile pellicola di materiale resistivo.

Un aspetto fondamentale è la capacità di identificare il valore nominale del resistore tramite il **codice dei colori**, composto da strisce colorate stampate sul corpo del componente. 
La lettura si effettua a partire dall'estremità a cui le strisce sono più vicine:
* Le prime due strisce indicano le prime due cifre del valore.
* La terza striscia rappresenta il fattore moltiplicativo (il numero di zeri da aggiungere).
* La quarta striscia (e a volte la quinta) indica la **tolleranza**.

![Tabella del codice dei colori dei resistori](/appunti_sta/immagini/codice_colori.jpg)
*Figura 1: Tabella riassuntiva del codice dei colori per i resistori.*

**Esempio pratico sull'importanza della tolleranza**: La tolleranza specifica la variazione massima percentuale del valore reale rispetto a quello nominale. Questa è una nozione cruciale in ingegneria, in quanto i componenti reali non sono mai perfetti e operano sempre all'interno di un intervallo di valori accettabile.

### 3.2 Il Multimetro: Lo Strumento Tuttofare
Il multimetro, conosciuto comunemente anche come "tester," è lo strumento più versatile e utilizzato in elettronica. È in grado di misurare le tre grandezze fondamentali: tensione (V), corrente (A) e resistenza (Ω). Un tipico multimetro digitale professionale è composto da un display, un selettore rotativo per la grandezza e la portata, e le boccole per i puntali di misura.

Nella metrologia (la scienza della misurazione), è fondamentale comprendere tre caratteristiche chiave dello strumento:
1. **Portata (o Fondo Scala)**: L'intervallo massimo di valori misurabili su una determinata impostazione.
2. **Sensibilità**: La più piccola variazione della grandezza che lo strumento è in grado di rilevare.
3. **Precisione**: La capacità dello strumento di fornire una misurazione vicina al valore reale della grandezza.

![Componenti del Multimetro](/appunti_sta/immagini/multimetro_tester.jpg)
*Figura 2: Panoramica dei comandi e dei connettori di un multimetro digitale.*

**Attenzione agli errori concettuali**: È cruciale non confondere la sensibilità con la precisione. Un multimetro che mostra un valore con molte cifre decimali (es. 2.543 V) ha un'alta sensibilità, ma se la sua precisione è solo del ±1%, quelle ultime cifre rilevate risultano del tutto inaffidabili.

### 3.3 Misura della Tensione (Voltaggio)
Per misurare la tensione, il multimetro deve essere impostato in modalità **voltmetro**. 
La regola d'oro è che un voltmetro deve sempre essere collegato in **parallelo** al componente di cui si desidera misurare la differenza di potenziale. Questo permette allo strumento di "leggere" la tensione tra due punti senza influenzare significativamente il flusso di corrente del circuito principale.

![Misura della tensione in parallelo](/appunti_sta/immagini/misura_tensione_parallelo.jpg)
*Figura 3: Circuito paralello*

![Misura della tensione in parallelo](/appunti_sta/immagini/misura_tensione_parallelo1.jpg)
*Figura 4: Corretto collegamento del voltmetro in parallelo al componente.*

### 3.4 Misura della Corrente (Amperaggio)
Per misurare l'intensità di corrente, il multimetro va impostato in modalità **amperometro**. 
A differenza della tensione, l'amperometro deve essere collegato in **serie** al circuito. Questo richiede fisicamente di interrompere il percorso della corrente per inserire lo strumento, in modo che sia attraversato dalla stessa esatta corrente che scorre nel circuito.

![Misura della corrente in serie](/appunti_sta/immagini/misura_corrente_serie.jpg)
*Figura 5: Corretto collegamento dell'amperometro in serie nel circuito.*

![Misura della corrente in serie](/appunti_sta/immagini/misura_corrente_serie1.jpg)
*Figura 6: Corretto collegamento dell'amperometro in serie nel circuito.*

### 3.5 Misura della Resistenza su un Circuito: il Metodo Volt-Amperometrico
La misurazione diretta della resistenza tramite **ohmmetro** è possibile solo se il componente è fisicamente disconnesso dal resto del circuito. 

![Misura della resistenza con ohmmetro](/appunti_sta/immagini/misura_resistenza_ohmmetro.jpg)
*Figura 7: Misurazione diretta tramite ohmmetro su un resistore isolato.*

Se il circuito è in funzione, si ricorre a un metodo indiretto chiamato **metodo volt-amperometrico**, basato sulla Prima Legge di Ohm:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R = V / I
</div>

Poiché gli strumenti reali non sono ideali (l'amperometro possiede una piccola resistenza interna e il voltmetro una grande resistenza interna), il loro inserimento altera il circuito introducendo un errore sistematico. Per minimizzarlo, si usano due configurazioni strategiche:

1. **Configurazione con Voltmetro a Valle**: Il voltmetro è collegato "a valle" dell'amperometro (in parallelo solo al resistore). L'amperometro misura la corrente totale, mentre il voltmetro legge la tensione corretta. **Utilizzo:** Preferibile per misurare *basse resistenze*, poiché la corrente che sfugge nel voltmetro diventa trascurabile.

![Misura della resistenza con voltmetro a valle](/appunti_sta/immagini/volt_valle.jpg)
*Figura 8: Collegamento con Volmetro a valle*

2. **Configurazione con Voltmetro a Monte**: Il voltmetro è "a monte" dell'amperometro (misura la tensione su resistore + amperometro). L'amperometro misura la corrente corretta. **Utilizzo:** Preferibile per misurare *alte resistenze*, poiché la caduta di tensione introdotta dall'amperometro risulta trascurabile rispetto a quella sul resistore.

![Misura della resistenza con voltmetro a monte](/appunti_sta/immagini/volt_monte.jpg)
*Figura 9: Collegamento con Volmetro a monte*

---

## Sintesi
* **Resistori e Codici**: I resistori sono componenti passivi che forniscono resistenze predefinite; il loro valore e la loro tolleranza si leggono tramite un codice a fasce colorate.
* **Multimetro (Tester)**: Strumento per misurare V, A, e Ω. Le sue caratteristiche chiave sono portata, sensibilità e precisione.
* **Regole di Misurazione**: 
  * Il **Voltmetro** si collega sempre in *parallelo*.
  * L'**Amperometro** si collega sempre in *serie* (aprendo il circuito).
* **Metodo Volt-Amperometrico**: Metodo indiretto per calcolare la resistenza (R=V/I) in circuiti attivi. Si usano configurazioni "a monte" o "a valle" per aggirare le resistenze interne degli strumenti e minimizzare gli errori di misurazione.

---

## Glossario Finale
* **Amperometro**: Strumento di misura o modalità del multimetro utilizzata per misurare l'intensità della corrente elettrica. Si collega sempre in serie.
* **Metrologia**: La scienza che si occupa della misurazione e delle sue applicazioni, studiando concetti come portata, sensibilità e precisione.
* **Ohmmetro**: Modalità del multimetro usata per misurare direttamente il valore di una resistenza. Si utilizza a componente disconnesso dal circuito.
* **Portata (Fondo Scala)**: L'intervallo massimo di valori che uno strumento può misurare con una specifica impostazione.
* **Precisione**: Indica quanto il valore misurato dallo strumento si avvicini al valore reale e assoluto della grandezza.
* **Sensibilità**: La più piccola variazione di grandezza che lo strumento è tecnicamente in grado di rilevare.
* **Tolleranza**: La variazione massima accettabile (espressa in percentuale) tra il valore reale di un componente e il suo valore nominale.
* **Voltmetro**: Strumento di misura o modalità del multimetro utilizzata per misurare la differenza di potenziale (tensione). Si collega sempre in parallelo.