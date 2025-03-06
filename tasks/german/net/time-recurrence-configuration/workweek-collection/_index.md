---
title: Passen Sie Arbeitswochen in Aspose.Tasks an
linktitle: Sammlung von Arbeitswochen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Arbeitswochen in Aspose.Tasks für .NET anpassen. Schritt-für-Schritt-Anleitung zum Erstellen personalisierter Projektkalender. Jetzt downloaden!
weight: 17
url: /de/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Passen Sie Arbeitswochen in Aspose.Tasks an

## Einführung
Willkommen zu unserem Tutorial zum Erstellen einer benutzerdefinierten Arbeitswoche mit Aspose.Tasks für .NET! In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Definition einer personalisierten Arbeitswoche für einen Kalender in Ihrem Projekt. Aspose.Tasks ist eine leistungsstarke Bibliothek, die Entwicklern die effiziente Arbeit mit Microsoft Project-Dokumenten in ihren .NET-Anwendungen ermöglicht.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
## Namespaces importieren
Stellen Sie in Ihrem C#-Projekt sicher, dass Sie die erforderlichen Namespaces importieren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Schritt 1: Erstellen Sie ein Projekt und einen Kalender
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Schritt 2: Definieren Sie eine benutzerdefinierte Arbeitswoche
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Schritt 3: Arbeitstage festlegen
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Schritt 4: Informationen zur Arbeitswoche anzeigen
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Dieser umfassende Leitfaden ermöglicht Ihnen die effiziente Erstellung und Verwaltung benutzerdefinierter Arbeitswochen mit Aspose.Tasks für .NET.
## Abschluss
Zusammenfassend bietet Aspose.Tasks für .NET eine robuste Lösung für die Handhabung von Projektkalendern mit benutzerdefinierten Arbeitswochen. Durch Befolgen dieses Tutorials haben Sie gelernt, wie Sie Informationen zu benutzerdefinierten Arbeitswochen in Ihrem Projekt erstellen und anzeigen.
## FAQs
### Kann ich in einem einzigen Projekt mehrere benutzerdefinierte Arbeitswochen haben?
Ja, Sie können einem Projektkalender mehrere benutzerdefinierte Arbeitswochen hinzufügen.
### Wie kann ich bestehende Arbeitswochen ändern?
 Nutzen Sie das bereitgestellte`WorkWeek`Eigenschaften und Methoden zur Änderung bestehender Arbeitswochen.
### Ist Aspose.Tasks mit .NET Core kompatibel?
Ja, Aspose.Tasks unterstützt .NET Core.
### Kann ich das Projekt mit benutzerdefinierten Arbeitswochen in das Microsoft Project-Dateiformat exportieren?
Absolut, mit Aspose.Tasks können Sie Ihr Projekt in verschiedenen Formaten speichern, einschließlich Microsoft Project.
### Wo kann ich Unterstützung für Fragen zu Aspose.Tasks erhalten?
 Besuche den[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für jegliche Unterstützung oder Hilfe.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
