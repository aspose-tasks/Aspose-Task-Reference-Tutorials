---
title: Gestione delle credenziali di MS Project Server in Aspose.Tasks
linktitle: Gestione delle credenziali di Project Server in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le credenziali di MS Project Server senza problemi con Aspose.Tasks per .NET. Migliorare l’efficienza della gestione dei progetti.
type: docs
weight: 22
url: /it/net/project-management-integration/project-server-credentials/
---
## introduzione
Nell’ambito della gestione del progetto, un coordinamento efficace e una comunicazione continua sono fondamentali per il successo dell’esecuzione del progetto. Aspose.Tasks per .NET fornisce una soluzione completa per la gestione delle credenziali di Microsoft Project Server, consentendo agli utenti di accedere e manipolare in modo sicuro i dati del progetto. Questo tutorial approfondisce il processo di gestione delle credenziali di MS Project Server utilizzando Aspose.Tasks per .NET, guidando gli utenti attraverso ogni passaggio per garantire un'esperienza fluida.
## Prerequisiti
Prima di intraprendere il viaggio di gestione delle credenziali di MS Project Server con Aspose.Tasks per .NET, assicurarsi che siano soddisfatti i seguenti prerequisiti:
### 1. Installazione di Aspose.Tasks per .NET
 Per iniziare, scaricare e installare Aspose.Tasks per .NET dal pacchetto fornito[Link per scaricare](https://releases.aspose.com/tasks/net/), Segui le istruzioni di installazione per integrare perfettamente la libreria nel tuo ambiente .NET.
### 2. Credenziali di accesso
Raccogli le credenziali necessarie per accedere a MS Project Server. Ciò include l'indirizzo del dominio, il nome utente e la password di SharePoint associati a Project Server.

## Importa spazi dei nomi
Nel tuo progetto .NET, importa gli spazi dei nomi richiesti per utilizzare in modo efficiente le funzionalità fornite da Aspose.Tasks per .NET.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Passaggio 1: definire il percorso della directory dei documenti
```csharp
String DataDir = "Your Document Directory";
```
## Passaggio 2: impostare l'indirizzo del dominio, il nome utente e la password di SharePoint
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Passaggio 3: creare le credenziali di Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Passaggio 4: caricare il file di progetto
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Passaggio 5: inizializzare Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Passaggio 6: crea un nuovo progetto
```csharp
manager.CreateNewProject(newProject);
```
## Passaggio 7: recupera l'elenco dei progetti
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Passaggio 8: scorrere l'elenco dei progetti
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Conclusione
Gestire in modo efficace le credenziali di MS Project Server è fondamentale per una gestione semplificata dei progetti. Aspose.Tasks per .NET semplifica questo processo fornendo un robusto insieme di funzionalità. Seguendo la guida passo passo delineata in questo tutorial, gli utenti possono integrare perfettamente Aspose.Tasks per .NET nei loro progetti, garantendo l'accesso sicuro e la manipolazione dei dati del progetto.
## Domande frequenti
### D: Aspose.Tasks per .NET è compatibile con tutte le versioni di Microsoft Project Server?
R: Aspose.Tasks per .NET è progettato per essere compatibile con varie versioni di Microsoft Project Server, garantendo versatilità e flessibilità agli utenti.
### D: Posso integrare Aspose.Tasks per .NET nel mio progetto .NET esistente?
R: Sì, Aspose.Tasks per .NET può essere perfettamente integrato nei progetti .NET esistenti, facilitando funzionalità di gestione efficiente dei progetti.
### D: Aspose.Tasks per .NET fornisce supporto per l'accesso alle risorse del progetto?
R: Assolutamente, Aspose.Tasks per .NET offre un supporto completo per l'accesso e la manipolazione delle risorse del progetto, migliorando l'efficienza della gestione del progetto.
### D: Sono disponibili opzioni di licenza per Aspose.Tasks per .NET?
R: Sì, Aspose.Tasks per .NET offre opzioni di licenza flessibili, comprese licenze temporanee per scopi di prova e licenze complete per uso commerciale.
### D: Dove posso cercare assistenza o supporto per Aspose.Tasks per .NET?
 R: Per qualsiasi domanda o assistenza relativa ad Aspose.Tasks per .NET, è possibile visitare il forum di supporto all'indirizzo[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Codice sorgente completo