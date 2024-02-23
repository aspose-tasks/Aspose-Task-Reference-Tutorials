---
title: Samling av tillgänglighetsperioder i Aspose.Tasks
linktitle: Samling av tillgänglighetsperioder i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar tillgänglighetsperioder för resurser i Aspose.Tasks för .NET. Denna steg-för-steg handledning guidar dig genom att lägga till, uppdatera och ta bort tillgänglighetsperioder, vilket säkerställer effektiv projektresursplanering.
type: docs
weight: 18
url: /sv/net/advanced-features/availability-period-collection/
---
## Introduktion

I den här handledningen kommer vi att utforska hur man arbetar med tillgänglighetsperiodens insamling av en resurs i Aspose.Tasks för .NET. Att hantera tillgänglighetsperioder är avgörande för projektledning, vilket gör att vi kan definiera när resurser finns tillgängliga för uppgifter inom ett projekt.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse: Kännedom om C# och .NET framework.

## Importera namnområden

Först måste vi importera de nödvändiga namnrymden till vårt projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Låt oss dela upp exempelkoden i flera steg och förstå varje del:

## Steg 1: Initiera projektet och resursen

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Här laddar vi en projektfil och skaffar en specifik resurs genom dess ID.

## Steg 2: Rensa befintliga tillgänglighetsperioder

```csharp
resource.AvailabilityPeriods.Clear();
```

Vi rensar alla befintliga tillgänglighetsperioder som är kopplade till resursen.

## Steg 3: Lägg till tillgänglighetsperioder

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Vi itererar genom en samling tillgänglighetsperioder och lägger till dem i resursen.

## Steg 4: Infoga en ny tillgänglighetsperiod

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Vi skapar en ny tillgänglighetsperiod för år 2013 och infogar den i kollektionen.

## Steg 5: Visa tillgänglighetsperioder

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Vi skriver ut antalet och detaljerna för varje tillgänglighetsperiod som är kopplad till resursen.

## Steg 6: Kopiera tillgänglighetsperioder till en annan resurs

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Vi kopierar tillgänglighetsperioderna från en resurs till en annan.

## Steg 7: Uppdatera och ta bort tillgänglighetsperioder

```csharp
// Uppdatera tillgängliga enheter för en viss period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Ta bort en viss period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Vi uppdaterar de tillgängliga enheterna under en period och tar bort specifika perioder från samlingen.

## Slutsats

den här handledningen har vi lärt oss hur man arbetar med tillgänglighetsperiodsamlingar i Aspose.Tasks för .NET. Att hantera resurstillgänglighet är avgörande för effektiv projektplanering och genomförande.

## FAQ's

### F1: Kan jag lägga till anpassade fält i tillgänglighetsperioder?

S1: Nej, tillgänglighetsperioder i Aspose.Tasks för .NET stöder inte anpassade fält.

### F2: Är tillgänglighetsperioder kopplade till specifika uppgifter?

S2: Nej, tillgänglighetsperioder är kopplade till resurser och definierar när de är tillgängliga för uppgifter i allmänhet.

### F3: Kan jag importera tillgänglighetsperioder från externa källor?

S3: Ja, du kan importera tillgänglighetsperioder från olika datakällor med Aspose.Tasks för .NET API:er.

### F4: Hur hanterar jag överlappande tillgänglighetsperioder?

S4: Aspose.Tasks för .NET tillhandahåller inte inbyggda mekanismer för att hantera överlappande perioder. Du kan behöva implementera anpassad logik för att hantera sådana scenarier.

### F5: Finns det en gräns för antalet tillgänglighetsperioder en resurs kan ha?

S5: Det finns ingen fördefinierad gräns för antalet tillgänglighetsperioder en resurs kan ha, men prestandan kan försämras med ett stort antal perioder.