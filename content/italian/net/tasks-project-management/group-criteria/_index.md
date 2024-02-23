---
title: Manipolazione dei criteri del gruppo di progetti MS in Aspose.Tasks
linktitle: Criteri di gruppo in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora come manipolare i file MS Project a livello di codice in .NET utilizzando Aspose.Tasks. Recupera informazioni sui gruppi di attività e sui criteri, esempi passo passo.
type: docs
weight: 27
url: /it/net/tasks-project-management/group-criteria/
---
## introduzione
Aspose.Tasks per .NET è una potente API che facilita il lavoro con i file Microsoft Project nelle applicazioni .NET. Che tu stia sviluppando un software di gestione dei progetti o abbia bisogno di manipolare i dati del progetto a livello di programmazione, Aspose.Tasks offre un set completo di funzionalità per soddisfare le tue esigenze.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
### 1. Conoscenza di C# e .NET Framework
La familiarità con il linguaggio di programmazione C# e .NET Framework è essenziale per comprendere e implementare gli esempi forniti in questo tutorial.
### 2. Installazione di Aspose.Tasks per .NET
 Assicurati di avere Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/tasks/net/) e seguire le istruzioni di installazione fornite.
### 3. Ambiente di sviluppo integrato (IDE)
Avere un IDE come Visual Studio installato sul tuo sistema per scrivere ed eseguire codice C#.

## Importa spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari nel codice C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Passaggio 1: caricare un file Microsoft Project
Innanzitutto, specifica il percorso del tuo file Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 sostituire`"Your Document Directory"` con il percorso del file di progetto.
## Passaggio 2: recuperare le informazioni sui gruppi di attività
Successivamente, recupera le informazioni sui gruppi di attività nel progetto:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Questo frammento di codice stampa il conteggio totale dei gruppi di attività, recupera il secondo gruppo di attività, il relativo nome e il conteggio dei criteri in esso contenuti.
## Passaggio 3: recuperare le informazioni sui criteri del gruppo di attività
Ora, approfondiamo i dettagli di un criterio specifico all'interno del gruppo di attività:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Questo segmento visualizza varie proprietà del criterio come indice, campo, informazioni sul raggruppamento, colore della cella, colore del carattere, intervallo di gruppo e punto iniziale.
## Passaggio 4: recuperare le informazioni sui caratteri di Criterion
Infine, ottieni i dettagli relativi ai caratteri del criterio:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Questo passaggio stampa il nome del carattere, la dimensione, lo stile e se il criterio è ordinato in ordine crescente o decrescente.

## Conclusione
In questo tutorial, abbiamo esplorato come utilizzare Aspose.Tasks per .NET per recuperare informazioni su gruppi di attività e criteri da un file di Microsoft Project. Seguendo la guida passo passo è possibile lavorare in modo efficiente con i dati di progetto a livello di codice nelle applicazioni .NET.
## Domande frequenti
### Aspose.Tasks può gestire file Microsoft Project di grandi dimensioni?
Aspose.Tasks è ottimizzato per gestire file di progetto di grandi dimensioni in modo efficiente, garantendo prestazioni elevate e affidabilità.
### Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?
Sì, Aspose.Tasks supporta varie versioni di Microsoft Project, garantendo la compatibilità tra diversi formati di file.
### Posso manipolare i dati del progetto utilizzando Aspose.Tasks?
Assolutamente, Aspose.Tasks fornisce funzionalità estese per manipolare i dati del progetto, incluse attività, risorse, calendari e altro.
### Aspose.Tasks offre supporto per diverse piattaforme .NET?
Sì, Aspose.Tasks supporta più piattaforme .NET tra cui .NET Framework, .NET Core e .NET Standard.
### Esiste un forum della community per Aspose.Tasks dove posso chiedere assistenza?
 Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per porre domande, condividere conoscenze e collaborare con altri utenti.