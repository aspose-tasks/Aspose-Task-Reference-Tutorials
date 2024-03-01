---
title: Verwaltung der Aufgabenbasisdauer in Aspose.Tasks
linktitle: Verwaltung der Aufgabenbasisdauer in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Aufgabenbasispläne in MS Project mit Aspose.Tasks für Java effizient verwalten. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess.
type: docs
weight: 12
url: /de/java/task-baselines/task-baseline-duration/
---
## Einführung
Die Verwaltung von Aufgabenbasisplänen in MS Project ist für die Projektplanung und -verfolgung von entscheidender Bedeutung. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java die Basisdauer von Aufgaben effektiv verwalten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist.
2.  Aspose.Tasks-Bibliothek: Laden Sie die Aspose.Tasks für Java-Bibliothek von herunter und installieren Sie sie[Hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Importieren Sie zunächst die notwendigen Pakete für Ihr Java-Projekt:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Schritt 1: Erstellen Sie eine Projektinstanz
Initialisieren Sie eine neue Projektinstanz mit dem folgenden Code:
```java
Project project = new Project();
```
## Schritt 2: Erstellen Sie eine Aufgabenbasislinie
Erstellen Sie eine neue Aufgabe und legen Sie ihre Basislinie mit dem folgenden Code fest:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Schritt 3: Informationen zur Aufgabenbasislinie anzeigen
Rufen Sie Aufgabenbasisinformationen wie Dauer, Startdatum, Enddatum und mehr ab und zeigen Sie sie an:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Schritt 4: Überprüfen Sie den vorläufigen Basisplan und die Fixkosten
Überprüfen Sie, ob es sich bei dem Basisplan um einen vorläufigen Basisplan handelt, und rufen Sie alle damit verbundenen Fixkosten ab:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Schritt 5: Zeitphasendaten drucken
Zeitphasendaten drucken, die der Aufgabenbasislinie zugeordnet sind:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Wenn Sie diese Schritte befolgen, können Sie die Dauer der Aufgabenbasis in MS Project mithilfe von Aspose.Tasks für Java effektiv verwalten.

## Abschluss
Die Verwaltung von Aufgabenbasisplänen ist für das Projektmanagement von entscheidender Bedeutung, damit Sie Abweichungen vom geplanten Zeitplan verfolgen können. Mit Aspose.Tasks für Java wird dieser Prozess rationalisiert und effizient, was eine bessere Projektkontrolle und -abwicklung ermöglicht.
## FAQs
### Was ist eine Aufgabenbasislinie in MS Project?
Eine Aufgabenbasislinie in MS Project ist eine Momentaufnahme des ursprünglich geplanten Zeitplans für eine Aufgabe, einschließlich ihres Startdatums, Enddatums und ihrer Dauer.
### Warum ist die Verwaltung von Aufgabenbasislinien wichtig?
Durch die Verwaltung von Aufgabenbasisplänen können Sie den geplanten Zeitplan mit dem tatsächlichen Projektfortschritt vergleichen und so eine bessere Nachverfolgung und Entscheidungsfindung ermöglichen.
### Kann ich eine Aufgabenbasislinie ändern, nachdem sie festgelegt wurde?
Ja, Sie können Aufgabenbasispläne in MS Project ändern, um Änderungen im Projektplan widerzuspiegeln. Es ist jedoch wichtig, etwaige Abweichungen vom ursprünglichen Ausgangswert zu dokumentieren.
### Unterstützt Aspose.Tasks andere Projektmanagementfunktionen?
Ja, Aspose.Tasks bietet eine breite Palette von Funktionen für das Projektmanagement, einschließlich Aufgabenplanung, Ressourcenzuweisung und Erstellung von Gantt-Diagrammen.
### Wo finde ich Unterstützung für Aspose.Tasks?
 Unterstützung für Aspose.Tasks finden Sie auf der[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15), wo Sie Fragen stellen und mit anderen Benutzern interagieren können.