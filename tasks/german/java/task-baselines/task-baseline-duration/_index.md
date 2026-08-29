---
date: 2026-08-29
description: Erfahren Sie, wie Sie die Basisliniendauer festlegen und den Projektfortschritt
  mit Aspose.Tasks for Java verfolgen. Dieser Schritt‑für‑Schritt‑Leitfaden hilft
  Ihnen, Aufgabenbaselines effizient zu verwalten.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Wie man die Basisliniendauer in Aspose.Tasks for Java festlegt
og_description: Erfahren Sie, wie Sie die Basisliniendauer festlegen und den Projektfortschritt
  mit Aspose.Tasks for Java verfolgen. Folgen Sie diesem ausführlichen Leitfaden,
  um Aufgabenbaselines effizient zu verwalten.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Wie man die Basisliniendauer festlegt, um den Projektfortschritt zu verfolgen
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Wie man die Basisliniendauer festlegt, um den Projektfortschritt zu verfolgen
url: /de/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Basislänge festlegt, um den Projektfortschritt zu verfolgen

## Einführung
Die Verfolgung des Projektfortschritts beginnt mit einer soliden Basislinie. In diesem Tutorial erfahren Sie **wie man die Basislänge** für Aufgaben in Microsoft Project‑Dateien mithilfe der Aspose.Tasks‑Bibliothek für Java festlegt und verstehen, warum das frühe Festlegen einer Basislinie Ihnen hilft, Terminabweichungen, Kostenabweichungen und Ressourcenüberbelegung während des gesamten Projektlebens zu überwachen.

## Schnelle Antworten
- **Was bedeutet „set baseline“?** Sie zeichnet den ursprünglichen Start, das Ende und die Dauer einer Aufgabe auf, sodass Sie zukünftige Änderungen vergleichen können.  
- **Welche Aspose.Tasks‑Klasse erstellt ein Projekt?** Die `Project`‑Klasse – Sie lernen außerdem, wie man **eine Projektinstanz** korrekt **erstellt**.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Evaluierungslizenz funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Zwischensummen‑Basislinien abrufen?** Ja, Aspose.Tasks ermöglicht das Abfragen von Zwischensummen‑Basislinien und deren Fixkosten.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher wird empfohlen.  
- **Wie hilft mir das, den Projektfortschritt zu verfolgen?** Sobald die Basislinie festgelegt ist, können Sie mithilfe integrierter Reporting‑Funktionen sofort die tatsächlichen Termine mit dem ursprünglichen Plan vergleichen.

## Was ist eine Aufgaben‑Basislinie und warum sie festlegen?
Eine Aufgaben‑Basislinie erfasst den geplanten Zeitplan (Startdatum, Enddatum und Dauer) zu einem bestimmten Zeitpunkt. Durch das Festlegen einer Basislinie schaffen Sie einen Referenzpunkt, der es einfach macht, Terminabweichungen, Kostenüberschreitungen und Ressourcenüberbelegung zu erkennen, während das Projekt fortschreitet.

## Warum Aspose.Tasks für die Basislinienverwaltung verwenden?
Aspose.Tasks bietet **volle .mpp‑Kompatibilität** – Sie können native Microsoft‑Project‑Dateien lesen und schreiben, ohne Microsoft Office installiert zu haben. Die API gibt Ihnen programmgesteuerten Zugriff auf **mehr als 50 Eingabe‑ und Ausgabeformate**, unterstützt **Zwischensummen‑Basislinien 1‑10** und kann **Projekte mit mehreren hundert Seiten** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was für leistungsstarke Batch‑Verarbeitung unerlässlich ist.

## Voraussetzungen
1. **Java‑Entwicklungsumgebung** – JDK 8+ installiert und konfiguriert.  
2. **Aspose.Tasks für Java** – Laden Sie die Bibliothek von der [Aspose.Tasks für Java Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE oder Build‑Tool** – Maven, Gradle oder jede bevorzugte IDE.

## Pakete importieren
Die folgenden Importe bringen die Kernklassen von Aspose.Tasks, die für die Arbeit mit Projekten, Aufgaben, Basislinien und zeitbezogenen Daten benötigt werden.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Schritt 1: Projektinstanz erstellen
Die `Project`‑Klasse repräsentiert eine Microsoft‑Project‑Datei im Speicher und ist der Einstiegspunkt für alle Vorgänge.

```java
Project project = new Project();
```

## Schritt 2: Aufgaben‑Basislinie erstellen
Ein `TaskBaseline` speichert den geplanten Start, das geplante Ende und die Dauer für eine bestimmte Aufgabe.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Schritt 3: Aufgaben‑Basisliniendaten anzeigen
Die Methode `getBaselines()` gibt die Sammlung von Basislinien zurück, die einer Aufgabe zugeordnet sind.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Schritt 4: Zwischensummen‑Basislinie und Fixkosten prüfen
`BaselineType` enumeriert die primären und Zwischensummen‑Basislinien (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Schritt 5: Zeitbezogene Daten ausgeben
`TimephasedData` stellt ein Stück Planungsinformation für ein bestimmtes Zeitintervall dar.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Durch Befolgen dieser Schritte können Sie **die Basislänge** für jede Aufgabe festlegen und detaillierte Basisliniendaten mit Aspose.Tasks für Java abrufen, was Ihnen eine zuverlässige Methode bietet, **den Projektfortschritt** während des gesamten Projektlebenszyklus zu verfolgen.

## Häufige Probleme und Lösungen
- **Basislinie erscheint nicht in MS Project:** Stellen Sie sicher, dass Sie `project.setBaseline(BaselineType.Baseline)` **nach** dem Hinzufügen der Aufgabe aufgerufen haben.  
- **NullPointerException bei `getBaselines()`:** Vergewissern Sie sich, dass die Aufgabe dem Projekt hinzugefügt wurde, bevor die Basislinie gesetzt wird.  
- **Zeit‑einheit‑Mismatch:** Verwenden Sie `TimeUnitType`, um die Dauer korrekt zu formatieren, insbesondere bei benutzerdefinierten Kalendern.

## FAQ

### Was ist eine Aufgaben‑Basislinie in MS Project?
Eine Aufgaben‑Basislinie in MS Project ist ein Schnappschuss des ursprünglich geplanten Zeitplans für eine Aufgabe, einschließlich Startdatum, Enddatum und Dauer.

### Warum ist das Verwalten von Aufgaben‑Basislinien wichtig?
Das Verwalten von Aufgaben‑Basislinien hilft beim Vergleich des geplanten Zeitplans mit dem tatsächlichen Projektfortschritt und erleichtert so die Nachverfolgung und Entscheidungsfindung.

### Kann ich eine Aufgaben‑Basislinie nach dem Festlegen ändern?
Ja, Sie können Aufgaben‑Basislinien in MS Project ändern, um Änderungen im Projektplan widerzuspiegeln. Es ist jedoch wichtig, alle Abweichungen von der ursprünglichen Basislinie zu dokumentieren.

### Unterstützt Aspose.Tasks weitere Projektmanagement‑Funktionalitäten?
Ja, Aspose.Tasks bietet eine breite Palette von Funktionen für das Projektmanagement, einschließlich Aufgabenplanung, Ressourcenallokation und Gantt‑Diagrammerstellung.

### Wo finde ich Unterstützung für Aspose.Tasks?
Sie finden Unterstützung für Aspose.Tasks im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15), wo Sie Fragen stellen und mit anderen Benutzern interagieren können.

## Weitere häufig gestellte Fragen
**F: Muss ich `setBaseline` für jede Aufgabe einzeln aufrufen?**  
**A: Nein. Der Aufruf von `project.setBaseline(BaselineType.Baseline)` zeichnet die Basislinie für alle Aufgaben im Projekt gleichzeitig auf.**

**F: Wie kann ich eine Zwischensummen‑Basislinie für eine bestimmte Aufgabe festlegen?**  
**A: Verwenden Sie `project.setBaseline(BaselineType.Baseline1)` (oder Baseline2‑Baseline10) nach der Aktualisierung des Aufgabenplans.**

**F: Ist es möglich, die Basisliniendaten in CSV zu exportieren?**  
**A: Ja. Iterieren Sie über `task.getBaselines()` und schreiben Sie die gewünschten Felder mit Standard‑Java‑I/O in eine CSV‑Datei.**

**F: Kann ich eine vorhandene .mpp‑Datei lesen, die bereits Basislinien enthält?**  
**A: Absolut. Laden Sie die Datei mit `new Project("myproject.mpp")` und greifen Sie dann wie oben gezeigt auf die Basislinien jeder Aufgabe zu.**

**F: Unterstützt Aspose.Tasks Multi‑Projekt‑Dateien?**  
**A: Aspose.Tasks arbeitet mit Einzel‑Projekt‑.mpp‑Dateien. Für Multi‑Projekt‑Szenarien kombinieren Sie die Projekte programmgesteuert.**

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Verwandte Tutorials

- [Aufgabenliste in Java erstellen – MS Project‑Basislinie mit Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [MPP‑Projekt in Java erstellen – Aufgabenfortschritt mit Aspose.Tasks ändern](/tasks/java/task-properties/change-progress/)
- [Projektmanagement‑Basislinie – Aufgabenplanung mit Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}