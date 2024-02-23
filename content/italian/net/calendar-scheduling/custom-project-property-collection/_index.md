---
title: Gestione della raccolta di proprietà del progetto personalizzato in Aspose.Tasks
linktitle: Gestione della raccolta di proprietà del progetto personalizzato in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficace le proprietà del progetto personalizzato in Aspose.Tasks per .NET, migliorando la tua esperienza di gestione dei progetti.
type: docs
weight: 24
url: /it/net/calendar-scheduling/custom-project-property-collection/
---
## introduzione

Sei pronto a migliorare la tua esperienza di gestione dei progetti con Aspose.Tasks per .NET? La gestione delle proprietà di progetto personalizzate è un aspetto cruciale della gestione dei progetti, poiché ti consente di aggiungere metadati specifici su misura per i requisiti del tuo progetto. In questo tutorial, approfondiremo come lavorare in modo efficace con raccolte di proprietà di progetti personalizzati utilizzando Aspose.Tasks per .NET.

## Prerequisiti

Prima di procedere, assicurati di aver configurato i seguenti prerequisiti:

1. Ambiente Visual Studio: avere Visual Studio installato nel sistema.
2.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Link per scaricare](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarizza con le nozioni di base del linguaggio di programmazione C#.

## Importa spazi dei nomi

Inizia importando gli spazi dei nomi necessari per lavorare con Aspose.Tasks per .NET:

```csharp
using Aspose.Tasks;
using System;


```

Suddividiamo il codice di esempio in più passaggi per una comprensione completa:

## Passaggio 1: inizializza il progetto

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Questo passaggio inizializza un nuovo progetto utilizzando Aspose.Tasks.

## Passaggio 2: verificare la disponibilità della raccolta di proprietà personalizzate

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Questo codice controlla se la raccolta delle proprietà personalizzate è di sola lettura.

## Passaggio 3: aggiungi proprietà personalizzate

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Qui aggiungiamo proprietà personalizzate al progetto, supportando i tipi Boolean, DateTime, Double e String.

## Passaggio 4: accedi alle proprietà personalizzate

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Questo ciclo ci consente di scorrere le proprietà personalizzate e visualizzarne il tipo, il nome e il valore.

## Passaggio 5: recupera il valore di una proprietà personalizzata

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Questo codice recupera il valore di una proprietà personalizzata specifica denominata "Nome personalizzato".

## Passaggio 6: ripetere i nomi delle proprietà personalizzate

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Qui iteriamo sui nomi delle proprietà personalizzate e le visualizziamo.

## Passaggio 7: rimuovere o cancellare le proprietà personalizzate

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Puoi rimuovere una proprietà personalizzata specifica tramite il suo nome o cancellare l'intera raccolta.

## Conclusione

Padroneggiare le raccolte di proprietà di progetto personalizzate in Aspose.Tasks per .NET ti consente di gestire in modo efficiente i metadati del progetto. Seguendo questa guida passo passo, puoi integrare perfettamente le proprietà personalizzate nel flusso di lavoro di gestione del progetto, migliorando l'organizzazione e l'efficienza.

## Domande frequenti

### Q1: posso aggiungere proprietà personalizzate di qualsiasi tipo di dati al mio progetto utilizzando Aspose.Tasks per .NET?

R1: Sì, puoi aggiungere proprietà personalizzate che supportano i tipi Boolean, DateTime, Double e String.

### Q2: è possibile scorrere i nomi delle proprietà personalizzate in Aspose.Tasks per .NET?

 A2: Assolutamente, puoi scorrere i nomi delle proprietà personalizzate utilizzando il file`Names` proprietà.

### Q3: Come posso rimuovere una proprietà personalizzata specifica dal mio progetto?

 A3: puoi rimuovere una proprietà personalizzata in base al suo nome utilizzando il file`Remove` metodo.

### Q4: Aspose.Tasks per .NET fornisce supporto per licenze temporanee?

R4: Sì, è possibile ottenere una licenza temporanea dal sito Web Aspose a scopo di valutazione.

### Q5: Dove posso trovare supporto o ulteriore assistenza per quanto riguarda Aspose.Tasks per .NET?

 R5: è possibile visitare il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15) per qualsiasi domanda o assistenza.