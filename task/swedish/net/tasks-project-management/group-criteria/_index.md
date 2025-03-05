---
title: Manipulering av MS Project Group Criteria i Aspose.Tasks
linktitle: Gruppkriterier i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska hur du manipulerar MS Project-filer programmatiskt i .NET med Aspose.Tasks. Hämta arbetsgrupps- och kriterieinformation steg-för-steg-exempel.
type: docs
weight: 27
url: /sv/net/tasks-project-management/group-criteria/
---
## Introduktion
Aspose.Tasks för .NET är ett kraftfullt API som underlättar arbetet med Microsoft Project-filer i dina .NET-applikationer. Oavsett om du utvecklar programvara för projektledning eller behöver manipulera projektdata programmatiskt, erbjuder Aspose.Tasks en omfattande uppsättning funktioner för att möta dina behov.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
### 1. Kunskaper i C# och .NET Framework
Bekantskap med programmeringsspråket C# och .NET Framework är viktigt för att förstå och implementera exemplen i denna handledning.
### 2. Installation av Aspose.Tasks för .NET
 Se till att du har Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/tasks/net/) och följ installationsanvisningarna.
### 3. Integrated Development Environment (IDE)
Ha en IDE som Visual Studio installerad på ditt system för att skriva och köra C#-kod.

## Importera namnområden
För att komma igång, importera de nödvändiga namnrymden i din C#-kod:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Steg 1: Ladda en Microsoft Project-fil
Ange först sökvägen till din Microsoft Project-fil:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Byta ut`"Your Document Directory"` med sökvägen till din projektfil.
## Steg 2: Hämta information om uppgiftsgrupper
Hämta sedan information om uppgiftsgrupper i projektet:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Detta kodavsnitt skriver ut det totala antalet uppgiftsgrupper, hämtar den andra uppgiftsgruppen, dess namn och antalet kriterier som den innehåller.
## Steg 3: Hämta uppgiftsgruppens kriteriuminformation
Låt oss nu fördjupa oss i detaljerna för ett specifikt kriterium inom uppgiftsgruppen:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Detta segment visar olika egenskaper för kriteriet såsom dess index, fält, grupperingsinformation, cellfärg, teckensnittsfärg, gruppintervall och startpunkt.
## Steg 4: Hämta Criterions teckensnittsinformation
Slutligen, skaffa teckensnittsrelaterade detaljer om kriteriet:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Detta steg skriver ut teckensnittsnamn, storlek, stil och om kriteriet är sorterat i stigande eller fallande ordning.

## Slutsats
I den här handledningen undersökte vi hur man använder Aspose.Tasks för .NET för att hämta information om uppgiftsgrupper och kriterier från en Microsoft Project-fil. Genom att följa steg-för-steg-guiden kan du effektivt arbeta med projektdata programmatiskt i dina .NET-applikationer.
## FAQ's
### Kan Aspose.Tasks hantera stora Microsoft Project-filer?
Aspose.Tasks är optimerad för att hantera stora projektfiler effektivt, vilket säkerställer hög prestanda och tillförlitlighet.
### Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?
Ja, Aspose.Tasks stöder olika versioner av Microsoft Project, vilket säkerställer kompatibilitet mellan olika filformat.
### Kan jag manipulera projektdata med Aspose.Tasks?
Absolut, Aspose.Tasks tillhandahåller omfattande funktioner för att manipulera projektdata, inklusive uppgifter, resurser, kalendrar och mer.
### Erbjuder Aspose.Tasks stöd för olika .NET-plattformar?
Ja, Aspose.Tasks stöder flera .NET-plattformar inklusive .NET Framework, .NET Core och .NET Standard.
### Finns det ett communityforum för Aspose.Tasks där jag kan söka hjälp?
 Ja, du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) att ställa frågor, dela kunskap och samarbeta med andra användare.