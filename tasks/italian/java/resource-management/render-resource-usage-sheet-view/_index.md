---
date: 2026-06-15
description: Scopri come convertire mpp in PDF e visualizzare le viste Resource Usage
  e Sheet utilizzando Aspose.Tasks per Java. Segui la nostra guida passo‑passo per
  impostare timescale e generare report PDF dettagliati senza sforzo.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Converti MPP in PDF e visualizza la vista Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Converti MPP in PDF e visualizza la vista Resource Usage – Aspose.Tasks
url: /it/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti MPP in PDF e visualizza la vista Utilizzo risorse – Aspose.Tasks

## Risposte rapide
- **Cosa fa Aspose.Tasks?** Legge, modifica e converte i file Microsoft Project (MPP) senza necessità di installare MS Project.  
- **Posso convertire MPP in PDF con una sola riga di codice?** Sì – carica il Project, imposta SaveOptions e chiama `save`.  
- **Quali scale temporali sono supportate?** Giorni, Terzi di mese e Mesi.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale per le distribuzioni non‑di prova.  
- **La libreria è compatibile con Java 8+?** Assolutamente – supporta Java 8 e versioni successive.

## Che cos'è la conversione da MPP a PDF?
*Convert mpp to pdf* indica il processo di prendere un file Microsoft Project (.mpp) e generare una versione Portable Document Format (PDF) che riproduce fedelmente tabelle, pianificazioni, diagrammi e assegnazioni delle risorse del progetto. Il PDF risultante può essere facilmente condiviso, stampato e archiviato senza richiedere Microsoft Project installato sulla macchina del destinatario.

## Perché convertire Project in PDF con Aspose.Tasks?
Aspose.Tasks supporta **50+ formati di input e output** e può renderizzare progetti di centinaia di pagine senza caricare l'intero file in memoria, riducendo l'uso di RAM fino al 70 %. L'output PDF conserva tabelle, diagrammi e assegnazioni delle risorse, rendendolo ideale per la distribuzione a stakeholder e l'archiviazione.

## Prerequisiti
1. **Java Development Kit (JDK)** – Java 8 o versioni successive installate sulla tua macchina.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dalla [download page](https://releases.aspose.com/tasks/java/).  

## Come convertire mpp in pdf usando Aspose.Tasks per Java?
Carica il file MPP di origine, configura la scala temporale desiderata, imposta il formato di presentazione su **ResourceUsage** e salva il risultato come PDF. Questo flusso end‑to‑end richiede solo poche chiamate API e viene eseguito in meno di un secondo per progetti di dimensioni tipiche.

### Passo 1: Leggi il progetto sorgente
Il classe `Project` rappresenta un file Microsoft Project caricato in memoria, fornendo accesso ai suoi dati e alla sua struttura.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Passo 2: Definisci SaveOptions con le impostazioni TimeScale richieste
`SaveOptions` configura come il progetto viene salvato, consentendo di specificare impostazioni specifiche del formato come la scala temporale.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Passo 3: Imposta il formato di presentazione su ResourceUsage
`PresentationFormat` determina quale vista del Project (ad es., ResourceUsage) viene renderizzata nel documento di output.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Passo 4: Salva il progetto come PDF
`project.save` scrive il progetto su file usando le `SaveOptions` fornite, producendo il PDF finale.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Passo 5: Renderizza le viste per altre impostazioni TimeScale
Ripeti i passaggi precedenti, modificando il valore `TimeScale` per renderizzare viste con scale temporali aggiuntive.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Passo 6: Opzionale – Converti più progetti in batch
Se devi **convertire project to pdf** per molti file, inserisci la logica sopra in un ciclo che itera su una directory di file *.mpp*. Questo approccio **salva ms project pdf** in blocco con minime modifiche al codice.  
Il codice seguente mostra un esempio completo di conversione di un file MPP in PDF con le impostazioni desiderate.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Problemi comuni e soluzioni
- **Font mancanti nel PDF** – Assicurati che i font richiesti siano installati sul server o incorporali tramite `PdfSaveOptions`.  
- **File di progetto di grandi dimensioni causano OutOfMemoryError** – Usa `LoadOptions.setLoadAllResources(false)` per caricare le risorse su richiesta.  
- **Rendering della scala temporale errato** – Verifica che `options.setTimeScale(TimeScale.Days)` (o altro enum) corrisponda alla granularità desiderata.

## Domande frequenti

**D: Aspose.Tasks può renderizzare altre viste oltre a Utilizzo risorse e Foglio?**  
R: Sì, supporta anche Gantt Chart, Task Usage, Calendar e molte altre viste.

**D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?**  
R: Assolutamente – gestisce formati MPP, MPT e XML da Project 2000 fino a Project 2021.

**D: Posso personalizzare l'aspetto delle viste renderizzate?**  
R: Sì, è possibile modificare colori, font e layout delle colonne tramite `PdfSaveOptions` e `PresentationOptions`.

**D: Aspose.Tasks richiede l'installazione di Microsoft Project?**  
R: No, è una libreria autonoma e funziona in qualsiasi ambiente compatibile con Java.

**D: Dove posso ottenere supporto tecnico?**  
R: Il supporto è disponibile tramite il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Ultimo aggiornamento:** 2026-06-15  
**Testato con:** Aspose.Tasks 24.12 per Java  
**Autore:** Aspose

## Tutorial correlati

- [Render Resource Usage and Sheet View in Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [How to Export PDF in Aspose.Tasks – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [How to Create MPP Files with Aspose.Tasks for Java](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}