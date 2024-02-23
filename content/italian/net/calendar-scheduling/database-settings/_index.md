---
title: Impostazioni del database in Aspose.Tasks
linktitle: Impostazioni del database in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come importare progetti da un database Primavera utilizzando Aspose.Tasks per .NET. Ottieni una guida passo passo in questo tutorial completo.
type: docs
weight: 29
url: /it/net/calendar-scheduling/database-settings/
---
## introduzione

Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di lavorare con file Microsoft Project nelle loro applicazioni .NET. In questo tutorial, ci concentreremo sull'importazione di progetti da un database Primavera utilizzando Aspose.Tasks.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato nel sistema.
-  Aspose.Tasks per la libreria .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
- Accesso a un database Primavera, insieme alle autorizzazioni necessarie.

## Importa spazi dei nomi

Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi necessari per lavorare con Aspose.Tasks per .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Ora suddividiamo il codice di esempio fornito in più passaggi:

## Passaggio 1: definire la stringa di connessione

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 In questo passaggio definiamo la stringa di connessione per connettersi al database Primavera. Assicurati di sostituire`DataDir` con la directory in cui si trova il file del database.

## Passaggio 2: crea le impostazioni del database

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Qui creiamo un'istanza di`PrimaveraDbSettings` classe, passando la stringa di connessione e l'ID progetto come parametri. Modifica l'ID progetto in base alle tue esigenze.

## Passaggio 3: impostare il nome invariante del provider

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Specificare il nome invariante del provider. In questo esempio utilizziamo SQLite, ma puoi modificarlo in base al provider del database.

## Passaggio 4: caricare il progetto

```csharp
var project = new Project(settings);
```

 Creane uno nuovo`Project` oggetto, passando le impostazioni del database come parametro.

## Passaggio 5: salva il progetto

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Infine, salva il progetto nella posizione desiderata con il formato file specificato.

## Conclusione

In questo tutorial, abbiamo imparato come importare progetti da un database Primavera utilizzando Aspose.Tasks per .NET. Seguendo i passaggi forniti, puoi integrare perfettamente la funzionalità di importazione del progetto nelle tue applicazioni .NET.

## Domande frequenti

### Q1: Posso importare progetti da diversi provider di database utilizzando Aspose.Tasks per .NET?

R1: Sì, è possibile importare progetti da vari provider di database modificando di conseguenza la stringa di connessione e il nome invariante del provider.

### Q2: È disponibile una prova gratuita per Aspose.Tasks per .NET?

 A2: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione per Aspose.Tasks per .NET?

 A3: È possibile trovare la documentazione[Qui](https://reference.aspose.com/tasks/net/).

### Q4: Come posso ottenere supporto per Aspose.Tasks per .NET?

 A4: è possibile ottenere supporto dal forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).

### Q5: ho bisogno di una licenza temporanea per utilizzare Aspose.Tasks per .NET?

 R5: Se desideri valutare la piena funzionalità della libreria, puoi ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).