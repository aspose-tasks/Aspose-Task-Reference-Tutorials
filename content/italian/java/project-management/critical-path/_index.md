---
title: Calcola il percorso critico del progetto MS in Aspose.Tasks
linktitle: Calcola il percorso critico nei progetti Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come calcolare il percorso critico in MS Project utilizzando Aspose.Tasks per Java. Ciò fornisce una guida passo passo per una gestione efficiente del progetto.
type: docs
weight: 10
url: /it/java/project-management/critical-path/
---
## introduzione
In questo tutorial, ti guideremo attraverso il processo di calcolo del percorso critico in MS Project utilizzando Aspose.Tasks per Java. Il percorso critico è essenziale per la gestione del progetto poiché aiuta a identificare la sequenza di attività che devono essere completate in tempo per garantire che la pianificazione complessiva del progetto non subisca ritardi.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per la libreria Java scaricata e aggiunta al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nella tua classe Java:
```java
import com.aspose.tasks.*;
```
## Passaggio 1: impostare la directory dei dati
Definisci il percorso della directory dei dati in cui si trova il file MS Project.
```java
String dataDir = "Your Data Directory";
```
## Passaggio 2: caricare il file MS Project
Carica il file MS Project utilizzando la libreria Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Passaggio 3: impostare la modalità di calcolo
Impostare la modalità di calcolo su automatica per abilitare il calcolo del percorso critico.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## Passaggio 4: aggiungi attività
Aggiungi attività al tuo progetto. In questo esempio aggiungiamo tre attività secondarie.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## Passaggio 5: creare collegamenti alle attività
Creare collegamenti alle attività per definire le dipendenze tra le attività.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## Passaggio 6: Visualizza il percorso critico
Recuperare e visualizzare il percorso critico del progetto.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## Passaggio 7: Visualizza risultato
Visualizza un messaggio che indica il completamento positivo del processo.
```java
System.out.println("Process completed Successfully");
```

## Conclusione
Il calcolo del percorso critico in MS Project utilizzando Aspose.Tasks per Java è fondamentale per una gestione efficace del progetto. Seguendo i passaggi descritti in questo tutorial, puoi identificare con precisione la sequenza delle attività fondamentali per la sequenza temporale del tuo progetto.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per Java con qualsiasi versione dei file MS Project?
R: Sì, Aspose.Tasks per Java supporta varie versioni di file MS Project, inclusi i file .mpp da MS Project 2003 a MS Project 2019.
### D: È disponibile una prova gratuita per Aspose.Tasks per Java?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Dove posso trovare supporto per Aspose.Tasks per Java?
 R: Puoi trovare supporto su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### D: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
 R: Sì, puoi acquistare una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).
### D: Come posso acquistare Aspose.Tasks per Java?
 R: È possibile acquistare Aspose.Tasks per Java dal sito Web[Qui](https://purchase.aspose.com/buy).