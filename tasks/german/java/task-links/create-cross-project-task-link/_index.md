---
title: Erstellen Sie einen projektübergreifenden Aufgabenlink in Aspose.Tasks
linktitle: Erstellen Sie einen projektübergreifenden Aufgabenlink in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Verbessern Sie die Projektzusammenarbeit mit Aspose.Tasks für Java. Erfahren Sie Schritt für Schritt, wie Sie projektübergreifende Aufgabenverknüpfungen erstellen. Jetzt Effizienz steigern!
weight: 10
url: /de/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie einen projektübergreifenden Aufgabenlink in Aspose.Tasks

## Einführung
In der dynamischen Welt des Projektmanagements sind Effizienz und Zusammenarbeit von größter Bedeutung. Aspose.Tasks für Java bietet eine robuste Lösung zur Verbesserung Ihrer Projektmanagementfunktionen. In diesem Tutorial befassen wir uns mit dem Prozess der Erstellung projektübergreifender Aufgabenverknüpfungen mithilfe von Aspose.Tasks für Java. Diese Schritt-für-Schritt-Anleitung vermittelt Ihnen die Fähigkeiten, Aufgaben über verschiedene Projekte hinweg nahtlos zu verknüpfen und so eine bessere Koordination und optimierte Arbeitsabläufe zu fördern.
## Voraussetzungen
Bevor wir mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Tasks für Java installiert. Sie können es hier herunterladen[Aspose.Tasks für Java-Veröffentlichungsseite](https://releases.aspose.com/tasks/java/).
- Ein grundlegendes Verständnis des Projektmanagements und der Aufgabenabhängigkeiten.
## Pakete importieren
Um den Prozess anzukurbeln, importieren wir die erforderlichen Pakete in Ihre Java-Umgebung. Dadurch wird sichergestellt, dass Sie Zugriff auf die Aspose.Tasks für Java-Funktionen haben. Verwenden Sie den folgenden Codeausschnitt:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Lassen Sie uns nun den obigen Code in verständliche Schritte unterteilen:
## Schritt 1: Richten Sie Ihre Umgebung ein
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Java installiert haben und die Aspose.Tasks for Java-Bibliothek korrekt zu Ihrem Projekt hinzugefügt wurde.
## Schritt 2: Erstellen Sie eine Projektinstanz
Initialisieren Sie ein neues Projekt mit der Aspose.Tasks-Bibliothek:
```java
Project project = new Project();
```
## Schritt 3: Fügen Sie eine Sammelaufgabe hinzu
Erstellen Sie eine Sammelaufgabe, um die verknüpften Aufgaben zu organisieren und zu verwalten:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Schritt 4: Externe Aufgabe hinzufügen
Um einen Link zu einer Aufgabe aus einem anderen Projekt zu erstellen, fügen Sie der Sammelaufgabe eine externe Aufgabe hinzu:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Schritt 5: Lokale Aufgabe hinzufügen
Fügen Sie der Sammelaufgabe eine lokale Aufgabe hinzu. Dies wird die mit der externen Aufgabe verknüpfte Aufgabe sein:
```java
Task t = summary.getChildren().add("Task");
```
## Schritt 6: Aufgabenlink erstellen
Stellen Sie die Aufgabenverknüpfung zwischen der externen Aufgabe und der lokalen Aufgabe her:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Schritt 7: Ergebnisse anzeigen
Lassen Sie sich abschließend das Ergebnis der Konvertierung anzeigen:
```java
System.out.println("Process completed Successfully");
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Tasks für Java projektübergreifende Aufgabenverknüpfungen erstellen. Diese Funktionalität verbessert die Zusammenarbeit und Koordination im Projektmanagement und gewährleistet eine nahtlose Integration zwischen Aufgaben in verschiedenen Projekten.
## FAQs
### Kann ich Aufgaben aus mehreren externen Projekten in derselben Sammelaufgabe verknüpfen?
Ja, Sie können Aufgaben aus verschiedenen externen Projekten innerhalb derselben Sammelaufgabe verknüpfen, indem Sie einem ähnlichen Prozess folgen.
### Was passiert, wenn die externe Aufgabe im verknüpften Projekt geändert wird?
Alle Änderungen an der externen Aufgabe werden in der verknüpften Aufgabe in Ihrem aktuellen Projekt widergespiegelt.
### Ist es möglich, Verknüpfungen zwischen Aufgaben in verschiedenen Dateiformaten zu erstellen?
Ja, Aspose.Tasks für Java unterstützt das Verknüpfen von Aufgaben zwischen Projekten in verschiedenen Dateiformaten.
### Kann ich die Verknüpfung von Aufgaben aufheben, sobald sie projektübergreifend verknüpft sind?
Ja, Sie können die Verknüpfung von Aufgaben aufheben, indem Sie die Aufgabenverknüpfung mit den entsprechenden Aspose.Tasks-Methoden entfernen.
### Gibt es Einschränkungen hinsichtlich der Anzahl der Aufgaben, die projektübergreifend verknüpft werden können?
Die Anzahl der Aufgaben, die verknüpft werden können, hängt von den Funktionen und Einschränkungen Ihrer Aspose.Tasks-Lizenz ab.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
