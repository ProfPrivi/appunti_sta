---
title: Espandere Arduino
description: Espandere le potenzialità di Arduino (Sensori, Attuatori e Shield)
---

# Lezione 5: Espandere le potenzialità di Arduino (Sensori, Attuatori e Shield)

## Introduzione
Nelle lezioni precedenti abbiamo imparato a leggere semplici segnali elettrici e ad accendere dei LED. Tuttavia, le vere potenzialità di Arduino si esprimono quando lo facciamo interagire con l'ambiente circostante in modi complessi. In questa lezione esploreremo il ciclo completo dell'interazione hardware (Percezione, Elaborazione, Azione) introducendo sensori ambientali avanzati, attuatori in grado di generare movimento o controllare alte tensioni, e infine le "Shield", vere e proprie espansioni per dotare Arduino di nuovi "superpoteri".

## Sviluppo dell'Argomento

### 1. Il Ciclo dell'Interazione: Sensori e Attuatori
Tutti i progetti di physical computing si basano su un ciclo fondamentale in tre fasi:
1.  **Sense/Perceive (Sensori):** Arduino rileva grandezze fisiche dall'ambiente (luce, temperatura, distanza).
2.  **Behavior (Software):** Il codice che abbiamo scritto analizza i dati e prende decisioni.
3.  **Act/React (Attuatori):** Arduino reagisce compiendo un'azione fisica (muovere un motore, emettere un suono, accendere un dispositivo).

### 2. I Sensori Ambientali
Oltre ai semplici pulsanti e alle fotoresistenze, esistono sensori specializzati per misurare l'ambiente:
*   **Temperatura e Umidità:** Sensori come il TMP36 (analogico, restituisce 10mV per ogni grado centigrado) o il DHT22 (digitale) permettono ad Arduino di leggere le condizioni climatiche della stanza.
*   **Movimento (PIR):** Il sensore PIR (Passive Infrared) rileva il movimento di corpi caldi. Il suo funzionamento base per Arduino è semplice: il suo pin di uscita invia un segnale HIGH (4V) quando rileva un movimento, e torna a LOW in assenza di disturbi.
*   **Distanza (Sonar):** Sensori a ultrasuoni come l'HC-SR04 emettono un'onda sonora (Ping) e misurano il tempo impiegato da quest'onda per tornare indietro (Echo) dopo aver colpito un ostacolo, permettendo di calcolare la distanza.

### 3. Oltre il LED: Attuatori Complessi
Quando Arduino deve compiere azioni fisiche più impegnative dell'accendere un piccolo LED, entrano in gioco componenti più robusti:

*   **Servomotori:** A differenza di un normale motore che gira all'infinito, il servomotore (es. SM-S2309S) è in grado di posizionarsi con precisione a un'angolazione specifica (es. da 0° a 180°). È composto da un motore elettrico meccanicamente collegato a un potenziometro. I suoi circuiti interni traducono il segnale PWM inviato da Arduino per raggiungere e mantenere l'esatta posizione richiesta.
*   **Relè Elettromagnetici:** Sono interruttori azionati elettronicamente. Arduino lavora a 5V e non può alimentare direttamente elettrodomestici. Il relè utilizza il segnale a 5V di Arduino per chiudere meccanicamente un secondo circuito, permettendo così di attivare e disattivare in sicurezza apparecchiature ad alta tensione (es. lampadari a 220V o cancelli automatici). *(Attenzione: lavorare con la 220V richiede l'intervento di personale qualificato a causa dei rischi per la sicurezza!)*

### 4. Le Shield: Espansioni Hardware
Cosa fare se vogliamo che Arduino si colleghi al Wi-Fi o controlli motori pesanti, ma il circuito è troppo complesso per una semplice breadboard? Utilizziamo le **Shield**.

Le shield sono schede di espansione pre-assemblate progettate per essere incastrate (impilate) esattamente sopra i pin della scheda Arduino principale. Aggiungono funzionalità "Plug and Play".
Essendo hardware open source, il mercato offre innumerevoli opzioni:
*   **Ufficiali:** Come la *Motor Shield* (per pilotare motori di grande potenza) o l'*Ethernet/WiFi Shield* (per connettere Arduino a Internet).
*   **Non Ufficiali:** Sono prodotte da terze parti e coprono qualsiasi esigenza, dai lettori MP3 ai moduli GPS, fino a espansioni per la sintesi vocale e RFID.

![Esempio di Arduino Shield](/appunti_sta/immagini/arduino_shield.png)
*Figura 2: Una Ethernet Shield incastrata (impilata) sopra una scheda Arduino.*

## Sintesi
*   **Logica del Physical Computing:** Si basa sul rilevamento dell'ambiente (Sensori), sull'elaborazione del codice (Software) e sull'azione fisica (Attuatori).
*   **Sensori Avanzati:** Permettono di rilevare movimento (PIR), temperatura/umidità (TMP36/DHT22) e distanza fisica dagli oggetti (Sonar a ultrasuoni).
*   **Attuatori Complessi:** Il servomotore trasforma il segnale PWM in un posizionamento angolare preciso; il relè permette ad Arduino (5V) di accendere dispositivi ad alta tensione (es. 220V) usandolo come interruttore comandato.
*   **Shield:** Schede di espansione hardware "a incastro" (open source) che estendono enormemente le capacità di base del microcontrollore, fornendo ad esempio connettività web o controllo motori avanzato.

## Glossario Finale
*   **Attuatore:** Un componente (come un motore o un relè) che trasforma il segnale elettrico in uscita da Arduino in un'azione fisica o meccanica nell'ambiente.
*   **PIR (Passive Infrared):** Sensore in grado di rilevare il movimento misurando le radiazioni a infrarossi emesse dagli oggetti nel suo campo visivo.
*   **Relè:** Interruttore elettromeccanico in cui un segnale a bassa tensione (come i 5V di Arduino) pilota un elettromagnete per chiudere o aprire un circuito ad alta tensione/potenza.
*   **Servomotore:** Dispositivo elettromeccanico provvisto di sensore di posizione interno, in grado di ruotare e mantenere con precisione l'angolazione comandata.
*   **Shield:** Circuito stampato aggiuntivo che si inserisce direttamente sopra i pin di un Arduino per estenderne le funzionalità senza dover creare complessi circuiti su breadboard.
*   **Sonar (Sensore a Ultrasuoni):** Dispositivo che calcola la distanza da un ostacolo emettendo onde sonore ad alta frequenza e misurando il tempo che l'eco impiega a ritornare.