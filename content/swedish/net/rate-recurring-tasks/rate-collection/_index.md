---
title: Master MS Project Rates med Aspose.Tasks
linktitle: Samling av priser i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar priser i MS Project-filer med Aspose.Tasks för .NET. Steg-för-steg handledning för effektiv resurshantering.
type: docs
weight: 11
url: /sv/net/rate-recurring-tasks/rate-collection/
---
## Introduktion
Välkommen till vår handledning om att hantera priser i MS Project med Aspose.Tasks för .NET! I den här guiden går vi igenom processen att arbeta med priser i dina MS Project-filer med Aspose.Tasks. Oavsett om du är en erfaren utvecklare eller precis har börjat med .NET-utveckling, kommer den här handledningen att ge dig steg-för-steg-instruktioner för att effektivt hantera priser inom dina projekt.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar:
### 1. Visual Studio installerad
Se till att du har Visual Studio installerat på ditt system. Du kan ladda ner den från webbplatsen om du inte redan har gjort det.
### 2. Aspose.Tasks för .NET
 Ladda ner och installera Aspose.Tasks för .NET-biblioteket från[hemsida](https://releases.aspose.com/tasks/net/).
### 3. Grundläggande kunskaper i C# och .NET
Bekanta dig med programmeringsspråket C# och grunderna i .NET-ramverket för att bättre förstå kodexemplen i denna handledning.
## Importera namnområden
ditt C#-projekt, importera de nödvändiga namnrymden för att använda Aspose.Tasks-funktioner:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Låt oss nu dela upp varje exempel i flera steg:
## Steg 1: Ladda en MS Project-fil
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Här skapar vi en ny`Project` objekt genom att ladda en befintlig MS Project-fil.
## Steg 2: Lägg till en resurs och ställ in arbete och priser
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Vi lägger till en ny resurs till projektet, anger dess typ som arbete, arbetsmängd och standardpris.
## Steg 3: Lägg till priser i resursen
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Vi lägger till priser till resursen och anger start- och slutdatum, standardpris och prisformat.
## Steg 4: Skriv ut prisinformation
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Det här steget skriver ut information om de priser som är kopplade till resursen.
## Steg 5: Uppdatera en kurs
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Vi uppdaterar slutdatumet för ett specifikt pris.
## Steg 6: Ta bort priser
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Detta steg tar bort alla priser av en viss typ.
## Steg 7: Iterera över återstående priser
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Slutligen upprepar vi de återstående priserna efter borttagning.
## Slutsats
Sammanfattningsvis gav denna handledning dig en omfattande guide om hur du hanterar priser i MS Project-filer med Aspose.Tasks för .NET. Genom att följa de steg-för-steg-instruktioner som beskrivs i denna handledning kan du effektivt hantera priser inom dina projekt och säkerställa korrekt resurshantering.
## FAQ's
### F: Kan jag använda Aspose.Tasks för .NET med andra projekthanteringsprogram?
S: Ja, Aspose.Tasks för .NET stöder integration med olika projekthanteringsprogram, inklusive MS Project, Primavera och mer.
### F: Är Aspose.Tasks för .NET kompatibelt med olika versioner av MS Project-filer?
S: Absolut, Aspose.Tasks för .NET stöder att arbeta med MS Project-filer av olika versioner, vilket säkerställer flexibilitet och kompatibilitet.
### F: Erbjuder Aspose.Tasks för .NET dokumentation och support?
 S: Ja, du kan hitta omfattande dokumentation och tillgång till supportforum på Aspose.Tasks[hemsida](https://reference.aspose.com/tasks/net/).
### F: Kan jag prova Aspose.Tasks för .NET innan jag köper?
S: Ja, du kan använda en gratis testversion av Aspose.Tasks för .NET för att utvärdera dess funktioner och kompatibilitet med dina krav.
### F: Hur kan jag köpa en licens för Aspose.Tasks för .NET?
 S: Du kan köpa en licens för Aspose.Tasks för .NET från[hemsida](https://purchase.aspose.com/temporary-license/)som ger flexibla licensalternativ för att passa dina behov.