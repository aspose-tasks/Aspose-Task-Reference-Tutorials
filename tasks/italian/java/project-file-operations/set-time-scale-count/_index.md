---
title: Padroneggiare il conteggio della scala temporale di MS Project in Aspose.Tasks
linktitle: Imposta il conteggio della scala temporale in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come gestire in modo efficace il conteggio della scala temporale in MS Project utilizzando Aspose.Tasks per Java. Ottimizza la visualizzazione e la gestione dei progetti senza sforzo.
weight: 22
url: /it/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare il conteggio della scala temporale di MS Project in Aspose.Tasks

## introduzione
La gestione del conteggio della scala temporale in MS Project può influire in modo significativo sulla visualizzazione e sulla gestione del progetto. Con Aspose.Tasks per Java, una potente API per la gestione programmatica delle attività di gestione dei progetti, puoi manipolare in modo efficiente il conteggio della scala temporale per personalizzare le visualizzazioni del progetto in base alle tue esigenze specifiche.
## Prerequisiti
Prima di iniziare, assicurati di avere a disposizione quanto segue:
1. Ambiente di sviluppo Java: assicurati di avere Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per Java Library: scarica e installa la libreria Aspose.Tasks per Java. Puoi ottenerlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Conoscenza di base della programmazione Java: la familiarità con il linguaggio di programmazione Java sarà utile.

## Importa pacchetti
Importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Passaggio 1: imposta la directory dei dati
Definisci il percorso della directory dei dati in cui verranno archiviati i file di progetto:
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso della directory dei dati.
## Passaggio 2: crea l'istanza del progetto
 Istanziarne uno nuovo`Project` oggetto:
```java
Project project = new Project();
```
Questo crea un nuovo oggetto di progetto.
## Passaggio 3: configura la visualizzazione del diagramma di Gantt
 Creare un`GanttChartView` oggetto per configurare la visualizzazione del diagramma di Gantt:
```java
GanttChartView view = new GanttChartView();
```
## Passaggio 4: impostare il conteggio della scala temporale per il livello inferiore
Imposta il conteggio e la visibilità dei tick per il livello della scala cronologica inferiore:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Specifica il conteggio degli intervalli e se visualizzare i segni di spunta per il livello inferiore.
## Passaggio 5: impostare il conteggio della scala temporale per il livello intermedio
Allo stesso modo, configura il livello della scala temporale intermedia:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Passaggio 6: aggiungi vista al progetto
Aggiungi la vista configurata al progetto:
```java
project.getViews().add(view);
```
Ciò aggiunge la vista personalizzata al progetto.
## Passaggio 7: aggiungere i dati di test al progetto
Aggiungi alcuni dati di test al progetto per la dimostrazione:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Ciò crea due attività con durate specificate.
## Passaggio 8: salva il progetto come PDF
Salvare il progetto come file PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Ciò salva il progetto con le configurazioni applicate in un file PDF.

## Conclusione
La gestione efficace del conteggio della scala temporale in MS Project utilizzando Aspose.Tasks per Java ti consente di personalizzare le visualizzazioni del progetto per una migliore visualizzazione e gestione.
## Domande frequenti
### D: Aspose.Tasks per Java può gestire file di progetto su larga scala?
R: Sì, Aspose.Tasks per Java è in grado di gestire in modo efficiente file di progetto su larga scala.
### D: Aspose.Tasks per Java è compatibile con diversi IDE Java?
R: Sì, Aspose.Tasks per Java funziona perfettamente con i più diffusi ambienti di sviluppo integrato Java (IDE) come Eclipse e IntelliJ IDEA.
### D: Posso personalizzare l'aspetto dei diagrammi di Gantt utilizzando Aspose.Tasks per Java?
R: Assolutamente, Aspose.Tasks per Java offre ampie funzionalità per personalizzare l'aspetto dei diagrammi di Gantt in base alle proprie esigenze.
### D: È disponibile una versione di prova per Aspose.Tasks per Java?
 R: Sì, puoi ottenere una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Dove posso ottenere supporto per Aspose.Tasks per Java?
 R: Puoi trovare supporto e assistenza sul forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
