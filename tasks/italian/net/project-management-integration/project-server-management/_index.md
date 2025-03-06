---
title: Gestione di MS Project Server con Aspose.Tasks
linktitle: Gestione di Project Server con Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Sblocca la gestione fluida di MS Project Server con Aspose.Tasks per .NET. Automatizza le attività del progetto senza sforzo.
type: docs
weight: 23
url: /it/net/project-management-integration/project-server-management/
---
## introduzione
In questo tutorial, approfondiremo la gestione di MS Project Server utilizzando Aspose.Tasks per .NET. Aspose.Tasks è una potente libreria che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice, consentendo una perfetta integrazione e manipolazione dei dati di progetto.
## Prerequisiti
Prima di immergerci nella gestione di MS Project Server con Aspose.Tasks, assicurati di avere i seguenti prerequisiti impostati:
1. Microsoft Project Server: devi accedere a un'istanza di Microsoft Project Server in cui disponi di privilegi amministrativi o almeno autorizzazioni per creare e gestire progetti.
2.  Aspose.Tasks per .NET Library: assicurati di aver scaricato e installato la libreria Aspose.Tasks per .NET. Puoi scaricarlo da[sito web](https://releases.aspose.com/tasks/net/).
3. Credenziali: ottieni le credenziali necessarie per autenticarti con la tua istanza di MS Project Server. Questo in genere include un nome utente e una password.
## Importa spazi dei nomi
Prima di iniziare, assicurati di aver importato gli spazi dei nomi richiesti nel codice C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Passaggio 1: impostare le credenziali di autenticazione
Innanzitutto, devi impostare le credenziali di autenticazione per connetterti alla tua istanza di MS Project Server. Ciò include l'indirizzo del dominio, il nome utente e la password.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Passaggio 2: caricare il progetto
Successivamente, carica il file MS Project che desideri gestire utilizzando Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Passaggio 3: creare Project Server Manager
 Istanziare a`ProjectServerManager` oggetto utilizzando le credenziali precedentemente definite.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Passaggio 4: definire le opzioni di salvataggio
Definisci eventuali opzioni di salvataggio specifiche per il tuo progetto. Ad esempio, è possibile impostare un timeout per l'operazione.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Passaggio 5: crea o aggiorna il progetto
Infine, crea o aggiorna il progetto su MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Congratulazioni! Hai gestito con successo MS Project Server utilizzando Aspose.Tasks per .NET.

## Conclusione
In questo tutorial, abbiamo esplorato come gestire MS Project Server a livello di codice utilizzando Aspose.Tasks per .NET. Con i passaggi forniti, puoi integrare perfettamente Aspose.Tasks nelle tue applicazioni .NET per automatizzare le attività di gestione dei progetti su MS Project Server.
## Domande frequenti
### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project Server?
R: Aspose.Tasks supporta l'integrazione con varie versioni di Microsoft Project Server, garantendo la compatibilità tra diversi ambienti.
### D: Posso eseguire operazioni di massa su progetti utilizzando Aspose.Tasks?
R: Sì, Aspose.Tasks ti consente di eseguire operazioni di massa come la creazione, l'aggiornamento e l'eliminazione di progetti su MS Project Server.
### D: Aspose.Tasks fornisce supporto per la pianificazione dei progetti e la gestione delle risorse?
R: Assolutamente, Aspose.Tasks offre supporto completo per la pianificazione dei progetti, l'allocazione delle risorse e le funzionalità di gestione delle attività.
### D: È possibile automatizzare le attività di reporting con Aspose.Tasks?
R: Sì, Aspose.Tasks ti consente di automatizzare la generazione di report personalizzati basati sui dati del progetto, facilitando il monitoraggio e l'analisi efficienti del progetto.
### D: Posso provare Aspose.Tasks prima di acquistarlo?
 R: Sì, puoi esplorare le funzionalità di Aspose.Tasks accedendo a una prova gratuita da[sito web](https://purchase.aspose.com/temporary-license/).