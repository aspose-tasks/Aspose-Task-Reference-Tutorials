---
date: 2026-01-13
description: Scopri come calcolare la percentuale delle risorse in Java con Aspose.Tasks,
  incluso come ottenere la percentuale di lavoro completato per le risorse di MS Project.
  Guida passo passo con esempi di codice.
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: calcolare la percentuale delle risorse in Java usando Aspose.Tasks
url: /it/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# calcolare la percentuale delle risorse java con Aspose.Tasks

## Introduzione
Benvenuti! In questo tutorial imparerete **come calcolare la percentuale delle risorse java** utilizzando la libreria Aspose.Tasks per Java. Ti guideremo nell'estrazione del *percent work complete* per ogni risorsa in un file Microsoft Project, spiegheremo perché questa metrica è importante e mostreremo il codice esatto di cui hai bisogno. Alla fine, sarai in grado di integrare i calcoli della percentuale delle risorse in qualsiasi soluzione di gestione progetti basati su Java.

## Risposte rapide
- **Cosa significa “percentuale di risorsa”?** È la percentuale di lavoro che una risorsa ha completato rispetto al totale del lavoro assegnato.
- **Quale chiamata API restituisce questo valore?** `Rsc.PERCENT_WORK_COMPLETE` tramite la classe `Resource`.
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa di Aspose.Tasks per l'uso in produzione.
- **Posso usarlo con altri framework Java?** Sì – l'API funziona con Spring, Hibernate e progetti Java standard.
- **Quale versione di Aspose.Tasks è necessaria?** Qualsiasi versione recente che supporti l'enumerazione `Rsc` (ad es., 24.x).

## Cos'è Java per calcolare la percentuale delle risorse?
Calcolare la percentuale delle risorse in Java significa leggere programmaticamente un file Microsoft Project e determinare quanto lavoro ha terminato ciascuna risorsa. queste informazioni aiutano il project manager a prevedere le tempistiche, bilanciare i carichi di lavoro e identificare i colli di bottiglia.

## Perché completare la percentuale di lavoro?
- **Monitoraggio dei progressi:** Visualizzare un colpo d'occhio quali membri del team sono in linea con il programma.
- **Capacity Planning:** Regolare le future assegnazioni basandosi sulle prestazioni reali.
- **Reporting:** Generare report di stato accurati per gli stakeholder senza calcoli manuali.

## Prerequisiti
### Ambiente di sviluppo Java
Assicurati di avere installato il Java Development Kit (JDK). Puoi scaricare il JDK da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Libreria Aspose.Tasks
Scarica e aggiungi la libreria Aspose.Tasks al tuo progetto da [qui](https://releases.aspose.com/tasks/java/) e segui le istruzioni di installazione fornite nella documentazione [qui](https://reference.aspose.com/tasks/java/).

## Importa pacchetti
Prima di iniziare a scrivere codice, importiamo i pacchetti necessari per questo tutorial:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## Passaggio 1: Imposta il percorso del file di progetto
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con la cartella che contiene il tuo file Microsoft Project.

## Passaggio 2: Carica il progetto
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Questo carica il file **Software Development.mpp** dalla directory specificata.

## Passaggio 3: Itera sulle risorse
```java
for (Resource res : prj.getResources()) {
```
Eseguiamo un ciclo su ogni risorsa definita nel progetto.

## Passaggio 4: Verifica il nome della risorsa e ottieni la percentuale di completamento
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Il codice verifica innanzitutto che la risorsa abbia un nome e poi stampa il valore **percent work complete** per quella risorsa.

## Problemi e soluzioni comuni
- **NullPointerException** – Assicurati che il percorso del file di progetto sia corretto e che il file venga caricato senza errori.
- **Percentuali errate** – Verifica che la risorsa abbia effettivamente assegnato lavoro; altrimenti la percentuale sarà `0`.
- **License error** – Usa una licenza valida di Aspose.Tasks o una licenza di valutazione temporanea per evitare restrizioni a runtime.

## Domande frequenti (originale)

### Posso utilizzare Aspose.Tasks per Java con altri framework Java?
Sì, Aspose.Tasks per Java è compatibile con vari framework Java come Spring, Hibernate e altri.

### Aspose.Tasks supporta tutte le versioni dei file Microsoft Project?
Aspose.Tasks fornisce supporto per tutte le versioni dei file Microsoft Project, inclusi MPP, MPT, XML e altri.

### Posso manipolare le pianificazioni dei progetti utilizzando Aspose.Tasks?
Assolutamente, Aspose.Tasks offre funzionalità completa per manipolare i piani di progetto, inclusi task, risorse, calendari e altro.

### Esiste un forum della community per il supporto di Aspose.Tasks?
Sì, puoi trovare assistenza e interagire con altri utenti sul forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

### Aspose.Tasks offre licenze temporanee a scopo di valutazione?
Sì, puoi ottenere una licenza temporanea per la valutazione da [qui](https://purchase.aspose.com/temporary-license/).

## Domande frequenti aggiuntive

**D: Come posso formattare l'output per mostrare le percentuali con il segno %?**
R: Recupera il valore numerico con `res.get(Rsc.PERCENT_WORK_COMPLETE)` e formattalo utilizzando `String.format("%.2f%%", value)`.

**D: Posso filtrare le risorse per visualizzare solo quelle con un livello di completamento inferiore al 50%?**
R: Sì, aggiungi una condizione `if` che verifichi `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` prima di stampare.

**D: È possibile riscrivere le percentuali nel file di progetto?**
R: Il campo `Rsc.PERCENT_WORK_COMPLETE` è di sola lettura; è necessario modificare le assegnazioni delle attività.

**D: Funziona con i file di Project Online (cloud)?**
R: È necessario prima scaricare il file .mpp in locale; Aspose.Tasks funziona con il formato del file, non direttamente con il servizio cloud.

## Conclusione
In questa guida abbiamo mostrato **come calcolare la percentuale di completamento delle risorse in Java** utilizzando Aspose.Tasks, concentrandoci sul recupero della *percentuale di completamento* per ciascuna risorsa. Seguendo i passaggi sopra descritti, è possibile integrare analisi precise della percentuale di utilizzo delle risorse nelle applicazioni Java, ottenendo una migliore visibilità sullo stato di salute del progetto e sull'utilizzo delle risorse.

---

**Ultimo aggiornamento:** 13/01/2026
**Testato con:** Aspose.Tasks per Java 24.10
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}