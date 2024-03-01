---
title: Aggiorna i dati delle attività in formato MPP in Aspose.Tasks
linktitle: Aggiorna i dati delle attività in formato MPP in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come aggiornare i dati delle attività in formato MPP utilizzando Aspose.Tasks per Java. Segui la nostra guida passo passo per una gestione efficiente del progetto.
type: docs
weight: 35
url: /it/java/task-properties/update-task-data/
---
## introduzione
Benvenuti nella nostra guida passo passo sull'aggiornamento dei dati delle attività in formato MPP utilizzando Aspose.Tasks per Java. In questo tutorial ti guideremo attraverso il processo, assicurandoti di comprendere ogni passaggio con chiarezza. Aspose.Tasks per Java fornisce una soluzione solida per lavorare con i file Microsoft Project e, alla fine di questa guida, sarai in grado di aggiornare in modo efficiente i dati delle attività in formato MPP.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Tasks per Java: assicurati di avere la libreria Aspose.Tasks installata. Puoi scaricarlo da[pagina di rilascio](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema.
- Ambiente di sviluppo integrato (IDE): utilizza un IDE di tua scelta per lo sviluppo Java.
## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java. Il frammento seguente mostra come importare i pacchetti:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Creare e configurare l'attività iniziale
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continua con il resto del codice)
```
## 2. Impostare la data di inizio e la durata
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continua con il resto del codice)
```
## 3. Creare un'attività di riepilogo
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continua con il resto del codice)
```
## 4. Imposta la scadenza e le note sull'attività
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continua con il resto del codice)
```
## 5. Configurare i vincoli delle attività
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continua con il resto del codice)
```
## 6. Creare attività aggiuntive
```java
//Crea 10 nuove attività
for (int i = 0; i < 10; i++) {
    //... (Continua con il resto del codice)
}
//... (Continua con il resto del codice)
```
## 7. Salvare il progetto
```java
// Salva il progetto
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Seguendo questi passaggi, hai aggiornato con successo i dati delle attività in formato MPP utilizzando Aspose.Tasks per Java.
## Conclusione
Congratulazioni! Hai completato una guida completa sull'aggiornamento dei dati delle attività in formato MPP utilizzando Aspose.Tasks per Java. Questa potente libreria semplifica le attività di gestione dei progetti, rendendola uno strumento prezioso per gli sviluppatori Java.
## Domande frequenti
### D: Dove posso trovare la documentazione Aspose.Tasks per Java?
 R: La documentazione è disponibile[Qui](https://reference.aspose.com/tasks/java/).
### D: Come posso scaricare Aspose.Tasks per Java?
 R: Puoi scaricarlo da[pagina di rilascio](https://releases.aspose.com/tasks/java/).
### D: È disponibile una prova gratuita?
 R: Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso ottenere supporto per Aspose.Tasks per Java?
 R: Visita il forum di supporto[Qui](https://forum.aspose.com/c/tasks/15).
### D: Offrite licenze temporanee a scopo di test?
 R: Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).