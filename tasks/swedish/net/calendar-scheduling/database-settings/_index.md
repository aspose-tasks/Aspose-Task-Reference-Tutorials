---
title: Databasinställningar i Aspose.Tasks
linktitle: Databasinställningar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du importerar projekt från en Primavera-databas med Aspose.Tasks för .NET. Få steg-för-steg-vägledning i denna omfattande handledning.
weight: 29
url: /sv/net/calendar-scheduling/database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databasinställningar i Aspose.Tasks

## Introduktion

Aspose.Tasks för .NET är ett kraftfullt bibliotek som låter utvecklare arbeta med Microsoft Project-filer i sina .NET-applikationer. I den här handledningen kommer vi att fokusera på att importera projekt från en Primavera-databas med Aspose.Tasks.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Visual Studio installerat på ditt system.
-  Aspose.Tasks för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
- Tillgång till en Primavera-databas, tillsammans med nödvändiga behörigheter.

## Importera namnområden

Först måste du importera de nödvändiga namnrymden till ditt C#-projekt. Dessa namnrymder ger tillgång till de klasser och metoder som behövs för att arbeta med Aspose.Tasks för .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Låt oss nu dela upp den medföljande exempelkoden i flera steg:

## Steg 1: Definiera anslutningssträng

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 I det här steget definierar vi anslutningssträngen för att ansluta till Primavera-databasen. Se till att du byter ut`DataDir` med katalogen där din databasfil finns.

## Steg 2: Skapa databasinställningar

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Här skapar vi en instans av`PrimaveraDbSettings` klass och skickar anslutningssträngen och projekt-ID som parametrar. Justera projekt-ID enligt dina krav.

## Steg 3: Ställ in leverantörens invarianta namn

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Ange leverantörens invarianta namn. I det här exemplet använder vi SQLite, men du kan ändra det baserat på din databasleverantör.

## Steg 4: Ladda projekt

```csharp
var project = new Project(settings);
```

 Skapa en ny`Project` objekt och skickar databasinställningarna som en parameter.

## Steg 5: Spara projekt

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Slutligen sparar du projektet på önskad plats med det angivna filformatet.

## Slutsats

I den här handledningen lärde vi oss hur man importerar projekt från en Primavera-databas med Aspose.Tasks för .NET. Genom att följa de medföljande stegen kan du sömlöst integrera projektimportfunktioner i dina .NET-applikationer.

## FAQ's

### F1: Kan jag importera projekt från olika databasleverantörer med Aspose.Tasks för .NET?

S1: Ja, du kan importera projekt från olika databasleverantörer genom att justera anslutningssträngen och leverantörens invarianta namn därefter.

### F2: Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?

 S2: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från[här](https://releases.aspose.com/).

### F3: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?

 S3: Du kan hitta dokumentationen[här](https://reference.aspose.com/tasks/net/).

### F4: Hur kan jag få support för Aspose.Tasks för .NET?

 S4: Du kan få stöd från Aspose.Tasks communityforum[här](https://forum.aspose.com/c/tasks/15).

### F5: Behöver jag en tillfällig licens för att använda Aspose.Tasks för .NET?

 S5: Om du vill utvärdera bibliotekets fulla funktionalitet kan du få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
