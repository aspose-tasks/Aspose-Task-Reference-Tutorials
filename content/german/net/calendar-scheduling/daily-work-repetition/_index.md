---
title: Tägliche Arbeitswiederholung in Aspose.Tasks
linktitle: Tägliche Arbeitswiederholung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET täglich wiederkehrende Aufgaben in Microsoft Project-Dateien erstellen. Steigern Sie mühelos Produktivität und Organisation.
type: docs
weight: 26
url: /de/net/calendar-scheduling/daily-work-repetition/
---
## Einführung

Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die einfache Bearbeitung von Microsoft Project-Dateien ermöglicht. Zu seinen unzähligen Funktionen gehört die Möglichkeit, wiederkehrende Aufgaben effizient zu erledigen. In diesem Tutorial befassen wir uns mit der Funktionalität der täglichen Arbeitswiederholung, die die Erstellung von Aufgaben ermöglicht, die sich innerhalb eines Projekts täglich wiederholen.

## Voraussetzungen

Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse in C# und .NET Framework.
- Visual Studio ist auf Ihrem System installiert.
-  Aspose.Tasks für .NET-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
- Vertrautheit mit Microsoft Project-Dateien (.mpp).

## Namespaces importieren

Bevor wir beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces importieren:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte unterteilen:

## Schritt 1: Laden Sie die Projektdatei

 Laden Sie zunächst die Projektdatei mit`Project` Klasse:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Schritt 2: Definieren Sie wiederkehrende Aufgabenparameter

Definieren Sie die Parameter für die wiederkehrende Aufgabe:

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

## Schritt 3: Legen Sie den Kalender und das Startdatum der Aufgabe fest

Legen Sie den Kalender und das Startdatum für die Aufgabe fest:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Aspose.Tasks für .NET verwenden, um wiederkehrende Aufgaben mit täglicher Arbeitswiederholung zu erstellen. Wenn Sie diese Schritte befolgen, können Sie Aufgaben innerhalb Ihrer Projekte effizient verwalten und so einen reibungslosen Arbeitsablauf und eine reibungslose Organisation gewährleisten.

## FAQs

### F1: Kann ich das Wiederholungsmuster weiter anpassen?

A1: Ja, Sie können Parameter wie Startdatum, Vorkommensnummer und Wiederholungsintervall anpassen, um das Wiederholungsmuster entsprechend Ihren Anforderungen anzupassen.

### F2: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?

A2: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so Kompatibilität und nahtlose Integration.

### F3: Wie kann ich mit Ausnahmen oder Änderungen an wiederkehrenden Aufgaben umgehen?

A3: Aspose.Tasks bietet robuste Funktionen zur Verwaltung von Ausnahmen und Änderungen innerhalb wiederkehrender Aufgaben und ermöglicht so Flexibilität und Anpassung.

### F4: Kann ich das Projekt in verschiedene Formate exportieren?

A4: Absolut, Aspose.Tasks bietet Unterstützung für den Export von Projekten in verschiedene Formate, darunter PDF, HTML, XML und mehr, und erleichtert so die einfache gemeinsame Nutzung und Zusammenarbeit.

### F5: Bietet Aspose.Tasks technischen Support?

A5: Ja, Aspose.Tasks bietet über sein Forum umfassenden technischen Support, in dem Sie Hilfe suchen, Erfahrungen austauschen und mit anderen Benutzern in Kontakt treten können.