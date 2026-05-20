---
date: 2026-05-20
description: Scopri come esportare il progetto in PDF, ridurre lo spazio del piè di
  pagina e salvare il progetto come immagine utilizzando Aspose.Tasks for Java. Ottimizza
  il layout di MS Project senza sforzo.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Esporta progetto in PDF e riduci lo spazio tra l'elenco delle attività
  e il piè di pagina in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Esporta progetto in PDF e riduci lo spazio tra l'elenco delle attività e il
  piè di pagina in Aspose.Tasks
url: /it/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esporta progetto in PDF e riduci lo spazio tra l'elenco delle attività e il piè di pagina in Aspose.Tasks

## Introduzione  
In questo tutorial scoprirai **come esportare un progetto in PDF** riducendo anche lo spazio indesiderato tra l'elenco delle attività e il piè di pagina nei file Microsoft Project. Alla fine della guida sarai in grado di generare PDF puliti, immagini PNG e pagine HTML con un layout compatto usando Aspose.Tasks per Java. Seguiamo il processo passo dopo passo, e vedrai perché è importante per la redazione di report professionali.

## Risposte rapide  
- **Cosa significa “export project to PDF”?** Converte un file MPP in un documento PDF preservando attività, linee temporali e formattazione.  
- **Perché ridurre lo spazio del piè di pagina?** Uno spazio più piccolo crea report più compatti e dall'aspetto più professionale, soprattutto per documenti stampati o visualizzati sul web.  
- **Posso anche salvare il progetto come immagine?** Sì – Aspose.Tasks supporta PNG, JPEG e altri formati immagine.  
- **È necessaria una licenza speciale?** È disponibile una versione di prova gratuita; è richiesta una licenza commerciale per l'uso in produzione.  
- **Quale versione di Java è necessaria?** Java 8 o superiore funziona con la libreria Aspose.Tasks attuale.  

## Cos'è “export project to PDF”?  
Esportare un progetto in PDF trasforma la struttura interna MPP in un documento portatile che può essere aperto su qualsiasi dispositivo senza necessità di Microsoft Project. È ideale per condividere report di stato, aggiornamenti per gli stakeholder o archiviare piani di progetto. Preserva il layout originale, i colori e la gerarchia delle attività, garantendo che il PDF abbia l'aspetto identico al file di origine.

## Perché ridurre lo spazio del piè di pagina?  
Il gap predefinito del piè di pagina può aggiungere spazio bianco inutile, causando problemi di impaginazione e un aspetto sbilanciato. Ridurre lo spazio assicura che il contenuto utilizzi la pagina in modo efficiente, rendendo il PDF o l'immagine finale più leggibili. Un layout più compatto riduce anche il numero totale di pagine, il che può abbassare i costi di stampa e migliorare la navigazione sullo schermo.

## Come ridurre lo spazio tra l'elenco delle attività e il piè di pagina?  
`setReduceFooterGap` è una proprietà Boolean che controlla lo spazio del piè di pagina durante l'esportazione.  
Aspose.Tasks fornisce un'opzione `setReduceFooterGap(true)` per le operazioni di salvataggio di immagine, PDF e HTML. Abilitare questo flag indica al motore di comprimere lo spazio tra l'ultima riga di attività e il piè di pagina della pagina. Quando impostato su true, il renderer taglia automaticamente il margine senza eliminare alcun dato delle attività, producendo un layout di pagina più pulito.

## Salva progetto come immagine con Aspose.Tasks  
`ImageSaveOptions` configura come un progetto viene renderizzato in un file immagine.  
La classe `ImageSaveOptions` consente di esportare un'istantanea del programma come PNG, JPEG o BMP. Quando abiliti anche `setReduceFooterGap(true)`, l'immagine generata rispecchia il layout compatto del PDF, fornendoti una visuale pulita per presentazioni o dashboard.

## Esportazione di progetto Java in PDF  
Le sezioni seguenti illustrano un flusso di lavoro completo per **l'esportazione di un progetto Java**, dal caricamento del file MPP al salvataggio in tre formati diversi.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK) – versione 8 o successiva.  
2. Aspose.Tasks for Java Library – download it from [here](https://releases.aspose.com/tasks/java/).  

## Importa pacchetti  
Before diving into the coding part, let's import the necessary packages:

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

## Passo 1: Fornisci il percorso alla tua directory dati  
```java
String dataDir = "Your Data Directory";
```  
Assicurati di sostituire `"Your Data Directory"` con il percorso della tua effettiva directory dati dove si trova il file Microsoft Project (`HomeMovePlan.mpp` in questo esempio).

## Passo 2: Leggi il file MPP  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Questa riga di codice legge il file Microsoft Project denominato `HomeMovePlan.mpp`.

## Passo 3: Imposta ImageSaveOptions (Salva progetto come immagine)  
`ImageSaveOptions` configura come un progetto viene renderizzato in un file immagine.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Configura le opzioni di salvataggio dell'immagine, impostando `ReduceFooterGap` su `true` per ridurre lo spazio tra l'elenco delle attività e il piè di pagina.

## Passo 4: Salva come immagine  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Salva il progetto come immagine con le opzioni configurate.

## Passo 5: Imposta PdfSaveOptions (Esporta progetto in PDF)  
`PdfSaveOptions` specifica le impostazioni per esportare un progetto in formato PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Definisci le opzioni di salvataggio PDF, assicurandoti di impostare `ReduceFooterGap` su `true`.

## Passo 6: Salva come PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Salva il progetto come PDF con le opzioni configurate.

## Passo 7: Imposta HtmlSaveOptions  
`HtmlSaveOptions` controlla la conversione di un progetto in HTML, includendo opzioni di stile e layout.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Specifica le opzioni di salvataggio HTML, impostando `ReduceFooterGap` su `true`.

## Passo 8: Salva come HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Salva il progetto come file HTML con le opzioni configurate.

## Casi d'uso comuni e consigli  
- **Report per stakeholder:** Esporta in PDF con spazio del piè di pagina ridotto per mantenere i report concisi e adatti alla stampa.  
- **Snapshot per dashboard:** Usa l'esportazione immagine quando ti serve una visuale rapida per Power BI o Confluence.  
- **Pubblicazione web:** L'esportazione HTML mantiene l'interattività e può essere incorporata direttamente nei portali intranet.  
- **Consiglio professionale:** Per progetti molto grandi, aumenta la `Resolution` in `ImageSaveOptions` a 300 dpi per mantenere la nitidezza beneficiando comunque dello spazio ridotto.

## Domande frequenti (Aggiuntive)

**Q: Come influisce la riduzione dello spazio del piè di pagina sulla paginazione?**  
A: Riduce lo spazio bianco nella parte inferiore di ogni pagina, consentendo a più attività di stare su una singola pagina e diminuendo il numero totale di pagine.

**Q: Posso applicare la stessa impostazione di riduzione dello spazio solo a una singola pagina?**  
A: Sì, impostando `setRenderToSinglePage(true)` in `ImageSaveOptions` è possibile controllare la paginazione mantenendo la riduzione dello spazio.

**Q: L'opzione `setReduceFooterGap` è disponibile per altri formati di output?**  
A: Attualmente è supportata per esportazioni PNG, PDF e HTML. Per altri formati potrebbe essere necessario regolare manualmente il layout.

**Q: Cosa succede se il mio progetto contiene campi personalizzati—vengono preservati?**  
A: Tutti i campi personalizzati vengono mantenuti durante l'esportazione; le modifiche al layout influenzano solo lo spazio, non i dati.

**Q: La libreria gestisce progetti di grandi dimensioni in modo efficiente?**  
A: Aspose.Tasks trasmette i dati in streaming e può elaborare file MPP di centinaia di pagine senza caricare l'intero file in memoria; tuttavia, è necessario allocare sufficiente spazio heap quando si esportano immagini ad alta risoluzione.

---

**Last Updated:** 2026-05-20  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose

## Tutorial correlati

- [Salva progetto come immagine – formato 24bppRgb con Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Salva progetto come modello, CSV e testo con Aspose.Tasks per Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Come creare file MPP – Crea e salva progetto vuoto in formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}