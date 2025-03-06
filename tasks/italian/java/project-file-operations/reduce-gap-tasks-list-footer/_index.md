---
title: Ridurre il divario tra l'elenco delle attività e il piè di pagina in Aspose.Tasks
linktitle: Ridurre il divario tra l'elenco delle attività e il piè di pagina in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come ridurre il divario tra gli elenchi di attività e i piè di pagina di MS Project utilizzando Aspose.Tasks per Java. Ottimizza il layout del documento di progetto senza sforzo.
weight: 10
url: /it/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ridurre il divario tra l'elenco delle attività e il piè di pagina in Aspose.Tasks

## introduzione
In questo tutorial, approfondiremo la riduzione del divario tra l'elenco delle attività e il piè di pagina nei file di Microsoft Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi, sarai in grado di ottimizzare il layout dei documenti del tuo progetto senza sforzo.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Tasks per Java Library: scarica e includi la libreria Aspose.Tasks per Java nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Prima di immergerci nella parte di codifica, importiamo i pacchetti necessari:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Passaggio 1: fornisci il percorso della directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Assicurati di sostituire`"Your Data Directory"` con il percorso della directory dei dati effettiva in cui si trova il file Microsoft Project (`HomeMovePlan.mpp` in questo esempio) si trova.
## Passaggio 2: leggere il file MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Questa riga di codice legge il file di Microsoft Project denominato`HomeMovePlan.mpp`.
## Passaggio 3: imposta le opzioni ImageSave
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Configurare le opzioni di salvataggio dell'immagine, impostazione`ReduceFooterGap` A`true` per ridurre il divario tra l'elenco delle attività e il piè di pagina.
## Passaggio 4: salva come immagine
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Salva il progetto come immagine con le opzioni configurate.
## Passaggio 5: imposta PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Definire le opzioni di salvataggio del PDF, assicurandosi di impostarle`ReduceFooterGap` A`true`.
## Passaggio 6: salva come PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Salva il progetto come PDF con le opzioni configurate.
## Passaggio 7: imposta HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // impostato su vero
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Specificare le opzioni di salvataggio HTML, impostazione`ReduceFooterGap` A`true`.
## Passaggio 8: salva come HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Salva il progetto come file HTML con le opzioni configurate.

## Conclusione
In conclusione, ridurre il divario tra l'elenco delle attività e il piè di pagina nei file di Microsoft Project è un processo semplice con Aspose.Tasks per Java. Seguendo i passaggi descritti in questo tutorial, puoi ottimizzare in modo efficiente il layout dei documenti del tuo progetto.

## Domande frequenti

### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?

R: Aspose.Tasks supporta i formati Microsoft Project 2003-2019, garantendo la compatibilità tra varie versioni.

### D: Posso personalizzare l'aspetto del piè di pagina nei documenti del mio progetto?

R: Sì, Aspose.Tasks offre ampie opzioni per personalizzare l'aspetto dei piè di pagina, inclusa la riduzione degli spazi vuoti e la regolazione del posizionamento dei contenuti.

### D: Aspose.Tasks supporta il salvataggio di progetti in formati diversi da PNG, PDF e HTML?

R: Sì, Aspose.Tasks supporta un'ampia gamma di formati, tra cui XLSX, XML e MPP, tra gli altri.

### D: È disponibile una versione di prova per Aspose.Tasks?

 R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).

### D: Dove posso ottenere supporto se riscontro problemi durante l'utilizzo di Aspose.Tasks?

 R: Puoi ottenere assistenza dal forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
