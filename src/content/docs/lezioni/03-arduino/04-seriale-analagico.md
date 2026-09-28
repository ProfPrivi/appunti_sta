---
title: Seriale e analogico
description: Comunicazione Seriale e il Mondo Analogico
---

# Lezione 4: Comunicazione Seriale e il Mondo Analogico

## Introduzione
Fino ad ora abbiamo interagito con Arduino in modo "digitale" o binario: acceso o spento, HIGH o LOW, 5V o 0V. Tuttavia, il mondo reale non è fatto solo di interruttori bianchi o neri, ma di sfumature: l'intensità della luce, il livello del volume, la variazione di temperatura. Questa è l'essenza del **Mondo Analogico**. In questa lezione capiremo come Arduino riesce a leggere queste sfumature, come può variare l'intensità di un LED senza limitarsi a spegnerlo o accenderlo, e infine come possiamo "leggere i suoi pensieri" scambiando dati con il computer tramite la Comunicazione Seriale.

## Sviluppo dell'Argomento

### 1. La Comunicazione Seriale (Il "Monitor" di Arduino)
Molto spesso, quando un circuito non funziona, ci chiediamo: "Cosa sta leggendo davvero il sensore?". Arduino può utilizzare la connessione seriale (tramite il cavo USB) non solo per ricevere l'alimentazione, ma anche per comunicare direttamente con il computer host. 
Questa funzionalità è vitale per lo scambio di dati e per il "debug" (la ricerca e correzione degli errori).

Per abilitare questa linea di comunicazione, dobbiamo inserire un'istruzione nel `setup()` e un'altra nel `loop()` per stampare i valori sulla console del computer:

```cpp
void setup() {
  // Abilita la comunicazione seriale a una velocità di 9600 bit al secondo
  Serial.begin(9600);
}

void loop() {
  // Stampa in console la frase o il valore desiderato
  Serial.println("Hello World!");
  delay(2000);
}
```

### 2. Il Mondo Analogico e l'Input (`analogRead`)
Un segnale analogico può assumere qualsiasi valore all'interno di un range noto, variando in modo continuo nel tempo (come un'onda). Poiché il microcontrollore "ragiona" esclusivamente in digitale (0 e 1), un segnale analogico deve essere prima campionato, ovvero convertito in una sequenza di bit che ne esprima l'ampiezza.

Arduino legge le variazioni di tensione da 0V a 5V e le converte in un valore digitale compreso in **1024 step**, ovvero in un intervallo di valori che va da **0 a 1023** (grazie a un convertitore interno a 10-bit).

> **Esempio Pratico: La Fotoresistenza**
> La fotoresistenza (LDR) è un componente elettronico la cui resistenza è inversamente proporzionale alla quantità di luce che lo colpisce. Il suo valore in ohm diminuisce man mano che aumenta l'intensità della luce, facendo variare in modo proporzionale la tensione che Arduino andrà a leggere.

Per leggere questo sensore usiamo il comando `analogRead()` sui pin dedicati (A0, A1, ecc.):
```cpp
// La lettura dell'ingresso analogico restituisce valori da 0 a 1023
int val = analogRead(photoResistor); 
```

### 3. Output Analogico e il PWM (`analogWrite`)
E se volessimo variare la luminosità di un LED in modo continuo, facendolo "sfumare"? I pin digitali standard possono solo erogare 5V o 0V. Per aggirare questo limite hardware, Arduino utilizza una tecnica geniale chiamata **PWM (Pulse Width Modulation)**.

Il PWM inganna l'occhio umano accendendo e spegnendo il pin digitale a una velocità elevatissima. Variando il **Duty Cycle** (la percentuale di tempo in cui il segnale è su HIGH rispetto al tempo totale del ciclo), simuliamo una tensione analogica intermedia. 
Mentre in lettura avevamo 1024 passi, l'istruzione `analogWrite()` accetta valori da **0 a 255**:
*   0% Duty Cycle (0V) -> `analogWrite(0)`
*   25% Duty Cycle -> `analogWrite(64)`
*   50% Duty Cycle -> `analogWrite(127)`
*   100% Duty Cycle (5V) -> `analogWrite(255)`

### 4. Lo Sketch Finale: Unire Sensori, Seriale e PWM
Uniamo i concetti: leggiamo la luce con una fotoresistenza, mostriamo il valore sul PC, e usiamo quel valore per regolare la luminosità di un LED.
*Nota matematica:* Poiché `analogRead` va da 0 a 1023 e `analogWrite` va da 0 a 255, dobbiamo dividere la lettura per 4.

```cpp
int ledPin = 9;            // LED connesso al pin digitale 9 (supporta il PWM)
int photoResistor = A0;    // Fotoresistenza connessa al pin analogico A0
int val = 0;               // Variabile per memorizzare il valore letto

void setup() {
  pinMode(ledPin, OUTPUT); // Imposta il pin del LED come uscita
  Serial.begin(9600);      // Avvia il Monitor Seriale per il debug
}

void loop() {
  // analogRead restituisce valori da 0 a 1023
  val = analogRead(photoResistor); 
  
  // Stampiamo il valore sul PC per capire quanta luce c'è
  Serial.println(val);
  
  // analogWrite accetta valori da 0 a 255. Dividiamo val per 4 per adattare la scala!
  analogWrite(ledPin, val / 4); 
}
```

![Circuito Potenziometro e PWM](/appunti_sta/immagini/circuito_analogico_pwm.png)
*Figura 1: Schema di collegamento per la lettura analogica e l'output in PWM.*

## Sintesi
*   **Comunicazione Seriale:** Utilizzata per far dialogare Arduino e PC tramite USB, indispensabile per scambiare dati e fare il debug dei valori letti dai sensori (`Serial.begin` e `Serial.println`).
*   **Mondo Analogico:** I segnali analogici assumono infiniti valori continui; per essere elaborati digitalmente devono essere campionati.
*   **`analogRead()`:** Comando usato per leggere i pin analogici (A0-A5). Arduino converte le tensioni (0-5V) in numeri interi da 0 a 1023.
*   **PWM (`analogWrite()`):** Tecnica che modula l'ampiezza dell'impulso digitale simulando un voltaggio intermedio. Accetta valori compresi tra 0 (0% duty cycle) e 255 (100% duty cycle).

## Glossario Finale
*   **analogRead():** Istruzione che converte il voltaggio presente su un pin analogico in un valore digitale a 10 bit (da 0 a 1023).
*   **analogWrite():** Istruzione che invia un'onda PWM a un pin compatibile, permettendo di variare la potenza erogata (da 0 a 255).
*   **Duty Cycle:** La frazione di tempo in cui un segnale digitale si trova a livello logico ALTO (HIGH) all'interno di un singolo periodo o ciclo (espresso in percentuale).
*   **Fotoresistenza:** Sensore la cui resistenza elettrica varia in modo inversamente proporzionale all'intensità della luce ambientale.
*   **PWM (Pulse Width Modulation):** Tecnica che permette di simulare un segnale analogico variando la larghezza (il tempo di accensione) degli impulsi digitali inviati a un componente.
*   **Seriale (Monitor):** Interfaccia di comunicazione bidirezionale che permette lo scambio di messaggi di testo tra Arduino e il computer.

<button onclick="window.print()" style="padding: 10px 15px; background-color: #dbae1a; color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold;">
  🖨️ Stampa / Salva in PDF
</button>