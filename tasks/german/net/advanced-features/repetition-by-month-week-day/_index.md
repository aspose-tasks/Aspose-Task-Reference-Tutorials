---
date: 2026-04-01
description: Erfahren Sie, wie Sie Wiederholungen in Aspose.Tasks für .NET festlegen,
  wiederkehrende Aufgaben hinzufügen und wiederkehrende Aufgaben nach Monat, Woche
  und Tag automatisieren.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Wiederholung nach Monat, Woche und Tag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man Wiederholungen in Aspose.Tasks festlegt (Monat, Woche, Tag)
url: /de/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Wiederholungen in Aspose.Tasks festlegt (Monat, Woche, Tag)

## Einleitung

Wenn Sie **wie man Wiederholungen festlegt** für Aufgaben in einem Projekt benötigen, bietet Aspose.Tasks für .NET eine saubere, programmatische Möglichkeit, wiederkehrende Aufgaben­definitionen hinzuzufügen, die monatlich, wöchentlich oder täglich ausgeführt werden. In diesem Tutorial gehen wir ein praxisnahes Beispiel durch, das zeigt, wie Sie **wiederkehrende Aufgaben** hinzufügen, **wiederkehrende Aufgaben automatisieren** und sie direkt aus C#‑Code verwalten. Am Ende sind Sie bereit, diese Funktionalität in jede Planungs‑ oder Projektmanagement‑Lösung zu integrieren.

## Schnelle Antworten
- **Was bedeutet “recurrence” in Aspose.Tasks?** Es definiert ein Muster (täglich, wöchentlich, monatlich), das automatisch Aufgabeninstanzen über einen Datumsbereich erstellt.  
- **Welche primäre Methode erstellt die Wiederholung?** `RecurringTaskParameters` kombiniert mit einem spezifischen `RecurrencePattern`.  
- **Benötige ich eine Lizenz, um diesen Code auszuführen?** Eine Testversion funktioniert für die Evaluierung; eine kommerzielle Lizenz ist für die Produktion erforderlich.  
- **Kann ich wöchentliche Aufgaben anstelle von monatlichen planen?** Ja – ersetzen Sie `MonthlyRecurrencePattern` durch `WeeklyRecurrencePattern`.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 und später.

## Was ist Wiederholung in Aspose.Tasks?

Wiederholung ist ein Satz von Regeln, der Aspose.Tasks anweist, Aufgabeninstanzen in regelmäßigen Intervallen—täglich, wöchentlich oder monatlich—zu erzeugen, ohne sie manuell zu duplizieren. Diese Funktion ist essenziell für Projekte, die Routineaktivitäten wie Status‑Meetings, Inspektionen oder Wartungsarbeiten enthalten.

## Warum Wiederholungsfunktionen verwenden?

- **Zeit sparen:** Keine Notwendigkeit, Aufgaben manuell zu kopieren‑und‑einzufügen.  
- **Fehler reduzieren:** Die Bibliothek garantiert konsistente Daten und Dauern.  
- **Flexibilität:** Muster kombinieren (z. B. „erster Sonntag aller 2 Monate“).  
- **Automatisierung:** Ideal zur Generierung von Zeitplänen in CI‑Pipelines oder Reporting‑Tools.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Grundlegendes Verständnis von C#** – Sie werden ein paar Zeilen C#‑Code schreiben.  
2. **Aspose.Tasks für .NET installiert** – holen Sie es von der [download page](https://releases.aspose.com/tasks/net/).  
3. **Eine .mpp‑Projektdatei** – wir verwenden `Project1.mpp` als Quelldatei.

## Namensräume importieren

Um zu beginnen, importieren Sie die erforderlichen Aspose.Tasks‑Namensräume:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Schritt 1: Projektdatei laden

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Wir erstellen eine `Project`‑Instanz, die auf eine vorhandene Microsoft‑Project‑Datei zeigt.

### Schritt 2: Wiederkehrende Aufgabenparameter definieren

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

Hier **erstellen wir wiederkehrende Aufgaben**‑Parameter:

- **TaskName** – der Name der erzeugten Aufgabe.  
- **Duration** – wie lange jede Instanz dauert.  
- **RecurrencePattern** – ein monatliches Muster, das alle 2 Monate am ersten Sonntag wiederholt.  
- **RecurrenceRange** – das Start‑ und Enddatum, das den Zeitplan begrenzt.

### Schritt 3: Wiederkehrende Aufgabe zum Projekt hinzufügen

```csharp
project.RootTask.Children.Add(parameters);
```

Diese Zeile **fügt die wiederkehrende Aufgabe** zur Wurzel der Projekt‑Hierarchie hinzu.

### Schritt 4: Aktualisiertes Projekt speichern

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Das Projekt wird als neue `.mpp`‑Datei gespeichert, die nun den automatisierten Zeitplan enthält.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| **Aufgabe erscheint nicht** | Wiederholungsbereich liegt außerhalb der Projekttermine. | Überprüfen Sie, ob `Start`‑ und `Finish`‑Werte innerhalb des Projektkalenders liegen. |
| **Falscher Wochentag** | `WeekDay`‑Enum stimmt nicht überein. | Verwenden Sie `DayOfWeek.Monday` … `DayOfWeek.Sunday` nach Bedarf. |
| **Lizenzausnahme** | Ausführung ohne gültige Lizenz in der Produktion. | Wenden Sie vor dem Speichern eine temporäre oder vollständige Lizenz an. |

## Häufig gestellte Fragen

### Q1: Kann ich das Wiederholungsmuster über die bereitgestellten Beispiele hinaus anpassen?

A1: Ja, Aspose.Tasks für .NET bietet umfangreiche Anpassungsoptionen für Wiederholungsmuster, sodass Sie sie an Ihre spezifischen Anforderungen anpassen können.

### Q2: Gibt es eine Testversion von Aspose.Tasks für .NET?

A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET von der [releases page](https://releases.aspose.com/) erhalten.

### Q3: Wie kann ich Support für Aspose.Tasks für .NET erhalten?

A3: Sie können Unterstützung suchen und sich mit der Community im [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) austauschen.

### Q4: Gibt es temporäre Lizenzen für Aspose.Tasks für .NET?

A4: Ja, Sie können temporäre Lizenzen über die [purchase page](https://purchase.aspose.com/temporary-license/) für Test‑ und Evaluierungszwecke erwerben.

### Q5: Wo finde ich umfassende Dokumentation für Aspose.Tasks für .NET?

A5: Sie können die detaillierte [documentation](https://reference.aspose.com/tasks/net/) auf der Aspose‑Website einsehen, die tiefgehende Anleitungen zur Nutzung der Bibliothek bietet.

---

**Zuletzt aktualisiert:** 2026-04-01  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}