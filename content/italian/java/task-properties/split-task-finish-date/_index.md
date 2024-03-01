---
title: Data di fine attività divisa in Aspose.Tasks
linktitle: Data di fine attività divisa in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come dividere le date di fine delle attività senza sforzo utilizzando Aspose.Tasks per Java. Migliora la gestione dei progetti con tempistiche precise.
type: docs
weight: 28
url: /it/java/task-properties/split-task-finish-date/
---
## introduzione
Nella gestione dei progetti, comprendere le tempistiche delle attività è fondamentale per il successo del completamento del progetto. Aspose.Tasks per Java fornisce potenti funzionalità per manipolare le attività del progetto in modo efficiente. In questo tutorial, approfondiremo la suddivisione delle date di fine delle attività utilizzando Aspose.Tasks, aiutandoti a gestire le tempistiche del progetto in modo efficace.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza base della programmazione Java.
-  Aspose.Tasks per la libreria Java installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/java/).
- Predisposizione di un ambiente di sviluppo Java.
## Importa pacchetti
Inizia includendo i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.*;
```
## Passaggio 1: trova un'attività divisa
Individua l'attività che desideri suddividere all'interno del progetto:
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Leggi il progetto
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Passaggio 2: trova il calendario del progetto
Recupera il calendario del progetto per calcoli accurati delle date:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Passaggio 3: calcolare la data di fine dell'attività con durate diverse
Ora calcola la data di fine dell'attività per varie durate:
## Passaggio 3.1: durata di 8 ore
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Ripetere il codice sopra per durate diverse, regolando le ore di conseguenza.
## Conclusione
Padroneggiare l'arte di manipolare le date di fine delle attività è fondamentale per una gestione efficace del progetto. Aspose.Tasks per Java semplifica questo processo, permettendoti di semplificare le tempistiche del tuo progetto senza sforzo.
## Domande frequenti
### Q1: Come posso scaricare Aspose.Tasks per Java?
 A1: Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/java/).
### Q2: dove posso trovare la documentazione per Aspose.Tasks?
 A2: Fare riferimento alla documentazione[Qui](https://reference.aspose.com/tasks/java/).
### Q3: Come posso ottenere una licenza temporanea per Aspose.Tasks?
 A3: Ottieni una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Q4: Dove posso chiedere supporto per Aspose.Tasks?
 R4: Visita il forum di supporto[Qui](https://forum.aspose.com/c/tasks/15).
### Q5: Posso acquistare Aspose.Tasks?
 A5: Sì, puoi acquistarlo[Qui](https://purchase.aspose.com/buy).