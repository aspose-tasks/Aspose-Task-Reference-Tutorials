---
date: 2026-04-03
description: Lernen Sie, wie Sie Aspose.Tasks verwenden, um ein wiederkehrendes Aufgabenprojekt
  hinzuzufügen und das Projekt als MPP zu speichern. Dieser Leitfaden zeigt die Funktion
  Wiederholung nach Jahr, Woche, Tag Schritt für Schritt.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Wiederholung nach Jahr, Woche, Tag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man Aspose.Tasks verwendet – Wiederholung nach Jahr, Woche, Tag
url: /de/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wiederholung nach Jahr Woche Tag in Aspose.Tasks

## Einführung

Wenn Sie **how to use Aspose.Tasks** für die Handhabung komplexer wiederkehrender Zeitpläne benötigen, bietet die Bibliothek eine feinkörnige Kontrolle über jährliche Muster. In diesem Tutorial führen wir Sie durch das Erstellen einer Aufgabe, die an einem bestimmten Wochentag eines bestimmten Monats wiederholt wird und mehrere Jahre umfasst. Am Ende können Sie **add recurring task project** Einträge hinzufügen und **save project as MPP** mit nur wenigen Zeilen C#.

## Schnelle Antworten
- **What does “Repetition by Year Week Day” mean?** Es wiederholt eine Aufgabe an einem gewählten Wochentag (z. B. erster Sonntag) eines bestimmten Monats jedes Jahr.  
- **Which .NET versions are supported?** Alle modernen .NET Framework- und .NET Core/5/6-Versionen.  
- **Do I need a license to run the code?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Can I change the recurrence range?** Ja – Sie können ein Startdatum, Enddatum oder eine feste Anzahl von Wiederholungen festlegen.  
- **Is the output an MPP file?** Absolut – das Projekt wird als MPP-Datei gespeichert, die für Microsoft Project bereit ist.

## Was ist die „Repetition by Year Week Day“-Funktion?

Die Funktion ermöglicht es Ihnen, eine jährliche Wiederholung zu definieren, die einen bestimmten **day of the week** (z. B. Sunday) und eine **position** innerhalb des Monats (erstes, zweites, letztes usw.) anspricht. Dies ist ideal für Aufgaben wie vierteljährliche Überprüfungen, jährliche Audits oder jedes Ereignis, das einem kalendarbasierten Rhythmus folgt.

## Warum Aspose.Tasks für wiederkehrende Aufgaben verwenden?

- **Precision** – Vollständige Kontrolle über Monate, Wochentage und Ordnungspositionen.  
- **Compatibility** – Erzeugt native MPP-Dateien, die fehlerfrei in Microsoft Project geöffnet werden können.  
- **No COM interop** – Reine .NET API, keine Office-Installation erforderlich.  
- **Scalability** – Funktioniert sowohl für kleine Projekte als auch für Unternehmens‑Zeitpläne.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Basic .NET knowledge** – Vertrautheit mit C# und objektorientierten Konzepten.  
2. **Aspose.Tasks for .NET** – Laden Sie es von dem [download link](https://releases.aspose.com/tasks/net/) herunter und fügen Sie die DLL zu Ihrem Projekt hinzu.  
3. **Access to the official docs** – Die [documentation](https://reference.aspose.com/tasks/net/) enthält ausführliche Details zu allen Klassen.  
4. **A development IDE** – Visual Studio, Rider oder ein beliebiger kompatibler .NET‑Editor.

Jetzt, da Sie bereit sind, sehen wir uns die Implementierung an.

## Wie man Aspose.Tasks für wiederkehrende Aufgaben verwendet

### Importieren der erforderlichen Namespaces

Zuerst bringen Sie die erforderlichen Namespaces in den Gültigkeitsbereich, damit Sie mit Projekten, Aufgaben und Speicheroptionen arbeiten können.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Schritt 1: Projekt und Aufgabenparameter initialisieren

Erstellen Sie eine neue `Project`‑Instanz und definieren Sie anschließend ein `RecurringTaskParameters`‑Objekt, das das Wiederholungsmuster beschreibt.

```csharp
// The path to the documents directory.
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

> **Pro tip:** Passen Sie `Month`, `WeekDay` und `Position` an Ihren realen Zeitplan an.

### Schritt 2: Parameter zum Projekt hinzufügen

Fügen Sie die Definition der wiederkehrenden Aufgabe in die Wurzel des Projekts ein.

```csharp
project.RootTask.Children.Add(parameters);
```

### Schritt 3: Projekt als MPP speichern

Speichern Sie schließlich das Projekt in einer MPP‑Datei, damit es in Microsoft Project oder einem kompatiblen Viewer geöffnet werden kann.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Dies demonstriert **save project as mpp** in einer einzigen Codezeile.

## Häufige Probleme und Lösungen

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Keine Aufgaben erscheinen nach dem Öffnen der MPP-Datei | Die Daten des Wiederholungsbereichs liegen außerhalb des Projektkalenders | Stellen Sie sicher, dass `Start` und `Finish` Daten innerhalb der Arbeitszeit des Projekts liegen |
| Ausnahme `ArgumentNullException` bei `Add` | `parameters` ist null oder nicht vollständig initialisiert | Stellen Sie sicher, dass alle erforderlichen Eigenschaften (TaskName, Duration, RecurrencePattern) gesetzt sind |
| Falscher Wochentag ausgewählt | `WeekDay`‑Enum‑Wert stimmt nicht überein | Verwenden Sie `DayOfWeek.Monday` … `DayOfWeek.Sunday` nach Bedarf |

## Häufig gestellte Fragen

**Q: Kann ich das Wiederholungsmuster über das bereitgestellte Beispiel hinaus anpassen?**  
A: Ja, Aspose.Tasks ermöglicht es Ihnen, `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` oder sogar benutzerdefinierte `RecurrenceRange`‑Objekte zu kombinieren, um jeden Zeitplan zu erfüllen.

**Q: Ist Aspose.Tasks für .NET mit anderer Projektmanagement‑Software kompatibel?**  
A: Absolut – die Bibliothek liest und schreibt MPP-, XML- und Primavera‑Formate und ermöglicht einen reibungslosen Datenaustausch.

**Q: Wie kann ich Ausnahmen oder Änderungen an wiederkehrenden Aufgaben behandeln?**  
A: Verwenden Sie die Klasse `ExceptionTask`, um Overrides für bestimmte Vorkommen zu erstellen, oder bearbeiten Sie die `RecurringTaskParameters` und speichern das Projekt erneut.

**Q: Unterstützt Aspose.Tasks cloud‑basierte Lösungen?**  
A: Ja, Sie können die API in Azure Functions, AWS Lambda oder jedem .NET‑kompatiblen Cloud‑Dienst ausführen.

**Q: Gibt es eine Testversion von Aspose.Tasks für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET über die [website](https://releases.aspose.com/) erhalten, die Ihnen ermöglicht, die Funktionen vor einer Kaufentscheidung zu erkunden.

**Q: Wie füge ich einer bestehenden Projektdatei eine wiederkehrende Aufgabe hinzu, ohne andere Daten zu überschreiben?**  
A: Laden Sie das bestehende Projekt mit `new Project("Existing.mpp")`, fügen Sie die `RecurringTaskParameters` zu `RootTask.Children` hinzu und speichern Sie die Datei anschließend mit `Save`.

## Fazit

Durch das Beherrschen von **how to use Aspose.Tasks** für das **Repetition by Year Week Day**‑Szenario erhalten Sie die Fähigkeit, **add recurring task project**‑Einträge zu erstellen, die perfekt mit realen Kalendern übereinstimmen, und **save project as MPP** für nahtlose Zusammenarbeit zu speichern. Integrieren Sie diese Code‑Snippets in Ihre eigenen Lösungen, um die Terminplanungsgenauigkeit zu erhöhen und manuellen Aufwand zu reduzieren.

---

**Zuletzt aktualisiert:** 2026-04-03  
**Getestet mit:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}