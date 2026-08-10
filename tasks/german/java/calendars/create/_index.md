---
date: 2026-08-03
description: Erfahren Sie, wie Sie einen MS Project-Kalender erstellen, einen Kalender
  zu einem Projekt hinzufügen und das Projekt mit Aspose.Tasks für Java als XML speichern.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Kalender zum Projekt hinzufügen mit Aspose.Tasks
og_description: Erstellen Sie einen MS Project-Kalender programmgesteuert mit Aspose.Tasks
  für Java. Fügen Sie Kalender hinzu, passen Sie Zeitpläne an und exportieren Sie
  in wenigen Minuten als XML.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Erstellen Sie einen MS Project-Kalender mit Aspose.Tasks für Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Erstellen Sie einen MS Project-Kalender mit Aspose.Tasks für Java
url: /de/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie einen MS Project-Kalender mit Aspose.Tasks für Java

## Einleitung
In modernen Projekt‑Management‑Workflows kann die Möglichkeit, **ms project calendar erstellen** programmgesteuert zu **erstellen**, Stunden manueller Bearbeitung sparen. Aspose.Tasks für Java bietet Ihnen eine saubere, typensichere API zum Manipulieren von Microsoft Project‑Dateien, ohne den Desktop‑Client zu öffnen. In diesem Tutorial lernen Sie, wie man einen Kalender hinzufügt, wie man einen MS Project‑Kalender erstellt und wie man das Projekt als XML speichert – alles mit nur wenigen Zeilen Java‑Code.

## Schnelle Antworten
- **Was bedeutet „create ms project calendar“?**  
  Es bedeutet, eine neue Arbeitszeitdefinition (Kalender) in eine Microsoft Project‑Datei per Code einzufügen.  
- **Welche Bibliothek übernimmt das?**  
  Aspose.Tasks für Java stellt die Klasse `Calendar` und den Container `Project` zur Verwaltung von Kalendern bereit.  
- **Benötige ich eine Lizenz?**  
  Eine temporäre Evaluierungslizenz funktioniert für Tests; für den Produktionseinsatz ist eine Volllizenz erforderlich.  
- **Kann ich die Datei als XML speichern?**  
  Ja – verwenden Sie `SaveFileFormat.Xml`, um das Projekt als XML‑Datei zu exportieren.  
- **Was sind die Voraussetzungen?**  
  Java JDK 8+ und das Aspose.Tasks‑für‑Java‑JAR in Ihrem Klassenpfad.

## Was ist create ms project calendar?
Das Erstellen eines MS Project‑Kalenders bedeutet, programmgesteuert eine neue Kalenderdefinition zu einer Projektdatei hinzuzufügen, Arbeitstage, Ausnahmen und tägliche Arbeitsstunden festzulegen und diesen Kalender dann Aufgaben, Ressourcen oder dem gesamten Projekt zuzuweisen, sodass die Terminberechnungen die definierte Arbeitszeit berücksichtigen.

## Warum Aspose.Tasks für Java verwenden, um einen Kalender zum Projekt hinzuzufügen?
Sie sollten Aspose.Tasks für Java verwenden, weil es eine vollständig typensichere API bietet, die ohne installierten Microsoft Project funktioniert, alle wichtigen Project‑Versionen (2007‑2021, über 5 Releases) unterstützt und in XML, MPP und **10+** weitere Formate exportieren kann, wodurch die automatisierte Massen‑Kalendererstellung auf jedem Server ermöglicht wird.

## Voraussetzungen
- **Java Development Kit (JDK) 8 oder neuer** installiert und konfiguriert.  
- **Aspose.Tasks for Java** Bibliothek – von der [offiziellen Website](https://releases.aspose.com/tasks/java/) herunterladen und das JAR zum Klassenpfad Ihres Projekts hinzufügen.  
- Eine IDE oder ein Build‑Tool (Maven/Gradle) Ihrer Wahl.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Importieren Sie das erforderliche Aspose.Tasks‑Paket
Zuerst bringen Sie die Aspose.Tasks‑Klassen in den Gültigkeitsbereich, damit Sie mit Projekten und Kalendern arbeiten können.

```java
import com.aspose.tasks.*;
```

### Schritt 2: Legen Sie den Pfad zum Datenverzeichnis fest
Definieren Sie, wo die erzeugte Projektdatei geschrieben wird. Ersetzen Sie den Platzhalter durch einen absoluten oder relativen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Erstellen Sie eine neue Project‑Instanz
`Project` ist die Kernklasse, die eine Microsoft Project‑Datei im Speicher repräsentiert.

```java
Project prj = new Project();
```

### Schritt 4: Definieren Sie die Kalender, die Sie hinzufügen möchten
`Calendar` definiert einen Zeitplan mit Arbeitstagen, Ausnahmen und Arbeitszeiten für ein Projekt.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro Tipp:** Nach dem Hinzufügen eines Kalenders können Sie dessen Arbeitstage mit `cal1.getWeekDays().add(...)` anpassen und die täglichen Arbeitsstunden mit `cal1.getBaseCalendar().setWorkingTime(...)` festlegen.

### Schritt 5: Speichern Sie das Projekt (Projekt als XML speichern)
`SaveFileFormat.Xml` weist Aspose.Tasks an, das Projekt im XML‑Format zu schreiben.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Schritt 6: Zeigen Sie eine Abschlussnachricht an
Informieren Sie den Benutzer, dass der Vorgang erfolgreich abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

Durch das Befolgen dieser sechs kurzen Schritte haben Sie erfolgreich **einen Kalender zu einem Projekt hinzugefügt** und das Ergebnis als XML‑Datei gespeichert.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|---------|-------|--------|
| **`NullPointerException` bei `prj.getCalendars()`** | Projektobjekt nicht korrekt initialisiert. | Stellen Sie sicher, dass `new Project()` aufgerufen wird, bevor Sie auf Kalender zugreifen. |
| **Datei nicht gefunden beim Speichern** | `dataDir` verweist auf einen nicht existierenden Ordner. | Erstellen Sie das Verzeichnis zuerst oder verwenden Sie einen absoluten Pfad. |
| **Kalendername erscheint als „no info“** | Platzhalternamen wurden im Beispiel verwendet. | Ersetzen Sie sie durch aussagekräftige Namen, die den Zeitplan widerspiegeln (z. B. „US Holiday Calendar“). |
| **Gespeichertes XML kann nicht in MS Project geöffnet werden** | Verwendung einer veralteten Aspose.Tasks‑Version. | Aktualisieren Sie auf die neueste Aspose.Tasks‑für‑Java‑Version. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks komplexe Kalender mit mehreren Ausnahmen verarbeiten?**  
A: Ja – nach dem Hinzufügen eines Kalenders können Sie Ausnahmen, Arbeitszeiten und arbeitsfreie Tage mithilfe der Klassen `WeekDay` und `Exception` definieren.

**F: Ist es möglich, den neuen Kalender bestimmten Aufgaben zuzuweisen?**  
A: Absolut. Rufen Sie eine Aufgabe über `prj.getRootTask().getChildren().add("Task Name")` ab und setzen Sie `task.set(Tsk.CALENDAR, cal3);`.

**F: Unterstützt die Bibliothek das Speichern in anderen Formaten wie MPP?**  
A: Ja. Ersetzen Sie `SaveFileFormat.Xml` durch `SaveFileFormat.Mpp` oder `SaveFileFormat.P6`, je nach Bedarf; Aspose.Tasks unterstützt **12** Ausgabeformate.

**F: Benötige ich eine Lizenz für Entwicklungs‑Builds?**  
A: Eine temporäre Evaluierungslizenz reicht für Tests aus; für Produktions‑Deployments ist eine Volllizenz erforderlich.

**F: Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?**  
A: Das Aspose.Tasks‑Community‑Forum ist eine ausgezeichnete Ressource: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Zuletzt aktualisiert:** 2026-08-03  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Wochentage in MS Project‑Kalender definiert – Aspose.Tasks Java](/tasks/java/calendars/)
- [Wie man Projektkalender in Java mit Aspose.Tasks festlegt](/tasks/java/calendars/properties/)
- [Erstellen benutzerdefinierter Kalenderausnahmen mit Aspose.Tasks für Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}