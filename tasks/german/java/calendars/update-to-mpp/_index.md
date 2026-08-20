---
date: 2026-08-13
description: Erfahren Sie, wie Sie Feiertage zu einem Kalender hinzufügen, den Kalender
  einem Projekt zuweisen und die MS Project‑Datei mit Aspose.Tasks für Java als MPP
  speichern.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Kalender in MPP‑Format mit Aspose.Tasks aktualisieren
og_description: Feiertage zum Kalender hinzufügen, ihn einem Projekt zuweisen und
  den Zeitplan mit Aspose.Tasks für Java in MPP konvertieren. Erfahren Sie die schrittweise
  Automatisierung.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Feiertage zum Kalender hinzufügen und als MPP mit Aspose.Tasks speichern
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Feiertage zum Kalender hinzufügen und als MPP mit Aspose.Tasks speichern
url: /de/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feiertage zum Kalender hinzufügen und als MPP mit Aspose.Tasks speichern

## Einführung

In der modernen Projektverwaltung müssen Sie häufig **add holidays to calendar**-Dateien hinzufügen, einen **MS Project calendar** erstellen und dann den Zeitplan im nativen MPP-Format teilen. Egal, ob Sie Zeitpläne aus mehreren Quellen konsolidieren oder Altdaten migrieren, das programmatische Erzeugen eines Kalenders eliminiert manuelle Fehler und beschleunigt die Bereitstellung. Dieses Tutorial führt Sie durch den gesamten Prozess, einen Kalender in MS Project zu erstellen, ihn mit Feiertagen anzupassen, **assign calendar to project** und schließlich **convert project to MPP** mithilfe der Aspose.Tasks Java API.

## Schnelle Antworten
- **What does this tutorial cover?** Hinzufügen von Feiertagen zu einem Kalender, Zuweisen zu einem Projekt und Speichern des Ergebnisses als MPP-Datei mit Aspose.Tasks für Java.  
- **Do I need a license?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Which Java version is required?** Java 8 oder höher (JDK 8+).  
- **Can I customize the calendar?** Ja – Sie können Arbeitszeiten, Ausnahmen und Feiertage hinzufügen.  
- **How long does implementation take?** Etwa 10‑15 Minuten für einen einfachen Kalender.  

## Was bedeutet „create calendar MS Project“?

Das Erstellen eines calendar MS Project bedeutet, die Arbeitstage, -stunden und Ausnahmen zu definieren, die die Aufgabenplanung in einer Microsoft Project-Datei steuern. Mit Aspose.Tasks können Sie diesen Kalender programmgesteuert erstellen, Feiertage festlegen und in ein Projekt einbetten, ohne die MS Project-Benutzeroberfläche zu öffnen.

## Warum Aspose.Tasks für diese Aufgabe verwenden?

Sie sollten Aspose.Tasks verwenden, weil es vollständige Java-Kompatibilität bietet, kein Microsoft Office benötigt und Ihnen ermöglicht, native MPP-Dateien direkt aus dem Code zu erzeugen und zu speichern. Die Bibliothek unterstützt alle Kalenderfunktionen, funktioniert in jeder Serverumgebung und verarbeitet Projekte mit bis zu 10.000 Aufgaben in weniger als einer Sekunde.

## Voraussetzungen

1. **Java Development Kit (JDK) 8+** – stellen Sie sicher, dass `java -version` 1.8 oder neuer ausgibt.  
2. **Aspose.Tasks for Java** – laden Sie die neueste JAR von der [Aspose website](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  
4. **Basic Java knowledge** – Vertrautheit mit Klassen, Methoden und Datei‑I/O.

## So fügen Sie Feiertage zum Kalender hinzu

Um Feiertage hinzuzufügen, erstellen Sie ein neues `Calendar`‑Objekt, rufen dessen `Exceptions`‑Sammlung ab und fügen `DateException`‑Einträge für jedes Feiertagsdatum hinzu. `DateException` stellt ein einzelnes nicht‑arbeitendes Datum oder einen Zeitraum in einem Kalender dar. Aspose.Tasks behandelt diese Daten dann als Nicht‑Arbeitstage, sodass Aufgaben um die definierten Feiertage herum geplant werden.

### Schritt 1: Erforderliche Pakete importieren

Zuerst bringen Sie die Aspose.Tasks‑Klassen und Java‑Hilfsprogramme in den Gültigkeitsbereich.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Schritt 2: Datenverzeichnis einrichten

Definieren Sie, wo Ihre Eingabevorlage und Ausgabedateien gespeichert werden. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Eingabe‑ und Ausgabedateinamen festlegen

Wir laden eine vorhandene MPP‑Datei (oder ein leeres Projekt) und schreiben das Ergebnis in eine neue Datei.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Schritt 4: Projekt laden und einen neuen Kalender hinzufügen

Die Klasse `Project` repräsentiert eine MS‑Project‑Datei im Speicher und bietet Zugriff auf deren Kalender, Aufgaben und Ressourcen.

Erstellen Sie eine `Project`‑Instanz aus der Quelldatei und fügen Sie einen Kalender mit dem Namen **„Calendar 1“** hinzu.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Schritt 5: Kalender anpassen (optional)

Das `Calendar`‑Objekt definiert Arbeitstage, -stunden und Ausnahmen für einen Projektzeitplan.

Wenn Sie spezifische Arbeitszeiten, Feiertage oder Ausnahmen benötigen, rufen Sie Ihre eigene Hilfsmethode auf. Das Beispiel verwendet `GetTestCalendar` als Platzhalter.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Sie können `cal1.getWeekDays()` direkt manipulieren, um die Arbeitsstunden für jeden Wochentag festzulegen, oder `cal1.getExceptions()` verwenden, um **add holidays to calendar**.

### Schritt 6: Kalender dem Projekt zuweisen

Weisen Sie dem Projekt mit, den neu erstellten Kalender für alle seine Planungsberechnungen zu verwenden.

```java
project.set(Prj.CALENDAR, cal1);
```

### Schritt 7: Projekt als MPP speichern

Die Aufzählung `SaveFileFormat` gibt das Ausgabeformat an, wobei `Mpp` das native Microsoft‑Project‑Format bezeichnet.

Jetzt **convert project to MPP**, indem Sie es mit der Option `SaveFileFormat.Mpp` speichern.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Schritt 8: Erfolgreichen Abschluss bestätigen

Eine einfache Konsolennachricht zeigt an, dass der Vorgang ohne Fehler abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

## Häufige Anwendungsfälle

- **Automated schedule generation** für wiederkehrende Projekte (z. B. wöchentliche Sprints).  
- **Migrating legacy CSV or Excel calendars** in eine voll ausgestattete MS‑Project‑Datei.  
- **Server‑side reporting**, bei dem ein Webservice auf Anfrage eine MPP‑Datei zurückgibt.  

## Fehlerbehebung & häufige Stolperfallen

| Problem | Ursache | Lösung |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` verweist auf einen nicht vorhandenen Ordner | Stellen Sie sicher, dass das Verzeichnis existiert oder erstellen Sie es programmgesteuert. |
| Calendar not applied to tasks | Aufgaben verweisen weiterhin auf den Standardkalender | Nach dem Setzen von `Prj.CALENDAR` aktualisieren Sie auch das `Task.CALENDAR` jeder Aufgabe, falls diese zuvor überschrieben wurden. |
| Output file is 0 KB | Fehlende Schreibberechtigungen | Führen Sie die JVM mit den entsprechenden Dateisystemrechten aus oder wählen Sie einen beschreibbaren Pfad. |

## Häufig gestellte Fragen

**Q: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?**  
A: Ja, Aspose.Tasks unterstützt alle Microsoft‑Project‑Dateiformate von Project 2007 bis Project 2024 und deckt mehr als 10 Versionen ab.

**Q: Kann ich Kalender an spezifische Projektanforderungen anpassen?**  
A: Absolut. Sie können Arbeitstage definieren, benutzerdefinierte Arbeitswochen festlegen, Feiertage hinzufügen und sogar mehrere Kalender innerhalb einer einzigen Projektdatei erstellen.

**Q: Bietet Aspose.Tasks für Java Unterstützung bei der Fehlerbehebung und Hilfe?**  
A: Ja, Sie können Hilfe im Aspose.Tasks Community‑Forum erhalten [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?**  
A: Ja, eine voll funktionsfähige Testversion ist verfügbar [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?**  
A: Temporäre Lizenzen können über die Aspose-Website angefordert werden [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Zuletzt aktualisiert:** 2026-08-13  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/calendars/create/)
- [Wie man Wochentage in MS Project-Kalendern definiert – Aspose.Tasks Java](/tasks/java/calendars/)
- [Benutzerdefinierte Kalenderausnahmen erstellen mit Aspose.Tasks für Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}