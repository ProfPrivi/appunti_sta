---
title: Legge di Ohm e Resistori
description: Work in Progress.
---

# Capitolo 2: La Legge di Ohm e il Ruolo dei Resistori

## Introduzione
Questo capitolo approfondisce il concetto di resistenza, una grandezza fondamentale che definisce come un materiale si oppone al passaggio della corrente elettrica. L'obiettivo della lezione è comprendere le leggi scoperte dal fisico Georg Ohm, che governano in modo matematico la stretta relazione tra tensione, corrente e resistenza.

---

## Sviluppo dell'Argomento

### 2.1 La Resistenza: L'Ostacolo al Flusso di Cariche
La resistenza elettrica, indicata con la lettera **R**, è una misura dell'opposizione che un materiale offre al flusso di cariche elettriche. 
Ma perché esiste questa opposizione? A livello microscopico, gli elettroni che si muovono in un conduttore "urtano" continuamente gli ioni del reticolo cristallino del materiale. Questo processo ostacola il loro movimento fluido e, come conseguenza, genera calore: un fenomeno noto come **effetto Joule**.

L'unità di misura della resistenza è l'**Ohm (Ω)**, in onore del fisico tedesco Georg Simon Ohm.

![Analogia Idraulica della Resistenza](/appunti_sta/immagini/analogia_resistenza.jpg)
*Figura 1: Analogia idraulica della resistenza.*

**Esempio pratico**: Continuando con la nostra analogia idraulica, la resistenza può essere paragonata alla larghezza o alla rugosità di un tubo. Un tubo molto stretto o con pareti ruvide offre una maggiore resistenza al flusso dell'acqua, riducendone la portata anche se la pressione (la tensione) rimane costante. In modo del tutto analogo, un conduttore con un'alta resistenza permette il passaggio di una corrente minore a parità di tensione applicata.

### 2.2 La Prima Legge di Ohm
La Prima Legge di Ohm stabilisce la relazione fondamentale tra tensione, corrente e resistenza per i cosiddetti **conduttori ohmici** (tipicamente i metalli mantenuti a una temperatura costante). 
La legge afferma che la resistenza funge da costante di proporzionalità che lega la tensione (V) applicata ai capi del conduttore all'intensità di corrente (I) che lo attraversa.

La formula principale è:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  V = I &middot; R
</div>

Da questa equazione matematica fondamentale, si possono ricavare facilmente le formule inverse, essenziali per il calcolo delle grandezze incognite in un circuito:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  I = V / R <br><br> R = V / I
</div>

![Il Triangolo di Ohm](/appunti_sta/immagini/triangolo_ohm.jpg)
*Figura 2: Il triangolo di Ohm per memorizzare facilmente le formule.*

![Il Triangolo di Ohm](/appunti_sta/immagini/idraulica_ohm.jpg)
*Figura 3: Rappresentazione idraulica della legge di Ohm.*

È importante notare che non tutti i materiali obbediscono a questa regola. I conduttori che seguono questa legge sono chiamati "conduttori ohmici" o "resistori". Esistono invece materiali, come i semiconduttori (es. i diodi e i LED), che sono definiti "non-ohmici", in quanto il loro rapporto V/I non si mantiene costante.

### 2.3 La Seconda Legge di Ohm: Fattori che Determinano la Resistenza
Mentre la Prima Legge si concentra sulla relazione tra le grandezze all'interno di un circuito, la Seconda Legge di Ohm spiega *quali proprietà fisiche e geometriche* di un conduttore determinano il suo specifico valore di resistenza. 

La resistenza di un conduttore dipende da tre fattori fisici principali:
1. Il tipo di materiale di cui è fatto.
2. La sua lunghezza (L).
3. L'area della sua sezione trasversale (A).

La formula che esprime questo concetto è:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  R = &rho; &middot; (L / A)
</div>

In questa formula, **ρ (rho)** indica la **resistività** del materiale. La resistività è una proprietà intrinseca del materiale stesso e non dipende dalle sue dimensioni; si misura in Ohm per metro (Ω·m). Un blocco di rame e un filo di rame avranno resistenze diversissime, ma condivideranno la stessa identica resistività.

**Esempio pratico**: Comprendere questa legge è vitale in elettronica. 
* Se raddoppi la lunghezza (L) di un filo, raddoppi la sua resistenza (la strada per gli elettroni è più lunga).
* Se aumenti lo spessore o la sezione (A) del filo, la resistenza diminuisce, perché fornisci più "spazio" per il passaggio degli elettroni, proprio come allargare un tubo aumenta la portata dell'acqua.

---

## Sintesi
* **La Resistenza (R)**: È l'ostacolo che le cariche incontrano nel loro movimento. Genera calore (effetto Joule) e si misura in Ohm (Ω).
* **Prima Legge di Ohm**: Mette in relazione le grandezze elettriche. Afferma che V = I · R per i conduttori ohmici.
* **Seconda Legge di Ohm**: Afferma che la resistenza dipende dalla geometria del conduttore (lunghezza L, sezione A) e dal materiale (resistività ρ) tramite la formula R = ρ · (L/A).
* **Dipendenza geometrica**: Più un filo è lungo, maggiore è la resistenza. Più un filo è spesso (largo), minore è la resistenza.

---

## Glossario Finale
* **Conduttore Ohmico (o Resistore)**: Un materiale (solitamente un metallo a temperatura costante) per il quale il rapporto tra la tensione applicata e la corrente generata rimane costante.
* **Effetto Joule**: Il fenomeno per cui il passaggio di corrente elettrica attraverso un conduttore (che oppone resistenza) produce calore.
* **Ohm (Ω)**: L'unità di misura della resistenza elettrica nel Sistema Internazionale.
* **Resistività (ρ)**: Una proprietà specifica e intrinseca di un determinato materiale (es. rame, oro, alluminio) che quantifica la sua innata capacità di opporsi al flusso di corrente. Si misura in Ω·m.