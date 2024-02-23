---
title: Impostazioni per il database di Microsoft Project in Aspose.Tasks
linktitle: Impostazioni per il database di Microsoft Project in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come configurare le impostazioni del database di Microsoft Project utilizzando Aspose.Tasks per una perfetta integrazione nelle applicazioni .NET.
type: docs
weight: 19
url: /it/net/advanced-concepts/msp-database-settings/
---
## introduzione

Se lavori con i database di Microsoft Project nelle tue applicazioni .NET utilizzando Aspose.Tasks, dovrai configurare le impostazioni necessarie per importare i dati del progetto senza problemi. Questo tutorial ti guiderà attraverso il processo passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Tasks per .NET: scarica e installa la libreria Aspose.Tasks da[Qui](https://releases.aspose.com/tasks/net/).
2. Accesso a un database di Microsoft Project: dovresti avere accesso a un database di Microsoft Project da cui importare i dati.

## Importa spazi dei nomi

Innanzitutto, assicurati di importare gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Passaggio 1: creare una stringa di connessione

Costruisci la stringa di connessione al tuo database Microsoft Project. Ecco un esempio:

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

Assicurati di sostituire i valori segnaposto con le credenziali effettive del database.

## Passaggio 2: configurare MspDbSettings

 Crea un'istanza di`MspDbSettings` e specificare la stringa di connessione insieme al GUID del progetto:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Passaggio 3: caricare i dati del progetto

 Istanziare a`Project` oggetto utilizzando le impostazioni configurate:

```csharp
var project = new Project(settings);
```

## Passaggio 4: salvare i dati del progetto

Salvare i dati del progetto caricati in un file:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Conclusione

In questo tutorial hai imparato come configurare le impostazioni per l'accesso ai database di Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi importare facilmente i dati del progetto nelle tue applicazioni, facilitando una gestione efficiente del progetto.

## Domande frequenti

### Q1: posso utilizzare Aspose.Tasks con diverse versioni dei database di Microsoft Project?

A1: Sì, Aspose.Tasks supporta varie versioni dei database di Microsoft Project, consentendo flessibilità nell'integrazione.

### Q2: Come posso risolvere i problemi di connessione con il database?

A2: assicurarsi che la stringa di connessione sia configurata correttamente con le credenziali e i dettagli del database appropriati. È inoltre possibile fare riferimento alla documentazione o chiedere supporto al[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: È disponibile una versione di prova per Aspose.Tasks?

 R3: Sì, puoi accedere a una versione di prova gratuita da[Qui](https://releases.aspose.com/).

### Q4: posso personalizzare lo schema per l'interazione del database?

 A4: Sì, è possibile specificare lo schema per il file`MspDbSettings` oggetto in base alla struttura del database.

### Q5: dove posso trovare documentazione più dettagliata sull'utilizzo di Aspose.Tasks?

 A5: È possibile esplorare la documentazione completa[Qui](https://reference.aspose.com/tasks/net/) per approfondimenti dettagliati sulle funzionalità di Aspose.Tasks.