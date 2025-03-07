---
title: Samling MS-projekt av dispositionskoder i Aspose.Tasks
linktitle: Samling av dispositionskoder i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du samlar in Microsoft Project-konturkoder med Aspose.Tasks för .NET. Denna omfattande handledning ger steg-för-steg-instruktioner.
weight: 11
url: /sv/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Samling MS-projekt av dispositionskoder i Aspose.Tasks

## Introduktion
I den här handledningen kommer vi att utforska hur man samlar in Microsoft Project-konturkoder med Aspose.Tasks för .NET. Vi delar upp processen i steg-för-steg-instruktioner för att säkerställa tydlighet och förståelse.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Visual Studio: Installera Visual Studio på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#-programmering: Förtrogenhet med C# kommer att vara fördelaktigt.

## Importera namnområden
Importera först de nödvändiga namnrymden för att komma åt Aspose.Tasks-funktionen i ditt C#-projekt.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Steg 1: Ladda projektfilen
 Börja med att ladda Microsoft Project-filen med hjälp av`Project` klass.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Steg 2: Samla dispositionskoder
Skapa en samlare för att samla in dispositionskoderna från projektuppgifterna.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Steg 3: Iterera genom uppgifter och dispositionskoder
Iterera genom de insamlade uppgifterna och konturkoderna och skriv ut deras detaljer.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Steg 4: Lägg till definition av anpassad dispositionskod
Lägg till en anpassad dispositionskoddefinition till projektet.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Steg 5: Skapa och infoga dispositionskod
Skapa en dispositionskod och infoga den i en uppgift.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Steg 6: Manipulera dispositionskoder
Manipulera konturkoderna efter behov, som att infoga, ta bort eller rensa.
```csharp
// Exempel på manipulation
// ...
// Sätt in kod med 2 i rätt läge
task.OutlineCodes.Insert(2, code2);
// Kontrollera om koden satts in
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Slutsats
den här handledningen lärde vi oss hur man samlar in Microsoft Project-konturkoder med Aspose.Tasks för .NET. Genom att följa dessa steg kan du effektivt hantera dispositionskoder inom dina projekt, vilket förbättrar organisationen och tydligheten.
## FAQ's
### F: Kan jag använda Aspose.Tasks för .NET med andra programmeringsspråk?
S: Ja, Aspose.Tasks för .NET riktar sig främst till .NET-plattformen, men det ger även stöd för andra programmeringsspråk genom Aspose.Tasks for Cloud.
### F: Finns det några begränsningar för storleken på projektfilerna som Aspose.Tasks för .NET kan hantera?
S: Aspose.Tasks för .NET kan hantera stora projektfiler effektivt, men prestandan kan variera beroende på filens komplexitet och storlek.
### F: Är Aspose.Tasks för .NET kompatibelt med de senaste versionerna av Microsoft Project?
S: Ja, Aspose.Tasks för .NET stöder olika versioner av Microsoft Project, inklusive de senaste.
### F: Kan jag anpassa utdataformatet när jag arbetar med Aspose.Tasks för .NET?
S: Absolut, Aspose.Tasks för .NET erbjuder omfattande alternativ för att anpassa utdataformatet enligt dina krav.
### F: Var kan jag hitta ytterligare support eller resurser för Aspose.Tasks för .NET?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för all hjälp eller frågor angående Aspose.Tasks för .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
