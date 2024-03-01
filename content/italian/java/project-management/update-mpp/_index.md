---
title: Aggiorna il file MPP in Aspose.Tasks
linktitle: Aggiorna il file MPP in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come aggiornare i file MPP senza problemi utilizzando Aspose.Tasks per Java. Segui la nostra guida passo passo per una manipolazione efficiente dei file di progetto.
type: docs
weight: 19
url: /it/java/project-management/update-mpp/
---
## introduzione
Nell'ambito della gestione dei progetti, la gestione e l'aggiornamento dei file di progetto è un compito cruciale. Aspose.Tasks per Java fornisce una potente soluzione agli sviluppatori Java per manipolare i file di Microsoft Project senza problemi. In questo tutorial, approfondiremo l'aggiornamento dei file MPP utilizzando Aspose.Tasks per Java.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere quanto segue:
1. Ambiente di sviluppo Java: assicurati di avere Java installato sul tuo sistema.
2.  Aspose.Tasks per Java: Scarica e installa Aspose.Tasks per Java dal file[pagina di download](https://releases.aspose.com/tasks/java/).
3. Conoscenza di base di Java: è necessaria la familiarità con il linguaggio di programmazione Java insieme agli esempi.

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo progetto Java per utilizzare in modo efficace le funzionalità Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Questa riga di codice importa tutte le classi e i metodi essenziali dalla libreria Aspose.Tasks, consentendoti di lavorare senza sforzo con i file di Microsoft Project.

Ora, analizziamo il processo di aggiornamento di un file MPP utilizzando Aspose.Tasks per Java in passaggi gestibili.
## Passaggio 2: definire la directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso effettivo in cui si trova il file MPP.
## Passaggio 3: leggere il progetto esistente
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Questo codice legge un file di progetto MPP esistente denominato`SampleMSP2010.mpp` dalla directory dei dati specificata.
## Passaggio 4: crea una nuova attività
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Qui aggiungiamo una nuova attività denominata "Task1" all'attività root del progetto.
## Passaggio 5: imposta le date di inizio e fine
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Queste righe di codice impostano la data di inizio e la data di fine per l'attività appena creata.
## Passaggio 6: salva il progetto
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Infine, questo passaggio salva il progetto aggiornato con l'attività appena aggiunta in un nuovo file MPP denominato`AfterLinking.mpp`.

## Conclusione
In questo tutorial, abbiamo esplorato come aggiornare i file MPP utilizzando Aspose.Tasks per Java. Seguendo la guida passo passo, puoi manipolare in modo efficiente i file Microsoft Project all'interno delle tue applicazioni Java.
## Domande frequenti
### D: Aspose.Tasks per Java può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks per Java fornisce funzionalità robuste per gestire strutture di progetti complessi in modo efficiente.
### D: È disponibile una prova gratuita per Aspose.Tasks per Java?
 R: Sì, puoi scaricare una versione di prova gratuita da[sito web](https://releases.aspose.com/).
### D: Aspose.Tasks per Java supporta diverse versioni dei file Microsoft Project?
R: Assolutamente, Aspose.Tasks per Java supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.
### D: Posso ottenere licenze temporanee per Aspose.Tasks per Java?
 R: Sì, sono disponibili licenze temporanee a scopo di test. Puoi ottenerli da[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).
### D: Dove posso cercare aiuto o supporto per quanto riguarda Aspose.Tasks per Java?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.