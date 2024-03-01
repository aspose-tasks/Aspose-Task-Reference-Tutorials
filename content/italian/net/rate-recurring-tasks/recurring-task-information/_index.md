---
title: Estrazione delle informazioni sulle attività ricorrenti in Aspose.Tasks
linktitle: Estrazione delle informazioni sulle attività ricorrenti in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come estrarre informazioni sulle attività ricorrenti dai file MS Project utilizzando Aspose.Tasks per .NET. Integrazione semplice per gli sviluppatori .NET.
type: docs
weight: 13
url: /it/net/rate-recurring-tasks/recurring-task-information/
---
## introduzione
Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di lavorare con file Microsoft Project nelle loro applicazioni .NET. In questo tutorial esploreremo come estrarre informazioni sulle attività ricorrenti dai file MS Project utilizzando Aspose.Tasks.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Conoscenza base del linguaggio di programmazione C#.
2. Visual Studio installato nel sistema.
3.  Aspose.Tasks per la libreria .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
## Importa spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari nel codice C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Ora suddividiamo l'esempio in più passaggi:
## Passaggio 1: imposta il percorso del file di progetto
```csharp
String DataDir = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso del file MS Project.
## Passaggio 2: caricare il file MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Questa riga inizializza un nuovo file`Project` oggetto caricando il file MS Project specificato dal percorso.
## Passaggio 3: leggere le informazioni ricorrenti delle attività
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Accedi e visualizza le informazioni sulle attività ricorrenti
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Continua a visualizzare altre informazioni sulle attività ricorrenti secondo necessità
}
```
Questo ciclo scorre tutte le attività del progetto e controlla se a ciascuna attività sono associate informazioni ricorrenti. In tal caso, recupera e visualizza varie proprietà dell'attività ricorrente, come data di inizio, durata, data di fine, ecc.
## Conclusione
In questo tutorial, abbiamo imparato come estrarre informazioni sulle attività ricorrenti dai file MS Project utilizzando Aspose.Tasks per .NET. Con questa conoscenza, ora puoi integrare questa funzionalità nelle tue applicazioni .NET per lavorare con attività ricorrenti in modo più efficiente.
## Domande frequenti
### D: Posso modificare le informazioni sulle attività ricorrenti utilizzando Aspose.Tasks per .NET?
R: Sì, puoi modificare le informazioni sulle attività ricorrenti a livello di codice utilizzando le API fornite.
### D: Aspose.Tasks supporta altri formati di file di progetto oltre a MS Project?
R: Sì, Aspose.Tasks supporta vari formati di file di progetto come MPP, XML e CSV.
### D: È disponibile una prova gratuita per Aspose.Tasks per .NET?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Dove posso trovare la documentazione per Aspose.Tasks per .NET?
 R: Puoi trovare la documentazione[Qui](https://reference.aspose.com/tasks/net/).
### D: Come posso ottenere supporto tecnico per Aspose.Tasks per .NET?
 R: È possibile ottenere supporto tecnico dal forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).