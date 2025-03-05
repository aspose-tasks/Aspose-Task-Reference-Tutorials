---
title: Wiederholung nach Monatstag in Aspose.Tasks
linktitle: Wiederholung nach Monatstag in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie wiederkehrende Aufgaben in .NET-Projekten mit Aspose.Tasks verwalten. Schritt-für-Schritt-Anleitung zum Umgang mit Wiederholungen pro Monat und Tag.
type: docs
weight: 25
url: /de/net/advanced-features/repetition-by-month-day/
---
## Einführung

Im Bereich der .NET-Entwicklung gilt Aspose.Tasks als leistungsstarkes Tool zur Verwaltung von Projektaufgaben und -plänen. Es bietet eine Fülle von Funktionen zur Optimierung der Arbeitsabläufe im Projektmanagement, einschließlich der Bearbeitung wiederkehrender Aufgaben. Die Wiederholung pro Monat und Tag ist eine häufige Anforderung bei der Projektplanung, und Aspose.Tasks bietet zuverlässige Unterstützung für dieses Szenario.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Grundlegendes Verständnis von C#: Um die in diesem Tutorial behandelten Konzepte zu verstehen, sind Kenntnisse der Programmiersprache C# erforderlich.
2. Installation von Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
3. Integrierte Entwicklungsumgebung (IDE): Installieren Sie eine IDE wie Visual Studio auf Ihrem System, um das Codieren zu erleichtern.

## Namespaces importieren

Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um auf die Funktionen von Aspose.Tasks zuzugreifen:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Lassen Sie uns das bereitgestellte Codebeispiel in eine Schritt-für-Schritt-Anleitung aufteilen:

## Schritt 1: Projektdatei laden

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Diese Codezeile initialisiert eine neue Instanz von`Project` Klasse und lädt die Projektdatei mit dem Namen „Project1.mpp“.

## Schritt 2: Definieren Sie wiederkehrende Aufgabenparameter

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

In diesem Abschnitt werden die Parameter für die wiederkehrende Aufgabe definiert, einschließlich Name, Dauer, Wiederholungsmuster und Wiederholungsbereich.

## Schritt 3: Aufgabe zum Projekt hinzufügen

```csharp
project.RootTask.Children.Add(parameters);
```

Hier fügen wir die wiederkehrenden Aufgabenparameter zum Projekt hinzu.

## Schritt 4: Projektdatei speichern

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Abschließend wird das geänderte Projekt mit der hinzugefügten wiederkehrenden Aufgabe gespeichert.

## Abschluss

In diesem Tutorial haben wir untersucht, wie man in Aspose.Tasks für .NET mit Wiederholungen pro Monat und Tag umgeht. Indem Sie die bereitgestellten Schritte befolgen, können Sie wiederkehrende Aufgaben innerhalb Ihrer Projektzeitpläne effizient verwalten.

## FAQs

### F1: Ist Aspose.Tasks mit allen Versionen von .NET kompatibel?

A1: Aspose.Tasks unterstützt verschiedene Versionen des .NET Frameworks und gewährleistet so die Kompatibilität zwischen verschiedenen Umgebungen.

### F2: Kann ich das Wiederholungsmuster weiter anpassen?

A2: Ja, Aspose.Tasks bietet umfangreiche Anpassungsmöglichkeiten zur Definition von Wiederholungsmustern entsprechend spezifischer Projektanforderungen.

### F3: Bietet Aspose.Tasks Unterstützung für andere Projektmanagementfunktionen?

A3: Absolut, Aspose.Tasks bietet eine breite Palette von Funktionen für das Projektmanagement, einschließlich Aufgabenverfolgung, Ressourcenzuweisung und Erstellung von Gantt-Diagrammen.

### F4: Gibt es eine Testversion für Aspose.Tasks?

 A4: Ja, Sie können eine kostenlose Testversion von nutzen[Hier](https://releases.aspose.com/) um die Möglichkeiten von Aspose.Tasks zu erkunden, bevor Sie eine Kaufentscheidung treffen.

### F5: Wo kann ich Hilfe suchen, wenn ich auf Probleme stoße oder Fragen habe?

 A5: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um Unterstützung von der Community oder dem Aspose-Team zu suchen.