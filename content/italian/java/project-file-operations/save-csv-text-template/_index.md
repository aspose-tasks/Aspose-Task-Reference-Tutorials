---
title: Salva come CSV, testo e modello in Aspose.Tasks
linktitle: Salva come CSV, testo e modello in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come salvare i file di Microsoft Project nei formati CSV, testo e modello utilizzando Aspose.Tasks per Java.
type: docs
weight: 16
url: /it/java/project-file-operations/save-csv-text-template/
---
## introduzione
In questo tutorial esploreremo come salvare i file di progetto in vari formati come CSV, testo e modello utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente libreria Java che consente agli sviluppatori di lavorare con file Microsoft Project senza la necessità di installare Microsoft Project.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per la libreria Java scaricata e configurata nel tuo progetto Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Conoscenza base del linguaggio di programmazione Java.

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo file Java:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Salva progetto come CSV
Analizziamo i passaggi per salvare un progetto come CSV:
### Passaggio 1: caricare il progetto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Passaggio 2: salva come CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Salva progetto come testo
Ecco come puoi salvare un progetto come testo:
### Passaggio 1: caricare il progetto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Passaggio 2: salva come testo
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Salva progetto come modello
Il salvataggio di un progetto come modello prevede i seguenti passaggi:
### Passaggio 1: caricare il progetto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Passaggio 2: imposta le opzioni del modello
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Passaggio 3: salva come modello
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Conclusione
In questo tutorial, abbiamo imparato come salvare i file di Microsoft Project come CSV, testo e modello utilizzando Aspose.Tasks per Java. Con questi semplici passaggi, puoi gestire in modo efficiente i file di progetto in vari formati, migliorando la tua produttività come sviluppatore Java.
## Domande frequenti
### D: Aspose.Tasks per Java può gestire file di progetto complessi?
R: Assolutamente! Aspose.Tasks per Java può gestire facilmente progetti di varia complessità, fornendo un supporto completo per i formati di file di Microsoft Project.
### D: È disponibile una versione di prova per Aspose.Tasks per Java?
 R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per Java da[Qui](https://releases.aspose.com/).
### D: Dove posso trovare supporto per Aspose.Tasks per Java?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda riguardante Aspose.Tasks per Java.
### D: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
 R: Sì, puoi acquistare una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/), permettendoti di valutare tutte le potenzialità della libreria.
### D: Aspose.Tasks per Java è compatibile con diversi sistemi operativi?
R: Sì, Aspose.Tasks per Java è compatibile con vari sistemi operativi, inclusi Windows, macOS e Linux.