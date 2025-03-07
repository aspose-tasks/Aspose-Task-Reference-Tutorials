---
title: Hantera projektsamlingar i Aspose.Tasks
linktitle: Hantera gruppinsamling i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar MS Project-samlingar effektivt med Aspose.Tasks för .NET. Följ vår steg-för-steg-guide.
weight: 26
url: /sv/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera projektsamlingar i Aspose.Tasks

## Introduktion
den här handledningen kommer vi att utforska hur man hanterar grupp MS Project-samlingar med Aspose.Tasks för .NET. Att hantera gruppsamlingar är avgörande för att organisera och manipulera uppgifter och resurser effektivt inom ditt projekt.
## Förutsättningar
Innan du fortsätter med denna handledning, se till att du har följande förutsättningar:
1.  Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[nedladdningslänk](https://releases.aspose.com/tasks/net/).
2. Grundläggande kunskaper om C#: Bekanta dig med programmeringsspråket i C# eftersom denna handledning involverar kodning i C#.
3. Utvecklingsmiljö: Konfigurera en utvecklingsmiljö som Visual Studio eller någon annan IDE som stöder .NET-utveckling.

## Importera namnområden
Låt oss först importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks-funktioner i vår C#-kod.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Steg 1: Ladda projektet
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Det här steget innebär att MS Project-filen laddas in i projektobjektet Aspose.Tasks, så att vi kan utföra operationer på det.
## Steg 2: Iterera över uppgiftsgrupper
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Här itererar vi över uppgiftsgrupper inom projektet och skriver ut detaljer som index, namn och synlighet i menyn för varje grupp.
## Steg 3: Iterera över resursgrupper
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
På samma sätt upprepas det här steget över resursgrupper och visar deras index, namn och synlighet i menyn.
## Steg 4: Rensa och kopiera grupper till ett annat projekt
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Rensa andra projekts grupper
otherProject.TaskGroups.Clear();
// Kopiera grupper till andra projekt
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Här rensar vi grupperna i ett annat projekt och kopierar sedan grupper från det ursprungliga projektet till det.
## Steg 5: Lägg till en anpassad uppgiftsgrupp
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
I det här steget skapar vi en anpassad uppgiftsgrupp och lägger till den i det andra projektet om den inte redan finns.
## Steg 6: Ta bort alla grupper
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Slutligen tar vi bort alla grupper från det andra projektet.

## Slutsats
Hantera grupp MS-projektsamlingar i Aspose.Tasks för .NET är avgörande för att organisera och manipulera projektdata effektivt. Genom att följa stegen som beskrivs i denna handledning kan du effektivt hantera uppgifts- och resursgrupper inom dina projekt, vilket förbättrar den övergripande projektledningen.
## FAQ's
### Är Aspose.Tasks för .NET kompatibelt med alla versioner av MS Project?
Aspose.Tasks för .NET stöder olika versioner av Microsoft Project, inklusive 2003, 2007, 2010, 2013, 2016 och 2019.
### Kan jag anpassa gruppegenskaper med Aspose.Tasks för .NET?
Ja, du kan anpassa gruppegenskaper som namn och synlighet med Aspose.Tasks för .NET.
### Erbjuder Aspose.Tasks för .NET plattformsoberoende kompatibilitet?
Aspose.Tasks för .NET riktar sig främst till .NET-ramverket, men det kan användas i plattformsoberoende scenarier med .NET Core och .NET Standard.
### Hur kan jag få support för Aspose.Tasks för .NET?
 Du kan få support för Aspose.Tasks för .NET genom[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 Ja, du kan ladda ner en gratis testversion av Aspose.Tasks för .NET från[hemsida](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
