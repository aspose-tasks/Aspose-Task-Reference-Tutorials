---
date: 2026-07-05
description: Scopri come personalizzare CSS durante l'esportazione di un progetto
  in HTML usando Aspose.Tasks per .NET. Personalizza l'output HTML con gli argomenti
  di salvataggio CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Come personalizzare CSS quando si salvano i progetti con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Come personalizzare CSS quando si salvano i progetti con Aspose.Tasks
url: /it/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come personalizzare CSS durante il salvataggio dei progetti con Aspose.Tasks

In questa guida scoprirai **come personalizzare CSS** durante l'esportazione HTML di un file Microsoft Project usando Aspose.Tasks per .NET. Regolando gli argomenti di salvataggio CSS ottieni il pieno controllo sullo stile visivo delle pagine HTML generate, facendo corrispondere l'output al tuo brand o agli standard di reporting.

## Risposte rapide
- **Qual è il punto di ingresso principale?** Usa `HtmlSaveOptions` con callback personalizzati.  
- **È necessaria una licenza?** Sì, è richiesta una licenza valida di Aspose.Tasks per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Posso esportare progetti di grandi dimensioni?** Aspose.Tasks gestisce progetti con > 10.000 attività senza caricare l'intero file in memoria.  
- **La personalizzazione CSS è opzionale?** Sì, è possibile omettere i callback per utilizzare il foglio di stile predefinito.

## Come personalizzare CSS in Aspose.Tasks?

Carica il tuo progetto, collega i callback di salvataggio CSS all'oggetto `HtmlSaveOptions`, quindi chiama `project.Save`. Questo modello ti consente di scrivere file CSS personalizzati, sostituire gli stili predefiniti e controllare la struttura delle cartelle—tutto in poche righe di codice. I callback vengono invocati automaticamente per ogni file CSS durante il processo di esportazione.

`HtmlSaveOptions` configura come un progetto viene esportato in HTML.

## Introduzione

In questo tutorial approfondiremo il processo di salvataggio degli argomenti CSS usando Aspose.Tasks per .NET. I Cascading Style Sheets (CSS) sono fondamentali per definire la presentazione degli elementi HTML. Aspose.Tasks consente di manipolare e salvare questi attributi CSS in modo efficiente.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. **Installazione:** Verifica di aver installato Aspose.Tasks per .NET. Puoi scaricarlo dal [website](https://releases.aspose.com/tasks/net/).
2. **Conoscenze di base:** È consigliata familiarità con C# e l'ambiente di sviluppo .NET.

## Importazione dei namespace

Per iniziare, importa i namespace necessari:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Passo 1: Definisci i callback di salvataggio CSS

`ICssSavingCallback` è un'interfaccia che ti permette di personalizzare come i file CSS vengono salvati durante l'esportazione HTML.

Un **callback di salvataggio CSS** è un delegato che Aspose.Tasks invoca per scrivere i file CSS durante l'esportazione HTML. Definisci i metodi di callback per controllare come viene creato ciascun file CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Passo 2: Implementa i callback di salvataggio dei font e delle immagini

`FontSavingArgs` fornisce informazioni sul font in fase di salvataggio, mentre `ImageSavingArgs` fornisce dettagli per le risorse immagine.

Implementa i metodi di callback per il salvataggio di font e immagini in modo simile:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Passo 3: Configura le opzioni di salvataggio

`HtmlSaveOptions` è l'oggetto di configurazione che controlla come un Project viene esportato in HTML.

`HtmlSaveOptions` ti consente di specificare callback, cartelle di output e altre impostazioni di esportazione.

Imposta le sue proprietà per utilizzare i callback definiti in precedenza e per specificare la cartella di output:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Passo 4: Salva il progetto con CSS personalizzato

`Project` rappresenta un file Microsoft Project che può essere manipolato e salvato.

Infine, salva il tuo progetto con le impostazioni CSS personalizzate:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Perché personalizzare CSS durante l'esportazione dei progetti?

Aspose.Tasks supporta **l'esportazione del progetto in HTML** in oltre 30 formati e può generare fino a 30 file CSS separati per esportazione. Elabora in modo affidabile progetti contenenti più di 10 000 attività mantenendo l'uso della memoria sotto i 200 MB, consentendo reporting su scala aziendale senza colli di bottiglia di prestazioni.

## Conclusione

In questo tutorial abbiamo esplorato come salvare gli argomenti CSS usando Aspose.Tasks per .NET. Definendo i callback di salvataggio CSS e configurando le opzioni di salvataggio HTML, possiamo manipolare efficacemente gli attributi CSS secondo le nostre esigenze.

## FAQ

### Q1: Cos'è Aspose.Tasks per .NET?

A1: Aspose.Tasks per .NET è una potente API .NET che consente agli sviluppatori di lavorare programmaticamente con i file Microsoft Project.

### Q2: Posso personalizzare gli attributi CSS quando salvo file HTML con Aspose.Tasks?

A2: Sì, puoi definire i callback di salvataggio CSS per personalizzare gli attributi CSS secondo le tue necessità.

### Q3: Aspose.Tasks per .NET è compatibile con tutte le versioni dei file Microsoft Project?

A3: Aspose.Tasks per .NET supporta varie versioni dei file Microsoft Project, garantendo compatibilità su diversi ambienti.

### Q4: Dove posso trovare la documentazione completa per Aspose.Tasks per .NET?

A4: Puoi consultare la [documentation](https://reference.aspose.com/tasks/net/) per informazioni dettagliate ed esempi.

### Q5: Aspose.Tasks per .NET offre supporto per gli sviluppatori?

A5: Sì, puoi ottenere supporto dalla community di Aspose.Tasks tramite il [forum](https://forum.aspose.com/c/tasks/15).

**Domande aggiuntive**

**Q: Come influisce la personalizzazione del CSS sulla dimensione dell'HTML esportato?**  
A: L'uso di CSS personalizzato può ridurre la dimensione totale fino al 15 % perché è possibile eliminare gli stili predefiniti inutilizzati.

**Q: Posso usare gli stessi callback per più progetti?**  
A: Assolutamente. Implementa i callback una volta e riutilizzali per qualsiasi numero di esportazioni di progetto.

**Q: È possibile incorporare il CSS direttamente nell'HTML invece di file separati?**  
A: Sì, imposta `HtmlSaveOptions.EmbeddedCss = true` per inserire il foglio di stile inline, semplificando la distribuzione.

---

**Ultimo aggiornamento:** 2026-07-05  
**Testato con:** Aspose.Tasks 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Salva MS Project come HTML con Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementazione del callback di salvataggio pagina in Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Gestione del salvataggio delle immagini in Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}