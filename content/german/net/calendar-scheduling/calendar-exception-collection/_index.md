---
title: Sammlung von Kalenderausnahmen in Aspose.Tasks
linktitle: Sammlung von Kalenderausnahmen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks Kalenderausnahmen in Ihren .NET-Projekten effizient behandeln und so eine genaue Planung und Ressourcenverwaltung gewährleisten.
type: docs
weight: 13
url: /de/net/calendar-scheduling/calendar-exception-collection/
---
## Einführung

Im Projektmanagement ist eine genaue Terminplanung entscheidend für den Erfolg. Allerdings erfordern reale Szenarien aufgrund von Feiertagen, besonderen Ereignissen oder anderen Faktoren häufig Abweichungen von Standardplänen. Aspose.Tasks für .NET bietet über die Funktion „Kalender-Ausnahmesammlung“ eine robuste Lösung für die Verwaltung solcher Ausnahmen. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess der Nutzung dieser Funktionalität.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1.  Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
2. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# wird zum Verständnis der Beispiele hilfreich sein.
3. Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung ein, z. B. Visual Studio oder JetBrains Rider.

## Namespaces importieren

Bevor Sie mit Aspose.Tasks für .NET arbeiten, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Dieser Schritt ermöglicht Ihnen den Zugriff auf die Klassen und Methoden, die zum Verwalten von Kalenderausnahmen erforderlich sind.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte unterteilen:

## Schritt 1: Projekt laden und Kalender abrufen

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

In diesem Schritt laden wir eine Projektdatei und rufen den gewünschten Kalender anhand seiner UID ab.

## Schritt 2: Vorhandene Ausnahmen löschen und Standardkalender festlegen

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Dieser Schritt löscht alle vorhandenen Ausnahmen aus dem Kalender und setzt ihn auf eine Standardkonfiguration.

## Schritt 3: Arbeitszeitausnahme definieren und hinzufügen

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Dieser Schritt definiert eine Arbeitszeitausnahme mit bestimmten Start- und Enddaten sowie Arbeitszeiten innerhalb dieser Daten und fügt sie dem Kalender hinzu.

## Schritt 4: Ausnahmen für arbeitsfreie Zeit definieren und hinzufügen

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Fügen Sie bei Bedarf weitere Ausnahmen hinzu

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

In diesem Schritt werden arbeitsfreie Ausnahmen wie Feiertage definiert und dem Kalender hinzugefügt.

## Schritt 5: Kalenderausnahmen anzeigen

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

In diesem Schritt werden die hinzugefügten Kalenderausnahmen zusammen mit ihren Details angezeigt.

## Schritt 6: Alle Ausnahmen entfernen

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Schließlich entfernt dieser Schritt alle Ausnahmen aus dem Kalender.

## Abschluss

Die Verwaltung von Kalenderausnahmen ist für eine genaue Projektplanung von entscheidender Bedeutung. Aspose.Tasks für .NET vereinfacht diese Aufgabe durch die Bereitstellung umfassender Funktionen, einschließlich der Calendar Exception Collection. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie verschiedene Planungsszenarien in Ihren Projekten effizient bewältigen.

## FAQs

### F1: Kann ich einem einzelnen Kalender mehrere Ausnahmen hinzufügen?

 A1: Ja, Sie können mit dem mehrere Ausnahmen zu einem Kalender hinzufügen`AddRange` Methode.

### F2: Wie gehe ich mit wiederkehrenden Ausnahmen wie wöchentlichen Feiertagen um?

A2: Sie können wiederkehrende Ausnahmen programmgesteuert berechnen und sie mithilfe benutzerdefinierter Logik zum Kalender hinzufügen.

### F3: Ist es möglich, Kalenderausnahmen aus externen Quellen zu importieren?

A3: Ja, Sie können Kalenderausnahmen aus externen Quellen wie Datenbanken oder CSV-Dateien lesen und in Ihr Projekt integrieren.

### F4: Was passiert, wenn es im Kalender überlappende Ausnahmen gibt?

A4: Mit Aspose.Tasks für .NET können Sie überlappende Ausnahmen behandeln, indem Sie Prioritäten definieren oder Konflikte basierend auf Ihren Projektanforderungen lösen.

### F5: Kann ich innerhalb einer Ausnahme die Arbeitszeiten für jeden Tag anpassen?

A5: Ja, Sie können innerhalb einer Ausnahme benutzerdefinierte Arbeitszeiten für einzelne Tage festlegen, um spezifischen Planungsanforderungen gerecht zu werden.