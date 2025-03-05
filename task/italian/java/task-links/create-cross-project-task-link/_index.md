---
title: Crea un collegamento attività tra progetti in Aspose.Tasks
linktitle: Crea un collegamento attività tra progetti in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Migliora la collaborazione sui progetti con Aspose.Tasks per Java. Impara a creare collegamenti di attività tra progetti passo dopo passo. Aumenta l'efficienza ora!
type: docs
weight: 10
url: /it/java/task-links/create-cross-project-task-link/
---
## introduzione
Nel dinamico mondo della gestione dei progetti, l’efficienza e la collaborazione sono fondamentali. Aspose.Tasks per Java fornisce una soluzione solida per migliorare le capacità di gestione dei progetti. In questo tutorial, approfondiremo il processo di creazione di collegamenti di attività tra progetti utilizzando Aspose.Tasks per Java. Questa guida passo passo ti fornirà le competenze per collegare perfettamente le attività tra diversi progetti, favorendo un migliore coordinamento e flussi di lavoro semplificati.
## Prerequisiti
Prima di intraprendere questo tutorial, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza pratica della programmazione Java.
-  Aspose.Tasks per Java installato. Puoi scaricarlo da[Aspose.Tasks per la pagina di rilascio di Java](https://releases.aspose.com/tasks/java/).
- Una conoscenza di base della gestione del progetto e delle dipendenze tra le attività.
## Importa pacchetti
Per avviare il processo, importiamo i pacchetti necessari nel tuo ambiente Java. Ciò garantisce l'accesso alle funzionalità Aspose.Tasks per Java. Utilizza il seguente snippet di codice:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Ora suddividiamo il codice sopra in passaggi comprensibili:
## Passaggio 1: configura il tuo ambiente
Prima di immergerti nel codice, assicurati di avere Java installato e che la libreria Aspose.Tasks per Java sia aggiunta correttamente al tuo progetto.
## Passaggio 2: crea un'istanza del progetto
Inizializza un nuovo progetto utilizzando la libreria Aspose.Tasks:
```java
Project project = new Project();
```
## Passaggio 3: aggiungi un'attività di riepilogo
Crea un'attività di riepilogo per organizzare e gestire le attività collegate:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Passaggio 4: aggiungi attività esterna
Per creare un collegamento a un'attività da un altro progetto, aggiungi un'attività esterna all'attività di riepilogo:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Passaggio 5: aggiungi attività locale
Aggiungi un'attività locale all'attività di riepilogo. Questa sarà l'attività collegata all'attività esterna:
```java
Task t = summary.getChildren().add("Task");
```
## Passaggio 6: crea collegamento attività
Stabilire il collegamento dell'attività tra l'attività esterna e l'attività locale:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Passaggio 7: visualizzare i risultati
Infine, visualizza il risultato della conversione:
```java
System.out.println("Process completed Successfully");
```
## Conclusione
Congratulazioni! Hai imparato con successo come creare collegamenti di attività tra progetti utilizzando Aspose.Tasks per Java. Questa funzionalità migliora la collaborazione e il coordinamento nella gestione dei progetti, garantendo una perfetta integrazione tra le attività in diversi progetti.
## Domande frequenti
### Posso collegare attività di più progetti esterni nella stessa attività di riepilogo?
Sì, puoi collegare attività di diversi progetti esterni all'interno della stessa attività di riepilogo, seguendo un processo simile.
### Cosa succede se l'attività esterna nel progetto collegato viene modificata?
Qualsiasi modifica all'attività esterna si rifletterà nell'attività collegata nel progetto corrente.
### È possibile creare collegamenti tra attività in diversi formati di file?
Sì, Aspose.Tasks per Java supporta il collegamento di attività tra progetti in vari formati di file.
### Posso scollegare le attività una volta collegate tra progetti?
Sì, puoi scollegare le attività rimuovendo il collegamento dell'attività utilizzando i metodi Aspose.Tasks appropriati.
### Esistono limitazioni al numero di attività che possono essere collegate tra progetti?
Il numero di attività che possono essere collegate è soggetto alle capacità e alle limitazioni della licenza Aspose.Tasks.