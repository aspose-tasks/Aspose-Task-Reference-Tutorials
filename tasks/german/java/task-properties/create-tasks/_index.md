---
date: 2026-09-25
description: Erfahren Sie, wie Sie in Java mit Aspose.Tasks einen Projektzeitplan
  erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie Zusammenfassungsaufgaben hinzufügen,
  die Projekt‑Hierarchie verwalten und das Dokumentenverzeichnis effizient festlegen.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Aufgaben in Aspose.Tasks erstellen
og_description: Erfahren Sie, wie Sie in Java mit Aspose.Tasks einen Projektzeitplan
  erstellen. Folgen Sie Schritt‑für‑Schritt‑Anleitungen, um Zusammenfassungsaufgaben
  hinzuzufügen, die Hierarchie zu verwalten und das Dokumentenverzeichnis festzulegen.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Wie man einen Projektzeitplan mit Aspose.Tasks für Java erstellt
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Wie man einen Projektzeitplan mit Aspose.Tasks für Java erstellt
url: /de/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So erstellen Sie einen Projektplan mit Aspose.Tasks für Java

## Einführung
In diesem Tutorial lernen Sie, wie Sie **Projektplan erstellen** in einer Java‑Anwendung mithilfe von Aspose.Tasks. Egal, ob Sie eine einfache To‑Do‑Liste oder einen komplexen Unternehmens‑Planer bauen, die nachfolgenden Schritte führen Sie durch das Hinzufügen von Zusammenfassungsaufgaben, das Verwalten der Projekt‑Hierarchie und das Festlegen des Dokumentverzeichnisses – alles mit klaren, ausführbaren Code‑Snippets. Am Ende haben Sie einen vollständig strukturierten Plan, der weiter bearbeitet oder exportiert werden kann.

## Schnelle Antworten
- **Was verwaltet Aspose.Tasks?** Es verwaltet Aufgabenhierarchien, Ressourcen, Kalender und Projektdateiformate (MS‑Project, Primavera usw.).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose temporäre Lizenz funktioniert für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche Java-Version wird unterstützt?** Java 8 und neuer werden vollständig unterstützt.  
- **Kann ich benutzerdefinierte Felder zu Aufgaben hinzufügen?** Ja, Sie können Aufgaben mit benutzerdefinierten Feldern über die API erweitern.  
- **Gibt es integrierte Unterstützung für Gantt‑Diagramme?** Aspose.Tasks kann in PDF/HTML exportieren, die Gantt‑Visualisierungen enthalten.

## Was ist ein Projektplan in Aspose.Tasks?
Ein Projektplan ist die vollständige Menge von Aufgaben, Abhängigkeiten und Zeitplänen, die definieren, wie die Arbeit ausgeführt wird. Aspose.Tasks speichert diese Informationen in einem `Project`‑Objekt, das Sie lesen, ändern und in verschiedenen Formaten speichern können. Es enthält Start‑ und Enddaten, Einschränkungen und Ressourcen‑Zuweisungen und ermöglicht umfassende Planung und Berichterstellung.

## Warum Aspose.Tasks für das Java‑Projektmanagement verwenden?
Aspose.Tasks unterstützt **30+ Eingabe‑ und Ausgabeformate** und kann Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was hohe Leistung für groß angelegte Java‑Projektmanagement‑Szenarien liefert.

## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
- **Java Development Kit (JDK)** – JDK 8 oder höher auf Ihrem Rechner installiert.  
- **Aspose.Tasks für Java Bibliothek** – Laden Sie die Bibliothek von [Aspose.Tasks für Java Download](https://releases.aspose.com/tasks/java/) herunter und installieren Sie sie.  
- **Integrierte Entwicklungsumgebung (IDE)** – Verwenden Sie Eclipse, IntelliJ IDEA oder eine andere Java‑freundliche IDE Ihrer Wahl.

## Pakete importieren
`Project`, `Task` und verwandte Klassen befinden sich im Namensraum `com.aspose.tasks`. Importieren Sie sie am Anfang Ihrer Java‑Datei:

Die `Project`‑Klasse stellt einen vollständigen Projektplan dar und bietet Methoden zum Manipulieren von Aufgaben und Ressourcen.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Die `Project`‑Klasse ist der Einstiegspunkt für alle Operationen an einer Projektdatei.

## So erstellen Sie einen Projektplan mit Aspose.Tasks?

Laden Sie eine neue `Project`‑Instanz, setzen Sie das Dokumentverzeichnis und beginnen Sie mit dem Hinzufügen von Aufgaben. Dieser direkte Abschnitt erklärt den Kernablauf: Sie erstellen ein `Project`, konfigurieren dessen `RootFolder` (das Dokumentverzeichnis) und fügen dann eine Zusammenfassungsaufgabe gefolgt von Unteraufgaben hinzu. Alle Änderungen bleiben im Speicher, bis Sie `save` aufrufen, um den Plan in einer Datei zu persistieren.

### Schritt 1: Dokumentverzeichnis festlegen
Definieren Sie, wohin die resultierende Projektdatei geschrieben wird. Das frühe Festlegen des Verzeichnisses stellt sicher, dass alle nachfolgenden Speicher‑Operationen einen konsistenten Pfad verwenden.

Die `RootFolder`‑Eigenschaft gibt den Basisordner an, aus dem Projektdateien gelesen oder in den sie geschrieben werden.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Schritt 2: Neues Projekt erstellen
Instanziieren Sie ein frisches `Project`‑Objekt, das Ihren Plan aufnehmen wird. Optional können Sie einen bereits vorhandenen Dateipfad übergeben, um einen bestehenden Plan zu laden und zu ändern.

Der `Project`‑Konstruktor erstellt einen leeren Plan, bereit für das Hinzufügen von Aufgaben.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Schritt 3: Zusammenfassende Aufgabe hinzufügen
Eine zusammenfassende Aufgabe gruppiert verwandte Unteraufgaben und erscheint als zusammenklappbarer Knoten in Gantt‑Diagrammen. Verwenden Sie die `Task`‑Klasse und setzen Sie `IsSummary` auf `true`.

Die `addTask`‑Methode erstellt eine neue Aufgabe unter einem angegebenen Elternteil und gibt deren ID zurück.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 4: Unteraufgabe hinzufügen
Unteraufgaben erben Start‑/Enddaten von ihrer übergeordneten zusammenfassenden Aufgabe, sofern Sie diese nicht überschreiben. Das Hinzufügen einer Unteraufgabe ist so einfach wie ein erneuter Aufruf von `addTask` mit Angabe der Eltern‑ID.

Ein Aufruf von `addTask` mit einer Eltern‑ID fügt eine Unteraufgabe unter dieser zusammenfassenden Aufgabe hinzu.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Fügen Sie nach Bedarf so viele Aufgaben und Unteraufgaben hinzu, wie Ihr Projekt erfordert. Jeder Schritt trägt zum Aufbau einer strukturierten Projekt‑Hierarchie bei, die nach MS‑Project, PDF oder anderen unterstützten Formaten exportiert werden kann.

## Häufige Probleme und Lösungen
- **Problem:** “Document directory not found.”  
  **Lösung:** Vergewissern Sie sich, dass der Pfad, den Sie `RootFolder` zuweisen, im Dateisystem existiert und dass Ihr Java‑Prozess Schreibrechte hat.
- **Problem:** Unteraufgaben erscheinen nicht unter der zusammenfassenden Aufgabe.  
  **Lösung:** Stellen Sie sicher, dass Sie beim Aufruf von `addTask` die korrekte Eltern‑Aufgaben‑ID übergeben. Die API verlangt die Eltern‑ID als zweites Argument.
- **Problem:** Große Projekte verursachen OutOfMemoryError.  
  **Lösung:** Aspose.Tasks verarbeitet Aufgaben im Streaming‑Modus; erhöhen Sie die JVM‑Heap‑Größe (`-Xmx2g`) oder teilen Sie den Plan in mehrere Dateien auf.

## Häufig gestellte Fragen
**F: Ist Aspose.Tasks für klein‑skalige Projekte geeignet?**  
A: Absolut. Die Bibliothek skaliert von einer einzelnen Aufgabenliste bis zu Unternehmens‑Plänen mit tausenden von Aufgaben.

**F: Wo finde ich detaillierte Dokumentation für Aspose.Tasks für Java?**  
A: Siehe die Dokumentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**F: Wie erhalte ich eine temporäre Lizenz für Aspose.Tasks?**  
A: Besuchen Sie die [temporary license request page](https://purchase.aspose.com/temporary-license/) für eine zeitlich begrenzte Lizenz, die für Entwicklung und Tests funktioniert.

**F: Kann ich Aufgabenattribute mit Aspose.Tasks anpassen?**  
A: Ja, Sie können Aufgaben mit benutzerdefinierten Feldern erweitern, Ressourcen zuweisen und Kalender programmgesteuert ändern.

**F: Gibt es eine Support‑Community für Aspose.Tasks‑Nutzer?**  
A: Absolut! Treten Sie der Aspose.Tasks‑Community im [the support forum](https://forum.aspose.com/c/tasks/15) bei.

---

**Zuletzt aktualisiert:** 2026-09-25  
**Getestet mit:** Aspose.Tasks 24.12 für Java  
**Autor:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Verwandte Tutorials

- [Projektstartdatum in MS Project mit Aspose.Tasks für Java festlegen](/tasks/java/project-properties/write-project-info/)
- [Aufgabenabhängigkeiten im Projektmanagement mit Aspose.Tasks erstellen](/tasks/java/task-links/create-task-link/)
- [Wie man Ressourcen zum Projekt hinzufügt und Ressourcen‑Zuweisungen in Aspose.Tasks erstellt](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}