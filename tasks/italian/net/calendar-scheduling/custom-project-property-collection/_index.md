---
date: 2026-10-15
description: Scopri come aggiungere una proprietà personalizzata e gestire le proprietà
  personalizzate del progetto in Aspose.Tasks per .NET, migliorando il controllo dei
  metadati del tuo progetto.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Gestione della collezione di proprietà personalizzate del progetto in Aspose.Tasks
og_description: Aggiungi una proprietà personalizzata ai tuoi file di progetto con
  Aspose.Tasks per .NET. Questa guida ti mostra come gestire le proprietà personalizzate,
  leggerle e aggiungere valori boolean o string in modo efficiente.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Aggiungi una proprietà personalizzata usando l'API .NET di Aspose.Tasks
  per i progetti
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Come aggiungere una proprietà personalizzata in Aspose.Tasks per .NET
url: /it/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere una proprietà personalizzata in Aspose.Tasks per .NET

## Introduzione

Il supporto per le proprietà personalizzate ti consente di memorizzare metadati specifici del progetto che i campi incorporati non coprono. In questo tutorial imparerai come **aggiungere una proprietà personalizzata**, leggerla e gestire l'intera collezione di proprietà personalizzate utilizzando Aspose.Tasks per .NET. Alla fine sarai in grado di personalizzare i file di progetto con valori Boolean, DateTime, Double e String che si adattano alle regole della tua azienda.

## Risposte rapide
- **Posso aggiungere una proprietà personalizzata Boolean?** Sì – usa `CustomPropertyType.Boolean`.
- **Quanti tipi di proprietà personalizzate sono supportati?** Quattro: Boolean, DateTime, Double, String.
- **La collezione di proprietà personalizzate è di sola lettura?** Può essere di sola lettura se il progetto è caricato da una fonte di sola lettura.
- **È necessaria una licenza per utilizzare questa funzionalità?** Una licenza temporanea è sufficiente per la valutazione; è richiesta una licenza completa per la produzione.
- **Quali versioni di .NET sono compatibili?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è una proprietà personalizzata?

Una proprietà personalizzata è un campo di metadati definito dall'utente che si associa a un oggetto Project. Consente di memorizzare informazioni aggiuntive come “Livello di rischio”, “ID cliente” o qualsiasi flag Boolean non coperto dai campi standard di MS‑Project.

## Perché aggiungere una proprietà personalizzata in Aspose.Tasks?

Aspose.Tasks supporta **oltre 50 formati di input e output** e può gestire progetti con **fino a 10.000 attività** senza caricare l'intero file in memoria. L'aggiunta di proprietà personalizzate consente di incorporare dati critici per il business direttamente nel file di progetto, eliminando la necessità di database esterni e garantendo che i dati viaggino con il progetto.

## Prerequisiti

- Visual Studio (qualsiasi edizione recente) installato sulla tua postazione di lavoro.  
- Aspose.Tasks per .NET – scaricalo dal [download link](https://releases.aspose.com/tasks/net/).  
- Familiarità di base con la sintassi C# e la struttura dei progetti .NET.

## Importare i namespace

I seguenti namespace ti danno accesso al modello di progetto core e alle API delle proprietà personalizzate.

```csharp
using Aspose.Tasks;
using System;


```

## Come aggiungere una proprietà personalizzata in Aspose.Tasks?

Per aggiungere una proprietà personalizzata, prima carica il progetto, quindi crea un oggetto `CustomProperty`, imposta il suo nome, tipo e valore, e infine aggiungilo alla collezione `CustomProperties` del progetto. Questa operazione incorpora i metadati direttamente nel file di progetto, e le modifiche vengono salvate quando chiami `project.Save(...)`.  

`CustomProperty` rappresenta un singolo campo definito dall'utente associato a un progetto.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Passo 1: inizializzare il progetto

`Project` è la classe primaria che rappresenta un file di progetto in Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Passo 2: verificare la disponibilità della collezione di proprietà personalizzate

`CustomProperties` è la collezione che contiene tutti gli oggetti di proprietà personalizzate per un progetto.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Passo 3: aggiungere proprietà personalizzate

Il metodo `Add` inserisce una nuova proprietà personalizzata nella collezione del progetto.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Passo 4: accedere alle proprietà personalizzate

La collezione `CustomProperties` implementa IEnumerable, consentendo l'iterazione su ogni `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Passo 5: recuperare il valore di una proprietà personalizzata

Il metodo `Get` restituisce il valore di una proprietà personalizzata in base al suo nome.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Passo 6: iterare sui nomi delle proprietà personalizzate

La proprietà `Names` fornisce un elenco di tutti i nomi delle proprietà personalizzate nella collezione.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Passo 7: rimuovere o cancellare le proprietà personalizzate

Il metodo `Remove` elimina una proprietà specifica, mentre `Clear` svuota l'intera collezione.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Problemi comuni e risoluzione

- **Collezione di sola lettura** – Se `project.CustomProperties.IsReadOnly` restituisce `true`, assicurati che il file sorgente non sia aperto con accesso in lettura esclusivo o copialo in una posizione scrivibile prima di modificare.  
- **Mancata corrispondenza del tipo** – Assegnare un valore che non corrisponde al `CustomPropertyType` dichiarato genera un `ArgumentException`. Imposta sempre il `Value` dopo aver definito il `Type` corretto.  
- **Salvataggio delle modifiche** – Dopo aver aggiunto o rimosso proprietà, chiama `project.Save("output.mpp")` per persistere le modifiche; altrimenti le modifiche rimangono solo in memoria.

## Domande frequenti

**Q: Posso aggiungere proprietà personalizzate di qualsiasi tipo di dato al mio progetto usando Aspose.Tasks per .NET?**  
A: Sì, puoi aggiungere proprietà personalizzate che supportano i tipi Boolean, DateTime, Double e String.

**Q: È possibile iterare sui nomi delle proprietà personalizzate in Aspose.Tasks per .NET?**  
A: Assolutamente, puoi iterare sui nomi delle proprietà personalizzate usando la proprietà `Names`.

**Q: Come posso rimuovere una specifica proprietà personalizzata dal mio progetto?**  
A: Puoi rimuovere una proprietà personalizzata per nome usando il metodo `Remove`.

**Q: Aspose.Tasks per .NET fornisce supporto per licenze temporanee?**  
A: Sì, puoi ottenere una licenza temporanea dal sito Aspose per scopi di valutazione.

**Q: Dove posso trovare supporto o ulteriore assistenza riguardo Aspose.Tasks per .NET?**  
A: Puoi visitare il forum Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) per qualsiasi domanda o assistenza.

---

**Ultimo aggiornamento:** 2026-10-15  
**Testato con:** Aspose.Tasks 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come leggere le proprietà di progetto incorporate usando Aspose.Tasks per .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Gestire la collezione di attributi di MS Project in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Tipi di campo personalizzato di Aspose.Tasks – Calendario e Pianificazione](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}