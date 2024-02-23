---
title: Festlegen wiederkehrender Aufgabenparameter in Aspose.Tasks
linktitle: Festlegen wiederkehrender Aufgabenparameter in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Parameter für wiederkehrende Aufgaben in Microsoft Project festlegen. Umfangreiches Tutorial mit Schritt-für-Schritt-Anleitung.
type: docs
weight: 14
url: /de/net/rate-recurring-tasks/recurring-task-parameters/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess der Festlegung der Parameter für wiederkehrende Microsoft Project-Aufgaben mithilfe von Aspose.Tasks für .NET.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Grundlegendes Verständnis der Programmiersprache C#.
2. Visual Studio oder eine andere C#-IDE installiert.
3. Die Aspose.Tasks for .NET-Bibliothek ist in Ihrem Projekt installiert und wird darauf verwiesen.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren:
```csharp
using Aspose.Tasks;
using System;

```
## Schritt 1: Definieren Sie das Dokumentenverzeichnis
```csharp
String DataDir = "Your Document Directory";
```
 ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrem Dokumentenverzeichnis.
## Schritt 2: Laden Sie die Projektdatei
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Diese Codezeile lädt die Microsoft Project-Datei in die`project` Variablen.
## Schritt 3: Definieren Sie wiederkehrende Aufgabenparameter
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Hier definieren Sie die Parameter für die wiederkehrende Aufgabe wie Aufgabenname, Dauer, Wiederholungsmuster, Wiederholungsbereich und ob der Ressourcenkalender ignoriert werden soll.
## Schritt 4: Legen Sie den Kalender für wiederkehrende Aufgaben fest
```csharp
parameters.SetCalendar(project, "Standard");
```
Dieser Schritt legt den Kalender für die wiederkehrende Aufgabe fest. In diesem Beispiel wird der Kalender auf „Standard“ gesetzt.
## Schritt 5: Parameter zum Projekt hinzufügen
```csharp
project.RootTask.Children.Add(parameters);
```
Fügen Sie abschließend die Parameter zur Stammaufgabe des Projekts hinzu.

## Abschluss
In diesem Tutorial haben wir gezeigt, wie Sie mit Aspose.Tasks für .NET Parameter für wiederkehrende Microsoft Project-Aufgaben festlegen. Wenn Sie diese Schritte befolgen, können Sie wiederkehrende Aufgaben in Ihren Projekten effizient verwalten.
## FAQs
### Kann ich das Wiederholungsmuster weiter anpassen?
Ja, Aspose.Tasks bietet verschiedene Wiederholungsmuster und Optionen, die Sie entsprechend Ihren Projektanforderungen anpassen können.
### Gibt es vor dem Kauf eine Testversion?
 Ja, Sie können eine kostenlose Testversion von Aspose.Tasks herunterladen[Webseite](https://purchase.aspose.com/buy) um die Funktionen der Bibliothek zu bewerten.
### Unterstützt Aspose.Tasks andere Projektdateiformate?
Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate, darunter MPP, XML, XLSX und mehr.
### Kann ich Unterstützung erhalten, wenn bei der Implementierung Probleme auftreten?
Ja, Sie können das Aspose.Tasks-Forum besuchen, um Hilfe von der Community zu erhalten, oder den Support kontaktieren, um direkte Hilfe zu erhalten.
### Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?
 Eine temporäre Lizenz erhalten Sie bei der[Webseite](https://purchase.aspose.com/temporary-license/) zu Testzwecken.