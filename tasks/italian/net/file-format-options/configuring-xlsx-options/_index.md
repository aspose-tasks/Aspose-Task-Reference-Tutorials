---
title: Configurare le opzioni XLSX di MS Project in Aspose.Tasks per .NET
linktitle: Configurazione delle opzioni XLSX in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come configurare le opzioni di MS Project XLSX in Aspose.Tasks per .NET. Personalizza colonne, codifica e altro ancora senza sforzo.
type: docs
weight: 11
url: /it/net/file-format-options/configuring-xlsx-options/
---
## introduzione
Microsoft Project (MS Project) è un potente strumento per la gestione dei progetti e Aspose.Tasks per .NET fornisce un'integrazione perfetta per lavorare con i file MS Project a livello di codice. In questo tutorial, esamineremo il processo di configurazione delle opzioni XLSX di MS Project utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
### 1. Aspose.Tasks per .NET installato
 Assicurati di avere Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarlo da[Aspose.Tasks per la pagina di download di .NET](https://releases.aspose.com/tasks/net/).
### 2. Conoscenza di base di C# e .NET Framework
Per seguire questo tutorial è necessaria la familiarità con il linguaggio di programmazione C# e il framework .NET.
### 3. File di progetto Microsoft
Tieni pronto un file Microsoft Project (MPP) che desideri configurare e salvare come file XLSX.

## Importazione di spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Passaggio 1: caricare il progetto
```csharp
var project = new Project("YourProjectFile.mpp");
```
Carica il file Microsoft Project che desideri configurare.
## Passaggio 2: definire XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Crea un'istanza di`XlsxOptions` per configurare le impostazioni per il salvataggio come XLSX.
## Passaggio 3: aggiungi colonne del diagramma di Gantt
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Aggiungi le colonne del diagramma di Gantt desiderate alle opzioni.
## Passaggio 4: aggiungere colonne di visualizzazione delle risorse
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Includi le colonne desiderate per la visualizzazione delle risorse nelle opzioni.
## Passaggio 5: aggiungi le colonne della vista assegnazione
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Aggiungi le colonne desiderate per la visualizzazione dei compiti nelle opzioni.
## Passaggio 6: imposta la codifica
```csharp
options.Encoding = Encoding.Unicode;
```
Imposta la codifica per il file di output.
## Passaggio 7: salva il progetto come XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Salva il progetto con le opzioni configurate come file XLSX.

## Conclusione
In questo tutorial, abbiamo imparato come configurare le opzioni XLSX di MS Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi personalizzare il formato di output in base alle tue esigenze, migliorando la flessibilità e l'usabilità del flusso di lavoro di gestione del progetto.
## Domande frequenti

### D: Posso configurare separatamente colonne diverse per il diagramma di Gantt, la visualizzazione risorse e la visualizzazione assegnazioni?

R: Sì, puoi personalizzare le colonne in modo indipendente per ciascuna vista utilizzando Aspose.Tasks per .NET.

### D: È disponibile una versione di prova prima di acquistare Aspose.Tasks per .NET?

 R: Sì, puoi scaricare una versione di prova gratuita da[Aspose.Tasks per la pagina delle versioni .NET](https://releases.aspose.com/).

### D: Come posso ottenere supporto se riscontro problemi o ho domande durante l'implementazione?

 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per l'assistenza della comunità e del team di supporto Aspose.

### D: Posso generare file XLSX con Aspose.Tasks per .NET su piattaforme non Windows?

R: Aspose.Tasks per .NET è progettato principalmente per piattaforme Windows, ma puoi esplorare le opzioni di compatibilità per altre piattaforme.

### D: Sono disponibili opzioni di licenza temporanea a scopo di test?

 R: Sì, puoi ottenere una licenza temporanea da[Pagina della licenza temporanea Aspose.Tasks](https://purchase.aspose.com/temporary-license/).