---
date: 2026-03-19
description: Scopri come aggiungere più colonne personalizzate e formattare la larghezza
  delle colonne personalizzate durante l'esportazione di un progetto in XML utilizzando
  Aspose.Tasks per .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aggiungi più colonne personalizzate alla vista Assegnazione in Aspose.Tasks
url: /it/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere più colonne personalizzate alla visualizzazione delle assegnazioni in Aspose.Tasks

## Introduzione

In questo tutorial scoprirai **come aggiungere più colonne personalizzate** a una visualizzazione delle assegnazioni con Aspose.Tasks per .NET. Le colonne personalizzate ti consentono di mostrare dati aggiuntivi—come note, costi o flag personalizzati—direttamente nei report esportati. Alla fine della guida sarai in grado di formattare la larghezza della colonna personalizzata, esportare il progetto in XML e personalizzare la visualizzazione per soddisfare le esigenze di gestione del progetto.

## Risposte rapide
- **Cosa posso ottenere?** Visualizzare qualsiasi dato di assegnazione nelle colonne personalizzate e controllarne l'aspetto.  
- **Quale formato lo supporta?** Esportare il progetto in XML (o altri formati) utilizzando `Spreadsheet2003SaveOptions`.  
- **È necessaria una licenza?** Sì, è necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Quali versioni .NET funzionano?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quante colonne posso aggiungere?** Illimitate – basta creare ulteriori istanze di `AssignmentViewColumn`.

## Cosa sono le colonne personalizzate multiple?

Le colonne personalizzate multiple sono campi definiti dall'utente che appaiono accanto alle colonne di assegnazione predefinite quando un progetto viene salvato o esportato. Ti offrono la flessibilità di mostrare qualsiasi proprietà di un oggetto `ResourceAssignment`, come note personalizzate, codici di costo o valori calcolati.

## Perché aggiungere più colonne personalizzate alla visualizzazione delle assegnazioni?
- **Reportistica avanzata:** Includere informazioni specifiche del progetto che non sono coperte dalle colonne integrate.  
- **Migliore presa di decisioni:** Gli stakeholder possono vedere i dati esatti di cui hanno bisogno senza scavare nei file grezzi.  
- **Formattazione coerente:** Controllare la larghezza della colonna e la conversione del testo per un output pulito e leggibile.  

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. Conoscenza di base del linguaggio di programmazione C#.
2. Libreria Aspose.Tasks per .NET installata. In caso contrario, puoi scaricarla **[qui](https://releases.aspose.com/tasks/net/)**.
3. Un ambiente di sviluppo integrato (IDE) come Visual Studio.

## Guida passo‑passo

### Passo 1: Importare i namespace
Innanzitutto, importa i namespace che forniscono le classi necessarie per lavorare con progetti e visualizzazioni.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Passo 2: Caricare il progetto
Crea un'istanza di `Project` e carica un file MPP esistente.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Passo 3: Creare le opzioni di salvataggio per foglio di calcolo
Istanzia `Spreadsheet2003SaveOptions` – questo oggetto ci consente di personalizzare la visualizzazione delle assegnazioni prima dell'esportazione.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Passo 4: Definire la colonna personalizzata
Crea un `AssignmentViewColumn` per ogni dato che desideri mostrare. Di seguito aggiungiamo una colonna **Notes** con una larghezza di 200 punti.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Suggerimento:** Per aggiungere *multiple* colonne personalizzate, ripeti questo passo con nomi di campo diversi e logica di delegato, quindi aggiungi ogni istanza a `options.AssignmentView.Columns`.

### Passo 5: Aggiungere la colonna personalizzata alle opzioni
Aggiungi la colonna (o le colonne) alla collezione `Columns` della visualizzazione delle assegnazioni.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Passo 6: Iterare attraverso le assegnazioni (debug opzionale)
Puoi iterare attraverso le assegnazioni per verificare che il testo della colonna personalizzata venga generato correttamente.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Passo 7: Salvare il progetto con colonne personalizzate
Infine, salva il progetto. L'esempio salva in XML, ma puoi scegliere qualsiasi formato supportato.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Come esportare il progetto in XML con colonne personalizzate?
Quando chiami `project.Save` con le `Spreadsheet2003SaveOptions` configurate, Aspose.Tasks scrive i dati del progetto—comprese tutte le **colonne personalizzate multiple**—nel file XML scelto. Questo facilita la condivisione di informazioni di progetto arricchite con altri sistemi o stakeholder.

## Formattare la larghezza della colonna personalizzata per una migliore leggibilità
Il secondo parametro del costruttore `AssignmentViewColumn` controlla la larghezza della colonna (misurata in punti). Regola questo valore in base alla quantità di testo prevista. Ad esempio, una larghezza di **300** funziona bene per note più lunghe, mentre **100** è sufficiente per flag brevi.

## Problemi comuni e soluzioni
- **Il testo della colonna appare vuoto:** Assicurati che il delegato restituisca una stringa e che la proprietà dell'assegnazione sottostante (ad es., `Asn.NotesText`) sia popolata.  
- **Le colonne non sono visibili nel file esportato:** Verifica che `options.AssignmentView.Columns` contenga le tue colonne personalizzate prima di chiamare `Save`.  
- **La larghezza sembra ignorata:** Alcuni formati di esportazione hanno proprie regole di layout; XML rispetta la larghezza, ma PDF/HTML potrebbero richiedere stilizzazioni aggiuntive.

## Domande frequenti

### Q1: Posso aggiungere più colonne personalizzate alla visualizzazione delle assegnazioni?
**R:** Sì, basta creare ulteriori oggetti `AssignmentViewColumn` e aggiungerli tutti a `options.AssignmentView.Columns`.

### Q2: Esistono convertitori predefiniti disponibili per i campi di assegnazione comuni?
**R:** Sì, Aspose.Tasks fornisce convertitori integrati per molti campi standard, facilitando l'estrazione dei dati senza scrivere delegati personalizzati.

### Q3: Posso personalizzare l'aspetto delle colonne personalizzate, ad esempio formattare il testo o applicare stili?
**R:** Assolutamente. Oltre a impostare la larghezza, puoi modificare il carattere, l'allineamento e altre proprietà visive tramite le opzioni di stile della colonna.

### Q4: È possibile rimuovere le colonne predefinite dalla visualizzazione delle assegnazioni?
**R:** Puoi escludere le colonne predefinite rimuovendole dalla collezione `Columns` o impostando la loro larghezza a zero.

### Q5: Aspose.Tasks supporta l'esportazione di progetti in altri formati oltre ai fogli di calcolo con colonne personalizzate?
**R:** Sì, Aspose.Tasks può esportare in PDF, HTML, XML e molti altri formati mantenendo le definizioni delle colonne personalizzate.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}