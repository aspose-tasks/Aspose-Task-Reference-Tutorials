---
date: 2026-07-29
description: Erfahren Sie, wie Sie Nichtarbeitstage planen, indem Sie einen Projektkalender
  mit Aspose.Tasks for Java erstellen, weekday exceptions definieren und holiday schedules
  verwalten.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Nichtarbeitstage planen – Projektkalender erstellen Aspose
og_description: Nichtarbeitstage mit Aspose.Tasks for Java planen. Erfahren Sie, wie
  Sie weekdays definieren, calendar exceptions hinzufügen und holiday schedules effizient
  verwalten.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Nichtarbeitstage planen – Projektkalender erstellen Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Nichtarbeitstage planen – Projektkalender erstellen Aspose
url: /de/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nichtarbeitstage planen – Projektkalender mit Aspose erstellen

### Einleitung
Wenn Sie **Nichtarbeitstage planen** für ein Projekt, müssen Sie in der Lage sein, Feiertage, besondere Schichten oder vorübergehende Schließungen direkt im Projektplan zu modellieren. Aspose.Tasks für Java gibt Ihnen die volle Kontrolle über Kalenderdefinitionen und ermöglicht das Hinzufügen von Ausnahmen, die real‑weltliche Zeitpläne widerspiegeln. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Definition von Wochentagen für Kalenderausnahmen, damit Ihre Projektzeitpläne genau und zuverlässig bleiben. Am Ende sehen Sie auch, wie dies in eine umfassendere **Strategie für Nichtarbeitstage** für jedes Unternehmensprojekt passt.

## Schnelle Antworten
- **Was bedeutet „schedule non working days“?**  
  Es bedeutet, Aspose.Tasks zu verwenden, um einen Kalender zu erstellen, der bestimmte Daten als nicht‑arbeitend markiert und dadurch die Aufgabendaten automatisch beeinflusst.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?**  
  Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDEs werden unterstützt?**  
  IntelliJ IDEA, Eclipse, NetBeans oder jede IDE, die Java 8+ unterstützt.  
- **Kann ich mehrere Ausnahmen zum selben Kalender hinzufügen?**  
  Ja – Sie können beliebig viele `CalendarException`‑Objekte hinzufügen.  
- **In welchen Dateiformaten kann ich das Projekt speichern?**  
  XML, MPP und mehrere andere von Aspose.Tasks unterstützte Formate.  

## Was ist ein Projektkalender in Aspose.Tasks?
Der **project calendar** ist das Top‑Level‑Objekt von Aspose.Tasks, das Arbeitstage und -stunden für ein Projekt definiert. Er beeinflusst direkt Start‑/Enddaten von Aufgaben, Ressourcenzuweisungen und Gesamtabrechnungen des Zeitplans. Durch die Anpassung eines Kalenders stellen Sie sicher, dass der Zeitplan reale Einschränkungen wie Firmenfeiertage oder Wochenendarbeitsrichtlinien berücksichtigt.

## Warum Wochentage für Kalenderausnahmen definieren?
Die Definition von Wochentagsausnahmen stellt sicher, dass die Projekt-Engine diese Tage als nicht‑arbeitend behandelt, wodurch Aufgaben nicht automatisch an diesen Tagen geplant werden und der Zeitplan mit realen Einschränkungen wie Feiertagen, Wartungsfenstern oder speziellen Schichtmustern in der gesamten Organisation übereinstimmt.

- **Genauere Zeitpläne:** Aufgaben werden nicht an Feiertagen oder Sperrzeiten eingeplant.  
- **Ressourcenplanung:** Ressourcen werden nur an gültigen Arbeitstagen zugewiesen, wodurch Überbelegungen vermieden werden.  
- **Compliance:** Zeitpläne folgen automatisch den Unternehmensrichtlinien oder gesetzlichen Feiertagskalendern.  

## Nichtarbeitstage‑Planung mit Kalenderausnahmen
Wenn Sie einen **Nichtarbeitstage‑Plan** pflegen, haben Sie in der Regel eine Masterliste von Feiertagen, Wartungsfenstern oder anderen Sperrzeiten. Das Hinzufügen dieser Daten als `CalendarException`‑Objekte garantiert, dass jede Berechnung – sei es die Kritische‑Pfad‑Analyse oder die Ressourcen‑Leveling – diese Einschränkungen automatisch berücksichtigt. Dieser Ansatz eliminiert manuelle Datumsanpassungen und reduziert das Risiko von Planabweichungen.

## Voraussetzungen
1. **Java Development Kit (JDK)** – Version 8 oder höher.  
2. **Aspose.Tasks for Java** – Download von der offiziellen [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Eine IDE** – IntelliJ IDEA, Eclipse, NetBeans oder jeder Java‑kompatible Editor.  

## Wie man Nichtarbeitstage mit Kalenderausnahmen plant
Laden Sie Ihr Projekt, erstellen Sie einen benutzerdefinierten Kalender und fügen Sie `CalendarException`‑Objekte hinzu, die die gewünschten Wochentage als nicht‑arbeitend markieren. Dieser gesamte Vorgang kann in wenigen einfachen Schritten abgeschlossen werden, und der resultierende Kalender beeinflusst automatisch die gesamte Aufgabenzuweisungslogik.

### Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Erforderliche Pakete importieren
Wir benötigen die Kernklassen von Aspose.Tasks und Javas `GregorianCalendar` für die Datumsverarbeitung.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Schritt 2: Datenverzeichnis definieren
Geben Sie an, wo die erzeugte Projektdatei gespeichert werden soll.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Projektinstanz erstellen
`Project` ist das Hauptobjekt, das alle Projektdaten enthält, einschließlich Aufgaben, Ressourcen und Kalender.

```java
Project project = new Project();
```

### Schritt 4: Kalender definieren
`Calendar` stellt einen Zeitplan für Arbeits- und Nichtarbeitszeiten innerhalb eines Projekts dar.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Schritt 5: Wochentagsausnahme definieren
`CalendarException` repräsentiert einen Zeitraum, der in einem Kalender als nicht‑arbeitend markiert ist.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Schritt 6: Projekt speichern
Speichern Sie das Projekt, einschließlich des benutzerdefinierten Kalenders und seiner Ausnahme, in einer XML‑Datei.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Ausnahmedaten nicht angewendet** | Stellen Sie sicher, dass `setEnteredByOccurrences(false)` und korrekte `FromDate/ToDate`‑Werte verwendet werden. |
| **Gespeicherte Datei ist leer** | Vergewissern Sie sich, dass `dataDir` auf einen beschreibbaren Ordner zeigt und der Dateiname mit `.xml` endet. |
| **Kalender wird bei der Aufgabenzuweisung nicht berücksichtigt** | Weisen Sie den Kalender Aufgaben oder Ressourcen zu, indem Sie `task.setCalendar(cal)` oder `resource.setCalendar(cal)` verwenden. |

## Häufig gestellte Fragen

**Q: Kann ich mehrere Ausnahmen für verschiedene Wochentage im selben Kalender definieren?**  
A: Ja. Fügen Sie zusätzliche `CalendarException`‑Objekte zu `cal.getExceptions()` für jeden einzelnen Zeitraum oder jede Regel hinzu.

**Q: Ist Aspose.Tasks für Java mit verschiedenen Java‑IDEs kompatibel?**  
A: Absolut. Die Bibliothek funktioniert mit IntelliJ IDEA, Eclipse, NetBeans und jeder IDE, die Standard‑Java‑Projekte unterstützt.

**Q: Kann ich Ausnahmearten außer täglichen Ausnahmen anpassen?**  
A: Ja. Verwenden Sie `CalendarExceptionType.Weekly`, `Monthly` oder `Yearly`, um Ihren Planungsanforderungen gerecht zu werden.

**Q: Wie kann ich Ausnahmen dynamisch basierend auf Projektanforderungen handhaben?**  
A: Erstellen Sie die Ausnahmeobjekte programmgesteuert – z. B. Feiertage aus einer Datenbank oder Konfigurationsdatei auslesen und in einer Schleife `CalendarException`‑Instanzen erzeugen.

**Q: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von der [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) herunterladen.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt, wie Sie **Nichtarbeitstage planen** können, indem Sie einen Projektkalender erstellen und Wochentagsausnahmen definieren, die Feiertage oder besondere Nichtarbeitsperioden genau widerspiegeln. Eine korrekte Kalenderkonfiguration ist entscheidend für realistische Zeitpläne, Ressourcenzuweisungen und den Gesamterfolg eines Projekts. Erkunden Sie weiter, indem Sie den benutzerdefinierten Kalender Aufgaben oder Ressourcen zuweisen und mit anderen Ausnahmetypen experimentieren, um einen umfassenden **Nichtarbeitstage‑Plan** für jedes Projekt zu erstellen.

---

**Zuletzt aktualisiert:** 2026-07-29  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/calendars/create/)
- [Kalenderausnahme in Aspose für Java erstellen](/tasks/java/calendar-exceptions/add-remove/)
- [Wie man Kalender festlegt und Wochentage in MS Project mit Aspose.Tasks definiert](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}