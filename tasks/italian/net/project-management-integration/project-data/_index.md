---
title: Padroneggiare i dati del progetto con Aspose.Tasks
linktitle: Lavorare con i dati del progetto in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come manipolare i dati di Microsoft Project utilizzando Aspose.Tasks in .NET. Crea attività, aggiungi risorse e salva progetti con facilità.
weight: 16
url: /it/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare i dati del progetto con Aspose.Tasks

## introduzione
In questo tutorial esploreremo come lavorare con i dati di Microsoft Project utilizzando la libreria Aspose.Tasks per .NET. Aspose.Tasks fornisce potenti funzionalità per manipolare i file di progetto, tra cui la creazione di attività, l'aggiunta di risorse, l'impostazione di proprietà e il salvataggio di progetti in vari formati.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Installazione della libreria Aspose.Tasks: scaricare e installare la libreria Aspose.Tasks da[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo .NET configurato.
3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.

## Importa spazi dei nomi
Prima di lavorare con Aspose.Tasks, importa gli spazi dei nomi necessari nel tuo progetto:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Passaggio 1: inizializzare l'oggetto del progetto
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Questa riga inizializza una nuova istanza di`Project` classe, che rappresenta un file di Microsoft Project.
## Passaggio 2: imposta le proprietà del progetto
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Queste righe mostrano come impostare le proprietà del progetto come il formato del lavoro e la modalità di creazione dell'attività.
## Passaggio 3: aggiunta di attività
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Qui, una nuova attività denominata "Attività 1" viene aggiunta all'attività root del progetto.
## Passaggio 4: impostazione delle proprietà dell'attività
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Queste righe impostano la data di inizio, la durata e la data di fine per "Attività 1".
## Passaggio 5: aggiunta di risorse
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Questa parte illustra come aggiungere una risorsa di lavoro al progetto.
## Passaggio 6: assegnazione delle risorse alle attività
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Queste righe mostrano come assegnare la risorsa lavorativa aggiunta in precedenza all'"Attività 1" con date di inizio, lavoro e fine specifiche.
## Passaggio 7: salvataggio del progetto
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Infine, il progetto viene salvato nel formato file XML di Microsoft Project.

## Conclusione
In questo tutorial abbiamo imparato come lavorare con i dati di Microsoft Project utilizzando la libreria Aspose.Tasks in .NET. Seguendo la guida passo passo, puoi manipolare file di progetto, aggiungere attività, risorse, assegnare risorse alle attività e salvare progetti in vari formati.
## Domande frequenti
### D: Aspose.Tasks può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks fornisce un supporto completo per strutture di progetti complessi, consentendo di gestire attività, risorse e assegnazioni in modo efficiente.
### D: Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?
R: Aspose.Tasks supporta un'ampia gamma di versioni di Microsoft Project, garantendo la compatibilità tra diversi ambienti.
### D: Posso integrare Aspose.Tasks con altre librerie .NET?
R: Assolutamente, Aspose.Tasks si integra perfettamente con altre librerie .NET, fornendo flessibilità nei tuoi progetti di sviluppo.
### D: Aspose.Tasks offre supporto per gli algoritmi di pianificazione del progetto?
R: Sì, Aspose.Tasks include algoritmi di pianificazione avanzati per aiutarti a ottimizzare le tempistiche del progetto e l'utilizzo delle risorse.
### D: Esiste un forum della community per gli utenti di Aspose.Tasks?
 R: Sì, puoi trovare risorse utili e interagire con altri utenti Aspose.Tasks su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
