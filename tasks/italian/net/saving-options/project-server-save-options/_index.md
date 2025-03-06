---
title: Server Salva opzioni MS Project per Aspose.Tasks
linktitle: Opzioni di salvataggio di Project Server per Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come salvare le opzioni di Microsoft Project per Aspose.Tasks utilizzando l'integrazione di Project Server. Migliora i flussi di lavoro di gestione dei progetti.
weight: 16
url: /it/net/saving-options/project-server-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Server Salva opzioni MS Project per Aspose.Tasks

## introduzione
In questo tutorial, approfondiremo il salvataggio delle opzioni di Microsoft Project per Aspose.Tasks utilizzando Project Server. Aspose.Tasks è una potente API .NET che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice. Sfruttando le funzionalità di Project Server, possiamo integrare perfettamente Aspose.Tasks nei nostri flussi di lavoro di gestione dei progetti. Questo tutorial ti guiderà attraverso il processo passo dopo passo.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  Aspose.Tasks per .NET: Installa Aspose.Tasks per .NET dal file[Link per scaricare](https://releases.aspose.com/tasks/net/).
   
2. Accesso a Project Server: avrai bisogno delle credenziali di accesso e dell'URL della tua istanza di Project Server. Se non ne hai uno, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
3. File di Microsoft Project: preparare il file di Microsoft Project (.mpp) che si desidera salvare utilizzando Aspose.Tasks.

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo progetto:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Passaggio 1: inizializza progetto e credenziali
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://progetto_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Assicurati di sostituire`"Your Document Directory"`, `URL`, `Domain`, `UserName` , E`Password` con i tuoi valori reali.
## Passaggio 2: creare Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Passaggio 3: definire le opzioni di salvataggio
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Aggiusta il`ProjectGuid`, `ProjectName`, `Timeout` , E`PollingInterval` in base alle vostre esigenze.
## Passaggio 4: salva il progetto sul server
```csharp
manager.CreateNewProject(project, options);
```
Ciò salverà il progetto in Project Server con le opzioni specificate.

## Conclusione
In questo tutorial, abbiamo imparato come salvare le opzioni di Microsoft Project per Aspose.Tasks utilizzando l'integrazione di Project Server. Seguendo questi passaggi, puoi incorporare perfettamente Aspose.Tasks nei flussi di lavoro di gestione dei progetti, migliorando l'efficienza e la produttività.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks con diverse versioni di Microsoft Project?
R: Sì, Aspose.Tasks supporta varie versioni di Microsoft Project, garantendo la compatibilità tra diversi ambienti.
### D: È disponibile una versione di prova per Aspose.Tasks?
 R: Sì, puoi ottenere una versione di prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### D: Aspose.Tasks supporta il multi-threading?
R: Sì, Aspose.Tasks è progettato per essere thread-safe, consentendo l'accesso simultaneo ai dati del progetto.
### D: Posso personalizzare le opzioni di salvataggio quando utilizzo l'integrazione di Project Server?
R: Sì, puoi personalizzare le opzioni di salvataggio come nome del progetto, timeout e intervallo di polling in base alle tue esigenze.
### D: Dove posso trovare supporto per Aspose.Tasks?
 R: Puoi trovare supporto e assistenza su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
