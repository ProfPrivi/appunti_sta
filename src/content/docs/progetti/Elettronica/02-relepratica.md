---
title: Attività Relè
description: Work in Progress.
---

# Lezione Pratica: Controllo di un LED con il Relè HK4100F su Breadboard

## Introduzione
Dopo aver compreso i principi teorici, questa lezione ci porta direttamente in laboratorio. L'obiettivo di questa esercitazione è duplice: da un lato, dimostrare visivamente e acusticamente il funzionamento meccanico ed elettrico del relè; dall'altro, illustrare in modo pratico il concetto di isolamento galvanico controllando un LED (circuito di carico) tramite un semplice pulsante (circuito di controllo).

---

## Sviluppo dell'Argomento

### 1. Materiale Necessario e Sicurezza
Per realizzare questo circuito, avremo bisogno dei seguenti componenti:
*   1 relè HK4100F (presente nel kit Arduino).
*   1 breadboard.
*   1 alimentatore o batteria a 5V DC.
*   1 pulsante a 4 pin, di tipo momentaneo e normalmente aperto.
*   1 diodo (o equivalente) per la funzione di flyback.
*   1 LED standard e 1 resistenza di limitazione (es. 220 &Omega; per un'alimentazione a 5V).
*   Cavi jumper di diverse lunghezze.

![Pulsante a 4 pin](/appunti_sta/immagini/pulsante_4pin.jpg)
*Figura 1: Esempio del pulsante a 4 pin momentaneo utilizzato nell'esercitazione.*

**Avvertenze di Sicurezza:**
Prima di iniziare il cablaggio, è fondamentale rispettare alcune regole:
*   Utilizzare esclusivamente tensioni di sicurezza (5V) per l'intera esercitazione; non collegare mai il relè o la breadboard a tensioni di rete (220V AC).
*   Prestare la massima attenzione alla polarità del diodo di flyback: la striscia (catodo) deve essere rivolta verso il polo positivo della bobina.
*   Rispettare la polarità del LED: l'anodo (il piedino più lungo) va collegato al lato positivo del circuito.

### 2. FASE 1: Cablaggio del Circuito Base
Il circuito si compone di due parti separate, che devono essere cablate sulla breadboard in modo chiaro per riflettere l'isolamento galvanico.

**Circuito di Controllo (Bobina del Relè):**
1.  Collega il polo positivo dell'alimentatore al rail positivo della breadboard e il polo negativo al rail negativo.
2.  Posiziona il relè HK4100F sulla breadboard.
3.  Collega un'estremità del pulsante al rail positivo della breadboard e l'altra estremità a un pin sulla stessa colonna del pin di un terminale della bobina del relè.
4.  Collega il secondo pin della bobina del relè al rail negativo della breadboard.
5.  Collega il diodo in parallelo alla bobina del relè, con la striscia (catodo) verso il polo positivo e l'altro capo (anodo) verso il polo negativo.

**Circuito di Carico (LED):**
1.  Collega il pin COM del relè al rail positivo della breadboard.
2.  Inserisci la resistenza di limitazione: un'estremità va al pin NO del relè, l'altra a una riga libera.
3.  Collega l'anodo del LED (piedino lungo) alla stessa riga della resistenza.
4.  Collega il catodo del LED (piedino corto) al rail negativo.
*(Nota: per una dimostrazione alternativa, è possibile collegare resistenza e LED al pin NC invece che al pin NO, osservando il comportamento invertito).*

![Schema Breadboard Fase 1](/appunti_sta/immagini/rele_breadboard_fase1.png)
*Figura 2: Cablaggio su breadboard per il controllo di un singolo LED.*

**Funzionamento Atteso:**
*   **Stato a Riposo:** Con l'alimentatore acceso e il pulsante non premuto, la bobina non è alimentata. Il contatto COM tocca il pin NC. Il circuito del LED sul pin NO è aperto e il LED rimane spento.
*   **Stato Attivo:** Premendo il pulsante, la corrente attraversa la bobina. Si udirà un "clic" meccanico: il contatto COM si sposta sul pin NO, chiudendo il circuito e facendo accendere il LED. Rilasciando il pulsante, un nuovo "clic" indicherà il ritorno allo stato di riposo, spegnendo il LED.

### 3. FASE 2: Commutazione di due circuiti
Come attività aggiuntiva, proviamo a sfruttare appieno i contatti del relè.
Provare a collegare un secondo LED e una seconda resistenza al pin NC del relè. In questa configurazione, quando si preme il pulsante, il primo LED si accenderà e il secondo si spegnerà, dimostrando la capacità di un singolo relè di commutare tra due percorsi di circuito distinti.

![Schema Breadboard Fase 2](/appunti_sta/immagini/rele_breadboard_fase2.png)
*Figura 3: Cablaggio su breadboard per la commutazione di due LED.*

![Schema Elettrico Fase 2](/appunti_sta/immagini/rele_schema_fase2.png)
*Figura 4: Schema elettrico della commutazione di due LED.*

### 4. FASE 3: Esame e Risoluzione dei Problemi
Come test finale per valutare le competenze acquisite:
Provare a collegare il circuito seguendo lo specifico schema elettrico riportato qui sotto. Dopodiché, osservare attentamente il sistema, esaminare il suo comportamento, redigere una relazione su quanto accade e spiegarne i motivi tecnici.

![Schema Elettrico Fase 3](/appunti_sta/immagini/rele_schema_fase3.png)
*Figura 5: Schema elettrico per l'attività di analisi e troubleshooting della FASE 3.*

---

## Sintesi
*   **Isolamento Galvanico Pratico:** Il circuito del pulsante (controllo) e quello del LED (carico) sono elettricamente separati, uniti solo dal campo magnetico del relè.
*   **Sicurezza:** È obbligatorio usare basse tensioni (5V) e collegare correttamente le polarità di LED e diodo di flyback.
*   **Commutazione Meccanica:** Il "clic" udibile conferma lo spostamento fisico dell'ancora interna tra i contatti NC e NO.
*   **Deviazione del Flusso:** Sfruttando i pin NC e NO contemporaneamente, il relè può alternare l'accensione di due dispositivi diversi con un unico comando.

---

## Glossario Finale
*   **Circuito di Carico:** La sezione di potenza del sistema (in questo caso il LED e la sua resistenza) in cui la corrente viene fisicamente interrotta o consentita dai contatti del relè.
*   **Circuito di Controllo:** La sezione a bassa potenza del sistema (pulsante e bobina) incaricata di inviare il segnale di comando.
*   **Pulsante Momentaneo:** Un interruttore che chiude il circuito (permette il passaggio di corrente) solo finché viene mantenuta la pressione fisica su di esso.
*   **Rail:** Le lunghe strisce di fori orizzontali sulla breadboard (solitamente contrassegnate con righe rosse e blu/nere) utilizzate per distribuire agevolmente l'alimentazione positiva e negativa a tutti i componenti.