---
title: Gestione della durata prevista delle attività in Aspose.Tasks
linktitle: Gestione della durata prevista delle attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come gestire in modo efficiente le basi delle attività in MS Project utilizzando Aspose.Tasks per Java. Questo tutorial ti guida passo passo attraverso il processo.
type: docs
weight: 12
url: /it/java/task-baselines/task-baseline-duration/
---
## introduzione
La gestione delle basi delle attività in MS Project è fondamentale per la pianificazione e il monitoraggio del progetto. In questo tutorial esploreremo come gestire in modo efficace le durate della baseline delle attività utilizzando Aspose.Tasks per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Ambiente di sviluppo Java: assicurati di avere Java Development Kit (JDK) installato sul tuo sistema.
2.  Libreria Aspose.Tasks: scarica e installa la libreria Aspose.Tasks per Java da[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari per il tuo progetto Java:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Passaggio 1: crea un'istanza del progetto
Inizializza una nuova istanza del progetto utilizzando il seguente codice:
```java
Project project = new Project();
```
## Passaggio 2: creare una previsione delle attività
Crea una nuova attività e imposta la sua baseline utilizzando il seguente codice:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Passaggio 3: visualizzare le informazioni sulla baseline delle attività
Recupera e visualizza informazioni sulla baseline delle attività come durata, data di inizio, data di fine e altro:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Passaggio 4: verificare la previsione provvisoria e i costi fissi
Controlla se la previsione è una previsione provvisoria e recupera eventuali costi fissi ad essa associati:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Passaggio 5: stampa dei dati rapportati alla scala cronologica
Stampa i dati rapportati alla scala cronologica associati alla baseline dell'attività:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Seguendo questi passaggi, puoi gestire in modo efficace le durate della previsione delle attività in MS Project utilizzando Aspose.Tasks per Java.

## Conclusione
La gestione delle previsioni delle attività è essenziale per la gestione dei progetti, poiché consente di tenere traccia delle deviazioni dalla pianificazione pianificata. Con Aspose.Tasks per Java, questo processo diventa snello ed efficiente, consentendo un migliore controllo e consegna del progetto.
## Domande frequenti
### Che cos'è una base di attività in MS Project?
Una previsione dell'attività in MS Project è un'istantanea della pianificazione pianificata iniziale per un'attività, inclusa la data di inizio, la data di fine e la durata.
### Perché la gestione delle attività di base è importante?
La gestione delle attività di base aiuta a confrontare la pianificazione pianificata con lo stato di avanzamento effettivo del progetto, facilitando un migliore monitoraggio e processo decisionale.
### Posso modificare una previsione di attività una volta impostata?
Sì, puoi modificare le basi delle attività in MS Project per riflettere le modifiche nel piano del progetto. Tuttavia, è essenziale documentare eventuali deviazioni rispetto al valore di riferimento originale.
### Aspose.Tasks supporta altre funzionalità di gestione dei progetti?
Sì, Aspose.Tasks offre un'ampia gamma di funzionalità per la gestione dei progetti, tra cui la pianificazione delle attività, l'allocazione delle risorse e la generazione di diagrammi di Gantt.
### Dove posso trovare supporto per Aspose.Tasks?
 Puoi trovare supporto per Aspose.Tasks su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), dove puoi porre domande e interagire con altri utenti.