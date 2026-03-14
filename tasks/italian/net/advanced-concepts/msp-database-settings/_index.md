---
date: 2026-03-14
description: Scopri come specificare lo schema del database per un database Microsoft
  Project utilizzando Aspose.Tasks e come importare i dati del progetto nelle applicazioni
  .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Specificare lo schema del database per il DB Progetto con Aspose.Tasks
url: /it/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Impostazioni per il Database Microsoft Project in Aspose.Tasks

## Introduzione

Se lavori con i database Microsoft Project nelle tue applicazioni .NET utilizzando Aspose.Tasks, dovrai **specificare lo schema del database** e configurare le impostazioni necessarie per **importare il progetto** in modo fluido. Questo tutorial ti guiderà passo passo, mostrandoti **come configurare i dettagli di connessione**, **creare la stringa di connessione .NET** e infine **salvare il progetto come MPP**.

## Risposte rapide
- **Qual è l'obiettivo principale?** Specificare lo schema del database e importare un database Project in un'app .NET.  
- **Quale libreria è necessaria?** Aspose.Tasks per .NET.  
- **Come mi connetto a Project Server?** Creando una corretta stringa di connessione SQL e utilizzando `MspDbSettings`.  
- **Quale formato di file viene prodotto?** Un file MPP salvato con `SaveFileFormat.Mpp`.  
- **Posso modificare il nome dello schema?** Sì, imposta la proprietà `Schema` su `MspDbSettings`.

## Come specificare lo schema del database per Project DB

Comprendere perché potresti dover **specificare lo schema del database** è fondamentale. In molti ambienti aziendali il database di Project Server risiede sotto uno schema personalizzato (ad es., `dbo`, `psdata`). Impostando esplicitamente lo schema, garantisci che Aspose.Tasks interroghi le tabelle corrette, evitando errori di runtime e assicurando un'importazione dati accurata.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Tasks per .NET: Scarica e installa la libreria Aspose.Tasks da [qui](https://releases.aspose.com/tasks/net/).  
2. Accesso a un Database Microsoft Project: Devi avere accesso a un database Microsoft Project da cui importare i dati.  

## Importare gli spazi dei nomi

Assicurati di importare gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Passo 1: Creare la stringa di connessione

Costruisci la stringa di connessione al tuo database Microsoft Project. Qui è dove **crei la stringa di connessione .NET** e definisci anche come **connetterti a Project Server**.

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

> **Consiglio:** Verifica attentamente i valori `DataSource` e `InitialCatalog`; devono corrispondere all'indirizzo del tuo server e al nome del database pubblicato.

## Passo 2: Configurare MspDbSettings

Crea un'istanza di `MspDbSettings`, passa la stringa di connessione e **specifica lo schema del database** impostando la proprietà `Schema`. Questo indica ad Aspose.Tasks quale schema interrogare.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Qui forniamo anche il GUID del progetto che identifica il progetto specifico da caricare.

## Passo 3: Caricare i dati del progetto

Istanzia un oggetto `Project` utilizzando le impostazioni configurate. Questo passaggio esegue effettivamente **l'importazione del progetto** dal database in un oggetto .NET.

```csharp
var project = new Project(settings);
```

## Passo 4: Salvare i dati del progetto

Infine, persisti il progetto caricato in un file MPP sul disco. Questo dimostra **come salvare il progetto come MPP** usando l'API di Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Dopo aver eseguito il codice, troverai il file `ImportProjectDataFromDatabase_out.mpp` nella directory di output, pronto per essere aperto in Microsoft Project.

## Conclusione

In questo tutorial hai imparato a **specificare lo schema del database** per un database Microsoft Project, a **configurare la connessione**, a **importare il progetto** e a **salvare il progetto come MPP** utilizzando Aspose.Tasks per .NET. Questi passaggi consentono un'integrazione fluida dei dati di Project Server nelle tue applicazioni personalizzate, aiutandoti a costruire soluzioni di gestione progetti robuste.

## Domande frequenti

### Q1: Posso usare Aspose.Tasks con versioni diverse di database Microsoft Project?
A1: Sì, Aspose.Tasks supporta varie versioni di database Microsoft Project, offrendo flessibilità nell'integrazione.

### Q2: Come posso risolvere i problemi di connessione al database?
A2: Assicurati che la stringa di connessione sia configurata correttamente con le credenziali e i dettagli del database appropriati. Puoi anche consultare la documentazione o richiedere supporto sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: È disponibile una versione di prova di Aspose.Tasks?
A3: Sì, puoi accedere a una versione di prova gratuita da [qui](https://releases.aspose.com/).

### Q4: Posso personalizzare lo schema per l'interazione con il database?
A4: Sì, puoi specificare lo schema per l'oggetto `MspDbSettings` in base alla struttura del tuo database.

### Q5: Dove posso trovare una documentazione più dettagliata sull'uso di Aspose.Tasks?
A5: Puoi esplorare la documentazione completa [qui](https://reference.aspose.com/tasks/net/) per approfondimenti dettagliati sulle funzionalità di Aspose.Tasks.

**D: Questo approccio funziona con i database Azure SQL?**  
R: Assolutamente. Basta adeguare il `DataSource` al nome del tuo server Azure e assicurarsi che le impostazioni TLS/SSL siano abilitate.

**D: Come gestisco grandi database Project senza timeout?**  
R: Incrementa il valore `ConnectTimeout` nella stringa di connessione e considera di caricare i progetti in batch, se necessario.

---

**Ultimo aggiornamento:** 2026-03-14  
**Testato con:** Aspose.Tasks 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}