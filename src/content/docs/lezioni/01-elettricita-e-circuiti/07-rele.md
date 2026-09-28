---
title: Relè
description: Work in Progress.
---

# Lezione Teorica: Il Relè Elettromeccanico e il Diodo di Flyback

## Introduzione
Benvenuti nel mondo dei relè. Il relè può essere compreso essenzialmente come un "interruttore controllato elettricamente", ovvero un dispositivo che permette di controllare il flusso di corrente in un circuito ad alta potenza (o alta tensione) utilizzando un semplice segnale elettrico a bassa potenza. Questa straordinaria capacità di isolamento tra il circuito di controllo e quello di carico è la sua caratteristica più distintiva. Tale peculiarità rende i relè componenti indispensabili in una vasta gamma di applicazioni, che spaziano dall'automotive alla domotica, fino ai sistemi di controllo industriale e all'informatica.

---

## Sviluppo dell'Argomento

### 1. Cos'è un Relè? Il Principio di Funzionamento
Un relè elettromeccanico sfrutta un principio fisico elementare ma estremamente potente: l'elettromagnetismo. Il cuore del relè è costituito da una **bobina**, che consiste in un avvolgimento di filo di rame attorno a un nucleo ferromagnetico. Quando una corrente elettrica fluisce attraverso questa bobina, essa si comporta a tutti gli effetti come un elettromagnete, generando un campo magnetico.

Questo campo magnetico produce una forza di attrazione che agisce su una parte meccanica mobile, spesso chiamata ancora o armatura. Il movimento dell'ancora è progettato meccanicamente per spostare una serie di contatti elettrici, i quali a loro volta aprono o chiudono il circuito di carico. Quando la corrente nella bobina viene interrotta, il campo magnetico scompare e una molla di richiamo riporta immediatamente l'ancora e i contatti nella loro posizione di riposo.

La vera potenza di questo meccanismo risiede nel concetto di **"isolamento galvanico"**: la capacità di separare fisicamente il circuito di controllo da quello di carico. Il segnale elettrico a bassa potenza che attiva la bobina non possiede alcuna connessione elettrica diretta con la corrente che fluisce attraverso i contatti. Il ponte di comunicazione tra i due circuiti è di natura puramente magnetica e meccanica. Questo significa che è possibile pilotare carichi ad alta tensione (come una lampada a 220V) impiegando un segnale a bassa tensione (come i 5V provenienti da una scheda di sviluppo tipo Arduino), annullando il rischio che l'alta tensione possa danneggiare il delicato circuito di controllo.

### 2. Anatomia di un Relè: Componenti e Terminologia
Per comprendere a fondo il funzionamento del relè, è essenziale conoscerne i componenti principali e la relativa terminologia tecnica:

*   **Bobina (Pin 5-8):** È la parte di controllo. I suoi terminali (spesso etichettati come A1 e A2) sono i punti in cui viene applicata la tensione per creare il campo magnetico.
*   **Contatti Elettrici:** Rappresentano la parte di potenza, gestendo il flusso di corrente nel circuito di carico. Tipicamente sono tre e si distinguono per il loro stato in condizioni di riposo:
    *   **COM (Comune) (Pin 1-12):** È il terminale che fa sempre parte del circuito di carico, collegandosi alternativamente a uno degli altri due contatti.
    *   **NO (Normalmente Aperto) (Pin 7):** In condizioni di riposo, questo contatto risulta aperto. Si chiude, permettendo il passaggio di corrente, solo quando la bobina viene alimentata.
    *   **NC (Normalmente Chiuso) (Pin 6):** In condizioni di riposo, questo contatto risulta chiuso. Si apre, interrompendo il passaggio di corrente, solo quando la bobina viene alimentata.

![Schema interno contatti relè](/appunti_sta/immagini/schema_rele.png)
*Figura 1: Schema interno dei contatti e della bobina di un relè.*

![Foto relè HK4100F](/appunti_sta/immagini/foto_rele.png)
*Figura 2: Aspetto fisico del relè HK4100F.*

La terminologia tecnica per descrivere le configurazioni dei contatti si basa sui concetti di **"Polo" (Pole)**, che si riferisce a un singolo circuito controllabile, e **"Tiro" (Throw)**, che descrive il numero di percorsi di uscita disponibili. Il relè analizzato in questa attività (HK4100F) possiede una configurazione **SPDT** (Single Pole, Double Throw), nota anche come "1 Form C". Un relè SPDT ha un singolo contatto comune (COM) commutabile tra due percorsi di uscita: l'NC e il NO.

### 3. Focus sul Diodo
Il diodo è un componente elettronico fondamentale che agisce come una valvola a senso unico per la corrente elettrica. Esso permette il flusso quasi esclusivamente in una sola direzione: dal terminale positivo (Anodo) a quello negativo (Catodo). 
Quando viene polarizzato direttamente (tensione positiva all'Anodo e negativa al Catodo), il diodo diventa conduttivo non appena la tensione supera un valore di soglia (circa 0.7 Volt per i diodi al silicio). Se la polarità viene invertita (polarizzazione inversa), il diodo si comporta come un interruttore aperto, bloccando il passaggio di corrente.

![Polarizzazione del diodo](/appunti_sta/immagini/diodo_polarizzazione.png)
*Figura 3: Comportamento del diodo in polarizzazione diretta e inversa.*

### 4. Il Diodo di Flyback: Protezione Essenziale per la Bobina
La bobina di un relè è un induttore, e come tale accumula energia nel suo campo magnetico quando viene attraversata dalla corrente. Quando la corrente viene interrotta in modo brusco (es. rilasciando un pulsante), il rapido collasso del campo magnetico genera un pericoloso picco di tensione inversa ad alta energia, noto come **"tensione di flyback"**. Questo picco può danneggiare gravemente i componenti elettronici sensibili collegati al circuito, come microcontrollori o transistor.

Per proteggere il circuito, è considerata una buona prassi di progettazione utilizzare un **diodo di flyback**, collegato in parallelo alla bobina del relè ma con polarità inversa. 
In condizioni normali, questo diodo è in stato di interdizione (non conduce). Tuttavia, quando si verifica la tensione di flyback (che ha polarità opposta all'alimentazione), il diodo si polarizza direttamente, offrendo un percorso di bassa resistenza per la corrente indotta. Questo permette all'energia del campo magnetico di dissiparsi in totale sicurezza.

### 5. Il Relè HK4100F: Analisi del Componente
Il relè HK4100F è un componente compatto ideale per progetti didattici. Operando con una tensione nominale della bobina di 5V DC, è in grado di commutare carichi massimi fino a 3A (250V AC o 30V DC).

Un punto di attenzione importante per gli studenti riguarda la piedinatura. Sebbene un relè SPDT necessiti concettualmente di soli cinque terminali, il modello HK4100F presenta 6 pin. Consultando il datasheet ufficiale, si evince che il pin COM è stato sdoppiato (Pin 1 e Pin 12) per permettere connessioni multiple e, soprattutto, per offrire una maggiore stabilità meccanica al componente quando inserito su una breadboard.

| Funzione Logica | Descrizione | Piedinatura (vista dal basso) |
| :--- | :--- | :--- |
| **Bobina (COIL)** | Terminali per l'alimentazione della bobina | Pin 5 e 8 |
| **Comune (COM)** | Terminale comune del circuito di carico | Pin 1 e 12 |
| **Normalmente Aperto (NO)** | Terminale di carico che si chiude attivando il relè | Pin 7 |
| **Normalmente Chiuso (NC)** | Terminale di carico che risulta chiuso a riposo | Pin 6 |
| **Pin Addizionale** | Pin per stabilità meccanica o connessione aggiuntiva | Pin 12 o 1 |

---

## Sintesi
*   **Funzione del Relè:** È un interruttore elettromeccanico che usa un segnale a bassa potenza per controllare carichi ad alta potenza.
*   **Isolamento Galvanico:** Il circuito di comando e quello di carico sono separati fisicamente; l'interazione avviene solo tramite campo magnetico e parti meccaniche, garantendo sicurezza.
*   **Contatti (SPDT):** Il relè possiede contatti Comune (COM), Normalmente Aperto (NO) e Normalmente Chiuso (NC).
*   **Diodo di Flyback:** Un diodo posizionato in parallelo inverso alla bobina per scaricare l'energia magnetica in eccesso durante lo spegnimento, proteggendo il circuito da picchi di tensione (tensione di flyback).
*   **Analisi Datasheet:** Lo studio dei documenti tecnici è essenziale, come dimostra la presenza del sesto pin (COM sdoppiato) nel modello HK4100F per stabilità meccanica.

---

## Glossario Finale
*   **Isolamento galvanico:** Principio di progettazione in cui due o più circuiti elettrici comunicano o interagiscono senza avere un percorso di conduzione elettrica diretta tra loro.
*   **Polarizzazione diretta:** Condizione in cui un diodo viene collegato con tensione positiva all'Anodo e negativa al Catodo, permettendo il passaggio della corrente.
*   **SPDT (Single Pole, Double Throw):** Configurazione di un interruttore o relè che controlla un singolo circuito (Polo) deviando la connessione tra due possibili uscite (Tiri).
*   **Tensione di flyback:** Picco di tensione inversa ad alta energia generato dal rapido collasso del campo magnetico di un induttore (come la bobina del relè) quando la corrente viene interrotta bruscamente.


<button onclick="window.print()" style="padding: 10px 15px; background-color: #dbae1a; color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold;">
  🖨️ Stampa / Salva in PDF
</button>