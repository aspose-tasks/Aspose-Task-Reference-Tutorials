---
title: Daglig arbetsupprepning i Aspose.Tasks
linktitle: Daglig arbetsupprepning i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du skapar dagliga återkommande uppgifter i Microsoft Project-filer med Aspose.Tasks för .NET. Öka produktiviteten och organisationen utan ansträngning.
type: docs
weight: 26
url: /sv/net/calendar-scheduling/daily-work-repetition/
---
## Introduktion

Aspose.Tasks för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att manipulera Microsoft Project-filer med lätthet. Bland dess otaliga funktioner är förmågan att hantera återkommande uppgifter effektivt. I den här handledningen kommer vi att fördjupa oss i funktionen Daily Work Repetition, som gör det möjligt att skapa uppgifter som upprepas dagligen inom ett projekt.

## Förutsättningar

Innan du dyker in i den här handledningen, se till att du har följande:

- Grundläggande kunskaper i C# och .NET framework.
- Visual Studio installerat på ditt system.
-  Aspose.Tasks för .NET-biblioteket. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
- Kännedom om Microsoft Project-filer (.mpp).

## Importera namnområden

Innan vi börjar, se till att du importerar de nödvändiga namnrymden:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Låt oss dela upp exemplet i flera steg:

## Steg 1: Ladda projektfilen

 Ladda först projektfilen med hjälp av`Project` klass:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Steg 2: Definiera parametrar för återkommande uppgift

Definiera parametrarna för den återkommande uppgiften:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Steg 3: Ställ in kalender och uppgifts startdatum

Ställ in kalender och startdatum för uppgiften:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Slutsats

I den här handledningen undersökte vi hur man använder Aspose.Tasks för .NET för att skapa återkommande uppgifter med dagliga arbetsupprepningar. Genom att följa dessa steg kan du effektivt hantera uppgifter inom dina projekt, vilket säkerställer smidigt arbetsflöde och organisation.

## FAQ's

### F1: Kan jag anpassa upprepningsmönstret ytterligare?

S1: Ja, du kan justera parametrar som startdatum, förekomstnummer och upprepningsintervall för att skräddarsy upprepningsmönstret enligt dina krav.

### F2: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project?

S2: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project, vilket säkerställer kompatibilitet och sömlös integration.

### F3: Hur kan jag hantera undantag eller ändringar av återkommande uppgifter?

S3: Aspose.Tasks tillhandahåller robust funktionalitet för att hantera undantag och ändringar inom återkommande uppgifter, vilket möjliggör flexibilitet och anpassning.

### F4: Kan jag exportera projektet till olika format?

S4: Absolut, Aspose.Tasks erbjuder stöd för export av projekt till olika format inklusive PDF, HTML, XML och mer, vilket underlättar delning och samarbete.

### F5: Erbjuder Aspose.Tasks teknisk support?

S5: Ja, Aspose.Tasks tillhandahåller omfattande teknisk support genom sitt forum, där du kan söka hjälp, dela erfarenheter och engagera dig med andra användare.