---
title: Statistiche per elementi di rischio in Aspose.Tasks
linktitle: Statistiche per elementi di rischio in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Sblocca la potenza dell'analisi del rischio nei file MS Project utilizzando Aspose.Tasks per .NET. Ottieni informazioni approfondite, riduci le incertezze e favorisci il successo dei progetti senza sforzo.
type: docs
weight: 21
url: /it/net/resource-risk-analysis/risk-item-statistics/
---
## introduzione
Stai cercando di migliorare le tue capacità di gestione dei progetti utilizzando Aspose.Tasks per .NET? Addentrati nel regno dell'analisi del rischio con il nostro tutorial passo passo su come ottenere statistiche per gli elementi di rischio nei file MS Project. Sfruttando le potenti funzionalità di Aspose.Tasks, puoi ottenere informazioni preziose sulle incertezze del progetto e prendere decisioni informate per mitigare i rischi in modo efficace.
## Prerequisiti
Prima di intraprendere questo viaggio, assicurati di possedere i seguenti prerequisiti:
1.  Aspose.Tasks per .NET Library: scarica e installa la libreria da[Aspose.Tasks per la documentazione .NET](https://reference.aspose.com/tasks/net/). Questa libreria fornisce strumenti robusti per manipolare i file MS Project a livello di codice.
2. Ambiente di sviluppo .NET: configura il tuo ambiente di sviluppo .NET, incluso Visual Studio o qualsiasi altro IDE di tua scelta, per facilitare la perfetta integrazione di Aspose.Tasks nei tuoi progetti.

## Importa spazi dei nomi
Incorpora gli spazi dei nomi necessari nel tuo progetto per sfruttare le funzionalità di Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Passaggio 1: definire la directory dei dati
```csharp
String DataDir = "Your Document Directory";
```
 Assicurarsi di sostituire`"Your Document Directory"` con il percorso della directory dei documenti in cui si trovano i file di MS Project.
## Passaggio 2: configurare le impostazioni di analisi del rischio
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Aggiusta il`IterationsCount`parametro in base ai requisiti del progetto per controllare la precisione dell'analisi del rischio.
## Passaggio 3: caricare il file MS Project
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Caricare il file MS Project desiderato nel file`project` oggetto di ulteriore analisi.
## Passaggio 4: definire l'attività e inizializzare il modello di rischio
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Specificare l'attività per l'analisi del rischio e configurare il modello di rischio con parametri appropriati come tipo di distribuzione, durate ottimistiche e pessimistiche e livello di confidenza.
## Passaggio 5: analizzare i rischi del progetto
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Avviare il processo di analisi del rischio utilizzando le impostazioni definite e i dati di progetto.
## Passaggio 6: recuperare e visualizzare le statistiche
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Recupera e visualizza varie metriche statistiche relative agli elementi di rischio nel file MS Project, inclusi valore atteso, deviazione standard, percentili, valori minimi e massimi.

## Conclusione
In conclusione, padroneggiare l'analisi dei rischi nei file MS Project utilizzando Aspose.Tasks per .NET apre un regno di possibilità per i project manager e le parti interessate. Seguendo il nostro tutorial completo, puoi affrontare le incertezze con sicurezza, garantendo risultati di progetto positivi.
## Domande frequenti
### Posso integrare Aspose.Tasks con altre librerie .NET per funzionalità estese?
Assolutamente! Aspose.Tasks si integra perfettamente con varie librerie .NET, consentendoti di amplificare le sue capacità in base ai requisiti del tuo progetto.
### È disponibile una versione di prova per Aspose.Tasks per .NET?
 Sì, puoi esplorare le funzionalità di Aspose.Tasks accedendo a[prova gratuita](https://releases.aspose.com/) disponibile sul nostro sito web.
### Con quale frequenza vengono rilasciati aggiornamenti e miglioramenti per Aspose.Tasks?
Ci impegniamo a migliorare continuamente Aspose.Tasks rilasciando periodicamente aggiornamenti e miglioramenti, assicurandoti di avere sempre accesso alle funzionalità e ottimizzazioni più recenti.
### Posso ottenere supporto tecnico per Aspose.Tasks?
Certamente! Il nostro team di supporto dedicato è prontamente disponibile su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assisterti in caso di domande o sfide che potresti incontrare durante il percorso di implementazione.
### Offrite licenze temporanee per progetti a breve termine?
 Sì, se hai bisogno di Aspose.Tasks per un progetto a breve termine, puoi usufruire del nostro conveniente[licenza temporanea](https://purchase.aspose.com/temporary-license/) opzione per soddisfare le tue esigenze di licenza senza impegni a lungo termine.