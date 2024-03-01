---
title: Gestire le durate delle attività in Aspose.Tasks
linktitle: Gestire le durate delle attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora Aspose.Tasks per Java e impara a gestire la durata delle attività senza sforzo. Segui la nostra guida passo passo per una pianificazione ed esecuzione efficace del progetto.
type: docs
weight: 20
url: /it/java/task-properties/manage-durations/
---
## introduzione
Aspose.Tasks per Java fornisce una soluzione solida per gestire in modo efficiente le attività e le durate del progetto. In questo tutorial esploreremo come gestire la durata delle attività utilizzando Aspose.Tasks, guidandoti attraverso ogni passaggio. Che tu sia uno sviluppatore esperto o un principiante, questa guida ti aiuterà a cogliere gli elementi essenziali per lavorare con le durate delle attività nei tuoi progetti.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
-  Java Development Kit (JDK): assicurati di avere Java installato sul tuo computer. Puoi scaricarlo[Qui](https://www.oracle.com/java/technologies/javase-downloads.html).
- Libreria Aspose.Tasks: scarica e includi la libreria Aspose.Tasks nel tuo progetto. Puoi trovare la biblioteca[Qui](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per lavorare con Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Passaggio 1: imposta il tuo progetto
```java
// Crea un nuovo progetto
Project project = new Project();
```
## Passaggio 2: aggiungi una nuova attività
```java
// Aggiungi una nuova attività al progetto
Task task = project.getRootTask().getChildren().add("Task");
```
## Passaggio 3: ottieni e converti la durata dell'attività
```java
// Ottieni la durata dell'attività in giorni (unità di tempo predefinita)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Converti la durata nell'unità di tempo delle ore
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Passaggio 4: aggiorna la durata dell'attività a 1 settimana
```java
// Aumenta la durata dell'attività a 1 settimana
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Passaggio 5: ridurre la durata dell'attività
```java
// Diminuire la durata dell'attività
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Seguendo questi passaggi, hai gestito con successo la durata delle attività nel tuo progetto Aspose.Tasks per Java.
## Conclusione
In questo tutorial, abbiamo trattato le nozioni di base sulla gestione delle durate delle attività utilizzando Aspose.Tasks per Java. Ora puoi incorporare con sicurezza queste tecniche nei tuoi progetti per una gestione efficace della durata delle attività.
## Domande frequenti
### Aspose.Tasks è compatibile con tutte le versioni Java?
Aspose.Tasks è compatibile con Java 6 e versioni successive.
### Posso utilizzare Aspose.Tasks per progetti commerciali?
 Sì, puoi utilizzare Aspose.Tasks sia per progetti personali che commerciali. Visita[Qui](https://purchase.aspose.com/buy) per i dettagli sulla licenza.
### Dove posso trovare ulteriore supporto e risorse?
 Visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto e le discussioni della comunità.
### Come posso ottenere una licenza temporanea a scopo di test?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) per test e valutazioni.
### È disponibile una prova gratuita per Aspose.Tasks?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/) per esplorare Aspose.Tasks prima di effettuare un acquisto.