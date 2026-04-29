---
date: 2026-01-18
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java einen Projektmanagement‑Baseline
  planen, sodass Sie Projektbaselines verwalten und geplante mit tatsächlichen Fortschritten
  vergleichen können.
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projektmanagement‑Baseline – Aufgabenplanung mit Aspose.Tasks
url: /de/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektmanagement-Baseline – Aufgabenplanung mit Aspose.Tasks

## Einführung in die Projektmanagement-Baseline
Die Verwaltung einer **Projektmanagement-Baseline** ist ein Grundpfeiler eines effektiven Projektmanagements. Sie ermöglicht es Ihnen, den ursprünglichen Plan zu erfassen und später den **geplanten vs. tatsächlichen Fortschritt** zu vergleichen, sodass Sie Abweichungen frühzeitig erkennen können. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Terminierung von Aufgaben‑Baselines mit Aspose.Tasks für Java und geben Ihnen die Werkzeuge, um **Projekt‑Baselines** sicher zu **verwalten** und Ihre Projekte auf Kurs zu halten.

## Schnelle Antworten
- **Was stellt eine Projektmanagement-Baseline dar?**  
  Die Baseline zeichnet den ursprünglichen Zeitplan, die Kosten und den Umfang für spätere Abweichungsanalysen auf.  
- **Welche Bibliothek übernimmt die Baseline‑Planung in Java?**  
  Aspose.Tasks für Java bietet eine robuste API zum Erstellen und Verwalten von Baselines.  
- **Benötige ich eine Lizenz, um den Code auszuführen?**  
  Eine kostenlose Testversion reicht für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Was sind die wichtigsten Voraussetzungen?**  
  Java Development Kit (JDK) und die Aspose.Tasks für Java‑Bibliothek.  
- **Kann ich Baseline‑Daten nach dem Setzen einsehen?**  
  Ja – verwenden Sie das `TaskBaseline`‑Objekt, um Start-, End- und Dauerwerte zu lesen.

## Was ist eine Projektmanagement-Baseline?
Eine Projektmanagement‑Baseline erfasst die genehmigte Version des Projektzeitplans, des Budgets und des Umfangs zu Beginn der Ausführung. Sie dient als Referenzpunkt zur Messung der Leistung und zur Identifizierung von Abweichungen während des gesamten Projektlebenszyklus.

## Warum Aspose.Tasks für die Baseline‑Planung verwenden?
Aspose.Tasks bietet eine reine Java‑API, die ohne installierten Microsoft Project funktioniert. Sie ermöglicht es Ihnen, **eine Projektinstanz zu erstellen**, Aufgaben zu definieren, Baselines zu setzen und Baseline‑Informationen programmgesteuert abzurufen – ideal für automatisierte Berichte oder die Integration in benutzerdefinierte PM‑Tools.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:

### Java-Entwicklungsumgebung
Stellen Sie sicher, dass das Java Development Kit (JDK) auf Ihrem System installiert ist. Sie können das JDK von der [Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen und installieren.

### Aspose.Tasks für Java‑Bibliothek
Laden Sie die Aspose.Tasks für Java‑Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter und binden Sie sie in Ihr Java‑Projekt ein.

## Pakete importieren
Beginnen Sie damit, die erforderlichen Pakete in Ihr Java‑Projekt zu importieren:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte:

## Schritt 1: Eine neue Projektinstanz erstellen
```java
Project project = new Project();
```

## Schritt 2: Eine Aufgabe definieren und Baseline setzen
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Schritt 3: Auf Baseline‑Informationen zugreifen
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Schritt 4: Baseline‑Dauer anzeigen
```java
System.out.println(baseline.getDuration().toString());
```

## Schritt 5: Baseline‑Startdatum anzeigen
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Schritt 6: Baseline‑Enddatum anzeigen
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

Durch das Befolgen dieser Schritte können Sie Aspose.Tasks für Java effektiv nutzen, um **Projekt‑Baselines** in Ihren Projekten zu **verwalten**.

## Häufige Probleme und Lösungen
- **Baseline nicht gesetzt:** Stellen Sie sicher, dass Sie `project.setBaseline(BaselineType.Baseline)` **nach** dem Hinzufügen von Aufgaben aufrufen; andernfalls ist die Baseline‑Sammlung leer.
- **Null‑Werte:** Wenn `task.getBaselines()` eine leere Liste zurückgibt, prüfen Sie, ob die Aufgabe zur Projekt‑Hierarchie hinzugefügt wurde, bevor Sie die Baseline setzen.
- **Datumsformat:** Die Methoden `getStart()` und `getFinish()` geben `Date`‑Objekte zurück. Verwenden Sie einen Formatter, wenn Sie ein benutzerdefiniertes Anzeigeformat benötigen.

## FAQ
### Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
Ja, Aspose.Tasks für Java bietet robuste Fähigkeiten, um Projekte unterschiedlicher Komplexität effizient zu verwalten.

### Ist Aspose.Tasks für Java mit anderen Java‑Bibliotheken kompatibel?
Absolut, Aspose.Tasks für Java lässt sich nahtlos in andere Java‑Bibliotheken integrieren und erweitert Ihre Projektmanagement‑Fähigkeiten.

### Kann ich Aufgaben‑Baselines mit Aspose.Tasks für Java anpassen?
Natürlich bietet Aspose.Tasks für Java umfangreiche Funktionen, um Aufgaben‑Baselines gemäß Ihren Projektanforderungen anzupassen und zu verwalten.

### Gibt es eine Testversion von Aspose.Tasks für Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von der [Release‑Seite](https://releases.aspose.com/) erhalten.

### Wo finde ich Support für Aspose.Tasks für Java?
Bei Fragen oder Unterstützung können Sie das Aspose.Tasks‑Forum [hier](https://forum.aspose.com/c/tasks/15) besuchen.

## Häufig gestellte Fragen

**F: Wie erstelle ich eine neue Projektinstanz in Aspose.Tasks?**  
A: Instanziieren Sie die Klasse `Project` (`Project project = new Project();`). Dadurch wird eine neue Projektdatei erstellt, die bereit für Aufgaben und Baselines ist.

**F: Was ist der Unterschied zwischen `BaselineType.Baseline` und anderen Baseline‑Typen?**  
A: `BaselineType.Baseline` bezieht sich auf die primäre Baseline (Baseline 1). Aspose.Tasks unterstützt außerdem Baseline 2‑10 für weitere Schnappschüsse.

**F: Kann ich die Baseline‑Daten nach Excel oder CSV exportieren?**  
A: Ja, Sie können über `TaskBaseline`‑Objekte iterieren und die Werte mit Standard‑Java‑I/O in eine CSV‑Datei schreiben.

**F: Wirkt sich das Setzen einer Baseline auf bestehende Aufgabendaten aus?**  
A: Das Setzen einer Baseline erfasst die aktuellen Daten, ändert jedoch nicht den aktiven Zeitplan der Aufgabe. Sie können Start‑/Enddaten nach dem Setzen der Baseline weiterhin anpassen.

**F: Ist es möglich, mehrere Baselines programmgesteuert zu vergleichen?**  
A: Absolut. Rufen Sie jede Baseline über `task.getBaselines().get(index)` ab und vergleichen Sie deren Eigenschaften `Start`, `Finish` und `Duration`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-18  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose