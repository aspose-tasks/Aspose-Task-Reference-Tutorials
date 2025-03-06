---
title: Hantering av MS Project Split Parts i Aspose.Tasks
linktitle: Hantera delade delar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar MS Project-delade delar effektivt med Aspose.Tasks för .NET. Förbättra ditt arbetsflöde för projektledning.
type: docs
weight: 18
url: /sv/net/rate-recurring-tasks/split-parts/
---

## Introduktion
Hantera MS-projektdelade delar kan vara en avgörande aspekt av projektledning när du använder Aspose.Tasks för .NET. I den här handledningen kommer vi att utforska hur du effektivt hanterar delade delar med hjälp av steg-för-steg-vägledning.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1.  Installation av Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[hemsida](https://releases.aspose.com/tasks/net/).
   
2. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnområden
Se till att importera de nödvändiga namnrymden i din C#-kod:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Steg 1: Skapa en projektinstans
```csharp
var project = new Project();
```
 Skapa en ny instans av`Project` klass.
## Steg 2: Ställ in projektstart- och slutdatum
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Ställ in start- och slutdatum för projektet.
## Steg 3: Lägga till en uppgift
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Lägg till en ny uppgift till projektet.
## Steg 4: Ställ in uppgiftsegenskaper
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Ställ in egenskaper som manuell status, startdatum och varaktighet för uppgiften.
## Steg 5: Lägga till resurstilldelningar
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Lägg till resurstilldelningar till uppgiften.
## Steg 6: Ställ in tilldelningsegenskaper
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Ställ in egenskaper som startdatum, arbete och slutdatum för uppdraget.
## Steg 7: Generera tidsfasdata
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Generera tidsfasdata för uppdraget baserat på projektkalendern.
## Steg 8: Dela upp uppgiften
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Dela upp uppgiften i flera delar inom den angivna tidsramen.
## Steg 9: Iterera över delade delar
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Iterera över de delade delarna av uppgiften och skriv ut deras start- och slutdatum.

## Slutsats
Effektiv hantering av MS Project-delade delar i Aspose.Tasks för .NET är avgörande för effektiviteten i projektledningen. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst hantera delade uppgifter och förbättra ditt arbetsflöde för projektledning.
## FAQ's
### F: Kan jag använda Aspose.Tasks för .NET med andra .NET-ramverk?
S: Ja, Aspose.Tasks för .NET är kompatibelt med olika .NET-ramverk inklusive .NET Core och .NET Standard.
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan få en gratis provperiod från[här](https://releases.aspose.com/).
### F: Stöder Aspose.Tasks för .NET resurshantering?
S: Ja, Aspose.Tasks för .NET låter dig hantera projektresurser effektivt.
### F: Kan jag anpassa projektkalendrar med Aspose.Tasks för .NET?
S: Absolut, du kan anpassa projektkalendrar enligt dina projektkrav.
### F: Var kan jag hitta support för Aspose.Tasks för .NET?
 S: Du kan hitta stöd och hjälp på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).