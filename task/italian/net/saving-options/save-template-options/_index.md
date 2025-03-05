---
title: Salva i file MS Project come modelli con Aspose.Tasks
linktitle: Salva opzioni modello per Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come salvare i file di Microsoft Project come modelli utilizzando Aspose.Tasks per .NET. Personalizza le impostazioni del modello per una gestione semplificata dei progetti.
type: docs
weight: 18
url: /it/net/saving-options/save-template-options/
---
## introduzione
In questo tutorial, esamineremo il processo di salvataggio di un modello utilizzando Aspose.Tasks per .NET. I modelli sono utili per standardizzare le strutture e le impostazioni del progetto per un utilizzo futuro. Dimostreremo come salvare un progetto come modello, ottimizzandone le proprietà lungo il percorso.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  Libreria Aspose.Tasks per .NET: assicurati di avere la libreria Aspose.Tasks per .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
2. Conoscenza della programmazione C#: è necessaria una conoscenza di base della programmazione C# per comprendere e implementare i frammenti di codice forniti.
3. File Microsoft Project: tieni pronto un file Microsoft Project (formato MPP) che desideri salvare come modello.

## Importa spazi dei nomi
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Passaggio 1: caricare il progetto
Per prima cosa dobbiamo caricare il file Microsoft Project (.mpp) che vogliamo salvare come modello.
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Passaggio 2: ottieni informazioni sul file di progetto
Recupera informazioni sul file di progetto caricato, come il suo formato.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Passaggio 3: configura le opzioni di salvataggio del modello
Crea opzioni di salvataggio del modello e configura le sue proprietà in base alle tue esigenze. Queste opzioni ti consentono di personalizzare quali dati devono essere rimossi dal modello.
```csharp
var options = new SaveTemplateOptions
{
	// Rimuovi tutti i costi fissi dal modello di progetto
	RemoveFixedCosts = true,
	// Rimuovere tutti i valori effettivi dal modello di progetto
	RemoveActualValues = true,
	// Rimuovere le tariffe delle risorse dal modello di progetto
	RemoveResourceRates = true,
	// Rimuovere tutti i valori di base dal modello di progetto
	RemoveBaselineValues = true
};
```
## Passaggio 4: salva il progetto come modello
Salva il progetto come modello con le opzioni specificate.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Passaggio 5: ottieni informazioni sul file modello
Recupera informazioni sul file modello salvato, come il suo formato.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Congratulazioni! Hai salvato con successo un modello utilizzando Aspose.Tasks per .NET, personalizzandone le proprietà secondo necessità.

## Conclusione
In questo tutorial, abbiamo esplorato come salvare un file Microsoft Project come modello utilizzando Aspose.Tasks per .NET. I modelli sono preziosi per standardizzare le strutture e le impostazioni del progetto, semplificando le future creazioni di progetti.
## Domande frequenti
### D: Posso personalizzare quali dati rimuovere dal modello?
R: Sì, puoi configurare le opzioni di salvataggio del modello per rimuovere dati specifici come costi fissi, valori effettivi, tariffe delle risorse e valori di base.
### D: Aspose.Tasks per .NET è compatibile con tutte le versioni di Microsoft Project?
R: Aspose.Tasks per .NET fornisce un'ampia compatibilità con varie versioni di Microsoft Project, garantendo integrazione e funzionalità perfette.
### D: Posso applicare modelli a progetti esistenti?
R: Sì, puoi applicare modelli a progetti esistenti caricando il file modello e unendolo al progetto corrente secondo necessità.
### D: Aspose.Tasks per .NET supporta lo sviluppo multipiattaforma?
R: Aspose.Tasks per .NET è progettato principalmente per applicazioni .NET framework in esecuzione su piattaforme Windows.
### D: È disponibile il supporto tecnico per Aspose.Tasks per .NET?
 R: Sì, puoi chiedere assistenza tecnica e guida alla community Aspose.Tasks[forum](https://forum.aspose.com/c/tasks/15) contatta direttamente il loro team di supporto.