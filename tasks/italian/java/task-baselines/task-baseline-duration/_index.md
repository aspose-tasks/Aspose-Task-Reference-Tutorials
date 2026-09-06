---
date: 2026-08-29
description: Scopri come impostare la durata della baseline e monitorare l'avanzamento
  del progetto utilizzando Aspose.Tasks for Java. Questa guida passo passo ti aiuta
  a gestire le baseline delle attività in modo efficiente.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Come impostare la durata della baseline in Aspose.Tasks for Java
og_description: Scopri come impostare la durata della baseline e monitorare l'avanzamento
  del progetto utilizzando Aspose.Tasks for Java. Segui questa guida dettagliata per
  gestire le baseline delle attività in modo efficiente.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Come impostare la durata della baseline per monitorare l'avanzamento del
  progetto
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Come impostare la durata della baseline per monitorare l'avanzamento del progetto
url: /it/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la durata della baseline per monitorare l'avanzamento del progetto

## Introduzione
Il monitoraggio dell'avanzamento del progetto inizia con una baseline solida. In questo tutorial scoprirai **come impostare la durata della baseline** per le attività nei file Microsoft Project utilizzando la libreria Aspose.Tasks per Java e comprenderai perché stabilire una baseline in anticipo ti aiuta a monitorare lo scostamento del programma, la variazione dei costi e il sovraccarico delle risorse per tutta la durata del progetto.

## Risposte rapide
- **Che cosa significa “set baseline”?** Registra la data di inizio, fine e la durata originali di un'attività così da poter confrontare le modifiche future.  
- **Quale classe Aspose.Tasks crea un progetto?** La classe `Project` – imparerai anche come **creare correttamente un'istanza di progetto**.  
- **Ho bisogno di una licenza per eseguire il codice?** Una licenza di valutazione gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso recuperare le baseline intermedie?** Sì, Aspose.Tasks consente di interrogare le baseline intermedie e i loro costi fissi.  
- **Quale versione di Java è richiesta?** Si consiglia Java 8 o successiva.  
- **Come mi aiuta a monitorare l'avanzamento del progetto?** Una volta impostata la baseline, puoi confrontare immediatamente le date effettive con il piano originale usando le funzionalità di reporting integrate.

## Cos'è una baseline di attività e perché impostarla?
Una baseline di attività cattura il programma pianificato (data di inizio, data di fine e durata) in un momento specifico. Impostando una baseline crei un punto di riferimento che rende facile individuare lo scostamento del programma, i superamenti dei costi e il sovraccarico delle risorse man mano che il progetto evolve.

## Perché utilizzare Aspose.Tasks per la gestione delle baseline?
Aspose.Tasks offre **compatibilità completa con .mpp** – puoi leggere e scrivere file Microsoft Project nativi senza necessità di installare Microsoft Office. L'API ti dà accesso programmatico a **oltre 50 formati di input e output**, supporta **baseline intermedie 1‑10** e può gestire **progetti di centinaia di pagine** senza caricare l'intero file in memoria, il che è essenziale per l'elaborazione batch ad alte prestazioni.

## Prerequisiti
1. **Ambiente di sviluppo Java** – JDK 8+ installato e configurato.  
2. **Aspose.Tasks per Java** – scarica la libreria dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).  
3. **IDE o strumento di build** – Maven, Gradle, o qualsiasi IDE tu preferisca.

## Importa pacchetti
Le seguenti importazioni includono le classi principali di Aspose.Tasks necessarie per lavorare con progetti, attività, baseline e dati temporizzati.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Passo 1: creare un'istanza di progetto
La classe `Project` rappresenta un file Microsoft Project in memoria ed è il punto di ingresso per tutte le operazioni.

```java
Project project = new Project();
```

## Passo 2: creare una baseline di attività
Un `TaskBaseline` memorizza l'inizio, la fine e la durata pianificati per una specifica attività.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Passo 3: visualizzare le informazioni della baseline di attività
Il metodo `getBaselines()` restituisce la collezione di baseline associate a un'attività.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Passo 4: verificare la baseline intermedia e il costo fisso
`BaselineType` enumera le baseline primarie e intermedie (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Passo 5: stampare i dati temporizzati
`TimephasedData` rappresenta un elemento di informazione di programmazione per un intervallo di tempo specifico.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Seguendo questi passaggi, puoi **impostare la durata della baseline** per qualsiasi attività e recuperare informazioni dettagliate sulla baseline usando Aspose.Tasks per Java, fornendoti un modo affidabile per **monitorare l'avanzamento del progetto** durante l'intero ciclo di vita del progetto.

## Problemi comuni e soluzioni
- **Baseline non appare in MS Project:** Assicurati di aver chiamato `project.setBaseline(BaselineType.Baseline)` **dopo** aver aggiunto l'attività.  
- **NullPointerException su `getBaselines()`:** Verifica che l'attività sia stata aggiunta al progetto prima di impostare la baseline.  
- **Mancata corrispondenza dell'unità di tempo:** Usa `TimeUnitType` per formattare correttamente la durata, soprattutto quando lavori con calendari personalizzati.

## FAQ

### Cos'è una baseline di attività in MS Project?
Una baseline di attività in MS Project è una fotografia del programma pianificato iniziale per un'attività, includendo la data di inizio, la data di fine e la durata.

### Perché è importante gestire le baseline delle attività?
Gestire le baseline delle attività aiuta a confrontare il programma pianificato con l'avanzamento reale del progetto, facilitando un migliore monitoraggio e processo decisionale.

### Posso modificare una baseline di attività una volta impostata?
Sì, puoi modificare le baseline delle attività in MS Project per riflettere le modifiche al piano di progetto. Tuttavia, è fondamentale documentare eventuali deviazioni dalla baseline originale.

### Aspose.Tasks supporta altre funzionalità di gestione del progetto?
Sì, Aspose.Tasks offre un'ampia gamma di funzionalità per la gestione del progetto, inclusi la pianificazione delle attività, l'allocazione delle risorse e la generazione di diagrammi di Gantt.

### Dove posso trovare supporto per Aspose.Tasks?
Puoi trovare supporto per Aspose.Tasks sul [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15), dove puoi fare domande e interagire con altri utenti.

## Ulteriori domande frequenti
**Q: Devo chiamare `setBaseline` per ogni attività singolarmente?**  
A: No. Chiamare `project.setBaseline(BaselineType.Baseline)` registra la baseline per tutte le attività del progetto in una volta sola.

**Q: Come posso impostare una baseline intermedia per un'attività specifica?**  
A: Usa `project.setBaseline(BaselineType.Baseline1)` (o Baseline2‑Baseline10) dopo aver aggiornato il programma dell'attività.

**Q: È possibile esportare i dati della baseline in CSV?**  
A: Sì. Itera su `task.getBaselines()` e scrivi i campi desiderati in un file CSV usando le normali I/O di Java.

**Q: Posso leggere un file .mpp esistente che contiene già baseline?**  
A: Assolutamente. Carica il file con `new Project("myproject.mpp")` e poi accedi alle baseline di ciascuna attività come mostrato sopra.

**Q: Aspose.Tasks gestisce file multi‑progetto?**  
A: Aspose.Tasks funziona con file .mpp a progetto singolo. Per scenari multi‑progetto, combina i progetti programmaticamente.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutorial correlati

- [Crea elenco attività Java – Baseline MS Project usando Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Crea progetto MPP Java – Modifica avanzamento attività con Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Baseline di gestione progetto – Pianificazione attività con Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}