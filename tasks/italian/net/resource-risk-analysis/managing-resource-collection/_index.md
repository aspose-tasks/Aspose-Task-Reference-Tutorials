---
title: Gestione della raccolta di risorse del progetto in Aspose.Tasks
linktitle: Gestione della raccolta di risorse in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente le raccolte di risorse di Microsoft Project in .NET utilizzando l'API Aspose.Tasks. Aumentare produttività e flessibilità.
weight: 13
url: /it/net/resource-risk-analysis/managing-resource-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione della raccolta di risorse del progetto in Aspose.Tasks

## introduzione
In questo tutorial esploreremo come gestire in modo efficace le raccolte di risorse di Microsoft Project utilizzando Aspose.Tasks per .NET. Aspose.Tasks è una potente API che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice, consentendo una perfetta integrazione e manipolazione dei dati di progetto.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza di C# e .NET Framework: questo tutorial presuppone familiarità con il linguaggio di programmazione C# e .NET Framework.
2. Installazione di Aspose.Tasks per .NET: assicurati di aver installato Aspose.Tasks per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
3. Configurazione dell'ambiente di sviluppo: configura il tuo ambiente di sviluppo con Visual Studio o qualsiasi altro IDE preferito.

## Importa spazi dei nomi
Prima di iniziare, importa gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Passaggio 1: caricare il file di progetto
Innanzitutto, carica il file Microsoft Project nell'oggetto del progetto Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Passaggio 2: aggiungi risorsa vuota
Successivamente, aggiungiamo una risorsa vuota al progetto:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Passaggio 3: aggiungi risorsa con un nome
Ora aggiungi una risorsa con un nome specificato al progetto:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Passaggio 4: aggiungere la risorsa prima di un'altra risorsa
Aggiungi una risorsa con un nome specificato prima di un'altra risorsa in base al suo ID:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Passaggio 5: accesso alle risorse tramite ID o UID
Puoi accedere alle risorse tramite il loro ID o UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Passaggio 6: stampa delle informazioni sulle risorse
Stampa le informazioni sulle risorse del progetto:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Passaggio 7: eliminazione delle risorse
Elimina risorse dal progetto:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Conclusione
La gestione delle raccolte di risorse di Microsoft Project utilizzando Aspose.Tasks per .NET fornisce agli sviluppatori un robusto set di strumenti per gestire in modo efficiente le risorse del progetto a livello di codice. Seguendo i passaggi descritti in questo tutorial, puoi manipolare senza problemi le risorse all'interno dei tuoi progetti, migliorando la produttività e la flessibilità nelle attività di gestione dei progetti.
## Domande frequenti
### D: Aspose.Tasks può gestire file di progetto su larga scala?

R: Sì, Aspose.Tasks è progettato per gestire in modo efficiente file di progetto su larga scala, offrendo prestazioni elevate e affidabilità.

### D: Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?

R: Aspose.Tasks supporta varie versioni di Microsoft Project, garantendo la compatibilità tra diversi ambienti.

### D: posso personalizzare le proprietà delle risorse utilizzando Aspose.Tasks?

R: Assolutamente, Aspose.Tasks offre ampie funzionalità per personalizzare le proprietà delle risorse in base ai requisiti specifici del progetto.

### D: Aspose.Tasks supporta il multi-threading per operazioni simultanee?

R: Sì, Aspose.Tasks supporta il multi-threading, consentendo operazioni simultanee sui dati del progetto per migliorare le prestazioni.

### D: Il supporto tecnico è disponibile per gli utenti Aspose.Tasks?

 R: Sì, gli utenti di Aspose.Tasks possono accedere al supporto tecnico tramite il forum[Qui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
