---
title: Effektiv MS Project Task Grouping med Aspose.Tasks
linktitle: Gruppera uppgifter i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du effektivt grupperar Microsoft Project-uppgifter med Aspose.Tasks för .NET.
type: docs
weight: 25
url: /sv/net/tasks-project-management/grouping-tasks/
---
## Introduktion
Att hantera uppgifter i Microsoft Project kan ibland vara utmanande, särskilt när det gäller att organisera dem effektivt. Aspose.Tasks för .NET erbjuder en heltäckande lösning på detta genom att tillhandahålla funktioner för att gruppera uppgifter effektivt. I den här handledningen kommer vi att utforska hur man grupperar MS Project-uppgifter med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1.  Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Se till att du har en .NET-utvecklingsmiljö inrättad.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden till ditt C#-projekt för att använda Aspose.Tasks-funktioner:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Steg 1: Ladda MS Project File
Börja med att ladda din MS Project-fil med följande kod:
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Steg 2: Få åtkomst till uppgiftsgrupper
Låt oss sedan komma åt aktivitetsgrupperna inom projektet:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## Steg 3: Hämta gruppinformation
Hämta nu information om uppgiftsgruppen:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Steg 4: Åtkomstgruppskriterier
Få tillgång till kriterierna som ställts in för uppgiftsgruppen:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Steg 5: Hämta kriteriuminformation
Hämta detaljerad information om varje kriterium:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Genom att följa dessa steg kan du effektivt gruppera MS Project-uppgifter med Aspose.Tasks för .NET, vilket förbättrar organisationen och hanteringen av dina projektdata.

## Slutsats
Sammanfattningsvis ger Aspose.Tasks för .NET kraftfulla funktioner för att gruppera MS Project-uppgifter, vilket möjliggör bättre organisation och hantering av projektdata. Genom att följa stegen som beskrivs i denna handledning kan du effektivt använda dessa funktioner i dina .NET-applikationer.
## FAQ's
### Kan jag gruppera uppgifter baserat på anpassade kriterier?
Ja, du kan definiera anpassade kriterier för att gruppera uppgifter enligt dina specifika krav med Aspose.Tasks för .NET.
### Stöder Aspose.Tasks olika versioner av MS Project-filer?
Ja, Aspose.Tasks stöder olika versioner av MS Project-filer, vilket säkerställer kompatibilitet och sömlös integration.
### Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 Ja, du kan få en gratis testversion av Aspose.Tasks för .NET från[här](https://releases.aspose.com/).
### Kan jag anpassa utseendet på grupperade uppgifter?
Absolut, Aspose.Tasks erbjuder alternativ för att anpassa utseendet på grupperade uppgifter, inklusive cellfärger, typsnitt och stilar.
### Var kan jag hitta support för Aspose.Tasks för .NET?
 Du kan hitta support och hjälp för Aspose.Tasks för .NET i[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).