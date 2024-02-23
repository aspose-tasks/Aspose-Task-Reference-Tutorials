---
title: Arbeta med tillgänglighetsperioder i Aspose.Tasks
linktitle: Arbeta med tillgänglighetsperioder i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du effektivt hanterar resurstillgänglighetsperioder med Aspose.Tasks för .NET. Den här handledningen ger en steg-för-steg-guide för att arbeta med tillgänglighetsperioder i dina .NET-projekt.
type: docs
weight: 17
url: /sv/net/advanced-features/working-with-availability-periods/
---
## Introduktion

den här handledningen kommer vi att utforska hur man arbetar med tillgänglighetsperioder i Aspose.Tasks för .NET. Tillgänglighetsperioder är avgörande för att hantera resurser effektivt i projektledningsscenarier. Vi guidar dig genom processen steg för steg.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

1. Visual Studio: Installera Visual Studio eller någon annan föredragen IDE för .NET-utveckling.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#-programmering: Bekantskap med C#-programmeringsspråkets grunder kommer att vara till hjälp.

## Importera namnområden

Innan du dyker in i koden, se till att importera de nödvändiga namnrymden:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Låt oss dela upp exempelkoden i flera steg:

## Steg 1: Skapa en ny projektinstans

```csharp
var project = new Project();
```

Den här raden initierar en ny instans av klassen Project, som representerar ett projekt i Aspose.Tasks.

## Steg 2: Lägg till en resurs

```csharp
var resource = project.Resources.Add("Work Resource");
```

Här lägger vi till en ny resurs till projektet med namnet "Arbetsresurs".

## Steg 3: Definiera tillgänglighetsperioder

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Vi kallar`GetPeriods()` metod för att hämta en samling tillgänglighetsperioder.

## Steg 4: Lägg till tillgänglighetsperioder till resursen

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Vi itererar genom samlingen av tillgänglighetsperioder som erhölls i föregående steg och lägger till dem i resursen.

## Steg 5: Visa information om tillgänglighetsperiod

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Slutligen går vi igenom tillgänglighetsperioderna som är kopplade till resursen och skriver ut deras detaljer, inklusive startdatum, slutdatum och tillgängliga enheter.

## Slutsats

I den här handledningen lärde vi oss hur man arbetar med tillgänglighetsperioder i Aspose.Tasks för .NET. Genom att följa steg-för-steg-guiden kan du effektivt hantera resurstillgänglighet i dina projektledningsapplikationer.

## FAQ's

### F1: Kan jag använda Aspose.Tasks för .NET i kommersiella projekt?

 S1: Ja, Aspose.Tasks för .NET kan användas i kommersiella projekt. Du kan köpa en licens[här](https://purchase.aspose.com/buy).

### F2: Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?

 S2: Ja, du kan få en gratis testversion av Aspose.Tasks för .NET[här](https://releases.aspose.com/).

### F3: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?

 S3: Du kan hitta dokumentationen[här](https://reference.aspose.com/tasks/net/).

### F4: Hur kan jag få support för Aspose.Tasks för .NET?

 S4: Du kan få stöd från communityforumet.[här](https://forum.aspose.com/c/tasks/15).

### F5: Erbjuder ni tillfälliga licenser för Aspose.Tasks för .NET?

 A5: Ja, tillfälliga licenser är tillgängliga[här](https://purchase.aspose.com/temporary-license/).