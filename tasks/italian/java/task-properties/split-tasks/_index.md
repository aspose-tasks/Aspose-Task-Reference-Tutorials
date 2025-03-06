---
title: Dividi attività in Aspose.Tasks
linktitle: Dividi attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Padroneggia la gestione delle attività in Java con Aspose.Tasks! Scopri come suddividere le attività in modo efficiente per tempistiche di progetto ottimizzate. Scarica ora!
weight: 29
url: /it/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dividi attività in Aspose.Tasks

## introduzione
Hai difficoltà con la gestione delle attività nel tuo progetto Java? Aspose.Tasks per Java fornisce una potente soluzione per suddividere le attività in modo efficiente, migliorando le capacità di gestione dei progetti. In questo tutorial, ti guideremo attraverso il processo di suddivisione delle attività utilizzando Aspose.Tasks per Java, aiutandoti a ottimizzare le tempistiche del progetto e l'allocazione delle risorse.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Tasks per la libreria Java scaricata e aggiunta al tuo progetto. Puoi scaricarlo da[Aspose.Tasks per la documentazione Java](https://reference.aspose.com/tasks/java/).
## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Passaggio 1: crea un nuovo progetto
Inizia creando un nuovo progetto utilizzando la libreria Aspose.Tasks:
```java
// Crea un nuovo progetto
Project splitTaskProject = new Project();
```
## Passaggio 2: imposta il calendario del progetto
Configura le impostazioni del calendario del progetto per stabilire la sequenza temporale:
```java
// Ottieni un calendario standard
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Configura le impostazioni del calendario del progetto
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continua con l'esempio)
```
## Passaggio 3: aggiungi un'attività di root
Aggiungi un'attività root al tuo progetto:
```java
// Compito di root
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Passaggio 4: aggiungi una nuova attività da dividere
Aggiungi una nuova attività al tuo progetto che desideri dividere:
```java
// Aggiungi una nuova attività
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Passaggio 5: creare un'assegnazione di risorse
Crea una nuova assegnazione di risorse per l'attività:
```java
// Creare una nuova assegnazione di risorse
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Passaggio 6: generare dati rapportati alla scala cronologica
Genera dati di assegnazione delle risorse rapportati alla scala cronologica:
```java
// Genera dati di assegnazione delle risorse rapportati alla scala cronologica
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Passaggio 7: dividere l'attività
Suddividi l'attività in più parti:
```java
// Suddividere il compito in 3 parti
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continua con l'esempio)
```
## Conclusione
Congratulazioni! Hai imparato con successo come dividere le attività utilizzando Aspose.Tasks per Java. Questa potente libreria semplifica la gestione delle attività nei progetti Java, fornendo soluzioni efficienti per ottimizzare le tempistiche del progetto e l'allocazione delle risorse.
## Domande frequenti
### Posso dividere attività con durate diverse?
Sì, puoi modificare la durata delle attività in base ai requisiti del tuo progetto.
### Aspose.Tasks per Java è compatibile con tutte le versioni Java?
Aspose.Tasks per Java è progettato per funzionare perfettamente con varie versioni Java, garantendo la compatibilità.
### Posso utilizzare Aspose.Tasks per Java gratuitamente?
Aspose.Tasks per Java offre una prova gratuita, consentendoti di esplorare le sue funzionalità prima di effettuare un acquisto.
### Come posso ottenere supporto per Aspose.Tasks per Java?
 Visitare il[Aspose.Tasks per il forum di supporto Java](https://forum.aspose.com/c/tasks/15) per ottenere assistenza e connettersi con la comunità.
### Ho bisogno di una licenza temporanea per Aspose.Tasks per Java?
 È possibile ottenere una licenza temporanea da[questo link](https://purchase.aspose.com/temporary-license/) a scopo di test e valutazione.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
