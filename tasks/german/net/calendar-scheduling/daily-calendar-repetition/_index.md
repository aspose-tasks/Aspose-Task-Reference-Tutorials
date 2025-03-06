---
title: Tägliche Kalenderwiederholung in Aspose.Tasks
linktitle: Tägliche Kalenderwiederholung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie in Aspose.Tasks für .NET wiederkehrende Aufgaben mit täglichen Kalenderwiederholungen erstellen. Verbessern Sie mühelos die Effizienz Ihres Projektmanagements.
type: docs
weight: 25
url: /de/net/calendar-scheduling/daily-calendar-repetition/
---
## Einführung

 Aspose.Tasks für .NET bietet leistungsstarke Tools zum programmgesteuerten Verwalten von Aufgaben und Projekten. Eine seiner bemerkenswerten Funktionen ist die Möglichkeit, tägliche Kalenderwiederholungen effizient zu verarbeiten. In diesem Tutorial erfahren Sie, wie Sie das verwenden`DailyCalendarRepetition` Klasse zusammen mit anderen relevanten Klassen, um wiederkehrende Aufgaben mit täglichen Wiederholungen basierend auf einem bestimmten Kalender zu erstellen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:

1.  Installation: Stellen Sie sicher, dass Aspose.Tasks für .NET installiert ist. Wenn nicht, können Sie es hier herunterladen[Hier](https://releases.aspose.com/tasks/net/).

2. Namespace-Import: Importieren Sie die erforderlichen Namespaces in Ihr Projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Schritt 1: Initialisieren Sie das Projekt

Zuerst müssen wir ein vorhandenes Projekt laden oder ein neues erstellen, um damit zu arbeiten:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Schritt 2: Definieren Sie den Kalender

Als nächstes erstellen wir einen Kalender mit einer 24-Stunden-Dauer und verknüpfen ihn mit dem Projekt:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Schritt 3: Legen Sie die Parameter für wiederkehrende Aufgaben fest

Legen wir nun die Parameter für unsere wiederkehrende Aufgabe fest. Wir definieren seinen Namen, seine Dauer, sein Wiederholungsmuster und seinen Bereich:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Schritt 4: Kalender für Aufgabe festlegen

Verknüpfen Sie den definierten Kalender mit der Aufgabe:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Schritt 5: Aufgabe zum Projekt hinzufügen

Fügen Sie die Aufgabe mit definierten Parametern zum Projekt hinzu:

```csharp
project.RootTask.Children.Add(parameters);
```

## Schritt 6: Speichern Sie das Projekt

Speichern Sie abschließend das Projekt mit der hinzugefügten wiederkehrenden Aufgabe:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Jetzt haben Sie mit Aspose.Tasks für .NET erfolgreich ein Projekt mit einer wiederkehrenden Aufgabe erstellt, die basierend auf einem 24-Stunden-Kalender täglich wiederholt wird!

## Abschluss

In diesem Tutorial haben wir gezeigt, wie Sie Aspose.Tasks für .NET verwenden, um tägliche Kalenderwiederholungen effizient zu verarbeiten. Wenn Sie diese Schritte befolgen, können Sie wiederkehrende Aufgaben nahtlos in Ihre Projekte integrieren und so Produktivität und Organisation verbessern.

## FAQs

### F1: Kann ich die Dauer jeder Wiederholung anpassen?

A1: Ja, Sie können die Dauer jeder Wiederholung Ihren Anforderungen entsprechend anpassen, indem Sie die Parameter im Code ändern.

### F2: Ist es möglich, unterschiedliche Kalender für verschiedene Aufgaben innerhalb desselben Projekts festzulegen?

A2: Absolut, Aspose.Tasks ermöglicht es Ihnen, einzelnen Aufgaben bestimmte Kalender zuzuweisen und bietet so Flexibilität bei der Planung.

### F3: Unterstützt Aspose.Tasks außer täglich auch andere Wiederholungsmuster?

A3: Ja, Aspose.Tasks bietet eine breite Palette von Wiederholungsmustern wie wöchentlich, monatlich, jährlich usw., um den unterschiedlichen Projektanforderungen gerecht zu werden.

### F4: Kann ich die wiederkehrenden Aufgaben visualisieren, die mit Aspose.Tasks erstellt wurden?

A4: Selbstverständlich bietet Aspose.Tasks Visualisierungsoptionen, mit denen Sie wiederkehrende Aufgaben effektiv analysieren und verfolgen können.

### F5: Gibt es eine Testversion für Aspose.Tasks?

 A5: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks unter nutzen[Hier](https://releases.aspose.com/) um die Funktionen zu erkunden, bevor Sie einen Kauf tätigen.