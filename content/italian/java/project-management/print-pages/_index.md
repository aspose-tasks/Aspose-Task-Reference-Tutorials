---
title: Stampa le pagine per separare l'immagine in Aspose.Tasks
linktitle: Stampa le pagine per separare l'immagine in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come stampare pagine per separare immagini in Aspose.Tasks per Java. Migliora la visualizzazione del progetto con questa guida passo passo.
type: docs
weight: 22
url: /it/java/project-management/print-pages/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo di stampa delle pagine per separare le immagini utilizzando Aspose.Tasks per Java. Questa funzionalità può essere particolarmente utile quando è necessario visualizzare separatamente layout di progetto o attività critiche.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo da[Qui](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks per Java Library: scarica e includi la libreria Aspose.Tasks per Java nel tuo progetto. Puoi ottenerlo da[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Assicurati di importare i pacchetti necessari all'inizio del tuo file Java:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Passaggio 1: caricare i dati del progetto
Innanzitutto, carica i dati del progetto dal tuo file MPP:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Passaggio 2: imposta le opzioni di salvataggio dell'immagine
Definire le opzioni per salvare l'immagine, tra cui data di inizio, data di fine, attività critiche, legenda e griglia:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Passaggio 3: personalizzare le griglie
Personalizza le linee della griglia per l'immagine, specificando tipo, colore e motivo:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Passaggio 4: salva le immagini
Salva il layout del progetto come immagini, sia come file singolo che come file separati:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Conclusione
In questo tutorial, abbiamo dimostrato come stampare pagine per separare immagini utilizzando Aspose.Tasks per Java. Seguendo i passaggi sopra descritti, puoi visualizzare in modo efficiente i layout del progetto e le attività critiche in base alle tue esigenze.
## Domande frequenti
### D: Posso personalizzare il formato dell'immagine durante il salvataggio dei layout del progetto?
 R: Sì, Aspose.Tasks per Java supporta vari formati di immagine come PNG, JPEG, BMP, ecc. È possibile specificare il formato desiderato nel`ImageSaveOptions` classe.
### D: Aspose.Tasks per Java è compatibile con diversi ambienti di sviluppo Java?
R: Sì, Aspose.Tasks per Java è compatibile con la maggior parte degli ambienti di sviluppo Java, inclusi Eclipse, IntelliJ IDEA e NetBeans.
### D: Posso integrare Aspose.Tasks per Java nel mio progetto Maven o Gradle?
R: Sì, puoi facilmente integrare Aspose.Tasks per Java nel tuo progetto Maven o Gradle aggiungendo la dipendenza appropriata nel tuo`pom.xml` O`build.gradle` file.
### D: Aspose.Tasks per Java supporta l'esportazione dei dati del progetto in altri formati oltre alle immagini?
R: Sì, Aspose.Tasks per Java supporta l'esportazione dei dati del progetto in vari formati come PDF, HTML, XLSX, ecc., fornendo flessibilità nella visualizzazione e nel reporting dei dati.
### D: È disponibile supporto comunitario per Aspose.Tasks per Java?
 R: Sì, puoi trovare il supporto della community, porre domande e interagire con altri utenti su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).