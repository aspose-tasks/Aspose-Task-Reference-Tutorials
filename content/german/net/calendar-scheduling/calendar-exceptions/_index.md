---
title: Behandeln von Kalenderausnahmen in Aspose.Tasks
linktitle: Behandeln von Kalenderausnahmen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie anhand von Schritt-für-Schritt-Anleitungen und Beispielen, wie Sie Kalenderausnahmen in Aspose.Tasks für .NET verwalten.
type: docs
weight: 12
url: /de/net/calendar-scheduling/calendar-exceptions/
---
## Einführung

In diesem Tutorial erfahren Sie, wie Sie Kalenderausnahmen in Aspose.Tasks mithilfe des .NET Frameworks verwalten. Mit Kalenderausnahmen können wir spezielle Daten oder Zeiträume in einem Projektkalender definieren, an denen sich der reguläre Arbeitsplan ändert, wie z. B. Feiertage oder vorübergehende Schließungen. Wir werden Schritt für Schritt verschiedene Methoden zur Behandlung von Kalenderausnahmen mit Aspose.Tasks für .NET behandeln.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio ist auf Ihrem System installiert.
- Aspose.Tasks für .NET-Bibliothek zu Ihrem Projekt hinzugefügt.

## Namespaces importieren

Importieren wir zunächst die notwendigen Namespaces für unser Projekt:

```csharp
using Aspose.Tasks;
using System;


```

## Schritt 1: Löschen einer Kalenderausnahme

Um eine Kalenderausnahme zu löschen, gehen Sie folgendermaßen vor:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Kalenderinformationen anzeigen
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Entfernen Sie die erste Ausnahme
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Schritt 2: Arbeitszeit einer Kalenderausnahme ermitteln

Um die Arbeitszeit einer Kalenderausnahme abzurufen, gehen Sie folgendermaßen vor:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Kalender- und Ausnahmeinformationen anzeigen
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Erhalten Sie Arbeitszeiten und zeigen Sie Details an
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Schritt 3: Kalenderausnahmen definieren

Um Kalenderausnahmen hinzuzufügen oder zu entfernen, führen Sie die folgenden Schritte aus:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Erstellen Sie eine neue Kalenderausnahme
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Ausnahmedetails festlegen
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Prüfen Sie, ob ein Datum eine Ausnahme darstellt
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Fügen Sie die Ausnahme zum Kalender hinzu
    calendar.Exceptions.Add(exception);

    // Entfernen Sie eine Ausnahme, falls vorhanden
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Fügen Sie eine neue Ausnahme hinzu
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Ausnahmen drucken
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Abschluss

In diesem Artikel haben wir verschiedene Aspekte der Behandlung von Kalenderausnahmen in Aspose.Tasks für .NET behandelt. Indem Sie die bereitgestellten Schritte befolgen, können Sie Ausnahmen in Ihren Projektzeitplänen effektiv verwalten und so eine genaue Darstellung von Arbeitszeiten und besonderen Ereignissen gewährleisten.

## FAQs

### F1: Kann ich einem einzelnen Kalender mehrere Ausnahmen hinzufügen?

A1: Ja, Sie können einem Kalender mehrere Ausnahmen hinzufügen, um verschiedene besondere Daten oder Zeiträume zu berücksichtigen.

### F2: Wie kann ich überprüfen, ob ein bestimmtes Datum eine Ausnahme darstellt?

 A2: Sie können das verwenden`CheckException()` Methode, um zu überprüfen, ob ein bestimmtes Datum unter eine Ausnahme fällt.

### F3: Ist es möglich, eine bestehende Ausnahme aus einem Kalender zu entfernen?

 A3: Ja, Sie können Ausnahmen entfernen, indem Sie auf zugreifen`Exceptions` Sammlung des Kalenders und Nutzung des`Remove()` Methode.

### F4: Welche Arten von Kalenderausnahmen werden unterstützt?

A4: Aspose.Tasks unterstützt verschiedene Arten von Ausnahmen, einschließlich täglicher, wöchentlicher, monatlicher und jährlicher Ausnahmen, und bietet so Flexibilität bei der Definition von Ausnahmeregeln.

### F5: Kann ich die Arbeitszeiten für bestimmte Ausnahmetermine anpassen?

A5: Ja, Sie können benutzerdefinierte Arbeitszeiten für einzelne Ausnahmetermine definieren, indem Sie die entsprechenden Methoden von Aspose.Tasks verwenden.