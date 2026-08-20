---
date: 2026-08-13
description: Erfahren Sie, wie Sie Arbeitswochen aus einem MS Project-Kalender mit
  Aspose.Tasks für Java auslesen. Folgen Sie der Schritt-für-Schritt-Anleitung mit
  Code-Beispielen und Tipps zur Fehlerbehebung.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Arbeitswochen aus dem Kalender mit Aspose.Tasks lesen
og_description: Wie Sie Arbeitswochen aus einem MS Project-Kalender mit Aspose.Tasks
  für Java auslesen. Folgen Sie dem kompakten Tutorial mit Einrichtungsschritten,
  Code-Snippets und Tipps zur Fehlerbehebung.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: So lesen Sie Arbeitswochen aus dem MS-Kalender mit Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: So lesen Sie Arbeitswochen aus dem MS-Kalender mit Aspose.Tasks
url: /de/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Arbeitswochen aus dem MS-Kalender mit Aspose.Tasks liest

## Einführung
In diesem Tutorial **lernen Sie, wie man Arbeitswochen** aus einem Microsoft Project‑Kalender mithilfe der Aspose.Tasks‑Bibliothek für Java ausliest. Egal, ob Sie ein Reporting‑Dashboard erstellen, Zeitpläne mit einem ERP‑System synchronisieren oder die Datenextraktion für Analysen automatisieren, der programmgesteuerte Zugriff auf Arbeitswochen‑Definitionen spart unzählige manuelle Stunden. Aspose.Tasks unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann mehrseitige Projektdateien verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was Ihnen sowohl Flexibilität als auch Leistung bietet.

## Schnelle Antworten
- **Was bedeutet „Arbeitswochen lesen“?** Es bezieht sich auf das Extrahieren von Arbeitswochen‑Definitionen (Daten und tägliche Arbeitszeit‑Regeln) aus einer Projektdatei mittels Java‑Code.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (kostenlose Testversion verfügbar).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine Testversion funktioniert für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Dateiformate werden unterstützt?** Sowohl *.mpp*‑ als auch Project‑XML‑Dateien werden verarbeitet, plus über 50 weitere Formate für Import/Export.  
- **Wie lange dauert die Implementierung?** In der Regel unter 10 Minuten, sobald die Bibliothek eingerichtet ist.

## Was ist eine Arbeitswoche in MS Project?
Eine Arbeitswoche definiert die Kalenderregeln, die festlegen, wann Ressourcen in einem bestimmten Zeitraum verfügbar sind. Sie enthält ein Startdatum, ein Enddatum und tägliche Arbeitszeit‑Intervalle (z. B. 9 Uhr–17 Uhr). In MS Project kann jeder Kalender mehrere Arbeitswochen enthalten, sodass Sie Feiertage, Schichtpläne oder saisonale Zeitpläne modellieren können.

## Wie liest Aspose.Tasks Arbeitswochen aus einem Kalender?
Aspose.Tasks stellt die `WorkWeekCollection` eines `Calendar`‑Objekts bereit. Durch Erzeugen einer `Project`‑Instanz, Auswahl des gewünschten Kalenders (nach UID oder Name) und Iteration über dessen `WorkWeekCollection` können Sie das Label jeder Arbeitswoche, den gültigen Datumsbereich und die detaillierten täglichen Arbeitszeit‑Slots abrufen. Die API übernimmt alle Datums‑ und Zeitkonvertierungen und berücksichtigt automatisch die Zeitzoneneinstellungen des Projekts.

## Warum Arbeitswochen in Java aus einem Microsoft Project‑Kalender lesen?
Das programmgesteuerte Auslesen von Arbeitswochen eliminiert manuelles Kopieren‑Einfügen, stellt sicher, dass nachgelagerte Systeme (ERP, HR, Reporting) exakt dieselben Planungsregeln verwenden, und gewährleistet Konsistenz über mehrere Projekte hinweg. Automatisierung reduziert zudem menschliche Fehler und beschleunigt Integrationspipelines, insbesondere wenn Sie jede Nacht Dutzende von Projektdateien verarbeiten müssen.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder höher installiert.  
2. **Aspose.Tasks für Java** – Laden Sie das neueste JAR von der offiziellen Seite herunter: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Eine **Beispiel‑Projektdatei** (`ReadWorkWeeksInformation.mpp`) in einem bekannten Ordner auf Ihrem Rechner abgelegt.

## Pakete importieren
Zuerst importieren Sie die Klassen, die wir für die Interaktion mit Kalendern und Arbeitswochen benötigen:

`Project` repräsentiert eine Microsoft Project‑Datei, `Calendar` stellt deren Kalender bereit, `WorkWeek` definiert eine Arbeitswoche und `WeekDay` steht für einen Tag.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der die `.mpp`‑Datei enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner:

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Project‑Instanz erstellen und auf den Kalender zugreifen
Die Klasse `Project` repräsentiert eine Microsoft Project‑Datei und bietet Zugriff auf deren Datenstrukturen, einschließlich Kalender, Aufgaben und Ressourcen.  
Instanziieren Sie ein `Project`‑Objekt, wählen Sie den gewünschten Kalender (nach UID) und erhalten Sie dessen `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro‑Tipp:** Wenn Sie sich nicht sicher sind, welche Kalender‑UID verwendet werden soll, iterieren Sie über `project.getCalendars()` und geben Sie zunächst den Namen und die UID jedes Kalenders aus.

## Schritt 3: Durch Arbeitswochen iterieren
Die Klasse `WorkWeek` kapselt eine Arbeitswochen‑Definition, die Start‑/Enddaten und tägliche Arbeitszeiteinstellungen enthält.  
Durchlaufen Sie jede `WorkWeek`, um deren Namen, Start‑/Enddaten und die täglichen Arbeitszeiten anzuzeigen:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Was Sie sehen werden:** Die Konsole gibt das Label jeder Arbeitswoche (z. B. „Standard“), deren gültigen Datumsbereich aus, und Sie können bis zu den genauen Arbeitsstunden für jeden Tag herunterbrechen.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|-----|
| `NullPointerException` beim Zugriff auf `calendar` | Falsche UID oder Kalender existiert nicht | Überprüfen Sie die UID mit `project.getCalendars().size()` und listen Sie zuerst die verfügbaren Kalender auf. |
| Keine Ausgabe für Arbeitswochen | Der ausgewählte Kalender hat keine benutzerdefinierten Arbeitswochen (verwendet Standard) | Verwenden Sie den Standardkalender (`project.getDefaultCalendar()`) oder erstellen Sie eine Arbeitswoche programmgesteuert. |
| Datumsformat sieht seltsam aus | `System.out.println` verwendet das Standardformat von `java.util.Date` | Verwenden Sie ein `SimpleDateFormat`, um Datumswerte nach Bedarf zu formatieren. |

## Häufig gestellte Fragen
**F: Kann ich die Arbeitswochen‑Informationen mit Aspose.Tasks für Java ändern?**  
A: Ja. Die API bietet `addWorkWeek()`, `removeWorkWeek()` und Property‑Setter, um Namen, Daten und Arbeitszeiten zu ändern.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut. Es unterstützt MPP‑Dateien von Project 98 bis zu den neuesten Versionen sowie Project‑XML‑Dateien.

**F: Kann ich Aspose.Tasks in andere Java‑Frameworks integrieren?**  
A: Ja. Die Bibliothek ist reines Java, sodass Sie sie zusammen mit Spring, Jakarta EE oder jedem anderen Framework verwenden können.

**F: Gibt es eine Testversion von Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose 30‑Tage‑Testversion von der offiziellen Seite herunterladen: [Aspose.Tasks trial](https://releases.aspose.com/).

**F: Wo finde ich Support für Aspose.Tasks?**  
A: Das Aspose‑Community‑Forum ist die beste Anlaufstelle: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Zuletzt aktualisiert:** 2026-08-13  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung die neueste)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/calendars/create/)
- [Kalenderausnahmen mit Aspose.Tasks abrufen – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Wie man Kalender festlegt und Wochentage in MS Project mit Aspose.Tasks definiert](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}