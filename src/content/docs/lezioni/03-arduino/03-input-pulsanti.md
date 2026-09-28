---
title: Input e Pulsanti
description: L'Input Digitale e la Gestione dei Pulsanti
---

# Lezione 3: L'Input Digitale e la Gestione dei Pulsanti

## Introduzione
Nelle lezioni precedenti abbiamo visto come Arduino possa controllare il mondo esterno emettendo segnali (Output). Tuttavia, un sistema realmente interattivo deve essere in grado di "ascoltare" l'ambiente per reagire di conseguenza. In questa lezione introdurremo il concetto di **Input Digitale** utilizzando il sensore più semplice in assoluto: il pulsante. Analizzeremo un problema fisico molto comune, il cosiddetto "ingresso indeterminato" (o stato *floating*), e scopriremo come risolverlo sia a livello hardware (con le resistenze di pull-up e pull-down) sia a livello software.

## Sviluppo dell'Argomento

### 1. Il Pulsante e l'Input Digitale
Un segnale digitale in ingresso può assumere solamente due valori distinti: ON (acceso) oppure OFF (spento). Il dispositivo meccanico più immediato per generare questo segnale è un comune pulsante. 

Quando premiamo il pulsante, chiudiamo il circuito permettendo alla corrente di raggiungere il pin di Arduino, che interpreterà il segnale come **HIGH** (5V). 
Tuttavia, bisogna fare attenzione alle correnti in gioco: un pin di input di Arduino sopporta una corrente massima di 40mA, ma la buona norma suggerisce di mantenersi intorno ai 20mA. Per calcolare la resistenza ideale da inserire in serie, usiamo la Legge di Ohm (R = V/I, ossia 5V / 0.02A = 250 &Omega;), adottando poi il valore commerciale standard più vicino (es. 330 &Omega;). Ma per leggere in modo affidabile lo stato del pulsante, dobbiamo affrontare un altro problema.

### 2. Il Problema dell'Ingresso Indeterminato
Cosa succede quando il pulsante *non* è premuto? In teoria, il circuito è aperto e Arduino dovrebbe leggere LOW (0V). In realtà, ci troviamo di fronte a un problema: quando il circuito è fisicamente aperto, non c'è nulla che "dica" al pin di restare stabilmente a livello LOW. 
Il pin si comporta come un'antenna: interferenze elettromagnetiche ambientali o cariche statiche potrebbero far alzare casualmente il livello della tensione fino a fargli leggere un falso segnale HIGH. Questo stato di incertezza elettronica si chiama ingresso indeterminato (o stato *floating*).

### 3. La Soluzione Hardware: Resistenze di Pull-Down e Pull-Up
Per evitare letture casuali, dobbiamo ancorare saldamente il pin a uno stato logico definito (0V o 5V) quando il pulsante è a riposo. Lo facciamo usando resistenze di valore elevato, tipicamente da **10 k&Omega;**.

*   **Resistenza di Pull-down ("tira giù"):** La resistenza è collegata tra il pin di input e la massa (GND). Quando il pulsante non è premuto, il pin "legge" lo zero (la massa). Quando andiamo a premere il pulsante, la corrente sceglierà la via a minor resistenza (verso il pin), portandolo a 5V e impedendo allo stesso tempo che si crei un cortocircuito letale tra i 5V e la massa.
*   **Resistenza di Pull-up ("tira su"):** La configurazione è speculare. A pulsante non premuto c'è costantemente corrente che passa attraverso la resistenza (collegata ai 5V) e giunge al pin, che legge HIGH. Quando premiamo il pulsante, la corrente segue la via a minor resistenza verso la massa, e il pin leggerà LOW.

![Circuito Pull-Down e Pull-Up](/appunti_sta/immagini/pull_down_up.png)
*Figura 1: Schema di collegamento di un pulsante con resistenza di pull-down e pull-up.*

### 4. La Soluzione Software: Pull-Up Interna
I progettisti di Arduino hanno inserito all'interno del microcontrollore delle resistenze di pull-up da 20 k&Omega; già integrate e pronte all'uso.
Per attivare la resistenza di pull-up interna ed evitare del tutto di dover montare la resistenza da 10 k&Omega; sulla breadboard, è sufficiente utilizzare questa istruzione nella funzione di `setup()`:

```cpp
void setup() {
  // Dichiara che il "pushButton" è un input e attiva la resistenza interna di pull-up:
  pinMode(pushButton, INPUT_PULLUP);
}
```

*Attenzione:* Usando questa tecnica, la logica di lettura si inverte. Pulsante non premuto = HIGH; pulsante premuto = LOW. Inoltre, se si commette un errore nella programmazione, il pin non sarà protetto dalla resistenza.

### 5. Lo Sketch di Controllo ("Button Sketch")
Vediamo come leggere lo stato di un pulsante per accendere un LED, utilizzando il comando `digitalRead()` e la struttura di controllo condizionale `if...else` (se...altrimenti).

```cpp
const int buttonPin = 2;   // Pin a cui è collegato il pulsante
const int ledPin = 13;     // Pin a cui è collegato il LED

int buttonState = 0;       // Variabile per memorizzare lo stato letto

void setup() {
  pinMode(ledPin, OUTPUT);   // Imposta il LED come uscita
  pinMode(buttonPin, INPUT); // Imposta il pulsante come ingresso standard (richiede resistenza esterna)
}

void loop() {
  // Legge lo stato del pulsante (HIGH o LOW) e lo salva nella variabile
  buttonState = digitalRead(buttonPin);

  // SE il pulsante è premuto (livello logico ALTO)
  if (buttonState == HIGH) {
    digitalWrite(ledPin, HIGH); // Accendi il LED
  } else {
    // ALTRIMENTI (se il pulsante non è premuto)
    digitalWrite(ledPin, LOW);  // Spegni il LED
  }
}
```

## Sintesi
*   **Input Digitale:** Segnali discreti interpretati da Arduino unicamente come ON/HIGH/5V o OFF/LOW/0V.
*   **Problema dell'Ingresso Indeterminato:** Un pin di input lasciato scollegato o a circuito aperto può registrare false attivazioni a causa di interferenze elettromagnetiche.
*   **Pull-down e Pull-up:** Resistenze (tipicamente da 10 k&Omega;) usate a livello hardware per forzare uno stato logico stabile (0V o 5V) quando il pulsante è a riposo.
*   **Pull-up Interna:** Resistenza integrata in Arduino (20 k&Omega;) attivabile via software tramite `INPUT_PULLUP` per semplificare i cablaggi sulla breadboard.
*   **digitalRead():** Il comando base per interrogare lo stato di un pin digitale e leggere l'informazione proveniente dall'esterno.

## Glossario Finale
*   **digitalRead():** Funzione nativa di Arduino che legge il valore di uno specifico pin digitale, restituendo lo stato `HIGH` o `LOW`.
*   **Floating (Ingresso Indeterminato):** Condizione instabile di un pin di input che non è saldamente collegato a una tensione di riferimento, rendendolo vulnerabile al rumore elettromagnetico ambientale.
*   **INPUT_PULLUP:** Parametro della funzione `pinMode()` che configura il pin come ingresso e attiva contestualmente la resistenza di pull-up interna del microcontrollore.
*   **Pull-down:** Configurazione in cui una resistenza collega il pin di input alla massa (GND), mantenendo il segnale a livello logico basso (LOW) in assenza di interazioni.
*   **Pull-up:** Configurazione in cui una resistenza collega il pin di input all'alimentazione (5V), mantenendo il segnale a livello logico alto (HIGH) in assenza di interazioni.

<button onclick="window.print()" style="padding: 10px 15px; background-color: #dbae1a; color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold;">
  🖨️ Stampa / Salva in PDF
</button>