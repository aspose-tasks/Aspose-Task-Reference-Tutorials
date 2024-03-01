---
title: Wiederholung nach Jahr, Wochentag in Aspose.Tasks
linktitle: Wiederholung nach Jahr, Wochentag in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Tasks für .NET bei der effizienten Verwaltung wiederkehrender Aufgaben. Schritt-für-Schritt-Anleitung zur Implementierung der Funktion „Wiederholung nach Jahr, Wochentag“.
type: docs
weight: 28
url: /de/net/advanced-features/repetition-by-year-week-day/
---
## Einführung

Im Projektmanagement stehen Effizienz und Präzision an erster Stelle. Aspose.Tasks für .NET erweist sich als leistungsstarkes Tool, das eine Fülle von Funktionen zur Optimierung der Projektabwicklung bietet. Zu seinem Arsenal gehört die Fähigkeit, wiederkehrende Aufgaben mit bemerkenswerter Flexibilität zu bewältigen. Eine dieser Funktionen ist die Funktion „Wiederholung nach Jahr, Wochentag“, mit der Benutzer Aufgaben einrichten können, die sich an bestimmten Wochentagen, innerhalb bestimmter Monate und über mehrere Jahre hinweg wiederholen.

## Voraussetzungen

Bevor Sie sich mit den Feinheiten der Verwendung der Funktion „Wiederholung nach Jahr, Wochentag“ in Aspose.Tasks für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Kenntnisse von .NET Framework

Machen Sie sich mit den Grundlagen des .NET Frameworks vertraut, einschließlich objektorientierter Programmierkonzepte und C#-Syntax.

### 2. Installation von Aspose.Tasks für .NET

 Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Download-Link](https://releases.aspose.com/tasks/net/). Befolgen Sie die bereitgestellten Installationsanweisungen, um die Bibliothek in Ihre Entwicklungsumgebung zu integrieren.

### 3. Zugriff auf Dokumentation

 Siehe die[Dokumentation](https://reference.aspose.com/tasks/net/) Hier finden Sie umfassende Anleitungen zu Aspose.Tasks für .NET, einschließlich ausführlicher Erläuterungen zu Klassen, Methoden und Anwendungsbeispielen.

## 4. Einrichtung der Entwicklungsumgebung

Stellen Sie sicher, dass Sie eine geeignete Entwicklungsumgebung konfiguriert haben, z. B. Visual Studio oder eine kompatible IDE für die .NET-Entwicklung.

Nachdem Sie nun die Voraussetzungen geschaffen haben, befassen wir uns mit der Schritt-für-Schritt-Anleitung zur Implementierung von „Wiederholung nach Jahr, Wochentag“ in Aspose.Tasks für .NET.


## Notwendige Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces, um auf die Aspose.Tasks-Klassen und -Funktionen in Ihrer .NET-Anwendung zuzugreifen.

Fügen Sie in Ihre C#-Codedatei die folgenden Namespace-Deklarationen ein:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Diese Namespaces bieten Zugriff auf die Aspose.Tasks-Bibliothek und die Klassen, die für die Arbeit mit Aufgaben und Projektdateien erforderlich sind.

Lassen Sie uns nun den Prozess der Einrichtung einer wiederkehrenden Aufgabe mithilfe der Funktion „Wiederholung nach Jahr, Woche, Tag“ in Aspose.Tasks für .NET in überschaubare Schritte aufteilen.

## Schritt 1: Projekt- und Aufgabenparameter initialisieren

Initialisieren Sie zunächst das Projekt und definieren Sie die Parameter für die wiederkehrende Aufgabe.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

Dieses Codesegment initialisiert ein neues Projekt und gibt Parameter für eine wiederkehrende Aufgabe an. Es legt den Aufgabennamen und die Dauer fest und definiert das Wiederholungsmuster.

## Schritt 2: Parameter zum Projekt hinzufügen

Als nächstes fügen Sie die definierten Parameter zum Projekt hinzu.

```csharp
project.RootTask.Children.Add(parameters);
```

Diese Zeile fügt die Aufgabenparameter zur Stammaufgabe des Projekts hinzu und integriert die Konfiguration wiederkehrender Aufgaben.

## Schritt 3: Projektdatei speichern

Speichern Sie abschließend die Projektdatei mit der konfigurierten wiederkehrenden Aufgabe.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Dieses Snippet speichert die Projektdatei mit der angegebenen Konfiguration wiederkehrender Aufgaben im angegebenen Ausgabeverzeichnis.

## Abschluss

Zusammenfassend lässt sich sagen, dass die Beherrschung der Funktion „Wiederholung nach Jahr, Wochentag“ in Aspose.Tasks für .NET Projektmanagern und Entwicklern die Möglichkeit gibt, wiederkehrende Aufgaben effizient, präzise und flexibel zu bearbeiten. Wenn Sie der in diesem Artikel beschriebenen Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktionalität nahtlos in Ihre Projektmanagement-Workflows integrieren und so Produktivität und Organisation steigern.

## FAQs

### F1: Kann ich das Wiederholungsmuster über die bereitgestellten Beispiele hinaus weiter anpassen?

A: Ja, Aspose.Tasks für .NET bietet umfangreiche Anpassungsoptionen für wiederkehrende Aufgaben, sodass Sie das Wiederholungsmuster an Ihre spezifischen Anforderungen anpassen können.

### F2: Ist Aspose.Tasks für .NET mit anderer Projektmanagementsoftware kompatibel?

A: Aspose.Tasks für .NET unterstützt die Interoperabilität mit verschiedenen Projektmanagementformaten und ermöglicht so eine nahtlose Integration mit gängigen Software-Suites.

### F3: Wie kann ich mit Ausnahmen oder Änderungen an wiederkehrenden Aufgaben umgehen?

A: Aspose.Tasks für .NET bietet APIs zur Behandlung von Ausnahmen und Änderungen an wiederkehrenden Aufgaben und gewährleistet so Flexibilität bei der Verwaltung sich entwickelnder Projektanforderungen.

### F4: Bietet Aspose.Tasks für .NET Unterstützung für cloudbasierte Projektmanagementlösungen?

A: Ja, Aspose.Tasks für .NET bietet Unterstützung für cloudbasierte Projektmanagementlösungen und erleichtert die Zusammenarbeit und Zugänglichkeit über verschiedene Plattformen hinweg.

### F5: Gibt es eine Testversion für Aspose.Tasks für .NET?

A: Ja, Sie können über die auf eine kostenlose Testversion von Aspose.Tasks für .NET zugreifen[Webseite](https://releases.aspose.com/)So können Sie die Funktionen erkunden, bevor Sie eine Kaufentscheidung treffen.