---
title: Estrai le informazioni sul progetto MS in Aspose.Tasks
linktitle: Estrazione delle informazioni sul progetto in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come estrarre le informazioni di MS Project senza sforzo utilizzando Aspose.Tasks per .NET. Immergiti nel nostro tutorial completo.
type: docs
weight: 20
url: /it/net/project-management-integration/project-information/
---
## introduzione
Stai cercando di estrarre in modo efficiente informazioni dai file Microsoft Project utilizzando Aspose.Tasks per .NET? In questo tutorial ti guideremo attraverso il processo passo dopo passo. Ma prima di immergerci nei dettagli dell'implementazione, assicuriamoci innanzitutto di avere tutto ciò di cui hai bisogno.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
### 1. Aspose.Tasks per .NET
 Assicurati di aver installato la libreria Aspose.Tasks per .NET. Se non lo hai già fatto, puoi scaricarlo dal file[Aspose.Tasks per il sito Web .NET](https://releases.aspose.com/tasks/net/).
### 2. Credenziali per SharePoint
Avrai bisogno delle credenziali per accedere a SharePoint in cui sono archiviati i file di MS Project. Assicurati di avere le seguenti informazioni:
- Indirizzo del dominio di SharePoint
- Nome utente
- Parola d'ordine
## Importazione di spazi dei nomi
Una volta risolti i prerequisiti, è il momento di importare gli spazi dei nomi necessari nel tuo progetto.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Ora suddividiamo il processo di estrazione delle informazioni di MS Project in più passaggi.
## Passaggio 1: fornire le credenziali
Innanzitutto, devi fornire le credenziali di SharePoint per accedere a Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Passaggio 2: inizializzare Project Server Manager
 Successivamente, inizializza a`ProjectServerManager` istanza con le credenziali fornite.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Passaggio 3: recupera l'elenco dei progetti
Ora puoi recuperare l'elenco dei progetti da Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Passaggio 4: stampare le informazioni sul progetto
Infine, scorri l'elenco dei progetti e stampa le relative informazioni.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Conclusione
Congratulazioni! Hai imparato con successo come estrarre le informazioni di MS Project utilizzando Aspose.Tasks per .NET. Con questa conoscenza, ora puoi integrare questa funzionalità nelle tue applicazioni .NET senza problemi.
## Domande frequenti
### Q1: posso utilizzare Aspose.Tasks per .NET con qualsiasi versione di Microsoft Project?
R: Sì, Aspose.Tasks per .NET supporta varie versioni di Microsoft Project, tra cui 2003, 2007, 2010, 2013, 2016 e 2019.
### Q2: Aspose.Tasks per .NET è compatibile con entrambe le piattaforme Windows e Linux?
R: Sì, Aspose.Tasks per .NET è compatibile con entrambe le piattaforme Windows e Linux, rendendolo versatile per diversi ambienti di sviluppo.
### Q3: posso estrarre le dipendenze delle attività utilizzando Aspose.Tasks per .NET?
R: Assolutamente! Aspose.Tasks per .NET fornisce funzionalità robuste per estrarre non solo le informazioni di base sul progetto ma anche le dipendenze delle attività e altri dettagli complessi.
### Q4: Aspose.Tasks per .NET offre supporto tecnico?
 R: Sì, puoi ottenere supporto tecnico per Aspose.Tasks per .NET tramite[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), dove puoi porre domande e chiedere assistenza agli esperti.
### Q5: Posso provare Aspose.Tasks per .NET prima di acquistarlo?
 R: Certamente! Puoi avvalerti di una prova gratuita di Aspose.Tasks per .NET da[pagina delle uscite](https://releases.aspose.com/), permettendoti di esplorare le sue funzionalità prima di prendere una decisione di acquisto.