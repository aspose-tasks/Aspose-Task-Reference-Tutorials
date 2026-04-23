---
date: 2026-01-23
description: Scopri come impostare la durata della baseline e creare un'istanza di
  progetto utilizzando Aspose.Tasks per Java. Questa guida passo passo ti aiuta a
  gestire le baseline delle attività in modo efficiente.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Come impostare la durata della baseline in Aspose.Tasks per Java
url: /it/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la durata della baseline in Aspose.Tasks per Java

## Introduzione
Imcome impostare la durata della baseline** per le attività in Microsoft Project utilizzando la libreria Aspose.Tasks per Java, e vedrai perché stabilire una baseline in anticipo può farti risparmiare tempo e problemi in seguito.

## Risposte rapide
-istra la data di inizio, fine e la durata originali di un'attività così puoi confrontare le modifiche future.  
- **Quale classe Aspose.Tasks crea un progetto?** La classe `Project` – imparerai anche come **creare un'istanza di progetto** correttamente.  
- **Ho bisogno di una licenza per eseguire il codice?** Una licenza di valutazione gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso recuperare le baseline  
- **Quale versione consiglia Java 8 o successiva.

## Cos'è una baseline di attività e impostarla?
Una?
- **Compatibilità completa .mpp** – leggi e scrivi file nativi di Microsoft Project senza necessità di Office.  
- **API ricca** – accedi ai dati della baseline, alle baseline intermedie e alle informazioni a tempo programmato in modo programmatico.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con qualsiasi JDK standard.

## Prerequisiti
1. **Ambiente di sviluppo Java** – JDK 8+ installato e configurato.  
2. **Aspose.Tasks per Java** – scarica la libreria da [qui](https://releases.aspose.com/tasks/java/).  
3. **IDE o strumento di build** – Maven, Gradle o qualsiasi IDE tu preferisca.

## Importare i pacchetti
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Passo 1: Creare un'istanza di progetto
Creating a project instance is the foundation for any further manipulation. This step shows how to **create project instance** using Aspose.Tasks:

```java
Project project = new Project();
```

## Passo 2: Creare una baseline di attività
Add a new task to the project’s root and set its baseline. This records the original schedule for the task:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Passo 3: Visualizzare le informazioni della baseline di attività
Retrieve the baseline you just created and print its key properties. This helps you verify that the baseline was set correctly:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Passo 4: Verificare la baseline intermedia e il costo fisso
If you’re working with interim baselines, you can query whether the current baseline is interim and any associated fixed cost:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Passo 5: Stampare i dati a tempo programmato
Time‑phased data shows how the baseline is distributed over time. Loop through the collection to inspect each entry:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Seguendo questi passaggi, puoi **impostare la durata della baseline** per qualsiasi attività e recuperare informazioni dettagliate sulla Aspose.Tasks per Java.

## Problemi comuni e soluzioni
- **Baseline non appare in MS Project:** Assicurati di aver chiamato `project.setBaseline(BaselineType.Baseline)` **dopo** aver aggiunto l'attività.  
- **NullPointerException su `getBaselines()`:** Verifica che l'attività sia stata aggiunta al progetto prima di impostare la baseline.  
- **Incongruenza dell'unità di tempo:** Usa `TimeUnitType` per formattare correttamente la durata, soprattutto quando lavori con calendari personalizzati.

## FAQ

### Cos'è una baseline di attività in MS Project?
Una baseline di attività in MS Project è un'istantanea del programma pianificato iniziale per un'attività, includendo la data di inizio, la data di fine e la durata.

### Perché è le baseline di attività?
Gestire le baselineare il programma pianificato con l'avanzamento reale### Aspose.Tasks supportagetti?
Sì, Aspose.Tasks offre un'ampia gamma di funzionalità per la gestione dei progetti, inclusi la pianificazione delle attività, l'allocazione delle risorse e la generazione di diagrammi di Gantt.

### Dove posso trovare supporto per Aspose.Tasks?
Puoi trovare supporto per Aspose.Tasks sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), dove puoi fare domande e interagire con altri utenti.

## Ulteriori domande frequenti
**D: Devo chiamare `setBaseline` per ogni attività singolarmente?**  
R: No. Chiamare `project.setBaseline(BaselineType.Baseline)` registra la baseline per tutte le attività del progetto in una volta.

**D: Come posso impostare una baseline intermedia per un'attività specifica?**  
R: Usa `project.setBaseline(BaselineType.Baseline1)` (o Baseline2‑Baseline10) dopo aver aggiornato il programma dell'attività.

**D: È possibile esportare i dati della baseline in CSV?**  
R: Sì. Itera su `task.getBaselines()` e scrivi i campi desiderati in un file CSV usando le normali I/O di Java.

**D: Posso leggere un file .mpp esistente che contiene già baseline?**  
R: Assolutamente. Carica il file con `new Project("myproject.mpp")` e poi accedi alle baseline di ciascuna attività come mostrato sopra.

**D: Aspose.Tasks gestisce file multi‑progetto?**  
R: Aspose.Tasks funziona con file .mpp a progetto singolo. Per scenari multi‑progetto, combina i progetti programmaticamente.

**Ultimo aggiornamento:** 2026-01-23  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}