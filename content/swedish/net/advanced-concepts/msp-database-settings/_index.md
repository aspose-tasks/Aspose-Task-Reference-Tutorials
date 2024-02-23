---
title: Inställningar för Microsoft Project Database i Aspose.Tasks
linktitle: Inställningar för Microsoft Project Database i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du konfigurerar Microsoft Project-databasinställningar med Aspose.Tasks för sömlös integrering i .NET-applikationer.
type: docs
weight: 19
url: /sv/net/advanced-concepts/msp-database-settings/
---
## Introduktion

Om du arbetar med Microsoft Project-databaser i dina .NET-applikationer med Aspose.Tasks, måste du konfigurera de nödvändiga inställningarna för att importera projektdata sömlöst. Denna handledning guidar dig genom processen steg för steg.

## Förutsättningar

Innan du börjar, se till att du har följande:

1.  Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks-biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Tillgång till en Microsoft Project-databas: Du bör ha tillgång till en Microsoft Project-databas att importera data från.

## Importera namnområden

Se först till att du importerar de nödvändiga namnrymden till ditt projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Steg 1: Skapa anslutningssträng

Konstruera anslutningssträngen till din Microsoft Project-databas. Här är ett exempel:

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

Se till att ersätta platshållarvärdena med dina faktiska databasuppgifter.

## Steg 2: Konfigurera MspDbSettings

 Skapa en instans av`MspDbSettings` och ange anslutningssträngen tillsammans med projektets GUID:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Steg 3: Ladda projektdata

 Instantiera en`Project` objekt med de konfigurerade inställningarna:

```csharp
var project = new Project(settings);
```

## Steg 4: Spara projektdata

Spara inlästa projektdata till en fil:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Slutsats

I den här handledningen har du lärt dig hur du konfigurerar inställningar för åtkomst till Microsoft Project-databaser med Aspose.Tasks för .NET. Genom att följa dessa steg kan du sömlöst importera projektdata till dina applikationer, vilket underlättar effektiv projektledning.

## FAQ's

### F1: Kan jag använda Aspose.Tasks med olika versioner av Microsoft Project-databaser?

S1: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project-databaser, vilket möjliggör flexibilitet i integrationen.

### F2: Hur kan jag felsöka anslutningsproblem med databasen?

S2: Se till att din anslutningssträng är korrekt konfigurerad med lämpliga referenser och databasdetaljer. Du kan också hänvisa till dokumentationen eller söka stöd från[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### F3: Finns det en testversion tillgänglig för Aspose.Tasks?

 S3: Ja, du kan få tillgång till en gratis testversion från[här](https://releases.aspose.com/).

### F4: Kan jag anpassa schemat för databasinteraktion?

 S4: Ja, du kan ange schemat för`MspDbSettings` objekt enligt din databasstruktur.

### F5: Var kan jag hitta mer detaljerad dokumentation om hur jag använder Aspose.Tasks?

 S5: Du kan utforska den omfattande dokumentationen[här](https://reference.aspose.com/tasks/net/) för detaljerade insikter i Aspose.Tasks-funktioner.