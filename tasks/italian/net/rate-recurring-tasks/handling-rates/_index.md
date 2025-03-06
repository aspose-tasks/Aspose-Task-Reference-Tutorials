---
title: Gestione delle tariffe dei progetti MS con Aspose.Tasks per .NET
linktitle: Gestione delle tariffe in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Padroneggia la gestione delle tariffe di MS Project con facilità utilizzando Aspose.Tasks per .NET. Automatizza le attività in modo efficiente per flussi di lavoro di progetto più fluidi.
weight: 10
url: /it/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione delle tariffe dei progetti MS con Aspose.Tasks per .NET

## introduzione
Benvenuti nel nostro tutorial sulla gestione delle tariffe di MS Project utilizzando Aspose.Tasks per .NET! In questa guida ti guideremo attraverso il processo passo dopo passo, assicurandoti di poter gestire in modo efficiente le tariffe all'interno dei tuoi documenti MS Project. Aspose.Tasks per .NET fornisce potenti funzionalità per manipolare i file MS Project a livello di codice, consentendoti di semplificare le attività di gestione del progetto senza sforzo.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1. Visual Studio installato: assicurati di avere Visual Studio installato nel tuo sistema.
2.  Aspose.Tasks per .NET Library: scarica e installa la libreria Aspose.Tasks per .NET. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/tasks/net/).
3. Comprensione di base di C#: acquisisci familiarità con i fondamenti del linguaggio di programmazione C#.
## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Questi spazi dei nomi forniranno l'accesso alle classi e ai metodi richiesti per la gestione di MS Project Rates.
## Passaggio 1: importare lo spazio dei nomi Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Ora suddividiamo l'esempio fornito in più passaggi e comprendiamo a fondo ogni passaggio.
## Passaggio 1: caricare il file di progetto
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 In questo passaggio, stiamo caricando un file MS Project esistente denominato "Project1.mpp" utilizzando il file`Project` classe fornita da Aspose.Tasks.
## Passaggio 2: aggiungi risorsa e imposta lavoro
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Qui aggiungiamo una nuova risorsa denominata "Risorsa 1" al progetto e ne impostiamo il tipo come "Lavoro". Definiamo anche la durata del lavoro per questa risorsa.
## Passaggio 3: imposta la tariffa standard
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
In questo passaggio impostiamo la tariffa standard per la risorsa su $ 20 l'ora.
## Passaggio 4: definire i periodi tariffari
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Qui definiamo i periodi tariffari per la risorsa. La tariffa 1 è fissata dal 1 gennaio 2019 all'11 novembre 2019, con tariffe standard e straordinarie specificate.
## Passaggio 5: aggiungi un altro periodo tariffario
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
In questo passaggio finale, aggiungiamo un altro periodo tariffario a partire dal 12 novembre 2019 al 31 dicembre 2019, con una tariffa standard e un costo per utilizzo diversi definiti.
Congratulazioni! Hai gestito con successo MS Project Rates utilizzando Aspose.Tasks per .NET.
## Conclusione
La gestione programmatica di MS Project Rates può migliorare in modo significativo il flusso di lavoro di gestione dei progetti. Con Aspose.Tasks per .NET, hai il potere di automatizzare le attività di gestione delle tariffe in modo efficiente, risparmiando tempo e risorse.
## Domande frequenti
### D: Aspose.Tasks può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks fornisce funzionalità robuste per gestire facilmente strutture di progetti complessi.
### D: Aspose.Tasks è compatibile con tutte le versioni dei file MS Project?
R: Aspose.Tasks supporta varie versioni dei file MS Project, garantendo la compatibilità tra diverse piattaforme.
### D: Posso modificare le tariffe esistenti in un file MS Project utilizzando Aspose.Tasks?
R: Assolutamente! Aspose.Tasks ti consente di modificare le tariffe esistenti, aggiungere nuove tariffe e gestirle dinamicamente.
### D: Aspose.Tasks offre supporto per i calcoli delle tariffe personalizzate?
R: Sì, puoi implementare calcoli di tariffe personalizzate utilizzando Aspose.Tasks per soddisfare requisiti di progetto specifici.
### D: Esiste un forum della community o supporto disponibile per gli utenti di Aspose.Tasks?
 R: Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)per chiedere assistenza e interagire con altri utenti.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
