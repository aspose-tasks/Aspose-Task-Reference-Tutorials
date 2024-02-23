---
title: Wochentage in Aspose.Tasks für .NET meistern
linktitle: Definieren von Wochentagen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die Möglichkeiten der Definition von Wochentagen in Aspose.Tasks .NET. Folgen Sie unserem ausführlichen Tutorial, um Projektkalender effizient zu verwalten, Arbeitszeiten anzupassen und mehr.
type: docs
weight: 10
url: /de/net/time-recurrence-configuration/defining-weekdays/
---
## Einführung
Wenn Sie mit Aspose.Tasks für .NET in die Welt des Projektmanagements eintauchen, ist das Verstehen und Bearbeiten von Wochentagen ein entscheidender Aspekt. Die effiziente Verwaltung und Anpassung von Wochentagen in Ihrem Projektkalender kann sich erheblich auf die Projektzeitpläne auswirken. In diesem Tutorial führen wir Sie durch den Prozess der Definition von Wochentagen mit Aspose.Tasks und stellen Schritt-für-Schritt-Anleitungen und Beispiele zur besseren Verständlichkeit bereit.
## Voraussetzungen
Bevor wir uns auf diese Reise begeben, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundlegendes Verständnis der Programmiersprache C#.
-  Aspose.Tasks für .NET-Bibliothek installiert. Wenn nicht, laden Sie es herunter von[Hier](https://releases.aspose.com/tasks/net/).
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr Projekt:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Überprüfen Sie die Wochentagsgleichheit
```csharp
// Ihr Dokumentenverzeichnis
String DataDir = "Your Document Directory";
// Projektdatei laden
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Zugriff wochentags
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Überprüfen Sie die Gleichheit anhand verschiedener Eigenschaften
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Fügen Sie ähnliche Ausgabeanweisungen für DayWorking, FromDate, ToDate und WorkingTimes hinzu
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Klonen Sie einen Wochentag
```csharp
// Projektdatei laden
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Erstellen Sie eine tiefe Kopie des Wochentags
var weekDay2 = weekDay1.Clone();
// Ausgabeeigenschaften beider Wochentage
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Fügen Sie ähnliche Ausgabeanweisungen für DayWorking, FromDate, ToDate und WorkingTimes hinzu
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Holen Sie sich den Hash-Code eines Wochentags
```csharp
// Projektdatei laden
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Ausgabeeigenschaften beider Wochentage
// Fügen Sie ähnliche Ausgabeanweisungen für DayWorking, FromDate, ToDate und WorkingTimes hinzu
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Erstellen Sie einen neuen Kalender mit definierten Wochentagen
```csharp
// Erstellen Sie ein neues Projekt
var project = new Project();
// Definieren Sie einen Kalender
var calendar = project.Calendars.Add("Calendar1");
// Fügen Sie Arbeitstage und Ausnahmetage hinzu
// Fügen Sie ähnliche Ausgabeanweisungen für FromDate und ToDate hinzu
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Arbeitszeiten für Freitag festlegen
// Fügen Sie ähnliche Ausgabeanweisungen für DayWorking, FromDate, ToDate und WorkingTimes hinzu
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Legen Sie die Standardarbeitszeit für einen Tag fest
```csharp
// Erstellen Sie ein neues Projekt
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Fügen Sie Standardarbeitszeiten für Montag bis Freitag hinzu
// Fügen Sie ähnliche Ausgabeanweisungen für DayWorking, FromDate, ToDate und WorkingTimes hinzu
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Wiederholen Sie dies für Dienstag, Mittwoch, Donnerstag und Freitag
// Legen Sie arbeitsfreie Tage für Samstag und Sonntag fest
// Fügen Sie ähnliche Ausgabeanweisungen für DayWorking, FromDate, ToDate und WorkingTimes hinzu
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Abschluss
In diesem Tutorial haben wir wesentliche Aspekte der Definition von Wochentagen in Aspose.Tasks für .NET behandelt. Die Manipulation von Wochentagen ist eine Schlüsselkompetenz für effektives Projektmanagement. Experimentieren Sie mit den bereitgestellten Beispielen, passen Sie sie an die Anforderungen Ihres Projekts an und nutzen Sie das volle Potenzial von Aspose.Tasks.
## FAQs
### Kann ich für jeden Tag individuelle Arbeitszeiten definieren?
Ja, Sie können anhand der bereitgestellten Beispiele individuelle Arbeitszeiten für bestimmte Wochentage festlegen.
### Ist es möglich, dem Kalender mehrere Ausnahmetage hinzuzufügen?
Absolut. Ändern Sie den Code im vierten Beispiel, um zusätzliche Ausnahmetage einzuschließen.
### Wie kann ich einen bestimmten Wochentag aus dem Kalender entfernen?
Nutzen Sie die entsprechenden Methoden der Aspose.Tasks-Bibliothek, um Wochentage nach Bedarf zu entfernen.
### Bleiben die an den Wochentagen vorgenommenen Änderungen in der Projektdatei erhalten?
Ja, alle Änderungen an Wochentagen werden beim Speichern in der Projektdatei widergespiegelt.
### Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
Aspose.Tasks unterstützt verschiedene Programmiersprachen, die Beispiele hier sind jedoch speziell für .NET.