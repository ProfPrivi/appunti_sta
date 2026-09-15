---
title: Analogico Vs Digitale
description: Analogico e Digitale
---

# Capitolo 5: Analogico vs. Digitale: Un Confronto Fondamentale

## Introduzione
Questo capitolo introduce una distinzione concettuale fondamentale per l'elettronica moderna e l'informatica: la differenza tra segnali analogici e digitali. L'obiettivo della lezione è comprendere come le informazioni fisiche del mondo reale vengano catturate, trasformate ed elaborate dai sistemi elettronici e dai computer.

---

## Sviluppo dell'Argomento

### 5.1 Il Segnale: Il Vettore dell'Informazione
In elettronica, un **segnale** è una grandezza fisica (solitamente una tensione o una corrente) che varia nel tempo con lo scopo di trasportare delle informazioni. 
Questa informazione può rappresentare qualsiasi cosa: un suono, la temperatura di una stanza, la pressione atmosferica, o i dati elaborati da un computer. I segnali si dividono in due grandi famiglie: analogici e digitali.

### 5.2 Il Segnale Analogico
Un segnale analogico è un segnale che può assumere un **numero infinito di valori** all'interno del suo campo di variabilità. 
La sua caratteristica principale è l'essere **continuo** sia in ampiezza che nel tempo. Il nome stesso "analogico" deriva dal fatto che questi segnali variano in modo "analogo" (ovvero proporzionale e fedele) alla grandezza fisica di origine che rappresentano.

**Esempio pratico**: Le grandezze fisiche naturali sono analogiche. La temperatura, l'umidità e la pressione variano in modo continuo. Un'onda sonora, ad esempio, viene tradotta in un segnale elettrico analogico la cui forma d'onda segue esattamente e fedelmente le variazioni di pressione e frequenza della voce.

![Grafico del Segnale Analogico](/appunti_sta/immagini/segnale_analogico.jpg)
*Figura 1: Andamento continuo nel tempo di un segnale analogico.*

### 5.3 Il Segnale Digitale
A differenza del segnale analogico, un segnale digitale può assumere solo un **numero limitato (finito) di valori**. È discreto sia in ampiezza che nel tempo e si presenta, di fatto, come una sequenza di numeri o cifre. 

Il caso più importante in informatica è il segnale digitale **binario**, che può assumere solamente due valori distinti, tipicamente rappresentati come "0" (zero) e "1" (uno).

**Esempio pratico**: I computer e le schede a microcontrollore, come **Arduino**, lavorano esclusivamente con grandezze di tipo digitale e finite. Questo comporta una necessità fondamentale: affinché un computer possa elaborare informazioni provenienti dal mondo reale (come una foto o un brano musicale), queste devono essere prima tradotte in sequenze di bit (0 e 1).

![Grafico del Segnale Digitale](/appunti_sta/immagini/segnale_digitale.jpg)
*Figura 2: Andamento a "gradini" discreti di un segnale digitale binario.*

### 5.4 Conversione e Vantaggi: Perché il Digitale vince?
Poiché il mondo fisico è analogico e il "cervello" dei computer è digitale, è indispensabile farli comunicare attraverso un processo di conversione. 
* Il **Convertitore Analogico-Digitale (ADC)** campiona un segnale analogico a intervalli regolari di tempo e lo traduce in una sequenza numerica.
* Il **Convertitore Digitale-Analogico (DAC)** compie il processo esattamente inverso.

**L'esempio del Modem**: Un esempio familiare è il modem casalingo, che ha proprio il compito di convertire i segnali digitali del computer in segnali analogici per farli viaggiare sulla linea telefonica, per poi riconvertirli in digitale quando arrivano al computer di destinazione.

### Il Teorema di Nyquist-Shannon

Perché la conversione ADC sia precisa, il campionamento non può essere casuale. Il Teorema di Nyquist stabilisce che, per ricostruire fedelmente un segnale analogico senza distorsioni (aliasing), la frequenza di campionamento (f<sub>s</sub>) deve essere almeno il doppio della frequenza massima (f<sub>max</sub>) contenuta nel segnale originale:

<div align="center" style="font-family: 'Courier New', Courier, monospace; font-size: 1.4em; font-weight: bold; color: #2c3e50; margin: 20px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px; border: 1px solid #dee2e6;">
  f<sub>s</sub> &ge; 2f<sub>max</sub>
</div>

> **Esempio Pratico:** L’orecchio umano percepisce suoni fino a circa 20.000 Hz. Per registrare fedelmente un brano, un CD Audio applica il teorema campionando la musica a 44.100 Hz (più del doppio di 20.000).

![Processo di conversione AD](/appunti_sta/immagini/conversione_ad.jpg)
*Figura 3: Le fasi di campionamento, quantizzazione e codifica nella conversione da analogico a digitale.*

**Perché usiamo il digitale? (La robustezza al rumore)**
Uno dei motivi principali per cui la tecnologia digitale ha soppiantato quella analogica è la sua incredibile **robustezza al rumore** (le interferenze elettriche). 
Se un segnale analogico subisce un'interferenza, il rumore si mescola indissolubilmente all'informazione; se proviamo ad amplificare il segnale, amplificheremo anche il rumore. 
In un segnale digitale, invece, il sistema deve solo distinguere tra uno "0" e un "1". Il segnale può tollerare forti interferenze senza che i suoi valori vengano fraintesi (un disturbo lieve non trasformerà uno "0" in un "1"). Inoltre, i segnali digitali possono essere rigenerati periodicamente, ricreando un segnale pulito ed eliminando del tutto il rumore accumulato.

---

## Sintesi
* **Segnale**: Grandezza fisica variabile nel tempo che trasporta un'informazione.
* **Segnale Analogico**: Varia in modo continuo e possiede infiniti valori, riproducendo fedelmente i fenomeni naturali (es. suono, temperatura).
* **Segnale Digitale**: Possiede un numero finito e discreto di valori (spesso binario: 0 e 1). È l'unico "linguaggio" comprensibile da computer e microcontrollori come Arduino.
* **Conversione**: I convertitori ADC e DAC fungono da traduttori tra il mondo naturale (analogico) e quello informatico (digitale).
* **Vantaggi del Digitale**: Elevata resistenza alle interferenze elettriche (rumore) e possibilità di essere rigenerato senza perdita di qualità.

---

## Glossario Finale
* **ADC (Analog-to-Digital Converter)**: Dispositivo elettronico che converte un segnale analogico continuo in un segnale digitale discreto.
* **DAC (Digital-to-Analog Converter)**: Dispositivo elettronico che esegue l'operazione inversa, trasformando i numeri digitali in un segnale analogico.
* **Rumore**: Qualsiasi disturbo o interferenza elettrica indesiderata che si sovrappone al segnale originale, degradandone la qualità.
* **Segnale Binario**: Tipo specifico di segnale digitale che utilizza solo due stati, convenzionalmente indicati con i valori logici 0 e 1.