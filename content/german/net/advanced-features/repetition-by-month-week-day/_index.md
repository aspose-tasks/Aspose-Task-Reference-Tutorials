---
title: Wiederholung nach Monat, Wochentag in Aspose.Tasks
linktitle: Wiederholung nach Monat, Wochentag in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie in Aspose.Tasks für .NET Wiederholungen nach Monat, Woche und Tag einrichten, um wiederkehrende Aufgaben effizient zu automatisieren.
type: docs
weight: 26
url: /de/net/advanced-features/repetition-by-month-week-day/
---
## Einführung

Im Bereich der Softwareentwicklung, insbesondere bei Projektmanagementanwendungen, ist die Fähigkeit zur effizienten Bewältigung wiederkehrender Aufgaben von größter Bedeutung. Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek zur Optimierung der Erstellung und Verwaltung von Projektaufgaben, einschließlich wiederkehrender Aufgaben. Eine dieser von Aspose.Tasks bereitgestellten Funktionen ist die Möglichkeit, Wiederholungen nach Monat, Woche und Tag einzurichten und so sicherzustellen, dass Aufgaben ohne manuelles Eingreifen termingerecht ausgeführt werden.

## Voraussetzungen

Bevor Sie sich mit den Feinheiten der Einrichtung von Wiederholungen nach Monat, Woche und Tag mithilfe von Aspose.Tasks für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Grundlegendes Verständnis von C#: Vertrautheit mit der Programmiersprache C# ist unerlässlich, um die bereitgestellten Codebeispiele zu verstehen und umzusetzen.
   
2.  Installation von Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie die Aspose.Tasks für .NET-Bibliothek heruntergeladen und installiert haben. Die Bibliothek erhalten Sie über die[Download-Seite](https://releases.aspose.com/tasks/net/).

3. Zugriff auf eine .mpp-Projektdatei: Halten Sie eine Microsoft Project-Datei (.mpp) bereit, da wir diese verwenden werden, um die Implementierung von Wiederholungen nach Monat, Woche und Tag zu demonstrieren.

## Namespaces importieren

Um mit der Verwendung von Aspose.Tasks für .NET in Ihrer C#-Anwendung zu beginnen, müssen Sie die erforderlichen Namespaces importieren. So können Sie es machen:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Lassen Sie uns das bereitgestellte Code-Snippet in mehrere Schritte aufteilen, um jeden Teil gründlich zu verstehen.

## Schritt 1: Projektdatei laden

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Dieser Schritt umfasst das Erstellen einer neuen Instanz von`Project` Klasse und Laden einer vorhandenen Microsoft Project-Datei (`Project1.mpp`) aus dem angegebenen Verzeichnis.

## Schritt 2: Definieren Sie wiederkehrende Aufgabenparameter

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

In diesem Schritt definieren wir die Parameter für eine wiederkehrende Aufgabe. Wir geben den Aufgabennamen, die Dauer, das Wiederholungsmuster (monatlich) und den Wiederholungsbereich (Ende an einem bestimmten Datum) an.

## Schritt 3: Wiederkehrende Aufgabe zum Projekt hinzufügen

```csharp
project.RootTask.Children.Add(parameters);
```

Hier fügen wir die definierten wiederkehrenden Aufgabenparameter zur Stammaufgabe des Projekts hinzu.

## Schritt 4: Projektdatei speichern

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Abschließend speichern wir die geänderte Projektdatei mit der hinzugefügten wiederkehrenden Aufgabe.

## Abschluss

Zusammenfassend lässt sich sagen, dass das Einrichten von Wiederholungen nach Monat, Woche und Tag in Aspose.Tasks für .NET ein unkomplizierter Prozess ist, der es Entwicklern ermöglicht, die Verwaltung wiederkehrender Aufgaben innerhalb ihrer Projekte effizient zu automatisieren. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie diese Funktionalität nahtlos in Ihre C#-Anwendungen integrieren und so Zeit und Aufwand im Projektmanagement sparen.

## FAQs

###F1: Kann ich das Wiederholungsmuster über die bereitgestellten Beispiele hinaus anpassen?

A1: Ja, Aspose.Tasks für .NET bietet umfangreiche Anpassungsoptionen für Wiederholungsmuster, sodass Sie diese an Ihre spezifischen Anforderungen anpassen können.

###F2: Gibt es eine Testversion für Aspose.Tasks für .NET?

 A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET erhalten[Veröffentlichungsseite](https://releases.aspose.com/).

###F3: Wie kann ich Unterstützung für Aspose.Tasks für .NET erhalten?

 A3: Sie können auf der Website um Hilfe bitten und mit der Community in Kontakt treten[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).

###F4: Sind temporäre Lizenzen für Aspose.Tasks für .NET verfügbar?

 A4: Ja, Sie können temporäre Lizenzen von erwerben[Kaufseite](https://purchase.aspose.com/temporary-license/) zu Test- und Evaluierungszwecken.

###F5: Wo finde ich eine umfassende Dokumentation für Aspose.Tasks für .NET?

 A5: Sie können sich auf die detaillierten Informationen beziehen[Dokumentation](https://reference.aspose.com/tasks/net/) Ausführliche Anleitungen zur Nutzung der Bibliothek finden Sie auf der Aspose-Website.