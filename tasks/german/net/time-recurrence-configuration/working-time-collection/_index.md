---
title: Arbeitszeiten in Aspose.Tasks meistern
linktitle: Erfassung der Arbeitszeiten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Tasks für .NET bei der effizienten Verwaltung von Projektzeitplänen. Passen Sie Kalender an, legen Sie Arbeitszeiten fest und optimieren Sie Ihre Projekte ganz einfach.
type: docs
weight: 14
url: /de/net/time-recurrence-configuration/working-time-collection/
---
## Einführung
Möchten Sie die Kunst der Arbeitszeitverwaltung in Aspose.Tasks für .NET erlernen? Suchen Sie nicht weiter! In dieser Schritt-für-Schritt-Anleitung befassen wir uns mit den Feinheiten der Arbeitszeiterfassung mit Aspose.Tasks und befähigen Sie so, benutzerdefinierte Kalender effizient zu verwalten und Ihre Projektzeitpläne zu optimieren.
## Voraussetzungen
Bevor wir uns auf diese Reise begeben, stellen Sie sicher, dass Sie über die folgenden Voraussetzungen verfügen:
-  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek von herunter und installieren Sie sie[Aspose.Tasks-Release-Seite](https://releases.aspose.com/tasks/net/).
- Arbeitsumgebung: Richten Sie eine geeignete Entwicklungsumgebung ein, vorzugsweise mit einer .NET-kompatiblen IDE.
## Namespaces importieren
Importieren Sie in Ihrem Projekt die erforderlichen Namespaces, um auf die Aspose.Tasks-Funktionen zuzugreifen:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Lassen Sie uns nun das Tutorial in mehrere Schritte unterteilen, um ein reibungsloses Lernerlebnis zu gewährleisten.
## Schritt 1: Erstellen Sie einen benutzerdefinierten Kalender
Erstellen Sie zunächst ein neues Projekt und fügen Sie ihm einen benutzerdefinierten Kalender hinzu:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Schritt 2: Arbeitstage definieren
Richten Sie Standardarbeitstage von Montag bis Freitag ein:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Schritt 3: Konfigurieren Sie die Samstagsarbeitszeiten
Arbeitszeiten für Samstage angeben:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Schritt 4: Samstagsarbeitszeiten ausdrucken
Drucken Sie die konfigurierten Arbeitszeiten für Samstag aus:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Schritt 5: Sonntagsarbeitszeiten konfigurieren
Arbeitszeiten für Sonntage festlegen:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Schritt 6: Sonntagsarbeitszeiten ausdrucken
Drucken Sie die konfigurierten Arbeitszeiten für Sonntag aus:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Schritt 7: Benutzerdefinierte Tage zum Kalender hinzufügen
Den konfigurierten Samstag und Sonntag in den Kalender einbinden:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Schritt 8: Durchgehen Sie die Arbeitszeiten
Durchlaufen Sie die Arbeitszeiten und zeigen Sie sie für jeden Tag im Kalender an:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Nachdem Sie nun erfolgreich durch die Schritte navigiert sind, sind Sie in der Lage, die Leistungsfähigkeit von Aspose.Tasks für .NET für die effektive Verwaltung Ihrer Arbeitszeiten zu nutzen.
## Abschluss
Wenn Sie die Erfassung von Arbeitszeiten in Aspose.Tasks beherrschen, können Sie Projektkalender individuell anpassen und so eine präzise Planung und effiziente Ressourcennutzung gewährleisten. Tauchen Sie mit Zuversicht in Ihre Projekte ein und nutzen Sie dabei das Wissen aus diesem umfassenden Leitfaden.
## Häufig gestellte Fragen
### Eignet sich Aspose.Tasks für das Management großer Projekte?
Ja, Aspose.Tasks ist für die Bearbeitung von Projekten unterschiedlicher Größe konzipiert und bietet robuste Funktionen für ein effizientes Projektmanagement.
### Kann ich Aspose.Tasks in andere .NET-Bibliotheken integrieren?
Sicherlich! Aspose.Tasks lässt sich nahtlos in andere .NET-Bibliotheken integrieren und erhöht so seine Vielseitigkeit und Kompatibilität.
### Wie oft wird Aspose.Tasks aktualisiert?
 Aspose.Tasks wird regelmäßig aktualisiert, um neue Funktionen, Erweiterungen und Kompatibilitätsverbesserungen zu integrieren. Überprüf den[Release-Seite](https://releases.aspose.com/tasks/net/) für die neuesten Updates.
### Gibt es eine kostenlose Testversion für Aspose.Tasks?
 Ja, Sie können Aspose.Tasks mit einer kostenlosen Testversion erkunden[dieser Link](https://releases.aspose.com/).
### Wo kann ich Unterstützung für Aspose.Tasks suchen?
 Bei Fragen oder Hilfe besuchen Sie bitte die[Aspose.Tasks-Supportforum](https://forum.aspose.com/c/tasks/15).