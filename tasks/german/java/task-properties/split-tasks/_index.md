---
date: 2026-02-26
description: Erfahren Sie, wie Sie Aufgaben mit Aspose.Tasks für Java aufteilen –
  der umfassende Leitfaden zum Aufteilen von Aufgaben, Festlegen des Projektkalenders
  und Erstellen von Ressourcen‑Zuweisungen.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Aufgaben in Aspose.Tasks aufteilt
url: /de/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Aufgaben in Aspose.Tasks aufteilt

## Einleitung
Wenn Sie nach **wie man Aufgaben aufteilt** in einem Java‑basierten Projekt suchen, sind Sie hier genau richtig. Aspose.Tasks for Java bietet Ihnen eine saubere, programmatische Möglichkeit, eine langlaufende Aufgabe in kleinere, handhabbare Teile zu zerlegen, was bei der Ressourcenlevelung, genauen Berichterstellung und strafferen Projektzeitplänen hilft. In diesem Tutorial führen wir Sie durch den gesamten Prozess – vom Einrichten des Projektkalenders über das Erstellen einer Ressourcen‑Zuweisung bis hin zum Aufteilen der Aufgabe in mehrere Segmente.

## Schnelle Antworten
- **Was ist Aufgabenaufteilung?** Aufteilen einer einzelnen Aufgabe in mehrere kleinere Intervalle bei gleichzeitiger Beibehaltung ihrer Gesamtdauer.  
- **Warum Aufgaben in Java aufteilen?** Es ermöglicht eine präzise Ressourcenallokation und bessere Fortschrittsverfolgung.  
- **Welche Bibliothek hilft?** Aspose.Tasks for Java stellt integrierte Methoden zum Aufteilen und Zeitphasen‑Management bereit.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Die Bibliothek funktioniert mit Java 8 und neuer.

## Voraussetzungen
Bevor Sie in das Tutorial eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Tasks for Java Bibliothek heruntergeladen und zu Ihrem Projekt hinzugefügt. Sie können sie von der [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) herunterladen.

## Pakete importieren
Beginnen Sie damit, die erforderlichen Pakete in Ihr Java‑Projekt zu importieren:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Schritt 1: Neues Projekt erstellen
Beginnen Sie damit, ein neues Projekt mit der Aspose.Tasks‑Bibliothek zu erstellen:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Schritt 2: Projektkalender festlegen
Das Festlegen des **Projektkalenders** definiert Arbeitstage, Feiertage und den Gesamtablauf Ihres Zeitplans. Dieser Schritt ist für genaue zeitphasenbasierte Berechnungen unerlässlich.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Schritt 3: Root‑Aufgabe hinzufügen
Jedes Projekt benötigt einen Root‑Container. Das Hinzufügen einer Root‑Aufgabe bietet Ihnen einen Ort, an dem Sie alle nachfolgenden Aufgaben anhängen können.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Schritt 4: Neue Aufgabe zum Aufteilen hinzufügen
Erstellen Sie die Aufgabe, die Sie aufteilen möchten. Hier setzen wir als Beispiel eine Dauer von drei Tagen.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Schritt 5: Ressourcen‑Zuweisung erstellen
Eine **Ressourcen‑Zuweisung** verknüpft eine Ressource (oder einen Platzhalter) mit der Aufgabe. Dies ist erforderlich, bevor zeitphasenbasierte Daten generiert werden.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Schritt 6: Zeitphasen‑Daten generieren
Zeitphasen‑Daten zeigen, wie die Arbeit über die Dauer der Aufgabe verteilt ist. Das Generieren dieser Daten bereitet die Aufgabe auf das Aufteilen vor.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Schritt 7: Aufgabe aufteilen
Jetzt **teilen wir die Aufgabe in Teile**. In diesem Beispiel teilen wir die dreitägige Aufgabe in drei eintägige Segmente.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Warum Aufgaben aufteilen?
Das Aufteilen von Aufgaben gibt Ihnen eine feinere Kontrolle über:
- **Ressourcenleveling:** Unterschiedliche Ressourcen jedem Segment zuweisen.  
- **Fortschrittsverfolgung:** Status pro Segment aktualisieren.  
- **Berichterstellung:** Detailliertere Gantt‑Diagramme und Berichte erzeugen.

## Häufige Probleme und Lösungen
- **Fehlende Kalenderdaten:** Stellen Sie sicher, dass Sie `timephasedDataFromTaskDuration` vor dem Aufteilen aufrufen.  
- **Null‑Dauer‑Segmente:** Prüfen Sie, dass jedes geteilte Intervall eine von Null verschiedene Dauer hat; andernfalls wird es von der Bibliothek ignoriert.  
- **Lizenzausnahmen:** Das Ausführen ohne gültige Lizenz kann ein Wasserzeichen zu exportierten Dateien hinzufügen.

## Häufig gestellte Fragen
### Kann ich Aufgaben mit unterschiedlichen Dauern aufteilen?
Ja, Sie können die Dauer jedes Teils an Ihre Projektanforderungen anpassen.

### Ist Aspose.Tasks for Java mit allen Java‑Versionen kompatibel?
Aspose.Tasks for Java ist so konzipiert, dass es nahtlos mit Java 8 und neuer funktioniert und somit eine breite Kompatibilität gewährleistet.

### Kann ich Aspose.Tasks for Java kostenlos nutzen?
Aspose.Tasks for Java bietet eine kostenlose Testversion, mit der Sie die Funktionen vor einem Kauf ausprobieren können.

### Wie kann ich Support für Aspose.Tasks for Java erhalten?
Besuchen Sie das [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15), um Unterstützung zu erhalten und sich mit der Community zu vernetzen.

### Benötige ich eine temporäre Lizenz für Aspose.Tasks for Java?
Sie können eine temporäre Lizenz über [diesen Link](https://purchase.aspose.com/temporary-license/) für Test‑ und Evaluierungszwecke erhalten.

---

**Zuletzt aktualisiert:** 2026-02-26  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}