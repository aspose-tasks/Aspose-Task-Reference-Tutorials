---
title: Durata dell'attività in diverse unità con Aspose.Tasks
linktitle: Durata dell'attività in diverse unità con Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora la gestione della durata delle attività nei progetti Java con Aspose.Tasks. Calcola e converti con precisione le durate in minuti, giorni, ore, settimane e mesi.
type: docs
weight: 32
url: /it/java/task-properties/task-duration-different-units/
---
## introduzione
Nell'ambito della gestione dei progetti, comprendere e gestire la durata delle attività è un aspetto critico. Aspose.Tasks per Java fornisce un potente set di strumenti per gestirlo in modo efficiente. In questo tutorial ti guideremo attraverso il recupero delle durate delle attività in varie unità utilizzando Aspose.Tasks.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Kit di sviluppo Java (JDK) installato
-  Aspose.Tasks per la libreria Java. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/java/)
- Una conoscenza di base della programmazione Java
## Importa pacchetti
Nel tuo progetto Java, includi la libreria Aspose.Tasks. Aggiungi la seguente istruzione di importazione all'inizio del codice:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Passaggio 1: imposta il tuo progetto
Inizia creando un nuovo progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito. Assicurati di includere la libreria Aspose.Tasks nelle dipendenze del tuo progetto.
## Passaggio 2: leggere il modello di progetto
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Leggi il file modello di MS Project
String fileName = dataDir + "project.xml";
// Leggere il file di input come Progetto
Project project = new Project(fileName);
```
 Assicurarsi di sostituire`"Your Document Directory"` con il percorso effettivo dei file di progetto.
## Passaggio 3: recuperare un'attività
```java
// Ottieni un'attività per calcolarne la durata in diversi formati
Task task = project.getRootTask().getChildren().getById(1);
```
 Qui stiamo ottenendo un'attività dal progetto. Regolare`getById(1)` in base all'ID attività del tuo progetto.
## Passaggio 4: durata in minuti
```java
// Ottieni la durata in minuti
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Questo passaggio calcola la durata dell'attività in minuti.
## Passaggio 5: durata in giorni
```java
// Ottieni la durata in giorni
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Questo passaggio calcola la durata dell'attività in giorni.
## Passaggio 6: durata in ore
```java
// Ottieni la durata in ore
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Questo passaggio calcola la durata dell'attività in ore.
## Passaggio 7: durata in settimane
```java
// Ottieni la durata in settimane
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Questo passaggio calcola la durata dell'attività in settimane.
## Passaggio 8: durata in mesi
```java
// Ottieni la durata in mesi
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Questo passaggio calcola la durata dell'attività in mesi.
## Conclusione
La gestione della durata delle attività è semplificata con Aspose.Tasks per Java. Questo tutorial ti ha guidato attraverso il processo passo dopo passo, fornendo chiarezza sulle diverse unità di tempo.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per Java con qualsiasi IDE Java?
Sì, Aspose.Tasks per Java è compatibile con qualsiasi Java Integrated Development Environment (IDE).
### D: Come posso ottenere l'ID di un'attività in un file di Microsoft Project?
È possibile controllare il file di progetto o utilizzare l'API Aspose.Tasks per recuperare gli ID attività a livello di codice.
### D: Aspose.Tasks è adatto alla gestione di progetti su larga scala?
Assolutamente. Aspose.Tasks è progettato per gestire in modo efficiente progetti di varie dimensioni.
### D: Dove posso trovare ulteriore documentazione?
 Visitare il[documentazione](https://reference.aspose.com/tasks/java/)per risorse complete.
### D: Posso provare Aspose.Tasks per Java prima dell'acquisto?
 Sì, puoi esplorare a[prova gratuita](https://releases.aspose.com/) per valutarne le capacità.