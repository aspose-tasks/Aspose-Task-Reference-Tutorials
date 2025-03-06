---
title: Verwalten der Tagestypsammlung in Aspose.Tasks
linktitle: Verwalten der Tagestypsammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Tagestypsammlungen in Aspose.Tasks für .NET effizient verwalten. Erstellen, ändern und manipulieren Sie ganz einfach Kalenderausnahmen.
type: docs
weight: 28
url: /de/net/calendar-scheduling/day-type-collection/
---
## Einführung

 Aspose.Tasks für .NET bietet robuste Funktionen für die Verwaltung von Tagestypsammlungen, die für die Definition wöchentlicher Kalenderausnahmen in Projektmanagementanwendungen von entscheidender Bedeutung sind. In diesem Tutorial erfahren Sie, wie Sie das verwenden`DayTypeCollection` Unterricht effizient durchführen. 

## Voraussetzungen

Bevor wir mit dem Tutorial fortfahren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse von C#: Vertrautheit mit der Programmiersprache C# und .NET Framework-Konzepten.

## Namespaces importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren:

```csharp
using Aspose.Tasks;
using System;


```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte unterteilen:

## Schritt 1: Projekt laden und auf Kalender zugreifen

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Dieser Schritt initialisiert eine neue Projektinstanz und ruft den Kalender anhand seiner UID ab.

## Schritt 2: Kalenderausnahmen durchlaufen

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Hier durchlaufen wir jede Kalenderausnahme und geben ihren Namen und die zugehörigen Tagestypen aus.

## Schritt 3: Kalenderausnahmen ändern

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

In diesem Schritt wird gezeigt, wie Sie Kalenderausnahmen ändern, indem Sie Tagestypen hinzufügen, entfernen oder aktualisieren.

## Schritt 4: Neue Kalenderausnahmen erstellen und bearbeiten

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

In diesem letzten Schritt erstellen wir neue Kalenderausnahmen und bearbeiten sie durch Hinzufügen und Kopieren von Tagestypen.

## Abschluss

 Zusammenfassend lässt sich sagen, dass die Verwaltung von Tagestypsammlungen in Aspose.Tasks für .NET für die Definition und Änderung wöchentlicher Kalenderausnahmen in Projektmanagementanwendungen von entscheidender Bedeutung ist. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie das effektiv nutzen`DayTypeCollection` Klasse zur Abwicklung verschiedener Kalenderoperationen.

## FAQs

### F1: Kann Aspose.Tasks für .NET verwendet werden, um Gantt-Diagramme programmgesteuert zu erstellen?

A1: Ja, Aspose.Tasks für .NET bietet APIs zum Erstellen und Bearbeiten von Gantt-Diagrammen in .NET-Anwendungen.

### F2: Ist Aspose.Tasks für .NET sowohl mit .NET Core als auch mit .NET Framework kompatibel?

A2: Ja, Aspose.Tasks für .NET unterstützt sowohl .NET Core als auch .NET Framework.

### F3: Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?

 A3: Sie können Unterstützung erhalten, indem Sie die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) Hier können Sie Fragen stellen und mit anderen Benutzern interagieren.

### F4: Bietet Aspose.Tasks für .NET eine kostenlose Testversion an?

 A4: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET bei erhalten[Hier](https://releases.aspose.com/).

### F5: Kann ich eine temporäre Lizenz für Aspose.Tasks für .NET erwerben?

 A5: Ja, temporäre Lizenzen können bei erworben werden[Aspose-Website](https://purchase.aspose.com/temporary-license/).