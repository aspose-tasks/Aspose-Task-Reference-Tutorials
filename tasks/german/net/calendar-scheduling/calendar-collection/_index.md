---
title: Verwalten der Kalendersammlung in Aspose.Tasks
linktitle: Verwalten der Kalendersammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Kalendersammlungen in Aspose.Tasks für .NET effizient verwalten. Erstellen, ändern und manipulieren Sie ganz einfach Kalender.
weight: 11
url: /de/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten der Kalendersammlung in Aspose.Tasks

## Einführung

In diesem Tutorial erfahren Sie, wie Sie Kalendersammlungen in Aspose.Tasks für .NET verwalten. Kalender spielen eine entscheidende Rolle im Projektmanagement und definieren Arbeitstage, Feiertage und Ausnahmen. Aspose.Tasks bietet robuste Funktionen zum Bearbeiten von Kalendern in Ihren Projekten.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio: Installieren Sie Visual Studio oder eine andere kompatible IDE für die .NET-Entwicklung.
2.  Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse von C#: Kenntnisse der Programmiersprache C# sind von Vorteil.

## Namespaces importieren

Importieren wir zunächst die notwendigen Namespaces, um mit Aspose.Tasks zu arbeiten:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Erstellen eines neuen Kalenders

###  Schritt 1: Initialisieren Sie ein neues`Project` object.
```csharp
var project = new Project();
```

### Schritt 2: Fügen Sie Kalender zur Kalendersammlung des Projekts hinzu.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Schritt 3: Gehen Sie die Kalender durch und zeigen Sie ihre Namen an.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Ersetzen eines Kalenders durch einen neuen Kalender

### Schritt 1: Laden Sie ein vorhandenes Projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Schritt 2: Entfernen Sie den vorhandenen Kalender (falls vorhanden).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Schritt 3: Fügen Sie einen neuen Kalender hinzu.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Kalender nach Name oder ID abrufen

### Schritt 1: Laden Sie das Projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Schritt 2: Kalender nach Name oder UID abrufen.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Schritt 3: Kalenderdetails anzeigen.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Durchlaufen von Kalendern

### Schritt 1: Laden Sie das Projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Schritt 2: Rufen Sie die Anzahl der Kalender ab.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Schritt 3: Durchlaufen Sie die Kalendersammlung und die Anzeigenamen.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Erstellen eines Standardkalenders

### Schritt 1: Initialisieren Sie ein neues Projekt.
```csharp
var project = new Project();
```

### Schritt 2: Definieren Sie einen neuen Kalender und machen Sie ihn zum Standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Schritt 3: Speichern Sie das Projekt.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Abschluss

Die Verwaltung von Kalendersammlungen in Aspose.Tasks für .NET ist für ein effektives Projektmanagement unerlässlich. Mit den bereitgestellten Funktionalitäten können Sie Kalender entsprechend Ihren Projektanforderungen effizient erstellen, ändern und bearbeiten.

## FAQs

### F1: Kann ich in Aspose.Tasks benutzerdefinierte Arbeitstage erstellen?

A1: Ja, Sie können benutzerdefinierte Arbeitstage erstellen, indem Sie Ausnahmen zu Kalendern hinzufügen.

### F2: Ist es möglich, Kalender aus Microsoft Project-Dateien zu importieren?

A2: Absolut, Aspose.Tasks unterstützt den Import von Kalendern aus Microsoft Project-Dateien.

### F3: Wie kann ich einen bestimmten Kalender aus einem Projekt entfernen?

 A3: Sie können einen Kalender entfernen, indem Sie ihn aus der Sammlung abrufen und dann den aufrufen`Remove` Methode.

### F4: Unterstützt Aspose.Tasks den Export von Kalendern in verschiedene Formate?

A4: Ja, Aspose.Tasks ermöglicht den Export von Kalendern in verschiedene Formate wie XML, MPP usw.

### F5: Kann ich die Arbeitszeiten für bestimmte Tage in einem Kalender anpassen?

A5: Natürlich können Sie über Ausnahmen im Kalender Arbeitszeiten für einzelne Tage festlegen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
