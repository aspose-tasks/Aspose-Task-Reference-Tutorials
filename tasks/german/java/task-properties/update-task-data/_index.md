---
date: 2026-03-03
description: Erfahren Sie, wie Sie Aufgabendaten mit Aspose.Tasks Java in das MPP‑Format
  aktualisieren. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung für ein effizientes
  Projektmanagement.
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Aufgabendaten in MPP-Format aktualisieren
url: /de/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aufgaben­daten auf MPP-Format aktualisieren in Aspose.Tasks

## Einführung
Willkommen zu unserer Schritt‑für‑Schritt‑Anleitung zum **Aktualisieren von Aufgabendaten in das MPP‑Format mit Aspose.Tasks für Java**. In diesem Tutorial lernen Sie, wie Sie Projektdateien programmgesteuert mit *aspose tasks java* manipulieren, von der Erstellung einer Zusammenfassungsaufgabe bis hin zur Konvertierung eines XML‑Projekts in eine MPP‑Datei. Am Ende können Sie Projektaufgaben effizient verwalten und die Lösung in Ihre Java‑Anwendungen integrieren.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Aktualisieren von Aufgabendaten und Speichern eines Projekts als MPP mit Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder Voll‑Lizenz erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Welches IDE eignet sich am besten?** Jedes Java‑IDE (IntelliJ IDEA, Eclipse, VS Code) funktioniert.  
- **Kann ich XML nach MPP konvertieren?** Ja – das Beispiel lädt ein XML‑Projekt und speichert es als MPP.  
- **Wie viele Aufgaben werden erstellt?** Das Beispiel erstellt eine Hauptaufgabe, eine Zusammenfassungsaufgabe und zehn weitere Aufgaben.

## Was ist Aspose.Tasks für Java?
Aspose.Tasks für Java ist eine leistungsstarke API, die Entwicklern das Lesen, Schreiben und Ändern von Microsoft‑Project‑Dateien (MPP, XML und mehr) ermöglicht, ohne dass Microsoft Project installiert sein muss. Sie unterstützt die vollständige Projekt‑Ebene‑Manipulation, einschließlich Aufgabenerstellung, Constraint‑Verarbeitung und Dateiformat‑Konvertierung.

## Warum Aspose.Tasks Java für das Projektmanagement verwenden?
- **Vollständige Kontrolle** über Aufgabeneigenschaften wie Startdatum, Dauer und Constraints.  
- **Nahtlose Konvertierung** zwischen XML und MPP, wodurch die Integration in bestehende Projekt‑Daten‑Pipelines ermöglicht wird.  
- **Kein COM‑Interop** – reines Java, ideal für plattformübergreifende Umgebungen.  
- **Hohe Leistung** bei großen Projektdateien, wodurch es sich für Unternehmens‑Lösungen eignet.

## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Tasks für Java: Stellen Sie sicher, dass die Aspose.Tasks‑Bibliothek installiert ist. Sie können sie von der [release page](https://releases.aspose.com/tasks/java/) herunterladen.
- Java Development Kit (JDK): Vergewissern Sie sich, dass Java auf Ihrem System installiert ist.
- Integrated Development Environment (IDE): Verwenden Sie ein IDE Ihrer Wahl für die Java‑Entwicklung.

## Pakete importieren
Beginnen Sie damit, die notwendigen Pakete in Ihr Java‑Projekt zu importieren. Das folgende Snippet zeigt, wie Pakete importiert werden:

```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```

## Wie man eine Zusammenfassungsaufgabe erstellt
Eine Zusammenfassungsaufgabe gruppiert verwandte Unteraufgaben und bietet Ihnen eine Übersicht über Arbeitspakete. Im Code unten erstellen wir eine Zusammenfassungsaufgabe und hängen die erste Aufgabe als Kind an sie an.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## Wie man das Startdatum für eine Aufgabe festlegt
Das Festlegen des Startdatums ist für eine genaue Terminplanung unerlässlich. Das Beispiel verwendet eine `Calendar`‑Instanz, um den Projektstart zu definieren, und weist sie der Aufgabe zu.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## Wie man XML nach MPP konvertiert
Die API kann eine XML‑Projektdatei lesen und direkt als MPP‑Datei speichern, wodurch eine einfache Migration von Legacy‑Formaten ermöglicht wird.

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## Wie man Fristen festlegt und Aufgabennotizen hinzufügt
Fristen helfen, Aufgaben im Zeitplan zu halten, während Notizen Kontext für Teammitglieder bieten.

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## Wie man Aufgabenkonstanten konfiguriert und die Aufgabendauer aktualisiert
Constraints wie *Finish No Later Than* leiten den Scheduler. Sie können zudem das Dauernformat ändern, um geschätzte Tage widerzuspiegeln.

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## Wie man zusätzliche Aufgaben erstellt (Verwaltung von Projektaufgaben)
Die nachfolgende Schleife demonstriert, wie mehrere Aufgaben programmgesteuert erzeugt werden – ein häufiges Szenario beim Import von Massendaten.

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## Wie man das Projekt speichert (Export nach MPP)
Zum Schluss speichern Sie das Projekt als MPP‑Datei, um die Änderungen zu persistieren.

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

Durch das Befolgen dieser Schritte haben Sie **Aufgabendaten auf MPP‑Format mit aspose tasks java aktualisiert**. Sie verfügen nun über eine solide Grundlage für die Verwaltung von Projektaufgaben, das Erstellen von Zusammenfassungsaufgaben, das Festlegen von Startdaten und das Konvertieren von XML‑Projekten nach MPP.

## Fazit
Herzlichen Glückwunsch! Sie haben einen umfassenden Leitfaden zum Aktualisieren von Aufgabendaten im MPP‑Format mit Aspose.Tasks für Java abgeschlossen. Diese leistungsstarke Bibliothek vereinfacht Projektmanagement‑Aufgaben und ist ein wertvolles Werkzeug für Java‑Entwickler, die **Projektaufgaben** programmgesteuert verwalten müssen.

## Häufig gestellte Fragen

### Q: Wo finde ich die Dokumentation zu Aspose.Tasks für Java?
A: Die Dokumentation ist [hier](https://reference.aspose.com/tasks/java/) verfügbar.

### Q: Wie kann ich Aspose.Tasks für Java herunterladen?
A: Sie können es von der [release page](https://releases.aspose.com/tasks/java/) herunterladen.

### Q: Gibt es eine kostenlose Testversion?
A: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Q: Wo bekomme ich Support für Aspose.Tasks für Java?
A: Besuchen Sie das Support‑Forum [hier](https://forum.aspose.com/c/tasks/15).

### Q: Bieten Sie temporäre Lizenzen für Testzwecke an?
A: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-03  
**Getestet mit:** Aspose.Tasks für Java 24.11 (latest)  
**Autor:** Aspose  

---