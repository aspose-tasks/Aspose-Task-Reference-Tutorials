---
title: Wochentage in Aspose.Tasks meistern
linktitle: Sammlung von Wochentagen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Tasks für .NET bei der mühelosen Verwaltung von Wochentagen. Passen Sie Arbeitstage an, entfernen Sie Wochenenden und erstellen Sie ganz einfach spezielle Kalender.
type: docs
weight: 11
url: /de/net/time-recurrence-configuration/weekday-collection/
---
## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die eine effiziente Bearbeitung von Projektmanagementdaten ermöglicht. In diesem Tutorial erkunden wir die Sammlung von Wochentagen in Aspose.Tasks, die es Ihnen ermöglicht, Arbeitstage anzupassen, Wochenenden zu entfernen und spezielle Kalender zu erstellen, um Ihre Projektanforderungen zu erfüllen. Unabhängig davon, ob Sie ein erfahrener Entwickler oder ein Neuling sind, führt Sie diese Schritt-für-Schritt-Anleitung durch den Prozess der Arbeit mit Wochentagen in Aspose.Tasks für .NET.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Installieren Sie die Aspose.Tasks für .NET-Bibliothek. Sie können es hier herunterladen[Aspose.Tasks für .NET-Downloadseite](https://releases.aspose.com/tasks/net/).
- Vertrautheit mit der Programmiersprache C#.
- Integrierte Entwicklungsumgebung (IDE) wie Visual Studio.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr C#-Projekt:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Schritt 1: Erstellen Sie eine Projektinstanz
Initialisieren Sie ein neues Aspose.Tasks-Projekt:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Schritt 2: Greifen Sie auf den Kalender zu
Rufen Sie den Projektkalender ab:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Schritt 3: Wochentage anpassen
Vorhandene Wochentage löschen und Standardarbeitstage festlegen:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Fügen Sie auf ähnliche Weise weitere Wochentage hinzu ...
```
## Schritt 4: Arbeitszeiten hinzufügen
Arbeitszeiten für bestimmte Wochentage hinzufügen:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Schritt 5: Kalenderinformationen anzeigen
Kalenderdetails an die Konsole ausgeben:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Anzeige aller Wochentage und Arbeitszeiten...
```
## Schritt 6: Wochenenden entfernen
Entfernen Sie Samstag und Sonntag aus den Wochentagen:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Schritt 7: Aktualisierte Arbeitszeiten anzeigen
Aktualisierte Arbeitszeiten nach Entfernen der Wochenenden ausgeben:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Anzeige aller aktualisierten Wochentage und Arbeitszeiten...
```
## Schritt 8: Erstellen Sie einen 24-Stunden-Kalender
Erstellen Sie einen 24-Stunden-Kalender und kopieren Sie Wochentage:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Abschluss
In diesem Tutorial haben wir die leistungsstarken Funktionen von Aspose.Tasks für .NET bei der Verwaltung von Wochentagen in Projektkalendern untersucht. Von der Anpassung der Arbeitstage bis zur Erstellung spezieller 24-Stunden-Kalender vereinfacht Aspose.Tasks den Prozess und bietet Flexibilität und Kontrolle im Projektmanagement.
## Häufig gestellte Fragen
### F: Kann ich Aspose.Tasks für .NET mit anderen Programmiersprachen verwenden?
A: Aspose.Tasks unterstützt hauptsächlich .NET-Sprachen, bietet aber auch Versionen für Java an.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können eine kostenlose Testversion herunterladen[Aspose.Tasks-Versionsseite](https://releases.aspose.com/).
### F: Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?
 A: Besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung oder erwägen Sie den Kauf eines Support-Plans.
### F: Wo finde ich eine umfassende Dokumentation zu Aspose.Tasks für .NET?
 A: Siehe[Aspose.Tasks für .NET-Dokumentation](https://reference.aspose.com/tasks/net/) für detaillierte Informationen.
### F: Wie erhalte ich eine temporäre Lizenz für Aspose.Tasks für .NET?
 A: Sie können eine temporäre Lizenz bei erwerben[temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).