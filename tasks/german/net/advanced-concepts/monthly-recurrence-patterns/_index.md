---
title: Umgang mit monatlichen Wiederholungsmustern in Aspose.Tasks
linktitle: Umgang mit monatlichen Wiederholungsmustern in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit monatlichen Wiederholungsmustern in Aspose.Tasks für .NET umgehen.
weight: 18
url: /de/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Umgang mit monatlichen Wiederholungsmustern in Aspose.Tasks

## Einführung

Aspose.Tasks für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten. Eine der wesentlichen Funktionalitäten ist die Möglichkeit, wiederkehrende Aufgaben effizient zu erledigen. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie mit Aspose.Tasks mit monatlichen Wiederholungsmustern arbeiten.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen installiert sind:

## Namespaces importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr .NET-Projekt importiert haben:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Lassen Sie uns nun den Prozess des Umgangs mit monatlich wiederkehrenden Mustern in mehrere Schritte unterteilen:

## Schritt 1: Initialisieren Sie das Projekt

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Schritt 2: Legen Sie die Parameter für wiederkehrende Aufgaben fest

Definieren Sie die Parameter für die wiederkehrende Aufgabe, einschließlich Aufgabenname, Dauer und Wiederholungsmuster:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Schritt 3: Parameter zum Projekt hinzufügen

```csharp
project.RootTask.Children.Add(parameters);
```

## Schritt 4: Speichern Sie das Projekt

Speichern Sie das geänderte Projekt mit der wiederkehrenden Aufgabe:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Abschluss

Die Handhabung monatlicher Wiederholungsmuster in Aspose.Tasks für .NET ist unkompliziert und effizient. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie ganz einfach wiederkehrende Aufgaben mit bestimmten monatlichen Intervallen und Wiederholungsbereichen erstellen.

## FAQs

### F1: Ist Aspose.Tasks mit allen Versionen von Microsoft Project-Dateien kompatibel?

A1: Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich MPP, MPT, XML und MPX.

### F2: Kann ich das Wiederholungsmuster weiter anpassen?

A2: Ja, Aspose.Tasks bietet umfangreiche Optionen zum Anpassen von Wiederholungsmustern, einschließlich täglich, wöchentlich, monatlich und jährlich.

### F3: Gibt es eine kostenlose Testversion für Aspose.Tasks?

 A3: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks auf der Website erhalten[Hier](https://releases.aspose.com/).

### F4: Wie kann ich Unterstützung für Aspose.Tasks erhalten?

 A4: Sie können Hilfe suchen und sich an Diskussionen zum Thema beteiligen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).

### F5: Wo kann ich eine Lizenz für Aspose.Tasks erwerben?

 A5: Sie können eine Lizenz für Aspose.Tasks auf der Website erwerben[Hier](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
