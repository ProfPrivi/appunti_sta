---
title: IDE e Output
description: L'Ambiente di Sviluppo (IDE) e l'Output Digitale
---

# Lezione 2: L'Ambiente di Sviluppo (IDE) e l'Output Digitale

## Introduzione
Nella prima lezione abbiamo esplorato l'hardware di Arduino; ora è il momento di dargli vita attraverso il software. In questa lezione scopriremo l'Ambiente di Sviluppo (IDE), impareremo la struttura fondamentale di un programma per Arduino e realizzeremo il nostro primo circuito pratico: faremo lampeggiare un LED utilizzando una breadboard. L'obiettivo è comprendere come un'istruzione scritta al computer si traduca in un'azione fisica (un Output Digitale) nel mondo reale.

## Sviluppo dell'Argomento

### 1. L'Ambiente di Sviluppo e lo "Sketch"
Per istruire il microcontrollore, utilizziamo un software gratuito chiamato IDE (Integrated Development Environment). I programmi scritti per Arduino prendono il nome di **"sketch"** e utilizzano un linguaggio di programmazione molto simile al C.

Ogni sketch di Arduino è diviso in due funzioni principali e fondamentali:
*   **`setup()`**: È la funzione di inizializzazione. Le istruzioni scritte all'interno delle sue parentesi graffe `{ }` vengono eseguite **una sola volta** quando la scheda viene accesa o resettata. Serve per preparare il sistema, ad esempio dichiarando quali pin useremo come entrate o come uscite.
*   **`loop()`**: È il cuore del programma. Terminato il setup, il microcontrollore entra nel `loop()` ed esegue le istruzioni contenute al suo interno **all'infinito**, riga dopo riga, finché non togliamo l'alimentazione.

Nel codice è utilissimo inserire dei **commenti**, ovvero testi ignorati da Arduino ma fondamentali per chi legge. Si indicano con `//` per una singola riga o racchiusi tra `/*` e `*/` per testi su più righe.

![Interfaccia dell'IDE di Arduino](/appunti_sta/immagini/ide_arduino.png)
*Figura 1: L'interfaccia dell'IDE di Arduino durante la compilazione di uno sketch.*

### 2. Il primo Output Digitale: Lo sketch "Blink"
Il programma "Blink" (lampeggio) è il classico "Hello World!" del mondo dell'elettronica. L'obiettivo è accendere un LED per un secondo e spegnerlo per un altro secondo, ripetutamente.

```cpp
int led = 13; // Diamo un nome al pin a cui è collegato il LED

void setup() {
  // Inizializza il pin digitale come uscita (OUTPUT)
  pinMode(led, OUTPUT);
}

void loop() {
  digitalWrite(led, HIGH);   // Accende il LED (porta il livello di tensione a HIGH / 5V)
  delay(1000);               // Aspetta un secondo (1000 millisecondi)
  digitalWrite(led, LOW);    // Spegne il LED (porta il livello di tensione a LOW / 0V)
  delay(1000);               // Aspetta un secondo
}
```

Analizziamo i comandi principali:
*   `pinMode(led, OUTPUT)`: Comunica ad Arduino che dal pin 13 dovrà *uscire* corrente.
*   `digitalWrite(led, HIGH)` / `digitalWrite(led, LOW)`: Scrive uno stato logico digitale sul pin, accendendo o spegnendo l'erogazione di 5V.
*   `delay(1000)`: Ferma l'esecuzione del programma per il numero di millisecondi indicato (1000 ms = 1 secondo).

### 3. Il LED e la Protezione Elettrica
Un **LED** (Light Emitting Diode) è un diodo che emette luce quando attraversato da corrente. Essendo un componente "polarizzato", ha un verso obbligato per funzionare: la corrente deve entrare dal piedino più lungo, chiamato **Anodo (+)**, e uscire dal piedino più corto, il **Catodo (-)**.

I pin digitali di Arduino erogano una tensione fissa di 5V. I LED standard, tuttavia, sono progettati per sopportare correnti molto basse (circa 20 mA) e tensioni inferiori (da 1.2V a 3.8V a seconda del colore). Se collegassimo il LED direttamente ad Arduino, si brucerebbe all'istante.
Per evitare che questo accada, dobbiamo assorbire la tensione in eccesso inserendo un **resistore** in serie al LED. Applicando la Legge di Ohm, un resistore da **220 &Omega;** o 330 &Omega; risulta perfetto per mettere in sicurezza il circuito collegato a un pin da 5V.

### 4. La Prototipazione sulla Breadboard
Per collegare fisicamente il LED e la resistenza ai pin di Arduino senza ricorrere al saldatore, utilizziamo uno strumento fondamentale: la **Breadboard** (o basetta sperimentale).

Lo sviluppo di un circuito è un processo iterativo che richiede molte modifiche veloci. La breadboard non richiede saldature ed è completamente riusabile, perciò è lo standard mondiale per la creazione di circuiti temporanei e per i test in laboratorio. All'interno dei suoi fori si celano dei collegamenti metallici che permettono alla corrente di fluire tra i componenti semplicemente infilandone i terminali nei buchi. Le lunghe linee orizzontali (spesso segnate in rosso e blu/nero) servono per distribuire l'alimentazione, mentre i fori centrali sono raggruppati in piccole colonne verticali indipendenti.

![Breadboard e Circuito Blink](/appunti_sta/immagini/breadboard_blink.png)
*Figura 2: Schema di collegamento di un LED e di una resistenza ad Arduino tramite breadboard.*

## Sintesi
*   **IDE e Sketch:** I programmi per Arduino (chiamati sketch) si scrivono al PC tramite l'IDE e si basano su un linguaggio derivato dal C/Wiring.
*   **Setup e Loop:** `setup()` esegue le impostazioni iniziali una sola volta; `loop()` ripete il codice principale all'infinito.
*   **Output Digitale:** Si configura il pin con `pinMode(pin, OUTPUT)` e si eroga/interrompe tensione con `digitalWrite(pin, HIGH/LOW)`.
*   **LED:** Componente polarizzato (Anodo positivo, Catodo negativo) che necessita obbligatoriamente di un resistore (es. 220 &Omega;) per operare a 5V in sicurezza.
*   **Breadboard:** Strumento essenziale per assemblare e testare circuiti elettronici provvisori in modo rapido e senza saldature.

## Glossario Finale
*   **Breadboard:** Basetta forata di prototipazione, dotata di collegamenti elettrici interni, usata per creare e testare circuiti senza effettuare saldature.
*   **Delay:** Istruzione software (espressa in millisecondi) che mette in pausa il microcontrollore, bloccando temporaneamente l'esecuzione del codice successivo.
*   **IDE:** Ambiente di Sviluppo Integrato (Integrated Development Environment); il software utilizzato per scrivere, compilare e caricare il codice sulla scheda Arduino.
*   **Sketch:** Nome convenzionale dato al codice sorgente o programma creato e salvato all'interno dell'IDE di Arduino.

<button onclick="window.print()" style="padding: 10px 15px; background-color: #dbae1a; color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold;">
  🖨️ Stampa / Salva in PDF
</button>