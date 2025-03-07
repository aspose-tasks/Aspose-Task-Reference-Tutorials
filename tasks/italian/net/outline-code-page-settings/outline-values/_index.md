---
title: Padroneggiare i valori di struttura del progetto MS con Aspose.Tasks
linktitle: Gestione dei valori di struttura in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire i valori della struttura di MS Project in modo efficiente utilizzando Aspose.Tasks per .NET. Personalizza facilmente i contorni del progetto.
weight: 16
url: /it/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare i valori di struttura del progetto MS con Aspose.Tasks

## introduzione
In questo tutorial esploreremo come gestire i valori della struttura di Microsoft Project utilizzando la libreria Aspose.Tasks per .NET. Con Aspose.Tasks, puoi facilmente manipolare i codici di struttura, creare nuovi valori di struttura e personalizzare i contorni del progetto in base alle tue esigenze.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Installazione di Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo configurato, come Visual Studio, con compatibilità con .NET Framework.
3. Comprensione di base della programmazione C#: acquisisci familiarità con le nozioni di base del linguaggio di programmazione C#, poiché utilizzeremo C# per lavorare con la libreria Aspose.Tasks.

## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo codice C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Passaggio 1: caricare il file di progetto
```csharp
// Il percorso della directory dei documenti.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Questo passaggio inizializza un nuovo oggetto Project e carica il file Microsoft Project dalla directory specificata.
## Passaggio 2: definire le definizioni del codice di struttura
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Qui definiamo due oggetti OutlineCodeDefinition e li aggiungiamo alla raccolta OutlineCodes del progetto.
## Passaggio 3: Definisci la maschera di contorno
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Questo passaggio configura una OutlineMask per la definizione del codice di struttura.
## Passaggio 4: creare valori di struttura
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
In questo passaggio creiamo due oggetti OutlineValue e ne impostiamo le proprietà quali valore, ID valore, tipo, descrizione e stato di compressione.

## Conclusione
La gestione dei valori di struttura di MS Project utilizzando Aspose.Tasks per .NET è semplice con le funzionalità fornite. Seguendo i passaggi descritti in questo tutorial, puoi manipolare in modo efficiente codici e valori di struttura per personalizzare le strutture del progetto in base alle tue esigenze.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks con altri framework .NET?
R: Sì, Aspose.Tasks è compatibile con vari framework .NET, garantendo flessibilità nel tuo ambiente di sviluppo.
### D: È disponibile una versione di prova per Aspose.Tasks?
 R: Sì, puoi accedere a una versione di prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Tasks?
 R: Per supporto e assistenza, è possibile visitare il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### D: Posso acquistare una licenza temporanea per Aspose.Tasks?
R: Sì, puoi acquistare una licenza temporanea per Aspose.Tasks da[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?
 R: Puoi fare riferimento alla documentazione completa disponibile[Qui](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
