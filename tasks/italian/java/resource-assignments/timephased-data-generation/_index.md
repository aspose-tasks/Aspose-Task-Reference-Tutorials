---
title: Genera dati rapportati alla scala cronologica in Aspose.Tasks
linktitle: Genera dati rapportati alla scala cronologica per le assegnazioni di risorse in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come generare dati rapportati alla scala cronologica per le assegnazioni di risorse utilizzando Aspose.Tasks per Java. Migliora l'efficienza della gestione dei progetti con questa guida completa.
weight: 24
url: /it/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera dati rapportati alla scala cronologica in Aspose.Tasks

## introduzione
In questo tutorial, esamineremo il processo di generazione di dati rapportati alla scala cronologica per le assegnazioni di risorse utilizzando Aspose.Tasks per Java. I dati temporali forniscono informazioni preziose su come le risorse vengono allocate nel tempo all'interno di un progetto, aiutando i project manager a prendere decisioni informate.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. È possibile scaricare e installare JDK da[Qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks per Java Library: è necessario disporre della libreria Aspose.Tasks per Java. Puoi scaricarlo da[sito web](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Innanzitutto, importiamo i pacchetti necessari per lavorare con Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Passaggio 1: leggere il file MPP di origine
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
// Leggere il file MPP di origine
Project project = new Project(dataDir + "project.mpp");
```
## Passaggio 2: ottenere l'assegnazione di attività e risorse
```java
// Ottieni il primo compito del progetto
Task task = project.getRootTask().getChildren().getById(1);
// Ottieni la prima assegnazione di risorse del progetto
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Passaggio 3: generare dati rapportati alla scala cronologica con contorno piatto
```java
// Il contorno piatto è il contorno predefinito
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 4: cambia contorno in Tartaruga
```java
// Cambia contorno in Tartaruga
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 5: modificare il contorno in BackLoaded
```java
// Cambia il contorno in BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 6: modificare il contorno in FrontLoaded
```java
// Cambia il contorno in FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 7: cambia contorno in campana
```java
// Cambia contorno in Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 8: modificare il contorno in EarlyPeak
```java
// Cambia contorno in EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 9: cambia Contour in LatePeak
```java
// Cambia contorno in LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Passaggio 10: cambia Contorno in DoublePeak
```java
// Cambia contorno in DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Conclusione
In questo tutorial, abbiamo spiegato come generare dati rapportati alla scala cronologica per le assegnazioni di risorse utilizzando Aspose.Tasks per Java. Comprendere i diversi profili di lavoro può aiutare i project manager a gestire in modo efficace l'allocazione e la pianificazione delle risorse nei loro progetti.
## Domande frequenti
### Posso utilizzare Aspose.Tasks con altre librerie Java?
Sì, Aspose.Tasks può essere integrato con altre librerie Java per migliorare le capacità di gestione dei progetti.
### Aspose.Tasks è adatto a progetti aziendali su larga scala?
Assolutamente, Aspose.Tasks è progettato per gestire progetti di tutte le dimensioni, compresi progetti aziendali su larga scala.
### Aspose.Tasks fornisce supporto per diversi formati di file di progetto?
Sì, Aspose.Tasks supporta vari formati di file di progetto, inclusi MPP, XML e MPX.
### Posso personalizzare i contorni del lavoro in base ai requisiti del mio progetto?
Sì, Aspose.Tasks consente agli utenti di definire contorni di lavoro personalizzati per soddisfare le loro specifiche esigenze di progetto.
### Esiste un forum della community in cui posso ottenere assistenza con Aspose.Tasks?
 Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto e discussioni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
