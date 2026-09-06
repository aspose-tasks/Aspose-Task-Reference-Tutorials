---
date: 2026-08-29
description: Erfahren Sie, wie Sie Baseline-Daten lesen und Aufgaben mit Aspose.Tasks
  für Java planen, um den geplanten mit dem tatsächlichen Fortschritt effizient zu
  vergleichen.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Baseline-Aufgabenplanung in Aspose.Tasks
og_description: Erfahren Sie, wie Sie Baseline-Daten lesen und Aufgaben mit Aspose.Tasks
  für Java planen, um den geplanten und tatsächlichen Fortschritt präzise zu vergleichen.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Wie man Baselines liest und Aufgaben plant mit Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Wie man Baselines liest und Aufgaben plant mit Aspose.Tasks
url: /de/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Baselines liest und Aufgaben plant mit Aspose.Tasks

In diesem Leitfaden erfahren Sie **wie man Baselines liest** Informationen und Aufgaben programmgesteuert mit Aspose.Tasks für Java plant. Am Ende des Tutorials können Sie den ursprünglichen Projektplan erfassen, ihn mit dem tatsächlichen Fortschritt vergleichen und Abweichungsberichte erstellen – und das, ohne Microsoft Project installiert zu haben.

## Einführung in die Projektmanagement‑Baseline

Die Verwaltung einer **Projektmanagement‑Baseline** ist ein Grundpfeiler eines effektiven Projektmanagements. Sie ermöglicht es Ihnen, den ursprünglichen Plan zu erfassen und später **geplanten vs. tatsächlichen Fortschritt** zu vergleichen, sodass Sie Abweichungen frühzeitig erkennen können. In diesem Tutorial führen wir Sie durch das Planen von Aufgaben‑Baselines mit Aspose.Tasks für Java und geben Ihnen die Werkzeuge, um **Projektbaselines** sicher zu verwalten und Ihre Projekte auf Kurs zu halten.

## Schnelle Antworten
- **Was stellt eine Projektmanagement‑Baseline dar?**  
  Sie zeichnet den genehmigten Zeitplan, die Kosten und den Umfang zu Projektbeginn auf und liefert eine Referenz für Abweichungsanalysen.  
- **Welche Bibliothek übernimmt die Baseline‑Planung in Java?**  
  Aspose.Tasks für Java bietet eine reine Java‑API, die mehr als 45 Eingabe‑ und Ausgabeformate unterstützt und Projekte mit bis zu 100 000 Aufgaben verarbeitet.  
- **Benötige ich eine Lizenz, um den Code auszuführen?**  
  Eine kostenlose Testversion funktioniert zum Testen; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Was sind die wichtigsten Voraussetzungen?**  
  Java Development Kit (JDK) 11+ und die Aspose.Tasks‑Bibliothek für Java.  
- **Kann ich Baseline‑Daten nach dem Setzen einsehen?**  
  Ja – verwenden Sie das `TaskBaseline`‑Objekt, um Start‑, End‑ und Dauerwerte zu lesen.

## Was ist eine Projektmanagement‑Baseline?
Eine Projektmanagement‑Baseline zeichnet den genehmigten Zeitplan, das Budget und den Umfang zu Beginn der Ausführung auf. Sie dient als Referenzpunkt zur Messung der Leistung und zur Identifizierung von Abweichungen im gesamten Projektlebenszyklus. Sie enthält die geplanten Start‑ und Enddaten, die Gesamtkosten und Detailangaben zum Umfang und liefert damit einen umfassenden Schnappschuss für zukünftige Vergleiche.

## Warum Aspose.Tasks für die Baseline‑Planung verwenden?
Aspose.Tasks bietet eine reine Java‑API, die ohne installierten Microsoft Project funktioniert. Sie unterstützt **mehr als 45 Eingabe‑ und Ausgabeformate**, kann Projekte mit **bis zu 100 000 Aufgaben** im speichereffizienten Modus verarbeiten und stellt integrierte Methoden zum Lesen und Schreiben von Baseline‑Daten bereit – wodurch automatisierte Berichte und Integration unkompliziert werden.

## Voraussetzungen
- **Java Development Kit (JDK)** – Installieren Sie JDK 11 oder höher. Sie können es von der [Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen.  
- **Aspose.Tasks für Java Bibliothek** – Laden Sie die neueste Version von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter und fügen Sie die JAR-Datei Ihrem Projekt‑Klassenpfad hinzu.

## Pakete importieren
Die Klassen `Project`, `Task` und `TaskBaseline` befinden sich im Namensraum `com.aspose.tasks`. Importieren Sie sie am Anfang Ihrer Quelldatei:

Die Klasse `Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne Projektdatei im Speicher repräsentiert. Sie bietet Zugriff auf Aufgaben, Ressourcen und Baseline‑Sammlungen.

## Wie liest man Baselines?
Laden Sie das Projekt und fragen Sie anschließend die `TaskBaseline`‑Sammlung für jede Aufgabe ab. Das `TaskBaseline`‑Objekt liefert den Baseline‑Start, das Ende und die Dauer, die beim Aufruf von `setBaseline` erfasst wurden. Dieser direkte Ansatz ermöglicht das Auslesen von Baseline‑Werten, ohne XML‑ oder Binärdateien zu parsen.

## Schritt 1: Neues Projekt‑Objekt erstellen
Die Klasse `Project` repräsentiert die gesamte Projektdatei im Speicher.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Schritt 2: Aufgabe definieren und Baseline setzen
`Task` repräsentiert ein einzelnes Arbeitselement, und `setBaseline` erfasst dessen aktuellen Zeitplan als Baseline.
```java
Project project = new Project();
```

## Schritt 3: Auf Baseline‑Informationen zugreifen
`TaskBaseline` enthält die gespeicherten Start‑, End‑ und Dauerwerte einer Baseline.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Schritt 4: Baseline‑Dauer anzeigen
`Duration` stellt die Zeitdauer einer Aufgabe oder Baseline dar.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Schritt 5: Baseline‑Startdatum anzeigen
`Start` ist das geplante Anfangsdatum der Baseline.
```java
System.out.println(baseline.getDuration().toString());
```

## Schritt 6: Baseline‑Enddatum anzeigen
`Finish` ist das geplante Abschlussdatum der Baseline.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Häufige Probleme und Lösungen
- **Baseline nicht gesetzt:** Stellen Sie sicher, dass Sie `project.setBaseline(BaselineType.Baseline)` **nach** dem Hinzufügen von Aufgaben aufrufen; andernfalls ist die Baseline‑Sammlung leer.  
- **Null‑Werte:** Wenn `task.getBaselines()` eine leere Liste zurückgibt, prüfen Sie, ob die Aufgabe vor dem Setzen der Baseline zur Projekt‑Hierarchie hinzugefügt wurde.  
- **Datumsformat:** Die Methoden `getStart()` und `getFinish()` geben `java.util.Date`‑Objekte zurück. Verwenden Sie `SimpleDateFormat`, wenn Sie ein benutzerdefiniertes Anzeigeformat benötigen.

## Häufig gestellte Fragen

**F: Wie erstelle ich ein neues Projekt‑Objekt in Aspose.Tasks?**  
A: Instanziieren Sie die Klasse `Project` (`Project project = new Project();`). Dies erzeugt eine neue Projektdatei, die bereit für Aufgaben und Baselines ist.

**F: Was ist der Unterschied zwischen `BaselineType.Baseline` und anderen Baseline‑Typen?**  
A: `BaselineType.Baseline` bezieht sich auf die primäre Baseline (Baseline 1). Aspose.Tasks unterstützt außerdem Baseline 2‑10 für zusätzliche Schnappschüsse.

**F: Kann ich die Baseline‑Daten nach Excel oder CSV exportieren?**  
A: Ja, Sie können über `TaskBaseline`‑Objekte iterieren und die Werte mit Standard‑Java‑I/O in eine CSV‑Datei schreiben.

**F: Beeinflusst das Setzen einer Baseline die bestehenden Aufgabendaten?**  
A: Das Setzen einer Baseline erfasst die aktuellen Daten, ändert jedoch nicht den aktiven Zeitplan der Aufgabe. Sie können Start‑/Enddaten nach dem Setzen der Baseline weiterhin anpassen.

**F: Ist es möglich, mehrere Baselines programmgesteuert zu vergleichen?**  
A: Absolut. Rufen Sie jede Baseline über `task.getBaselines().get(index)` ab und vergleichen Sie deren `Start`-, `Finish`‑ und `Duration`‑Eigenschaften.

---

**Zuletzt aktualisiert:** 2026-08-29  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Verwandte Tutorials

- [Aufgabenliste in Java erstellen – MS Project Baseline mit Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Wie man Baseline‑Dauer in Aspose.Tasks für Java festlegt](/tasks/java/task-baselines/task-baseline-duration/)
- [MPP‑Projekt in Java erstellen – Aufgabenfortschritt mit Aspose.Tasks ändern](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}