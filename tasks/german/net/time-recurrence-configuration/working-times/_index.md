---
title: Arbeitszeiten in Aspose.Tasks konfigurieren
linktitle: Arbeitszeiten in Aspose.Tasks konfigurieren
second_title: Aspose.Tasks .NET-API
description: Verbessern Sie die Projektplanung in .NET mit Aspose.Tasks. Konfigurieren Sie mühelos Arbeitszeiten für ein präzises Ressourcenmanagement. Laden Sie die Bibliothek jetzt herunter!
weight: 13
url: /de/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Arbeitszeiten in Aspose.Tasks konfigurieren

## Einführung
Im Projektmanagement ist die genaue Kontrolle der Arbeitszeiten entscheidend für eine genaue Terminplanung und Ressourcenzuteilung. Aspose.Tasks für .NET bietet eine leistungsstarke Lösung für den Umgang mit Arbeitszeitinformationen in Ihren Projekten. Dieses Tutorial führt Sie durch den Prozess der Konfiguration von Arbeitszeiten mit Aspose.Tasks in einer .NET-Umgebung.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundlegendes Verständnis der Programmiersprache C#.
-  Aspose.Tasks für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
- Visual Studio oder eine beliebige bevorzugte C#-Entwicklungsumgebung einrichten.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces, um auf die Aspose.Tasks-Funktionen zuzugreifen:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Schritt 1: Kalender erstellen
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Hier initiieren wir ein neues Projekt und erstellen einen Kalender mit dem Namen „MyCalendar“, der auf dem Standardkalender basiert. Dieser Kalender dient zur Festlegung konkreter Arbeitszeiten.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Schritt 2: Informationen zur Arbeitswoche anzeigen
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
In diesem Schritt wird die Gesamtzahl der Arbeitstage im angegebenen Kalender gedruckt.
## Schritt 3: Details zu den Arbeitszeiten
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
In diesem Teil durchlaufen wir jeden Wochentag und drucken den Tagestyp und die zugehörigen Arbeitszeiten aus. Sie können die Arbeitszeiten für jeden Wochentag individuell an Ihre Projektanforderungen anpassen.
## Abschluss
Durch die effektive Konfiguration der Arbeitszeiten in Aspose.Tasks für .NET wird eine genaue Projektplanung und Ressourcenverwaltung gewährleistet. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie Arbeitszeitanpassungen nahtlos in Ihre Projektabläufe integrieren.
## Häufig gestellte Fragen
### Eignet sich Aspose.Tasks für das Management großer Projekte?
Ja, Aspose.Tasks ist für die Bearbeitung von Projekten unterschiedlicher Größe konzipiert und bietet robuste Funktionen für ein effizientes Projektmanagement.
### Kann ich für verschiedene Teammitglieder unterschiedliche Arbeitszeiten festlegen?
Absolut. Sie können die Arbeitszeiten pro Ressource individuell anpassen und so individuelle Zeitpläne erstellen.
### Unterstützt Aspose.Tasks die Integration mit anderen Projektmanagement-Tools?
Ja, Aspose.Tasks erleichtert die Integration mit verschiedenen Projektmanagement-Tools und verbessert so die Interoperabilität.
### Ist es möglich, Projektdaten in verschiedenen Formaten zu importieren/exportieren?
Aspose.Tasks unterstützt mehrere Dateiformate und ermöglicht so nahtlose Import-/Exportvorgänge für Projektdaten.
### Wie häufig werden Aspose.Tasks-Updates veröffentlicht?
Es werden regelmäßig Updates veröffentlicht, um die Kompatibilität mit den neuesten Technologien sicherzustellen und auf Benutzerfeedback einzugehen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
