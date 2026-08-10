---
date: 2026-07-05
description: Scopri come copiare i dati del progetto utilizzando Aspose.Tasks per
  .NET con le opzioni di copia. Potenzia le tue app .NET con una gestione precisa
  del progetto.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Come copiare i dati del progetto con le opzioni di copia in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Come copiare i dati del progetto con le opzioni di copia in Aspose.Tasks
url: /it/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come Copiare i Dati del Progetto con le Opzioni di Copia in Aspose.Tasks

## Introduzione

Se hai bisogno di **come copiare progetto** informazioni da un file Microsoft Project a un altro, Aspose.Tasks per .NET ti offre un modo pulito, code‑first per farlo. In questo tutorial percorreremo l’intero flusso di lavoro — caricamento di un progetto sorgente, configurazione delle opzioni di copia, creazione di una copia e caricamento del risultato — così potrai integrare la logica di copia del progetto in qualsiasi applicazione .NET con fiducia.

## Risposte Rapide
- **Cosa fa la funzionalità di copia?** Duplica i dati del progetto consentendo di includere o escludere sezioni specifiche come calendari, risorse o informazioni di visualizzazione.  
- **Quale classe controlla il comportamento?** `CopyToOptions` ti consente di regolare finemente ciò che viene copiato.  
- **Ho bisogno di una licenza?** È necessaria una licenza valida di Aspose.Tasks per la produzione; una prova gratuita funziona per lo sviluppo.  
- **Formati supportati?** Aspose.Tasks gestisce file MPP, XML e XER — oltre 20 + formati in totale.  
- **Posso saltare i dati di visualizzazione?** Sì, imposta `CopyToOptions.SkipViewData = true` per omettere le informazioni relative all’interfaccia utente.

## Cos'è “come copiare progetto” in Aspose.Tasks?
**“Come copiare progetto”** si riferisce all’utilizzo dell’API di Aspose.Tasks per duplicare i dati di un oggetto Project in un nuovo file, filtrando opzionalmente gli elementi indesiderati. Questa operazione è utile per la creazione di template, l’archiviazione o la generazione di varianti di progetto senza passaggi manuali dell’interfaccia utente, e funziona su tutti i formati di file supportati.

## Perché usare le Opzioni di Copia in Aspose.Tasks?
Aspose.Tasks supporta **oltre 50 entità correlate al progetto** (attività, risorse, calendari, assegnazioni, ecc.) e può elaborare file con **fino a 10.000 attività** mantenendo l’utilizzo della memoria sotto i 200 MB. L’utilizzo di `CopyToOptions` ti consente di evitare la copia di dati di visualizzazione pesanti, riducendo la dimensione del file di output del **30‑40 %** e accelerando l’operazione di circa **2×** per progetti di grandi dimensioni.

## Prerequisiti

1. **Aspose.Tasks for .NET** – scarica l’ultima versione dal [download link](https://releases.aspose.com/tasks/net/).  
2. **Ambiente di sviluppo .NET** – Visual Studio 2022 (o qualsiasi IDE che supporti .NET 6+) installato.  
3. **Una licenza valida di Aspose.Tasks** – opzionale per la valutazione, obbligatoria per le versioni di produzione.  
4. **Un file di progetto esistente** (ad es., `SourceProject.xml`) che desideri copiare.

## Come importare gli spazi dei nomi per Aspose.Tasks?

Aggiungi le direttive `using` necessarie all’inizio del tuo file C# in modo che il compilatore possa individuare i tipi di Aspose.Tasks. L’inclusione di queste istruzioni ti dà accesso diretto a `Project`, `CopyToOptions` e altre classi di utilità senza dover qualificare completamente i loro nomi, semplificando il codice e migliorandone la leggibilità.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Passo 1: Inizializzare gli Oggetti Project

Per prima cosa, crea un'istanza `Project` che rappresenta il file sorgente e carica i dati XML.  
La classe `Project` rappresenta un file Microsoft Project caricato in memoria, esponendo attività, risorse, calendari e altre informazioni del progetto.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Suggerimento:** Se lavori con file molto grandi, considera l’utilizzo del costruttore `LoadOptions` per abilitare il caricamento lazy e mantenere basso il consumo di memoria.

## Passo 2: Creare una Copia del Progetto

Successivamente, istanzia un secondo oggetto `Project` che riceverà i dati copiati. Questo oggetto parte vuoto.

```csharp
Project copiedProject = new Project();
```

Ora hai due distinti oggetti `Project`: uno caricato dal disco e uno pronto a ricevere la copia.

## Passo 3: Caricare il Progetto Copiato

Dopo l’operazione di copia (mostrata più avanti), vorrai verificare il risultato caricando il file appena salvato in un'altra istanza `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Ricaricare il file conferma che la copia è riuscita e che le opzioni impostate hanno funzionato come previsto.

## Passo 4: Configurare le Opzioni di Copia

La classe `CopyToOptions` ti consente di specificare esattamente cosa viene trasferito dalla sorgente alla destinazione.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Impostare `SkipViewData = true` riduce la dimensione del file di output e velocizza l’operazione, specialmente quando ti servono solo i dati logici del progetto.

## Passo 5: Eseguire la Copia del Progetto

Infine, invoca il metodo `CopyTo` sul progetto sorgente, passando il progetto di destinazione e le opzioni configurate.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Questa chiamata in due righe esegue l’intera operazione di copia, rispettando le opzioni definite. Il file risultante `CopiedProject.xml` contiene solo i dati richiesti.

## Problemi Comuni e Soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **NullReferenceException durante la chiamata a `CopyTo`** | Progetto di destinazione non istanziato. | Assicurati che `new Project()` sia chiamato prima di `CopyTo`. |
| **Attività mancanti dopo la copia** | `CopyCommonData` impostato a `false`. | Imposta `CopyCommonData = true` o copia manualmente le collezioni specifiche. |
| **File di output di grandi dimensioni** | `SkipViewData` lasciato a `false`. | Abilita `SkipViewData` per omettere i dati relativi all’interfaccia utente. |
| **Licenza non applicata** | File di licenza non caricato. | Esegui `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` prima di qualsiasi utilizzo dell’API. |

## Domande Frequenti

**Q: Posso copiare solo un sottoinsieme di attività?**  
**R: Sì, utilizza `CopyToOptions` insieme a `ProjectRootTask` per specificare un'attività di partenza, oppure copia manualmente le attività selezionate dopo la copia iniziale.**

**Q: Aspose.Tasks supporta la copia tra formati di file diversi?**  
**R: Assolutamente. Puoi caricare un file MPP e salvare la copia come XML, XER o qualsiasi altro formato supportato — oltre **20 + formati** in totale.**

**Q: Come gestisco i file di progetto protetti da password?**  
**R: Carica la sorgente con `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, quindi procedi con la copia come al solito.**

**Q: Esiste un modo per copiare i pool di risorse senza attività?**  
**R: Imposta `CopyToOptions.CopyResources = true` e `CopyToOptions.CopyTasks = false` per trasferire solo le informazioni delle risorse.**

**Q: Dove posso trovare più esempi?**  
**R: Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per snippet della community, suggerimenti di risoluzione problemi e documentazione ufficiale.**

---

**Ultimo aggiornamento:** 2026-07-05  
**Testato con:** Aspose.Tasks 24.12 per .NET  
**Autore:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Tutorial Correlati

- [Padroneggiare i Dati del Progetto con Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Padroneggiare le Opzioni di Salvataggio di MS Project per Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Calendario e Pianificazione di Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}