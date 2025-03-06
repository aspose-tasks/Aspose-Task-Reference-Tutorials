---
title: Leggi MS Project da Primavera con Aspose.Tasks per Java
linktitle: Leggi Progetto da Primavera in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come leggere i file MS Project da Primavera XML senza problemi utilizzando Aspose.Tasks per Java. Migliora l'efficienza della gestione dei tuoi progetti.
weight: 20
url: /it/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi MS Project da Primavera con Aspose.Tasks per Java

## introduzione
Nella gestione dei progetti, l’interoperabilità tra diverse piattaforme software è fondamentale per un flusso di lavoro senza interruzioni. Aspose.Tasks per Java fornisce funzionalità robuste per leggere file Microsoft Project da Primavera XML. Questo tutorial ti guiderà attraverso il processo di lettura dei file MS Project da Primavera utilizzando Aspose.Tasks per Java, consentendoti di esaminare in modo efficiente le proprietà specifiche di Primavera delle attività.
## Prerequisiti
Prima di procedere, assicurati di avere installati e configurati i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Tasks per Java: Scarica e installa Aspose.Tasks per Java da[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Passaggio 1: configurare la directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Assicurarsi di sostituire`"Your Data Directory"` con il percorso effettivo della directory dei dati.
## Passaggio 2: leggere il progetto da Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Assicurarsi di sostituire`"PrimaveraProject.xml"` con il nome effettivo del file XML Primavera.
## Passaggio 3: scorrere le attività e recuperare le proprietà specifiche di Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Questo codice scorre ogni attività del progetto, stampando le proprietà specifiche di Primavera rilevanti.

## Conclusione
In questo tutorial, hai imparato come leggere i file MS Project da Primavera XML utilizzando Aspose.Tasks per Java. Questa funzionalità consente una perfetta integrazione e analisi dei dati di progetto su diverse piattaforme, migliorando l'efficienza complessiva della gestione del progetto.
## Domande frequenti
### D: Posso modificare le proprietà specifiche di Primavera delle attività utilizzando Aspose.Tasks per Java?
R: Sì, Aspose.Tasks per Java fornisce API per modificare le proprietà specifiche di Primavera delle attività secondo necessità.
### D: Aspose.Tasks per Java supporta la lettura di altri formati di file di progetto?
R: Sì, Aspose.Tasks per Java supporta la lettura di vari formati di file di progetto tra cui MPP, XML e Primavera XML.
### D: Aspose.Tasks per Java è adatto per applicazioni di gestione di progetti a livello aziendale?
R: Assolutamente, Aspose.Tasks per Java offre funzionalità robuste e scalabilità, rendendolo adatto per applicazioni di gestione di progetti a livello aziendale.
### D: Posso estrarre informazioni sulle risorse dai progetti Primavera utilizzando Aspose.Tasks per Java?
R: Sì, Aspose.Tasks per Java ti consente di estrarre informazioni sulle risorse insieme ai dettagli delle attività dai progetti Primavera.
### D: Dove posso trovare ulteriore supporto o documentazione per Aspose.Tasks per Java?
 R: Puoi trovare documentazione completa e accedere ai forum di supporto su[Aspose.Tasks per la documentazione Java](https://reference.aspose.com/tasks/java/) pagina.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
