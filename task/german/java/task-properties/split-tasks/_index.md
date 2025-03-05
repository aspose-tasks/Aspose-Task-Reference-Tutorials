---
title: Teilen Sie Aufgaben in Aspose.Tasks
linktitle: Teilen Sie Aufgaben in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Meistern Sie die Aufgabenverwaltung in Java mit Aspose.Tasks! Erfahren Sie, wie Sie Aufgaben effizient aufteilen, um die Projektzeitpläne zu optimieren. Jetzt downloaden!
type: docs
weight: 29
url: /de/java/task-properties/split-tasks/
---
## Einführung
Haben Sie Probleme mit der Aufgabenverwaltung in Ihrem Java-Projekt? Aspose.Tasks für Java bietet eine leistungsstarke Lösung zur effizienten Aufteilung von Aufgaben und verbessert die Projektmanagementfunktionen. In diesem Tutorial führen wir Sie durch den Prozess der Aufgabenaufteilung mit Aspose.Tasks für Java und helfen Ihnen dabei, Ihre Projektzeitpläne und Ressourcenzuweisungen zu optimieren.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
-  Aspose.Tasks für Java-Bibliothek heruntergeladen und Ihrem Projekt hinzugefügt. Sie können es hier herunterladen[Aspose.Tasks für Java-Dokumentation](https://reference.aspose.com/tasks/java/).
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt:
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
## Schritt 1: Erstellen Sie ein neues Projekt
Erstellen Sie zunächst ein neues Projekt mithilfe der Aspose.Tasks-Bibliothek:
```java
// Erstellen Sie ein neues Projekt
Project splitTaskProject = new Project();
```
## Schritt 2: Projektkalender festlegen
Legen Sie die Kalendereinstellungen des Projekts fest, um die Zeitachse festzulegen:
```java
// Besorgen Sie sich einen Standardkalender
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Legen Sie die Kalendereinstellungen des Projekts fest
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (weiter mit dem Beispiel)
```
## Schritt 3: Fügen Sie eine Root-Aufgabe hinzu
Fügen Sie Ihrem Projekt eine Root-Aufgabe hinzu:
```java
// Root-Aufgabe
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Schritt 4: Fügen Sie eine neue Aufgabe zu Split hinzu
Fügen Sie Ihrem Projekt eine neue Aufgabe hinzu, die Sie aufteilen möchten:
```java
// Fügen Sie eine neue Aufgabe hinzu
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Schritt 5: Erstellen Sie eine Ressourcenzuweisung
Erstellen Sie eine neue Ressourcenzuweisung für die Aufgabe:
```java
// Erstellen Sie eine neue Ressourcenzuweisung
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Schritt 6: Zeitphasendaten generieren
Generieren Sie Zeitphasendaten für die Ressourcenzuweisung:
```java
// Generieren Sie Zeitphasendaten zur Ressourcenzuweisung
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Schritt 7: Teilen Sie die Aufgabe auf
Teilen Sie die Aufgabe in mehrere Teile auf:
```java
// Teilen Sie die Aufgabe in 3 Teile auf
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (weiter mit dem Beispiel)
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie Aufgaben mit Aspose.Tasks für Java aufteilen. Diese leistungsstarke Bibliothek vereinfacht die Aufgabenverwaltung in Java-Projekten und bietet effiziente Lösungen zur Optimierung von Projektzeitplänen und Ressourcenzuweisungen.
## Häufig gestellte Fragen
### Kann ich Aufgaben mit unterschiedlicher Dauer aufteilen?
Ja, Sie können die Dauer der Aufgaben entsprechend Ihren Projektanforderungen anpassen.
### Ist Aspose.Tasks für Java mit allen Java-Versionen kompatibel?
Aspose.Tasks für Java ist so konzipiert, dass es nahtlos mit verschiedenen Java-Versionen zusammenarbeitet und so die Kompatibilität gewährleistet.
### Kann ich Aspose.Tasks für Java kostenlos nutzen?
Aspose.Tasks für Java bietet eine kostenlose Testversion, mit der Sie die Funktionen erkunden können, bevor Sie einen Kauf tätigen.
### Wie erhalte ich Unterstützung für Aspose.Tasks für Java?
 Besuche den[Aspose.Tasks für Java-Supportforum](https://forum.aspose.com/c/tasks/15) um Hilfe zu erhalten und mit der Community in Kontakt zu treten.
### Benötige ich eine temporäre Lizenz für Aspose.Tasks für Java?
 Eine temporäre Lizenz erhalten Sie bei[dieser Link](https://purchase.aspose.com/temporary-license/) zu Test- und Evaluierungszwecken.