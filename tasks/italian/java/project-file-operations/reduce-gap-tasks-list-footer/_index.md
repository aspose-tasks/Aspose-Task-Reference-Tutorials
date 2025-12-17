---
date: 2025-12-17
description: Scopri come esportare il progetto in PDF, ridurre lo spazio a piè di
  pagina e salvare il progetto come immagine usando Aspose.Tasks per Java. Ottimizza
  il layout di MS Project senza sforzo.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Esporta il progetto in PDF e riduci lo spazio tra l'elenco delle attività e
  il piè di pagina in Aspose.Tasks
url: /it/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esporta il progetto in PDF e riduci lo spazio tra l'elenco attività e il piè di pagina in Aspose.Tasks

## Introduzione  
In questo tutorial scoprirai **come esportare un progetto in PDF** riducendo al contempo lo spazio indesiderato tra l'elenco attività e il piè di pagina nei file Microsoft Project. Alla fine della guida sarai in grado di generare PDF puliti, immagini PNG e pagine HTML con un layout compatto usando Aspose.Tasks per Java. Segui il processo passo‑passo.

## Risposte rapide  
- **Cosa significa “esportare progetto in PDF”?** Converte un file MPP in un documento PDF preservando attività, linee temporali e formattazione.  
- **Perché ridurre lo spazio del piè di pagina?** Uno spazio più piccolo crea report più compatti e dall’aspetto professionale, soprattutto per documenti stampati o visualizzati sul web.  
- **Posso anche salvare il progetto come immagine?** Sì – Aspose.Tasks supporta PNG, JPEG e altri formati immagine.  
- **È necessaria una licenza speciale?** È disponibile una versione di prova gratuita; per l’uso in produzione è richiesta una licenza commerciale.  
- **Quale versione di Java è necessaria?** Java 8 o superiore funziona con la libreria corrente di Aspose.Tasks.

## Cos’è “esportare progetto in PDF”?  
Esportare un progetto in PDF trasforma la struttura interna MPP in un documento portatile che può essere aperto su qualsiasi dispositivo senza bisogno di Microsoft Project. È ideale per condividere report di stato, aggiornamenti per gli stakeholder o per archiviare piani di progetto.

## Perché ridurre lo spazio del piè di pagina?  
Lo spazio predefinito del piè di pagina può aggiungere spazi bianchi inutili, causando problemi di impaginazione e un aspetto sbilanciato. Ridurre questo spazio garantisce che il contenuto utilizzi la pagina in modo efficiente, rendendo il PDF o l’immagine finale più leggibile.

## Come ridurre lo spazio tra l'elenco attività e il piè di pagina?  
Aspose.Tasks fornisce l’opzione `setReduceFooterGap(true)` per le operazioni di salvataggio immagine, PDF e HTML. Abilitare questa opzione indica al motore di comprimere lo spazio tra l’ultima riga di attività e il piè di pagina.

## Salva il progetto come immagine con Aspose.Tasks  
Se ti serve uno snapshot visivo del tuo programma, puoi **salvare il progetto come immagine** (PNG) applicando le stesse impostazioni di riduzione dello spazio.

## Esportazione del progetto Java in PDF  
Le sezioni seguenti illustrano un flusso di lavoro completo per **esportare un progetto Java**, dal caricamento del file MPP al salvataggio in tre formati diversi.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK) – versione 8 o successiva.  
2. Libreria Aspose.Tasks per Java – scaricala da [here](https://releases.aspose.com/tasks/java/).  

## Importazione dei pacchetti
Prima di passare alla parte di codifica, importiamo i pacchetti necessari:
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

## Passo 1: Fornire il percorso alla directory dei dati
```java
String dataDir = "Your Data Directory";
```
Assicurati di sostituire `"Your Data Directory"` con il percorso della tua directory dati reale dove si trova il file Microsoft Project (`HomeMovePlan.mpp` in questo esempio).

## Passo 2: Leggere il file MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Questa riga di codice legge il file Microsoft Project denominato `HomeMovePlan.mpp`.

## Passo 3: Impostare ImageSaveOptions (Salva progetto come immagine)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Configura le opzioni di salvataggio immagine, impostando `ReduceFooterGap` su `true` per ridurre lo spazio tra l’elenco attività e il piè di pagina.

## Passo 4: Salva come immagine
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Salva il progetto come immagine con le opzioni configurate.

## Passo 5: Impostare PdfSaveOptions (Esporta progetto in PDF)
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

## Passo 7: Impostare HtmlSaveOptions
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

## Conclusione  
In conclusione, ridurre lo spazio tra l’elenco attività e il piè di pagina nei file Microsoft Project è un processo semplice con Aspose.Tasks per Java. Seguendo i passaggi descritti in questo tutorial, potrai **esportare il progetto in PDF**, salvarlo come immagine o generare HTML mantenendo un layout compatto e professionale.

## FAQ

### Q: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?

A: Aspose.Tasks supporta i formati Microsoft Project 2003‑2019, garantendo la compatibilità con varie versioni.

### Q: Posso personalizzare l’aspetto del piè di pagina nei miei documenti di progetto?

A: Sì, Aspose.Tasks offre ampie opzioni per personalizzare i piè di pagina, inclusa la riduzione degli spazi e la regolazione del posizionamento del contenuto.

### Q: Aspose.Tasks supporta il salvataggio dei progetti in formati diversi da PNG, PDF e HTML?

A: Sì, Aspose.Tasks supporta una vasta gamma di formati, tra cui XLSX, XML e MPP, tra gli altri.

### Q: È disponibile una versione di prova per Aspose.Tasks?

A: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks da [here](https://releases.aspose.com/).

### Q: Dove posso ottenere supporto se incontro problemi usando Aspose.Tasks?

A: Puoi ricevere assistenza dal forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Domande frequenti (Aggiuntive)

**Q: Come influisce la riduzione dello spazio del piè di pagina sulla paginazione?**  
A: Minimizza lo spazio vuoto nella parte inferiore di ogni pagina, consentendo di inserire più attività in una singola pagina e riducendo il numero totale di pagine.

**Q: Posso applicare la stessa impostazione di riduzione dello spazio a una sola pagina?**  
A: Sì, impostando `setRenderToSinglePage(true)` in `ImageSaveOptions` puoi controllare la paginazione mantenendo la riduzione dello spazio.

**Q: L’opzione `setReduceFooterGap` è disponibile per altri formati di output?**  
A: Attualmente è supportata per le esportazioni PNG, PDF e HTML. Per altri formati potrebbe essere necessario regolare manualmente il layout.

**Q: Cosa succede se il mio progetto contiene campi personalizzati—vengono preservati?**  
A: Tutti i campi personalizzati vengono mantenuti durante l’esportazione; le regolazioni di layout influenzano solo la spaziatura, non i dati.

**Q: La libreria gestisce progetti di grandi dimensioni in modo efficiente?**  
A: Aspose.Tasks trasmette i dati in streaming e può elaborare file MPP di grandi dimensioni; tuttavia, assicurati di disporre di memoria sufficiente quando esporti immagini ad alta risoluzione.

---

**Ultimo aggiornamento:** 2025-12-17  
**Testato con:** Aspose.Tasks 24.11 per Java  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}