---
date: 2026-07-19
description: Scopri come aggiungere tipi di campo personalizzati in Aspose.Tasks per
  .NET con codice passo-passo, prerequisiti e FAQ.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Tipi di campo personalizzati in Aspose.Tasks
og_description: Scopri come aggiungere tipi di campo personalizzati in Aspose.Tasks
  per .NET. Segui questa guida passo-passo per creare, definire e utilizzare gli attributi
  estesi in modo efficiente.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Come aggiungere tipi di campo personalizzati in Aspose.Tasks per .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Come aggiungere tipi di campo personalizzati in Aspose.Tasks per .NET
url: /it/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere tipi di campo personalizzati in Aspose.Tasks

## Introduzione

In questo tutorial scoprirai **come aggiungere un campo personalizzato** a un file Microsoft Project utilizzando Aspose.Tasks per .NET. I campi personalizzati ti consentono di memorizzare informazioni aggiuntive—come punteggi di rischio, codici dipartimento o note personalizzate—direttamente su attività, risorse o sul progetto stesso. Ti guideremo attraverso l'intero processo, dalla configurazione dell'ambiente alla definizione, aggiunta e verifica di un campo di testo personalizzato.

## Risposte rapide
- **Che cos'è un campo personalizzato?** Una colonna definita dall'utente che può contenere testo, numeri, date o flag su attività/risorse.  
- **Quale classe definisce un campo personalizzato?** `ExtendedAttributeDefinition`.  
- **Posso aggiungere un campo personalizzato a un progetto esistente?** Sì—carica il progetto, crea la definizione, quindi aggiungila alla collezione.  
- **È necessaria una licenza per Aspose.Tasks?** È necessaria una licenza per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è “come aggiungere campo personalizzato” in Aspose.Tasks?
**Come aggiungere un campo personalizzato** si riferisce al processo di creazione di un `ExtendedAttributeDefinition` e al suo collegamento alla collezione `ExtendedAttributes` di un progetto. Questo consente di memorizzare metadati aggiuntivi che non fanno parte dello schema standard di Project. Può essere utilizzato per attività, risorse o per il progetto stesso, permettendo di catturare informazioni come livelli di rischio, codici dipartimento o note personalizzate non disponibili nei campi predefiniti.

## Perché utilizzare i campi personalizzati nella gestione dei progetti?
Aspose.Tasks supporta **oltre 50 tipi di attributi estesi integrati** e ti consente di definire **un numero illimitato di campi personalizzati** senza influire significativamente sulla dimensione del file. Utilizzando i campi personalizzati puoi:  
Questi campi appaiono come colonne aggiuntive in Microsoft Project e possono essere referenziati in formule, report e filtri. Sono memorizzati all'interno del file di progetto e viaggiano con esso, garantendo che gli strumenti a valle mantengano i dati personalizzati.

## Prerequisites

### 1. Visual Studio installato
Assicurati che Visual Studio (2019 o successivo) sia installato sulla tua macchina. Puoi scaricarlo dal sito web di Microsoft.

### 2. Aspose.Tasks for .NET
Aggiungi il pacchetto NuGet Aspose.Tasks al tuo progetto. Scarica l'ultima versione da [qui](https://releases.aspose.com/tasks/net/).

### 3. Conoscenze di base di C#
Dovresti sentirti a tuo agio con la sintassi di C#, le classi e la struttura dei progetti .NET.

## Importare gli spazi dei nomi

Il `Project`, `ExtendedAttributeDefinition` e gli enum correlati si trovano nello spazio dei nomi `Aspose.Tasks`. Importalo all'inizio del tuo file:

Lo spazio dei nomi `Aspose.Tasks` fornisce tutti i tipi principali per gestire i file Microsoft Project.

```csharp

```

## Come aggiungere un campo personalizzato a un progetto?

Carica il progetto esistente, crea una definizione di campo personalizzato e aggiungila alla collezione di attributi estesi del progetto—tutto in tre passaggi concisi. Questo modello funziona per attività, risorse e per il progetto stesso, e garantisce che il campo personalizzato venga conservato quando salvi il file.

### Passo 1: Creare l'oggetto Project
`Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file Project in memoria. Istanziandolo carichi il file e ottieni l'accesso a attività, risorse e attributi estesi.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Passo 2: Definire il campo personalizzato
`ExtendedAttributeDefinition` descrive una nuova colonna. In questo esempio creiamo un campo personalizzato di tipo **Testo** per le attività e gli assegniamo l'alias “MyText”. Il valore enum `ExtendedAttributeTask.Text1` indica ad Aspose.Tasks dove memorizzare il valore.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Passo 3: Aggiungere la definizione del campo personalizzato al progetto
La collezione `ExtendedAttributes` del progetto contiene tutte le definizioni dei campi personalizzati. Aggiungere la definizione la rende disponibile per ogni attività nel progetto.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Problemi comuni e soluzioni
- **Il campo non appare nell'interfaccia di MS Project** – Assicurati di impostare la proprietà `Alias`; MS Project visualizza l'alias come intestazione della colonna.  
- **Il salvataggio genera un'eccezione** – Verifica che il file di progetto non sia di sola lettura e che tu abbia una licenza valida.  
- **I valori del campo personalizzato vengono persi dopo il ricaricamento** – Assicurati di chiamare `project.Save("output.mpp")` dopo aver assegnato i valori alle attività.

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri framework .NET?**  
R: Sì, Aspose.Tasks funziona con .NET Framework, .NET Core e .NET 5/6/7.

**D: Aspose.Tasks è adatto per applicazioni a livello enterprise?**  
R: Assolutamente. Supporta l'elaborazione di progetti con **fino a 10.000 attività** e può essere eseguito in ambienti server multithread.

**D: Aspose.Tasks supporta più formati di file di progetto?**  
R: Sì—Aspose.Tasks legge e scrive i formati MPP, XML, HTML e CSV, coprendo **tutte le principali versioni di Microsoft Project**.

**D: Posso manipolare i dati delle risorse usando Aspose.Tasks?**  
R: Sì, puoi aggiungere, aggiornare e eliminare risorse, nonché assegnare loro campi personalizzati.

**D: Esiste un forum della community per gli utenti di Aspose.Tasks?**  
R: Sì, puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per interagire con altri utenti e ottenere supporto dal team Aspose.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Gestire le definizioni di attributi estesi di MS Project in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipolare gli attributi estesi di MS Project con Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Integrazione Field Helper di MS Project in Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}