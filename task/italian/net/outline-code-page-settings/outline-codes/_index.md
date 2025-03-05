---
title: Gestire i codici di struttura del progetto in Aspose.Tasks per .NET
linktitle: Gestione dei codici struttura in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Impara a gestire i codici di struttura di MS Project con Aspose.Tasks per .NET. Semplifica l'organizzazione del progetto senza sforzo.
type: docs
weight: 10
url: /it/net/outline-code-page-settings/outline-codes/
---
## introduzione
In questo tutorial esploreremo come gestire i codici di struttura di Microsoft Project utilizzando Aspose.Tasks per .NET. I codici struttura sono campi personalizzati in Microsoft Project che consentono agli utenti di classificare e organizzare le attività in base a criteri specifici. Aspose.Tasks semplifica il processo di lettura e manipolazione di questi codici di struttura a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Aspose.Tasks for .NET Library: Scarica e installa la libreria Aspose.Tasks for .NET dal[sito web](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: configurare un ambiente di sviluppo adatto per la programmazione .NET, come Visual Studio.
3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile per comprendere gli esempi di codice.

## Importazione di spazi dei nomi
Per iniziare, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Ciò consente di accedere alle classi e ai metodi forniti dalla libreria Aspose.Tasks.
1. Apri Visual Studio: avvia il tuo IDE di Visual Studio.
2. Crea un nuovo progetto: avvia un nuovo progetto C# o aprine uno esistente in cui intendi utilizzare Aspose.Tasks.
3. Aggiungere riferimento ad Aspose.Tasks: fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, selezionare "Gestisci pacchetti NuGet", cercare "Aspose.Tasks" e installare la versione più recente.
4. Importa spazio dei nomi Aspose.Tasks: nella parte superiore del file C#, aggiungi la seguente direttiva using:
```csharp
using Aspose.Tasks;
using System;

```
## Passaggio 1: definire la directory dei documenti
Innanzitutto, imposta il percorso della directory contenente il file MS Project.
```csharp
String DataDir = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso effettivo del file di progetto.
## Passaggio 2: caricare il file di progetto
 Istanziarne uno nuovo`Project` oggetto caricando il file MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Ciò inizializza l'oggetto del progetto con il file specificato.
## Passaggio 3: leggere i codici di struttura
Scorrere tutte le attività del progetto e recuperare i relativi codici di struttura.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Questo frammento di codice scorre ogni attività, controlla se dispone di codici di struttura e stampa dettagli come ID campo, Guid valore e ID valore per ciascun codice di struttura associato all'attività.

## Conclusione
In conclusione, Aspose.Tasks per .NET offre potenti funzionalità per la gestione dei codici di struttura di Microsoft Project a livello di programmazione. Seguendo i passaggi descritti in questo tutorial, puoi leggere e manipolare in modo efficiente i codici di struttura nei file MS Project utilizzando C#.
## Domande frequenti
### D: Posso modificare i codici di struttura utilizzando Aspose.Tasks?
R: Sì, è possibile modificare i codici di struttura a livello di codice utilizzando Aspose.Tasks per .NET. Accedi semplicemente ai codici di struttura delle attività e aggiorna i loro valori secondo necessità.
### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?
R: Aspose.Tasks supporta un'ampia gamma di versioni di Microsoft Project, tra cui 2003, 2007, 2010, 2013, 2016 e 2019.
### D: Aspose.Tasks richiede una licenza per uso commerciale?
R: Sì, è necessaria una licenza valida per l'uso commerciale di Aspose.Tasks. È possibile ottenere una licenza dal sito Web Aspose.
### D: Posso provare Aspose.Tasks prima dell'acquisto?
R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks dal sito Web per valutarne caratteristiche e capacità.
### D: Dove posso ottenere supporto per Aspose.Tasks?
 R: Puoi ottenere supporto per Aspose.Tasks visitando il forum all'indirizzo[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Codice sorgente completo