---
title: Arbeta med uppdrag i Aspose.Tasks
linktitle: Arbeta med uppdrag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar projektuppdrag i .NET med Aspose.Tasks. Utforska olika konturer för resursschemaläggning.
weight: 13
url: /sv/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Arbeta med uppdrag i Aspose.Tasks

## Introduktion

I den här handledningen kommer vi att utforska hur man arbetar med uppgifter i Aspose.Tasks för .NET. Uppdrag är avgörande i projektledning eftersom de allokerar resurser till uppgifter, hjälper till att schemalägga och spåra framsteg. Vi kommer att fokusera på att generera resurstilldelning tidsfasad data med olika konturer med hjälp av Aspose.Tasks.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

1.  Installation av Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[nedladdningslänk](https://releases.aspose.com/tasks/net/).
2. Grundläggande förståelse för C# och .NET Framework: Bekantskap med programmeringsspråket C# och .NET Framework är nödvändigt för att följa med.

## Importera namnområden

Se till att importera de nödvändiga namnrymden till ditt C#-projekt:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Steg 1: Skapa ett projekt och en uppgift

Låt oss börja med att skapa ett nytt projekt och lägga till en uppgift till det. Ställ in startdatum, varaktighet och slutdatum för uppgiften:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Steg 2: Lägg till en resurs och tilldela till uppgift

Lägg sedan till en resurs till projektet och tilldela den till den tidigare skapade uppgiften:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Steg 3: Generera tidsfasdata med olika konturer

Låt oss nu generera tidsfasdata med olika konturer för resurstilldelningen:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Steg 4: Ändra konturer och generera data

Vi kan ändra konturtypen och generera tidsfasdata därefter. Här är några exempel:

```csharp
// Ändra kontur
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generera tidsfasdata och skriv ut
// Upprepa detta steg för andra konturtyper
```

## Slutsats

den här handledningen har vi lärt oss hur man arbetar med uppgifter i Aspose.Tasks för .NET. Vi utforskade att generera resurstilldelning tidsfasad data med olika konturer. Denna kunskap kan vara oerhört användbar i scenarier för projektledning.

## FAQ's

### F1: Kan jag använda Aspose.Tasks för att schemalägga uppgifter i min .NET-applikation?

S1: Ja, Aspose.Tasks tillhandahåller omfattande API:er för uppgiftsschemaläggning och hantering i .NET-applikationer.

### F2: Finns det en gratis testversion tillgänglig för Aspose.Tasks?

 A2: Ja, du kan utnyttja en gratis provperiod från[här](https://releases.aspose.com/).

### F3: Finns det några begränsningar för antalet uppgifter eller resurser i Aspose.Tasks?

S3: Aspose.Tasks sätter inga begränsningar på antalet uppgifter eller resurser du kan hantera i dina projekt.

### F4: Kan jag anpassa konturerna för resurstilldelningar i Aspose.Tasks?

S4: Ja, som visas i denna handledning kan du ställa in olika konturer som sköldpadda, klocka, topp, etc., enligt dina projektkrav.

### F5: Var kan jag hitta stöd för Aspose.Tasks-relaterade frågor?

S5: Du kan hitta support på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) där experter och samhällsmedlemmar aktivt engagerar sig i diskussioner.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
