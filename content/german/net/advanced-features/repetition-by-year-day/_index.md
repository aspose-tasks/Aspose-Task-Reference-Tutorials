---
title: Wiederholung nach Jahr und Tag in Aspose.Tasks
linktitle: Wiederholung nach Jahr und Tag in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie in Aspose.Tasks für .NET mit Jahrestagswiederholungen umgehen, um die Verwaltung wiederkehrender Aufgaben effizient zu optimieren.
type: docs
weight: 27
url: /de/net/advanced-features/repetition-by-year-day/
---
## Einführung

Im Bereich des Projektmanagements spielen eine effiziente Aufgabenplanung und -wiederholung eine entscheidende Rolle, um eine pünktliche Ausführung und einen reibungslosen Arbeitsablauf sicherzustellen. Aspose.Tasks für .NET bietet Entwicklern eine robuste Lösung, mit der sie wiederkehrende Aufgaben in ihren Anwendungen mühelos erledigen können. In diesem Tutorial befassen wir uns mit den Feinheiten der Arbeit mit jährlichen Tageswiederholungen mithilfe von Aspose.Tasks und bieten eine umfassende Anleitung zum Erstellen wiederkehrender Aufgaben auf der Grundlage jährlicher Muster.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/tasks/net/).
   
2. Entwicklungsumgebung: Richten Sie eine geeignete Entwicklungsumgebung mit Visual Studio oder einer anderen bevorzugten IDE für die .NET-Entwicklung ein.

3. Grundkenntnisse von C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut, um sie zusammen mit den Codebeispielen zu befolgen.

4. Projektmanagementkonzepte: Das Verständnis der Projektmanagementkonzepte und der Aufgabenplanung wird dabei helfen, die Tutorialkonzepte effektiv zu verstehen.

## Namespaces importieren

Bevor wir mit dem Codieren beginnen, importieren wir die erforderlichen Namespaces, um die Aufgabenbearbeitung mit Aspose.Tasks für .NET zu erleichtern.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen und jeden Schritt im Detail erläutern.

## Schritt 1: Projektdatei laden

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Hier initialisieren wir ein neues`Project` Objekt und laden Sie eine vorhandene Projektdatei mit dem Namen „Project1.mpp“.

## Schritt 2: Definieren Sie wiederkehrende Aufgabenparameter

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 In diesem Schritt definieren wir Parameter für unsere wiederkehrende Aufgabe. Wir geben den Aufgabennamen, die Dauer und das Wiederholungsmuster an. Für die jährliche Wiederholung verwenden wir die`YearlyRecurrencePattern` und stellen Sie mit ein, dass die Wiederholung am 1. Juli stattfinden soll`ByYearDayRepetition`, Darüber hinaus definieren wir den Wiederholungsbereich vom 1. Juli 2018 bis zum 1. Juli 2019.

## Schritt 3: Aufgabe zum Projekt hinzufügen

```csharp
project.RootTask.Children.Add(parameters);
```

Hier fügen wir die definierten wiederkehrenden Aufgabenparameter zur Stammaufgabe des Projekts hinzu.

## Schritt 4: Projekt speichern

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Abschließend speichern wir die geänderte Projektdatei mit der hinzugefügten wiederkehrenden Aufgabe.

## Abschluss

In diesem Tutorial haben wir den Prozess der Arbeit mit Jahrestagswiederholungen in Aspose.Tasks für .NET untersucht. Durch Befolgen der bereitgestellten Schritte können Entwickler wiederkehrende Aufgabenfunktionen nahtlos in ihre Anwendungen integrieren und so die Projektmanagementfunktionen verbessern.

## FAQs

### F1: Kann Aspose.Tasks komplexe Wiederholungsmuster verarbeiten?

A1: Ja, Aspose.Tasks bietet umfassende Unterstützung für verschiedene Wiederholungsmuster, einschließlich komplexer Muster wie jährliche, monatliche, wöchentliche und tägliche Wiederholungen.

### F2: Ist Aspose.Tasks mit verschiedenen Projektdateiformaten kompatibel?

A2: Auf jeden Fall unterstützt Aspose.Tasks gängige Projektdateiformate wie MPP, XML und CSV und gewährleistet so die Kompatibilität zwischen verschiedenen Projektmanagement-Tools.

### F3: Bietet Aspose.Tasks Dokumentation und Support für Entwickler?

A3: Ja, Entwickler können auf umfangreiche Dokumentation zugreifen und bei Fragen oder Problemen in den Aspose.Tasks-Community-Foren Hilfe suchen.

### F4: Kann ich Aufgabeneigenschaften wie Dauer und Startdatum mit Aspose.Tasks anpassen?

A4: Natürlich bietet Aspose.Tasks robuste APIs zur dynamischen Bearbeitung von Aufgabeneigenschaften, sodass Entwickler Dauer, Startdatum, Abhängigkeiten und mehr anpassen können.

### F5: Ist Aspose.Tasks sowohl für kleine als auch für Unternehmensprojekte geeignet?

A5: Tatsächlich ist Aspose.Tasks so konzipiert, dass es den Bedürfnissen von Entwicklern gerecht wird, die an Projekten aller Größenordnungen arbeiten, von Einzelaufgaben bis hin zu großen Unternehmensprojekten.