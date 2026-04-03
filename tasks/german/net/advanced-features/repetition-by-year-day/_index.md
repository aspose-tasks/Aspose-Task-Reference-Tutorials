---
date: 2026-04-03
description: Lernen Sie die Aufgabenplanung im Projektmanagement und wie man wiederkehrende
  Aufgaben mit Aspose.Tasks für .NET hinzufügt, einschließlich des Speicherns des
  Projekts als MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Wiederholung nach Jahrestag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projektmanagement‑Aufgabenplanung mit Jahres‑Tag‑Wiederholung in Aspose.Tasks
url: /de/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektmanagement-Aufgabenplanung mit Jahres‑Tag‑Wiederholung in Aspose.Tasks

## Einleitung

Effiziente **Projektmanagement-Aufgabenplanung** ist das Rückgrat jedes erfolgreichen Projekts. Wenn Aufgaben jährlich wiederkehren — zum Beispiel jährliche Audits, Wartungsfenster oder saisonale Überprüfungen — kann die manuelle Handhabung dieser Wiederholungen fehleranfällig und zeitaufwendig werden. Aspose.Tasks für .NET vereinfacht dies, indem es Ihnen ermöglicht, Jahr‑Tag‑Muster programmgesteuert zu definieren, sodass Sie sich auf das Wesentliche konzentrieren können: Mehrwert zu liefern. In diesem Tutorial lernen Sie **wie man wiederkehrende Aufgaben** basierend auf einem bestimmten Tag des Jahres hinzufügt und sehen genau **wie man das Projekt als MPP speichert** für eine nahtlose Integration mit Microsoft Project.

## Schnelle Antworten
- **Was bedeutet „Jahrestag‑Wiederholung“?** Sie plant eine Aufgabe an einem bestimmten Tag eines bestimmten Monats jedes Jahres.  
- **Welche API‑Klasse erzeugt die Wiederholung?** `YearlyRecurrencePattern` kombiniert mit `ByYearDayRepetition`.  
- **Kann ich ein Start‑ und Enddatum festlegen?** Ja, mit `EndByRecurrenceRange`.  
- **Welches Dateiformat wird erzeugt?** Das Projekt wird als MPP‑Datei gespeichert (`SaveFileFormat.Mpp`).  
- **Benötige ich eine Lizenz für die Produktion?** Für den nicht‑evaluativen Einsatz ist eine kommerzielle Lizenz erforderlich.

## Voraussetzungen

Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

1. Aspose.Tasks für .NET Bibliothek: Laden Sie die Aspose.Tasks für .NET Bibliothek herunter und installieren Sie sie von der [Website](https://releases.aspose.com/tasks/net/).  
2. Entwicklungsumgebung: Richten Sie eine geeignete Entwicklungsumgebung mit Visual Studio oder einer anderen bevorzugten IDE für .NET‑Entwicklung ein.  
3. Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut, um den Codebeispielen folgen zu können.  
4. Projektmanagement‑Konzepte: Das Verständnis von Projektmanagement‑Konzepten und Aufgabenplanung hilft, die Tutorial‑Konzepte effektiv zu erfassen.

## Namensräume importieren

Bevor wir mit dem Codieren beginnen, importieren wir die erforderlichen Namensräume, um die Aufgabenmanipulation mit Aspose.Tasks für .NET zu erleichtern.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte und erläutern jeden Schritt im Detail.

## Wie man eine wiederkehrende Aufgabe mit Jahres‑Tag‑Muster hinzufügt

### Schritt 1: Projektdatei laden

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Hier initialisieren wir ein neues `Project`‑Objekt und laden eine vorhandene Projektdatei mit dem Namen **Project1.mpp**.

### Schritt 2: Parameter für wiederkehrende Aufgabe definieren

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

In diesem Schritt definieren wir die Parameter für unsere wiederkehrende Aufgabe. Wir geben den Aufgabennamen, die Dauer und das Wiederholungsmuster an. Für die jährliche Wiederholung verwenden wir das `YearlyRecurrencePattern` und setzen die Wiederholung auf den **1. Juli** mittels `ByYearDayRepetition`. Zusätzlich definieren wir den Wiederholungsbereich vom 1. Juli 2018 bis zum 1. Juli 2019.

### Schritt 3: Aufgabe zum Projekt hinzufügen

```csharp
project.RootTask.Children.Add(parameters);
```

Hier fügen wir die definierten Parameter der wiederkehrenden Aufgabe zur Stammaufgabe des Projekts hinzu.

### Schritt 4: Projekt als MPP speichern

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Abschließend **speichern wir das Projekt als MPP‑Datei**, sodass es bereit ist, in Microsoft Project oder einem kompatiblen Viewer geöffnet zu werden.

## Warum das wichtig ist

- **Automatisierung** – Eliminieren Sie die manuelle Eingabe jährlicher Aufgaben und reduzieren Sie menschliche Fehler.  
- **Konsistenz** – Stellt sicher, dass dasselbe Tag‑Monat‑Muster über mehrere Jahre hinweg angewendet wird.  
- **Integration** – Die resultierende MPP‑Datei kann mit Stakeholdern geteilt werden, die auf Microsoft Project angewiesen sind.  

## Häufige Fallstricke & Tipps

- **DateTime‑Präzision** – Stellen Sie sicher, dass die Startzeit mit Ihrem Projektkalender übereinstimmt; andernfalls kann die Aufgabe verschoben angezeigt werden.  
- **Zeitzonen** – Die API arbeitet mit `DateTime`‑Objekten; berücksichtigen Sie eine UTC‑Umwandlung, wenn Ihre Anwendung mehrere Regionen abdeckt.  
- **Lizenzdurchsetzung** – Im Evaluierungsmodus kann die gespeicherte MPP‑Datei ein Wasserzeichen enthalten; verwenden Sie für die Produktion eine gültige Lizenz.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks komplexe Wiederholungsmuster verarbeiten?**  
A: Ja, Aspose.Tasks bietet umfassende Unterstützung für verschiedene Wiederholungsmuster, einschließlich jährlicher, monatlicher, wöchentlicher und täglicher Wiederholungen.

**Q: Ist Aspose.Tasks mit verschiedenen Projektdateiformaten kompatibel?**  
A: Absolut, Aspose.Tasks unterstützt gängige Projektdateiformate wie MPP, XML und CSV und gewährleistet die Kompatibilität mit verschiedenen Projektmanagement‑Tools.

**Q: Bietet Aspose.Tasks Dokumentation und Support für Entwickler?**  
A: Ja, Entwickler können umfangreiche Dokumentation nutzen und Unterstützung in den Aspose.Tasks‑Community‑Foren für alle Fragen oder Probleme erhalten.

**Q: Kann ich Aufgaben‑Eigenschaften wie Dauer und Startdatum mit Aspose.Tasks anpassen?**  
A: Selbstverständlich, Aspose.Tasks stellt robuste APIs zur Verfügung, um Aufgaben‑Eigenschaften dynamisch zu manipulieren, sodass Entwickler Dauer, Startdaten, Abhängigkeiten und mehr anpassen können.

**Q: Ist Aspose.Tasks sowohl für kleine als auch für Unternehmens‑Projekte geeignet?**  
A: In der Tat, Aspose.Tasks ist darauf ausgelegt, den Bedürfnissen von Entwicklern gerecht zu werden, die an Projekten jeder Größe arbeiten, von einzelnen Aufgaben bis hin zu groß angelegten Unternehmensprojekten.

---

**Zuletzt aktualisiert:** 2026-04-03  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}