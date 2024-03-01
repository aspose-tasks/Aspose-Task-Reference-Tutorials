---
title: Padroneggiare le opzioni di salvataggio di MS Project per Aspose.Tasks
linktitle: Opzioni generali di salvataggio per Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Impara a salvare i file MS Project in modo efficiente utilizzando Aspose.Tasks per .NET. Personalizza facilmente le opzioni di output per i tuoi progetti.
type: docs
weight: 17
url: /it/net/saving-options/general-save-options/
---
## introduzione
Aspose.Tasks per .NET offre potenti funzionalità per manipolare i file di Microsoft Project a livello di codice. In questo tutorial, approfondiremo le complessità del salvataggio dei file MS Project utilizzando varie opzioni fornite da Aspose.Tasks. Nello specifico, ci concentreremo sulle opzioni di salvataggio generali disponibili per Aspose.Tasks, consentendoti di personalizzare l'output in base alle tue esigenze specifiche.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  Installazione di Aspose.Tasks per .NET: scaricare e installare Aspose.Tasks per .NET dal[Link per scaricare](https://releases.aspose.com/tasks/net/).
2. Comprensione di base di .NET Framework: la familiarità con i concetti di programmazione .NET è utile.

## Importazione di spazi dei nomi
Prima di immergerti nel codice, assicurati di importare gli spazi dei nomi necessari:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Passaggio 1: caricare il file di progetto
Innanzitutto, devi caricare il file MS Project utilizzando Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Passaggio 2: definire le opzioni di salvataggio
 Definisci le opzioni di salvataggio in base alle tue esigenze. In questo esempio, stiamo utilizzando`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Passaggio 3: personalizzare le colonne della vista
Puoi personalizzare le colonne della vista come il diagramma di Gantt, la vista delle risorse e la vista delle assegnazioni. Ecco come aggiungere colonne a ciascuna:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Passaggio 4: salva il progetto con le opzioni
Infine, salva il progetto con le opzioni specificate:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusione
Padroneggiare le opzioni generali di salvataggio di MS Project con Aspose.Tasks per .NET ti consente di personalizzare in modo efficiente il formato di output in base alle esigenze del tuo progetto.
## Domande frequenti
### D: Aspose.Tasks è compatibile con diverse versioni dei file MS Project?
R: Sì, Aspose.Tasks supporta varie versioni dei file MS Project, garantendo la compatibilità tra diversi ambienti.
### D: Posso provare Aspose.Tasks prima dell'acquisto?
 R: Sì, puoi esplorare Aspose.Tasks con una prova gratuita disponibile[Qui](https://releases.aspose.com/).
### D: Dove posso trovare la documentazione per Aspose.Tasks?
 R: È possibile trovare la documentazione dettagliata[Qui](https://reference.aspose.com/tasks/net/), fornendo indicazioni complete sull'utilizzo delle funzionalità Aspose.Tasks.
### D: Come posso ottenere licenze temporanee per Aspose.Tasks?
 R: Le licenze temporanee sono disponibili a scopo di valutazione[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso chiedere supporto per le query relative ad Aspose.Tasks?
 R: Puoi iscriverti al forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15)per ottenere assistenza da esperti e colleghi sviluppatori.