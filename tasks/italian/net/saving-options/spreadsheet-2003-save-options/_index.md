---
title: MS Project con opzioni foglio di calcolo 2003 per Aspose.Tasks
linktitle: Foglio di calcolo 2003 Salva opzioni per Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Foglio di calcolo principale 2003 Salva le opzioni di MS Project con Aspose.Tasks per .NET. Personalizza e salva senza problemi i file MS Project a livello di codice.
type: docs
weight: 19
url: /it/net/saving-options/spreadsheet-2003-save-options/
---
## introduzione
In questo tutorial, approfondiremo l'utilizzo di Aspose.Tasks per .NET per utilizzare le opzioni di salvataggio di MS Project di Spreadsheet 2003. Questo potente strumento consente la manipolazione e la personalizzazione senza soluzione di continuità dei file MS Project nell'ambiente .NET. Analizziamo il processo passo dopo passo.
## Prerequisiti
Prima di intraprendere questo tutorial, assicurati di possedere i seguenti prerequisiti:
1.  Installazione di Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET dal[Link per scaricare](https://releases.aspose.com/tasks/net/).
2. Familiarità con la programmazione C#: per comprendere i concetti discussi in questo tutorial è necessaria una conoscenza di base del linguaggio di programmazione C#.

## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto C#:
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Questi spazi dei nomi forniscono l'accesso alle funzionalità necessarie per salvare i file MS Project utilizzando il formato Foglio di calcolo 2003 e personalizzare le opzioni di visualizzazione.
## Passaggio 1: caricare il progetto
Innanzitutto, carica il file MS Project utilizzando Aspose.Tasks:
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 Sostituire`"Your Document Directory"`con il percorso effettivo della directory in cui si trova il file MS Project.
## Passaggio 2: definire le opzioni di salvataggio
 Definire le opzioni di salvataggio del foglio di calcolo 2003 creando un'istanza di`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Passaggio 3: personalizzare le colonne della vista
Personalizza le colonne della vista per il diagramma di Gantt, la vista Risorse e la vista Assegnazione:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
Questi passaggi aggiungono colonne personalizzate alle rispettive visualizzazioni, migliorando le capacità di visualizzazione e analisi del file MS Project.
## Passaggio 4: salva il progetto
Infine, salva il progetto con le opzioni specificate:
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
Questo comando salva il progetto modificato con il formato Foglio di calcolo 2003 e le colonne di visualizzazione personalizzate.

## Conclusione
L'utilizzo di Aspose.Tasks per .NET, in particolare le opzioni di salvataggio di MS Project di Spreadsheet 2003, consente agli sviluppatori di gestire e personalizzare in modo efficiente i file di MS Project a livello di codice. Seguendo la guida dettagliata descritta in questo tutorial, puoi integrare perfettamente queste funzionalità nelle tue applicazioni .NET, migliorando produttività e flessibilità.

## Domande frequenti
### D: Aspose.Tasks per .NET può essere utilizzato sia in applicazioni Web che desktop?
R: Sì, Aspose.Tasks per .NET può essere perfettamente integrato sia in applicazioni web che desktop, fornendo funzionalità coerenti su tutte le piattaforme.
### D: È disponibile una versione di prova per Aspose.Tasks per .NET?
R: Sì, puoi accedere a una prova gratuita di Aspose.Tasks per .NET da[sito web](https://releases.aspose.com/), permettendoti di esplorarne le funzionalità prima di effettuare un acquisto.
### D: Esistono limitazioni alla personalizzazione delle colonne di visualizzazione utilizzando Aspose.Tasks per .NET?
R: Aspose.Tasks per .NET offre ampie opzioni di personalizzazione per le colonne di visualizzazione, con limitazioni minime. Tuttavia, personalizzazioni complesse potrebbero richiedere una conoscenza avanzata della libreria.
### D: Posso chiedere assistenza se riscontro problemi durante l'utilizzo di Aspose.Tasks per .NET?
 R: Assolutamente! È possibile trovare supporto e risorse completi sul forum Aspose.Tasks all'indirizzo[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15), dove esperti e membri della comunità sono disponibili per aiutarti a risolvere qualsiasi domanda o problema che potresti incontrare.
### D: Come posso ottenere una licenza temporanea per Aspose.Tasks per .NET?
 R: È possibile acquisire una licenza temporanea per Aspose.Tasks per .NET da[pagina di acquisto](https://purchase.aspose.com/temporary-license/), consentendoti di valutare tutte le funzionalità della libreria.