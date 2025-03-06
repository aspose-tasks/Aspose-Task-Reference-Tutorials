---
title: Aktualisieren Sie Aufgabendaten in Aspose.Tasks auf das MPP-Format
linktitle: Aktualisieren Sie Aufgabendaten in Aspose.Tasks auf das MPP-Format
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Aufgabendaten mit Aspose.Tasks für Java in das MPP-Format aktualisieren. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für ein effizientes Projektmanagement.
type: docs
weight: 35
url: /de/java/task-properties/update-task-data/
---
## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Aktualisieren von Aufgabendaten in das MPP-Format mit Aspose.Tasks für Java. In diesem Tutorial führen wir Sie durch den Prozess und stellen sicher, dass Sie jeden Schritt klar verstehen. Aspose.Tasks für Java bietet eine robuste Lösung für die Arbeit mit Microsoft Project-Dateien. Am Ende dieses Handbuchs werden Sie in der Lage sein, Aufgabendaten im MPP-Format effizient zu aktualisieren.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Tasks für Java: Stellen Sie sicher, dass die Aspose.Tasks-Bibliothek installiert ist. Sie können es hier herunterladen[Release-Seite](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
- Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine IDE Ihrer Wahl für die Java-Entwicklung.
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt. Das folgende Snippet zeigt, wie Pakete importiert werden:
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
## 1. Erstellen und konfigurieren Sie die erste Aufgabe
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Fahren Sie mit dem Rest des Codes fort)
```
## 2. Legen Sie Startdatum und Dauer fest
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Fahren Sie mit dem Rest des Codes fort)
```
## 3. Erstellen Sie eine Sammelaufgabe
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Fahren Sie mit dem Rest des Codes fort)
```
## 4. Legen Sie Fristen und Aufgabennotizen fest
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Fahren Sie mit dem Rest des Codes fort)
```
## 5. Konfigurieren Sie Aufgabeneinschränkungen
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Fahren Sie mit dem Rest des Codes fort)
```
## 6. Erstellen Sie zusätzliche Aufgaben
```java
//Erstellen Sie 10 neue Aufgaben
for (int i = 0; i < 10; i++) {
    //... (Fahren Sie mit dem Rest des Codes fort)
}
//... (Fahren Sie mit dem Rest des Codes fort)
```
## 7. Speichern Sie das Projekt
```java
// Speichern Sie das Projekt
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Durch Befolgen dieser Schritte haben Sie Aufgabendaten mit Aspose.Tasks für Java erfolgreich in das MPP-Format aktualisiert.
## Abschluss
Glückwunsch! Sie haben eine umfassende Anleitung zum Aktualisieren von Aufgabendaten im MPP-Format mit Aspose.Tasks für Java fertiggestellt. Diese leistungsstarke Bibliothek vereinfacht Projektmanagementaufgaben und macht sie zu einem wertvollen Werkzeug für Java-Entwickler.
## FAQs
### F: Wo finde ich die Dokumentation zu Aspose.Tasks für Java?
 A: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/tasks/java/).
### F: Wie kann ich Aspose.Tasks für Java herunterladen?
 A: Sie können es von herunterladen[Release-Seite](https://releases.aspose.com/tasks/java/).
### F: Gibt es eine kostenlose Testversion?
 A: Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wo erhalte ich Unterstützung für Aspose.Tasks für Java?
 A: Besuchen Sie das Support-Forum[Hier](https://forum.aspose.com/c/tasks/15).
### F: Bieten Sie temporäre Lizenzen zu Testzwecken an?
 A: Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).