---
title: Använda trädalgoritmen i Aspose.Tasks
linktitle: Använda trädalgoritmen i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du effektivt manipulerar uppgiftshierarkier i dina .NET-projekt med Aspose.Tasks' trädalgoritm.
type: docs
weight: 13
url: /sv/net/advanced-concepts/tree-algorithm/
---
## Introduktion

Aspose.Tasks för .NET tillhandahåller kraftfulla funktioner för att arbeta med projektledningsuppgifter, resurser och scheman. En sådan funktion är trädalgoritmen, som tillåter användare att manipulera uppgiftshierarkier effektivt. I den här handledningen kommer vi att utforska hur man använder trädalgoritmen i Aspose.Tasks för .NET för att samla in vanligt arbete och uppdatera arbetsvärden inom ett projekt.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# krävs för att följa exemplen.

## Importera namnområden

I ditt C#-projekt, importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks-funktioner:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Låt oss nu dela upp varje exempel i flera steg:

## Steg 1: Ladda projektfilen

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Ladda projektfilen i minnet med hjälp av`Project` klass.

## Steg 2: Definiera uppgiftshierarki

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definiera uppgiftshierarkin genom att lägga till överordnade och underordnade uppgifter.

## Steg 3: Ställ in uppgiftsegenskaper

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Ställ in egenskaper som startdatum, varaktighet och slutdatum för uppgifter.

## Steg 4: Lägg till resurs

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Lägg till resurser till projektet och tilldela dem uppgifter efter behov.

## Steg 5: Använd trädalgoritm

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Initiera`WorkAccumulator` klass och tillämpa trädalgoritmen för att samla in gemensamt arbete.

## Steg 6: Uppdatera Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Uppdatera arbetsvärdena för uppgifter baserat på den insamlade informationen.

## Slutsats

I den här handledningen har vi lärt oss hur man använder trädalgoritmen i Aspose.Tasks för .NET för att effektivt manipulera uppgiftshierarkier. Genom att följa steg-för-steg-guiden kan du effektivt hantera uppgifter och resurser inom dina projekt.

## FAQ's

### F1: Vad är Aspose.Tasks för .NET?

S1: Aspose.Tasks för .NET är ett kraftfullt API som tillåter utvecklare att manipulera Microsoft Project-filer programmatiskt med C#.

### F2: Kan jag ladda ner en gratis testversion av Aspose.Tasks för .NET?

 S2: Ja, du kan ladda ner en gratis testversion av Aspose.Tasks för .NET från[här](https://releases.aspose.com/).

### F3: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?

 S3: Du kan hitta dokumentationen för Aspose.Tasks för .NET[här](https://reference.aspose.com/tasks/net/).

### F4: Hur kan jag få support för Aspose.Tasks för .NET?

 S4: För support relaterat till Aspose.Tasks för .NET kan du besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### F5: Finns det en tillfällig licens tillgänglig för teständamål?

 S5: Ja, du kan få en tillfällig licens för teständamål från[här](https://purchase.aspose.com/temporary-license/).