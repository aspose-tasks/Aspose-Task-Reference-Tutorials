---
title: Tariffe dei progetti Master MS con Aspose.Tasks
linktitle: Raccolta delle tariffe in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le tariffe nei file MS Project utilizzando Aspose.Tasks per .NET. Tutorial passo passo per una gestione efficace delle risorse.
type: docs
weight: 11
url: /it/net/rate-recurring-tasks/rate-collection/
---
## introduzione
Benvenuti nel nostro tutorial sulla gestione delle tariffe in MS Project utilizzando Aspose.Tasks per .NET! In questa guida ti guideremo attraverso il processo di utilizzo delle tariffe nei file MS Project utilizzando Aspose.Tasks. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato con lo sviluppo .NET, questo tutorial ti fornirà istruzioni dettagliate per gestire in modo efficace le tariffe all'interno dei tuoi progetti.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
### 1. Visual Studio installato
Assicurati di avere Visual Studio installato sul tuo sistema. Puoi scaricarlo dal sito web se non lo hai già fatto.
### 2. Aspose.Tasks per .NET
 Scarica e installa la libreria Aspose.Tasks per .NET da[sito web](https://releases.aspose.com/tasks/net/).
### 3. Conoscenza di base di C# e .NET
Acquisisci familiarità con il linguaggio di programmazione C# e le nozioni di base di .NET Framework per comprendere meglio gli esempi di codice forniti in questo tutorial.
## Importa spazi dei nomi
Nel tuo progetto C#, importa gli spazi dei nomi necessari per utilizzare le funzionalità Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Ora suddividiamo ciascun esempio in più passaggi:
## Passaggio 1: caricare un file MS Project
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Qui ne creiamo uno nuovo`Project` oggetto caricando un file MS Project esistente.
## Passaggio 2: aggiungi una risorsa e imposta lavoro e tariffe
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Aggiungiamo una nuova risorsa al progetto, ne impostiamo il tipo come lavoro, importo del lavoro e tariffa standard.
## Passaggio 3: aggiungi tariffe alla risorsa
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Aggiungiamo le tariffe alla risorsa specificando le date di inizio e fine, la tariffa standard e il formato della tariffa.
## Passaggio 4: stampare le informazioni sulle tariffe
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Questo passaggio stampa le informazioni sulle tariffe associate alla risorsa.
## Passaggio 5: aggiorna una tariffa
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Aggiorniamo la data di fine di una tariffa specifica.
## Passaggio 6: rimuovi le tariffe
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Questo passaggio rimuove tutte le tariffe di un tipo specifico.
## Passaggio 7: ripetere le tariffe rimanenti
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Infine, iteriamo sulle tariffe rimanenti dopo la rimozione.
## Conclusione
In conclusione, questo tutorial ti ha fornito una guida completa sulla gestione delle tariffe nei file MS Project utilizzando Aspose.Tasks per .NET. Seguendo le istruzioni dettagliate descritte in questo tutorial, puoi gestire in modo efficiente le tariffe all'interno dei tuoi progetti, garantendo un'accurata gestione delle risorse.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con altri software di gestione dei progetti?
R: Sì, Aspose.Tasks per .NET supporta l'integrazione con vari software di gestione dei progetti, tra cui MS Project, Primavera e altri.
### D: Aspose.Tasks per .NET è compatibile con diverse versioni dei file MS Project?
R: Assolutamente, Aspose.Tasks per .NET supporta il lavoro con file MS Project di diverse versioni, garantendo flessibilità e compatibilità.
### D: Aspose.Tasks per .NET offre documentazione e supporto?
 R: Sì, puoi trovare documentazione completa e accesso ai forum di supporto su Aspose.Tasks[sito web](https://reference.aspose.com/tasks/net/).
### D: Posso provare Aspose.Tasks per .NET prima dell'acquisto?
R: Sì, puoi usufruire di una prova gratuita di Aspose.Tasks per .NET per valutarne le funzionalità e la compatibilità con le tue esigenze.
### D: Come posso acquistare una licenza per Aspose.Tasks per .NET?
 R: È possibile acquistare una licenza per Aspose.Tasks per .NET da[sito web](https://purchase.aspose.com/temporary-license/)che fornisce opzioni di licenza flessibili per soddisfare le tue esigenze.