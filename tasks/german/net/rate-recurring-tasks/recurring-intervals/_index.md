---
title: Mühelose wiederkehrende Intervalle für MS Project in Aspose.Tasks
linktitle: Wiederkehrende Intervalle in Aspose.Tasks verwalten
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie, wie Sie mit Aspose.Tasks für .NET mühelos wiederkehrende Intervalle in MS Project verwalten.
type: docs
weight: 12
url: /de/net/rate-recurring-tasks/recurring-intervals/
---
## Einführung
Möchten Sie wiederkehrende Intervalle in Microsoft Project-Dateien mit Aspose.Tasks für .NET effizient verwalten? Dieses umfassende Tutorial führt Sie Schritt für Schritt durch den Prozess und stellt sicher, dass Sie wiederkehrende Intervalle in Ihren Projekten mühelos bewältigen können. Bevor wir uns mit dem Tutorial befassen, gehen wir einige Voraussetzungen durch, um sicherzustellen, dass Sie für den Einstieg bereit sind.
## Voraussetzungen
Bevor Sie mit diesem Tutorial fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Kenntnisse der C#-Programmierung: Grundlegende Kenntnisse der Programmiersprache C# und ihrer Syntax sind erforderlich.
2. Visual Studio installiert: Stellen Sie sicher, dass Visual Studio auf Ihrem System zum Codieren und Kompilieren der .NET-Anwendungen installiert ist.
3. Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek herunter und installieren Sie sie. Sie können es von bekommen[Hier](https://releases.aspose.com/tasks/net/).

## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces, um auf die von der Aspose.Tasks for .NET-Bibliothek bereitgestellten Funktionen zuzugreifen.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Lassen Sie uns nun jedes Beispiel in mehrere Schritte aufteilen und diese im Detail erläutern.
## Schritt 1: Projektobjekt initialisieren:
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Hier initialisieren wir eine neue Instanz von`Project` Klasse, indem Sie den Pfad zur Microsoft Project-Datei angeben.
## Schritt 2: Statusdatum festlegen:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Dieser Schritt setzt das Statusdatum des Projekts auf sein Startdatum.
## Schritt 3: Greifen Sie auf die Gantt-Diagrammansicht zu:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Wir greifen auf die Gantt-Diagrammansicht des Projekts zu.
## Schritt 4: Fortschrittszeile lesen:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Dieser Schritt ruft das wiederkehrende Intervall für Fortschrittslinien aus der Gantt-Diagrammansicht ab.
## Schritt 5: Intervallinformationen anzeigen:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Hier zeigen wir Informationen zum Intervall, zur Wochenwochennummer und zu den Wochentagen an.
## Schritt 6: Wiederkehrendes Intervall neu definieren:
```csharp
var newInterval = new RecurringInterval();
```
 Wir erstellen eine neue Instanz von`RecurringInterval` um das wiederkehrende Intervall neu zu definieren.
## Schritt 7: Monatliche Fortschrittslinien festlegen:
```csharp
// Legen Sie monatliche Fortschrittslinien pro Tag fest.
interval.MonthlyDay = true;
// Legen Sie die Tagesanzahl der monatlichen Fortschrittslinien fest.
interval.MonthlyDayDayNumber = 1;
// Legen Sie die Monatsanzahl der monatlichen Fortschrittszeilen fest.
interval.MonthlyDayMonthNumber = 1;
// Legen Sie Fortschrittslinien nach dem ersten oder letzten vordefinierten Tag fest.
interval.MonthlyFirstLast = true;
// Legen Sie den Typ der monatlichen Fortschrittslinien für den ersten oder letzten Tag fest.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Legen Sie die Anzahl der Fortschrittszeilen für den Monat fest.
interval.MonthlyFirstLastMonthNumber = 1;
```
Diese Schritte konfigurieren die monatlichen Fortschrittslinien gemäß den angegebenen Parametern.
## Schritt 8: Fortschrittslinien aktualisieren:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Wir aktualisieren die Fortschrittslinien in der Gantt-Diagrammansicht mit dem neu definierten wiederkehrenden Intervall.
## Schritt 9: Projekt als PDF speichern:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Abschließend speichern wir das Projekt mit dem aktualisierten wiederkehrenden Intervall als PDF-Datei.

## Abschluss
Zusammenfassend lässt sich sagen, dass die Verwaltung wiederkehrender Intervalle in Microsoft Project-Dateien mit Aspose.Tasks für .NET durch die umfassenden Funktionen der Bibliothek vereinfacht wird. Wenn Sie die in diesem Tutorial beschriebene Schritt-für-Schritt-Anleitung befolgen, können Sie wiederkehrende Intervalle in Ihren Projekten effizient bewältigen und so Produktivität und Organisation verbessern.
### FAQs
### Kann ich Aspose.Tasks für .NET mit anderen Programmiersprachen verwenden?
Ja, Aspose.Tasks für .NET kann mit jeder von .NET unterstützten Sprache wie C# und VB.NET verwendet werden.
### Gibt es eine Testversion für Aspose.Tasks für .NET?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?
 Unterstützung erhalten Sie im Aspose.Tasks-Forum[Hier](https://forum.aspose.com/c/tasks/15).
### Kann ich eine temporäre Lizenz für Aspose.Tasks für .NET erwerben?
 Ja, Sie können eine temporäre Lizenz bei erwerben[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich die vollständige Dokumentation für Aspose.Tasks für .NET?
 Die vollständige Dokumentation finden Sie hier[Hier](https://reference.aspose.com/tasks/net/).