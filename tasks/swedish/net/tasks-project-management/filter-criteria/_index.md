---
title: Bemästra MS Project Filter Criteria med Aspose.Tasks
linktitle: Filtrera kriterier i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du implementerar filterkriterier i MS Project med Aspose.Tasks för .NET. Öka projektledningseffektiviteten med riktad dataanalys.
weight: 18
url: /sv/net/tasks-project-management/filter-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra MS Project Filter Criteria med Aspose.Tasks

## Introduktion
Inom projektledningssfären står Microsoft Project som ett stabilt verktyg som erbjuder en uppsjö av funktioner för att hjälpa projektplanerare och chefer. Bland dess många funktioner finns möjligheten att filtrera projektdata, så att användare kan fokusera på specifika aspekter av deras projekts uppgifter. Men att bemästra dessa filtreringsfunktioner kan vara en svår uppgift utan rätt vägledning. Denna handledning syftar till att avmystifiera processen genom att tillhandahålla en steg-för-steg-guide för att implementera filterkriterier i MS Project med Aspose.Tasks för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# är nödvändigt för att förstå de begrepp som behandlas i denna handledning.
2.  Installation av Aspose.Tasks för .NET: Se till att du har Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
3. Microsoft Project File: Ha en Microsoft Project-fil (t.ex. Project2003.mpp) redo, som du kommer att använda för att implementera filterkriterierna.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks för .NET. Följ dessa steg:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Steg 1: Ladda projektfilen
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Förklaring: Den här kodraden initierar en ny instans av`Project` klass och laddar Microsoft Project-filen som anges av dess sökväg.
## Steg 2: Hämta uppgiftsfilter
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Förklaring: Här hämtar vi ett uppgiftsfilter från projektet. Justera indexet (`[1]`) enligt ditt krav för att välja önskat filter.
## Steg 3: Visa kriterierader
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Förklaring: Det här avsnittet itererar genom varje kriterierad i filtret och visar dess fält, operation, test och värden (om några).
## Steg 4: Skriv ut filterkriterier
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Förklaring: Skriver ut hur filterkriterierna fungerar.
## Steg 5: Visa kriteriedetaljer
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Förklaring: Den här delen hämtar och visar detaljerad information om varje kriterierad, vilket ger insikter i filtrets konfiguration.

## Slutsats
Att bemästra filterkriterier i MS Project med Aspose.Tasks för .NET är en värdefull färdighet som avsevärt kan förbättra projektledningseffektiviteten. Genom att följa den här handledningen har du lärt dig hur du manipulerar filterkriterier programmatiskt, vilket ger dig möjlighet att skräddarsy projektvyer efter dina specifika behov.
## FAQ's
### F: Kan jag använda flera filter samtidigt i MS Project?
S: Ja, du kan kombinera flera filter för att förfina dina projektdata ytterligare.
### F: Stöder Aspose.Tasks äldre versioner av Microsoft Project-filer?
S: Ja, Aspose.Tasks tillhandahåller bakåtkompatibilitet, vilket gör att du kan arbeta med olika versioner av Microsoft Project-filer.
### F: Är Aspose.Tasks kompatibelt med andra .NET-ramverk?
S: Aspose.Tasks stöder .NET Framework, .NET Core och .NET Standard, vilket säkerställer flexibilitet i olika utvecklingsmiljöer.
### F: Kan jag anpassa filterkriterier baserat på dynamiska förhållanden?
S: Absolut, du kan programmatiskt justera filterkriterier baserat på dynamiska parametrar, vilket möjliggör adaptiv projektdataanalys.
### F: Var kan jag söka hjälp om jag stöter på problem med Aspose.Tasks?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) att söka stöd från samhället eller direkt kontakta Aspose.Tasks support för personlig assistans.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
