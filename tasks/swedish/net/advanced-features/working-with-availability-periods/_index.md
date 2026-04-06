---
date: 2026-04-06
description: Lär dig hur du lägger till en resurs i projektet och ställer in resursens
  tillgänglighetsperioder med Aspose.Tasks för .NET. Steg‑för‑steg‑guide för att hantera
  resurskalendrar.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Arbeta med tillgänglighetsperioder i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Lägg till resurs till projektet och ange tillgänglighet i Aspose.Tasks
url: /sv/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till resurs i projekt och ange tillgänglighet i Aspose.Tasks

## Introduktion

I den här handledningen kommer du att lära dig **hur man lägger till resurs i projekt** och sedan definiera dess tillgänglighetsperioder med hjälp av Aspose.Tasks .NET-biblioteket. Att hantera resurskalendrar är avgörande för realistiska projektscheman, och stegen nedan guidar dig genom hela processen — från att skapa en projektinstans till att skriva ut detaljerna för varje period.

## Snabba svar
- **Vad är huvudmålet?** Att lägga till en resurs i ett projekt och konfigurera dess tillgänglighetsperioder.  
- **Vilket bibliotek krävs?** Aspose.Tasks för .NET.  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs.  
- **Stödda .NET-versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementeringstid?** Vanligtvis under 15 minuter för grundläggande scenarier.

## Vad är “add resource to project”?

Att lägga till en resurs i ett projekt skapar en platshållare för en person, utrustning eller material som kan tilldelas uppgifter. När resursen finns kan du **ange resursens tillgänglighet**, definiera dess arbetskalender och låta schemaläggaren respektera dessa begränsningar.

## Varför konfigurera arbetsschema och tillgänglighetsperioder?

- **Noggrann planering:** Uppgifter schemaläggs endast när resursen faktiskt är ledig.  
- **Kostnadskontroll:** Tillgänglighetsenheter speglar deltidsinsats, vilket hjälper dig att korrekt beräkna arbetskostnader.  
- **Resursutjämning:** Motorn kan automatiskt jämna ut överallokeringar när den känner till varje resurs kalender.

## Förutsättningar

1. Visual Studio (eller någon .NET‑kompatibel IDE).  
2. Aspose.Tasks för .NET – ladda ner från [här](https://releases.aspose.com/tasks/net/).  
3. Grundläggande C#-kunskaper.

## Importera namnrymder

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Hur lägger man till resurs i projekt?

### Steg 1: Skapa en ny `Project`-instans

```csharp
var project = new Project();
```

Detta objekt representerar hela projektfilen i minnet.

### Steg 2: Lägg till en resurs i projektet

```csharp
var resource = project.Resources.Add("Work Resource");
```

Anropet skapar en **resource** med namnet *Work Resource* som du senare kan koppla till uppgifter.

### Steg 3: Definiera tillgänglighetsperioder

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` är en hjälpfunktion (implementation visas ej) som returnerar en samling av `AvailabilityPeriod`-objekt. Varje period specificerar ett startdatum, ett slutdatum och enheterna (procent av heltid) som resursen är tillgänglig.

### Steg 4: Lägg till perioderna till resursen

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Här **anger vi resursens tillgänglighet** genom att loopa igenom samlingen och lägga till varje period i resursens kalender.

### Steg 5: Visa tillgänglighetsdetaljerna

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Konsolutdata låter dig verifiera att perioderna har sparats korrekt.

## Vanliga fallgropar & tips

- **Datumprecision:** `AvailableFrom` och `AvailableTo` är `DateTime`-värden; se till att de är satta till midnatt om du vill ha hel-dagsperioder.  
- **Enhetsintervall:** Giltiga värden är 0‑100 %; värden utanför detta intervall kastar ett undantag.  
- **Överlappande perioder:** Överlappande perioder slås ihop automatiskt, men det är tydligare att hålla dem separata.

## Vanliga frågor

### Q1: Kan jag använda Aspose.Tasks för .NET i kommersiella projekt?
A1: Ja, Aspose.Tasks för .NET kan användas i kommersiella projekt. Du kan köpa en licens [här](https://purchase.aspose.com/buy).

### Q2: Finns det en gratis provversion av Aspose.Tasks för .NET?
A2: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET [här](https://releases.aspose.com/).

### Q3: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?
A3: Du kan hitta dokumentationen [här](https://reference.aspose.com/tasks/net/).

### Q4: Hur kan jag få support för Aspose.Tasks för .NET?
A4: Du kan få support från community-forumet [här](https://forum.aspose.com/c/tasks/15).

### Q5: Erbjuder ni tillfälliga licenser för Aspose.Tasks för .NET?
A5: Ja, tillfälliga licenser finns tillgängliga [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-04-06  
**Testad med:** Aspose.Tasks för .NET (senaste stabila versionen)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}