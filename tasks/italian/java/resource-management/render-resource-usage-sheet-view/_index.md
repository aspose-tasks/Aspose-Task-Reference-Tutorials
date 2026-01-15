---
date: 2026-01-15
description: Scopri come salvare il progetto come PDF e rendere le visualizzazioni
  Utilizzo risorse e Foglio di MS Project usando Aspose.Tasks per Java. Segui la nostra
  guida passo‑passo per esportare il progetto in PDF senza sforzo.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salva progetto come PDF – Genera l'utilizzo delle risorse e la vista foglio
  in Aspose.Tasks
url: /it/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva il progetto come PDF – Renderizza le visualizzazioni Resource Usage e Sheet in Aspose.Tasks

## Introduzione
In questo tutorial scoprirai come **salvare il progetto come PDF** rendendo le visualizzazioni Resource Usage e Sheet di un file Microsoft Project. Che tu debba generare un report stampabile per gli stakeholder o convertire file MPP in un formato universalmente visualizzabile, Aspose.Tasks per Java rende il processo semplice—non è necessaria l'installazione di Microsoft Project.

## Risposte rapide
- **Cosa fa “save project as pdf”?** Converte un file Project (MPP) in un documento PDF preservando la visualizzazione selezionata.  
- **Quale visualizzazione può essere esportata?** Resource Usage, Sheet, Gantt, Task Usage e altre.  
- **Posso cambiare la scala temporale nel PDF?** Sì—le opzioni includono Days, ThirdsOfMonths e Months.  
- **È necessario avere Microsoft Project installato?** No, Aspose.Tasks funziona in modo indipendente.  
- **È necessaria una licenza per la produzione?** Sì, è necessaria una licenza commerciale per l'uso non‑trial.

## Cos'è “save project as PDF”?
Salvare un progetto come PDF crea una rappresentazione statica ad alta risoluzione di una visualizzazione Project scelta. È ideale per condividerla con i clienti, archiviare o stampare senza esporre il file di progetto sottostante.

## Perché usare Aspose.Tasks per esportare il progetto in PDF?
- **Nessuna dipendenza esterna** – funziona su qualsiasi piattaforma che supporta Java.  
- **Controllo dettagliato** – puoi selezionare la visualizzazione, la scala temporale e il layout.  
- **Alta fedeltà** – il PDF rispecchia l'aspetto della visualizzazione originale di Project.  
- **Pronto per l'automazione** – integralo in pipeline CI, servizi di reporting o convertitori batch.

## Prerequisiti
Prima di immergerci, assicurati di avere:

1. **Java Development Kit (JDK)** – si consiglia l'ultima versione.  
2. **Aspose.Tasks for Java** – scarica dalla [pagina di download](https://releases.aspose.com/tasks/java/).  

## Importa i pacchetti
Per prima cosa, importa le classi necessarie nel tuo progetto Java:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Guida passo‑passo

### Passo 1: Leggi il progetto sorgente
Carica il file MPP che desideri convertire.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Passo 2: Definisci SaveOptions con la scala temporale richiesta (Esporta il progetto in PDF)
Configura le opzioni di esportazione PDF e imposta la scala temporale desiderata.  
*Qui utilizziamo **Days** come esempio.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Passo 3: Imposta il formato di presentazione su ResourceUsage
Scegli la visualizzazione che desideri renderizzare. In questo caso, la visualizzazione **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Passo 4: Salva il progetto (Converti MPP in PDF)
Esegui la conversione e genera il file PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Passo 5: Renderizza le visualizzazioni per altre impostazioni di scala temporale (Cambia scala temporale PDF)
Ripeti i passaggi precedenti per produrre PDF con diverse scale temporali come **ThirdsOfMonths** e **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Problemi comuni e soluzioni
- **Errori file non trovato** – Verifica che `dataDir` punti alla cartella corretta e che il nome del file MPP corrisponda esattamente.  
- **Output PDF vuoto** – Assicurati che `PresentationFormat` corrisponda a una visualizzazione che contiene dati (ad es., ResourceUsage).  
- **Scala temporale errata** – Controlla che `options.setTimescale()` sia chiamato prima di ogni `project.save()`.

## Domande frequenti

### Aspose.Tasks può renderizzare altre visualizzazioni oltre a Resource Usage e Sheet?
Aspose.Tasks supporta il rendering di varie visualizzazioni come Gantt Chart, Task Usage e visualizzazioni Calendar, tra le altre.

### Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
Sì, Aspose.Tasks supporta un'ampia gamma di formati di file Microsoft Project, inclusi MPP, MPT e formati XML.

### Posso personalizzare l'aspetto delle visualizzazioni renderizzate usando Aspose.Tasks?
Assolutamente! Aspose.Tasks offre numerose opzioni per personalizzare l'aspetto e il layout delle visualizzazioni renderizzate in base alle tue esigenze specifiche.

### Aspose.Tasks richiede l'installazione di Microsoft Project sul sistema?
No, Aspose.Tasks è una libreria autonoma e non richiede l'installazione di Microsoft Project per funzionare.

### È disponibile supporto tecnico per gli utenti di Aspose.Tasks?
Sì, gli utenti di Aspose.Tasks possono usufruire del supporto tecnico tramite il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---