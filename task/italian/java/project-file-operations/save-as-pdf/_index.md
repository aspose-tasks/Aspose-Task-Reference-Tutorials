---
title: Salva come PDF in Aspose.Tasks
linktitle: Salva come PDF in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come convertire i file di progetto in PDF utilizzando Aspose.Tasks per Java. Semplici passaggi per una conversione efficiente.
type: docs
weight: 17
url: /it/java/project-file-operations/save-as-pdf/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo di salvataggio di un progetto come PDF utilizzando Aspose.Tasks per Java. Con Aspose.Tasks puoi convertire in modo efficiente i file di progetto in formato PDF, garantendo compatibilità e facilità di condivisione. Immergiamoci nei passaggi:
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Tasks per Java Library: scarica e installa la libreria Aspose.Tasks. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/tasks/java/).
3. Un file di progetto: tieni pronto un file di progetto (ad esempio, HomeMovePlan.mpp) che desideri convertire in PDF.

## Importa pacchetti
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Passaggio 1: leggere il file di progetto di input
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Assicurati di sostituire`"Your Data Directory"` con il percorso della directory dei dati contenente il file di progetto.
## Passaggio 2: salva il progetto come PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Questo frammento di codice salva il progetto come file PDF con il nome "Project5.pdf".
## Passaggio 3: adattamento dei contenuti alle dimensioni della cella
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Qui impostiamo le opzioni per il salvataggio del PDF, incluso l'adattamento del contenuto, la scala temporale e il formato della presentazione.
## Passaggio 4: nascondi le leggende
```java
o.setLegendOnEachPage(false);
```
Questo passaggio nasconde le legende su ogni pagina del PDF.
## Passaggio 5: salva il progetto con le opzioni applicate
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Infine, questo codice salva il progetto con le opzioni applicate in un file PDF.

## Conclusione
In questo tutorial, abbiamo imparato come utilizzare Aspose.Tasks per Java per salvare un progetto come PDF. Seguendo questi semplici passaggi, puoi convertire in modo efficiente i file di progetto per condividerli e distribuirli facilmente.
## Domande frequenti
### D: Aspose.Tasks è compatibile con tutte le versioni di Java?
R: Sì, Aspose.Tasks supporta le versioni Java a partire da JDK 6 e successive.
### D: Posso personalizzare l'aspetto dell'output PDF?
R: Assolutamente! Aspose.Tasks fornisce varie opzioni per personalizzare l'output PDF in base alle proprie esigenze.
### D: Aspose.Tasks supporta altri formati di file per la conversione?
R: Sì, Aspose.Tasks supporta un'ampia gamma di formati di file, inclusi MPP, XML, XLSX e altri.
### D: È disponibile una versione di prova per Aspose.Tasks?
 R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### D: Dove posso ottenere supporto per Aspose.Tasks?
 R: Per supporto e assistenza, è possibile visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).