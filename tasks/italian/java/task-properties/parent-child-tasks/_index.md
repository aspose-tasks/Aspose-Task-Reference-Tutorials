---
title: Gestisci attività padre e figlio in Aspose.Tasks
linktitle: Gestisci attività padre e figlio in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Migliora l'efficienza della gestione dei progetti con Aspose.Tasks per Java. Impara a gestire le attività di genitore e figlio passo dopo passo. Inizia ora!
weight: 24
url: /it/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestisci attività padre e figlio in Aspose.Tasks

## introduzione
Nell’ambito della gestione dei progetti, un’organizzazione efficace delle attività è fondamentale. Aspose.Tasks per Java fornisce una soluzione solida per gestire in modo efficiente le attività padre e figlio. In questo tutorial, ti guideremo attraverso il processo di utilizzo di Aspose.Tasks per Java per semplificare le attività del tuo progetto.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza di base della programmazione Java.
-  Aspose.Tasks per la libreria Java installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/java/).
- Un ambiente di sviluppo integrato Java (IDE) configurato sul tuo sistema.
## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Questi pacchetti facilitano la perfetta integrazione con Aspose.Tasks per le funzionalità Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Passaggio 1: imposta la data di inizio del progetto
Inizia impostando la data di inizio del progetto e altri parametri rilevanti.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Qui è possibile aggiungere codice aggiuntivo per le importazioni di pacchetti
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Passaggio 2: aggiungi attività principale (attività 1)
Crea un'attività principale denominata "Attività 1" e configurane le proprietà.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Passaggio 3: aggiungere l'attività principale (attività 2) con le attività secondarie
Ora aggiungi un'altra attività principale denominata "Attività 2" e includi le attività secondarie (Attività 3 e Attività 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Aggiungi attività secondarie all'attività 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Qui è possibile aggiungere ulteriori configurazioni per l'Attività 3 e l'Attività 4
```
## Passaggio 4: configura le attività secondarie
Specificare date di inizio, durate e vincoli per l'Attività 3 e l'Attività 4.
```java
// Configura l'attività 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configura l'attività 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Passaggio 5: aggiorna la percentuale di completamento delle attività
Modifica la percentuale di completamento per l'Attività 3 e l'Attività 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Passaggio 6: salva il progetto
Infine, salva il progetto con le modifiche applicate.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Questa guida passo passo dimostra come gestire le attività padre e figlio in modo efficace utilizzando Aspose.Tasks per Java. Sperimenta diverse configurazioni per soddisfare le esigenze del tuo progetto.
## Conclusione
In conclusione, Aspose.Tasks per Java consente agli sviluppatori di gestire in modo efficiente le attività del progetto, garantendo organizzazione e monitoraggio senza soluzione di continuità. Implementa i passaggi delineati per migliorare le tue capacità di gestione del progetto.
## Domande frequenti
### Aspose.Tasks per Java è compatibile con diversi formati di file di progetto?
Sì, Aspose.Tasks per Java supporta vari formati di file di progetto, inclusi MPP e XML.
### Posso personalizzare le proprietà dell'attività oltre a quanto trattato in questo tutorial?
Assolutamente! Aspose.Tasks per Java fornisce ampie opzioni di personalizzazione per le proprietà dell'attività.
### Esiste un forum della community per Aspose.Tasks dove posso cercare supporto?
 Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il sostegno della comunità.
### Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare la documentazione completa per Aspose.Tasks per Java?
 La documentazione è disponibile[Qui](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
