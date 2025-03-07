---
title: Raccogliere statistiche sugli elementi di rischio del progetto MS in Aspose.Tasks
linktitle: Raccolta di statistiche sugli elementi di rischio in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come raccogliere statistiche sugli elementi di rischio dai file MS Project utilizzando Aspose.Tasks per .NET. Migliora le tue capacità di gestione dei progetti.
weight: 22
url: /it/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Raccogliere statistiche sugli elementi di rischio del progetto MS in Aspose.Tasks

## introduzione
In questo tutorial esploreremo come raccogliere statistiche sugli elementi di rischio dai file MS Project utilizzando Aspose.Tasks per .NET. Questa libreria fornisce potenti funzionalità per analizzare i dati del progetto, inclusa la valutazione del rischio e l'analisi statistica.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks. Puoi ottenerlo da[pagina di download](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: disporre di un ambiente di sviluppo configurato per la programmazione .NET.

## Importa spazi dei nomi
Prima di iniziare a scrivere codice, assicurati di importare gli spazi dei nomi necessari nel tuo progetto:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Passaggio 1: caricare il file di progetto
Innanzitutto, devi caricare il file MS Project nella tua applicazione. Ecco come puoi ottenerlo:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Passaggio 2: definire le impostazioni di analisi del rischio
Inizializza le impostazioni dell'analisi del rischio, incluso il numero di iterazioni, come mostrato di seguito:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Passaggio 3: inizializzare un modello di rischio
Imposta un modello di rischio per l'analisi, specificando il tipo di distribuzione, le percentuali ottimistiche e pessimistiche e il livello di confidenza:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Passaggio 4: eseguire l'analisi dei rischi
 Istanziare il`RiskAnalyzer` lezione e analizzare il progetto:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Passaggio 5: recuperare le statistiche
Recupera le statistiche degli elementi di rischio, come la fine anticipata, dal risultato dell'analisi:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Passaggio 6: stampa delle statistiche
Itera sulle statistiche e stampa i dettagli:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Stampa altre statistiche rilevanti...
}
```

## Conclusione
In questo tutorial, abbiamo imparato come utilizzare Aspose.Tasks per .NET per raccogliere statistiche sugli elementi di rischio dai file MS Project. Seguendo questi passaggi, puoi analizzare in modo efficace i dati del progetto e valutare i potenziali rischi, contribuendo a migliorare il processo decisionale e la gestione del progetto.

## Domande frequenti
### D: Aspose.Tasks può gestire file MS Project di grandi dimensioni?
R: Sì, Aspose.Tasks è in grado di gestire file MS Project di grandi dimensioni in modo efficiente, offrendo prestazioni affidabili e scalabilità.
### D: Aspose.Tasks supporta altri formati di file di progetto oltre a .mpp?
R: Sì, Aspose.Tasks supporta vari formati di file di progetto, inclusi XML e MPT.
### D: Aspose.Tasks è adatto per applicazioni di gestione di progetti a livello aziendale?
R: Assolutamente, Aspose.Tasks è progettato per soddisfare le esigenze delle applicazioni di gestione dei progetti a livello aziendale, fornendo funzionalità robuste e ampia documentazione.
### D: Posso personalizzare le impostazioni di analisi del rischio in Aspose.Tasks?
R: Sì, Aspose.Tasks offre flessibilità nella configurazione delle impostazioni di analisi del rischio per soddisfare i requisiti e gli scenari specifici del progetto.
### D: Il supporto tecnico è disponibile per gli utenti Aspose.Tasks?
 R: Sì, gli utenti di Aspose.Tasks possono accedere al supporto tecnico tramite Aspose[forum](https://forum.aspose.com/c/tasks/15), dove possono porre domande, segnalare problemi e interagire con la community.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
