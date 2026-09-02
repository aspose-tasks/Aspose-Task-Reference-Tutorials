---
date: 2026-04-13
description: Erfahren Sie, wie Sie Arbeitszeiten festlegen und Kalenderkollektionen
  in Aspose.Tasks für .NET verwalten. Importieren Sie Kalender aus Microsoft Project,
  entfernen Sie Kalender aus einem Projekt und rufen Sie Kalender einfach nach Namen
  ab.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Verwalten der Kalendersammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Arbeitszeiten in der Aspose.Tasks‑Kalendersammlung festlegen
url: /de/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Arbeitszeiten im Aspose.Tasks Kalender-Set festlegen

In diesem Tutorial lernen Sie, wie Sie **Arbeitszeiten festlegen** und Kalender‑Sammlungen mit Aspose.Tasks für .NET verwalten. Kalender definieren Arbeitstage, Feiertage und Ausnahmen, sodass Sie durch deren Beherrschung Projektpläne präzise steuern können. Wir zeigen Ihnen außerdem, wie Sie Kalender aus Microsoft Project importieren, einen Kalender aus einem Projekt entfernen und einen Kalender nach Namen abrufen.

## Schnelle Antworten
- **Was ist die primäre Klasse für Kalender?** `Project.Calendars`‑Sammlung.  
- **Wie lege ich Arbeitszeiten fest?** Erstellen oder ändern Sie ein `Calendar`‑Objekt und definieren dessen `WorkingTime`.  
- **Kann ich Kalender aus Microsoft Project importieren?** Ja – laden Sie eine MPP‑Datei und greifen Sie auf deren Kalender zu.  
- **Wie entferne ich einen Kalender aus einem Projekt?** Verwenden Sie `Project.Calendars.Remove(calendar)`.  
- **Wie rufe ich einen Kalender nach Namen ab?** Rufen Sie `Project.Calendars.GetByName("YourCalendar")` auf.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Visual Studio: Installieren Sie Visual Studio oder eine andere kompatible IDE für .NET‑Entwicklung.  
2. Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET von [here](https://releases.aspose.com/tasks/net/) herunter und installieren Sie es.  
3. Grundlegendes Verständnis von C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.

## Namespaces importieren

Zuerst importieren wir die notwendigen Namespaces, um mit Aspose.Tasks zu arbeiten:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Erstellen eines neuen Kalenders

### Schritt 1: Initialisieren eines neuen `Project`-Objekts.
```csharp
var project = new Project();
```

### Schritt 2: Kalender zur Kalender‑Sammlung des Projekts hinzufügen.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Schritt 3: Durch die Kalender iterieren und deren Namen anzeigen.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Wie legt man Arbeitszeiten für einen Kalender fest?

Um **Arbeitszeiten festzulegen**, ändern Sie die `WorkingTime`‑Sammlung eines `Calendar`.  
Zum Beispiel können Sie einen standardmäßigen Arbeitstag von 9 Uhr bis 17 Uhr definieren oder benutzerdefinierte Ausnahmen hinzufügen.  
Der Code dafür ist identisch mit den später gezeigten Beispielen, wenn wir einen Standardkalender erstellen.

## Ersetzen eines Kalenders durch einen neuen Kalender

### Schritt 1: Ein vorhandenes Projekt laden.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Schritt 2: Den vorhandenen Kalender entfernen (falls vorhanden).  
Dies demonstriert das Szenario **Kalender aus Projekt entfernen**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Schritt 3: Einen neuen Kalender hinzufügen.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Kalender nach Name oder ID abrufen

### Schritt 1: Das Projekt laden.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Schritt 2: Kalender nach Name oder UID abrufen.  
Dies veranschaulicht die Operation **Kalender nach Namen abrufen**.
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

## Durch Kalender iterieren

### Schritt 1: Das Projekt laden.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Schritt 2: Die Anzahl der Kalender ermitteln.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Schritt 3: Durch die Kalender‑Sammlung iterieren und Namen anzeigen.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Erstellen eines Standardkalenders

### Schritt 1: Ein neues Projekt initialisieren.
```csharp
var project = new Project();
```

### Schritt 2: Einen neuen Kalender definieren und zum Standard machen.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Schritt 3: Das Projekt speichern.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Häufige Probleme und Lösungen

- **Kalender nicht gefunden bei Verwendung von `GetByName`** – Stellen Sie sicher, dass der exakte Name, einschließlich Groß‑/Kleinschreibung, mit dem beim Hinzufügen des Kalenders verwendeten übereinstimmt.  
- **Arbeitszeiten wurden nicht angewendet** – Nachdem Sie `WorkingTime` gesetzt haben, denken Sie daran, das Projekt zu speichern; andernfalls bleiben die Änderungen nur im Speicher.  
- **Importieren von Kalendern aus einer MPP‑Datei schlägt fehl** – Überprüfen Sie, ob die Quelldatei eine gültige Microsoft‑Project‑Datei ist und Sie Leseberechtigungen besitzen.

## FAQ

### Q1: Kann ich benutzerdefinierte Arbeitstage in Aspose.Tasks erstellen?

A1: Ja, Sie können benutzerdefinierte Arbeitstage erstellen, indem Sie Ausnahmen zu Kalendern hinzufügen.

### Q2: Ist es möglich, Kalender aus Microsoft‑Project‑Dateien zu importieren?

A2: Absolut, Aspose.Tasks unterstützt das Importieren von Kalendern aus Microsoft‑Project‑Dateien.

### Q3: Wie kann ich einen bestimmten Kalender aus einem Projekt entfernen?

A3: Sie können einen Kalender entfernen, indem Sie ihn aus der Sammlung holen und anschließend die `Remove`‑Methode aufrufen.

### Q4: Unterstützt Aspose.Tasks das Exportieren von Kalendern in verschiedene Formate?

A4: Ja, Aspose.Tasks ermöglicht das Exportieren von Kalendern in verschiedene Formate wie XML, MPP usw.

### Q5: Kann ich Arbeitszeiten für bestimmte Tage in einem Kalender anpassen?

A5: Natürlich, Sie können Arbeitszeiten für einzelne Tage mithilfe von Ausnahmen im Kalender definieren.

## Häufig gestellte Fragen

**Q: Was ist der beste Weg, einen 24‑Stunden‑Schichtkalender festzulegen?**  
A: Erstellen Sie einen neuen Kalender, leeren Sie vorhandene `WorkingTime`‑Einträge und fügen Sie für jeden Wochentag einen einzigen `WorkingTime`‑Bereich von 00:00 bis 24:00 hinzu.

**Q: Kann ich einen Kalender von einem Projekt in ein anderes kopieren?**  
A: Ja – exportieren Sie den Kalender mit `project.Save` nach XML und importieren Sie ihn anschließend in ein anderes Projekt mit `new Project(xmlPath)`.

**Q: Wie importiere ich Kalender aus Microsoft Project programmgesteuert?**  
A: Laden Sie die MPP‑Datei mit `new Project("source.mpp")`; die Kalender stehen anschließend über `project.Calendars` zur Verfügung.

**Q: Gibt es ein Limit für die Anzahl der Kalender in einem Projekt?**  
A: Praktisch gibt es kein Limit; die Sammlung kann so viele Kalender aufnehmen, wie der Speicher zulässt, jedoch sollte die Liste aus Leistungsgründen überschaubar bleiben.

**Q: Aktualisieren Änderungen an einem Kalender automatisch die Aufgaben, die ihn verwenden?**  
A: Ja – Aufgaben, die mit einem Kalender verknüpft sind, übernehmen die aktualisierten Arbeitszeiten nach dem Speichern des Projekts.

---

**Letzte Aktualisierung:** 2026-04-13  
**Getestet mit:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}