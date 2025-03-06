---
title: Verwalten Sie übergeordnete und untergeordnete Aufgaben in Aspose.Tasks
linktitle: Verwalten Sie übergeordnete und untergeordnete Aufgaben in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Steigern Sie die Effizienz des Projektmanagements mit Aspose.Tasks für Java. Erfahren Sie Schritt für Schritt, wie Sie übergeordnete und untergeordnete Aufgaben verwalten. Jetzt loslegen!
weight: 24
url: /de/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten Sie übergeordnete und untergeordnete Aufgaben in Aspose.Tasks

## Einführung
Im Bereich des Projektmanagements ist eine effektive Aufgabenorganisation von entscheidender Bedeutung. Aspose.Tasks für Java bietet eine robuste Lösung zur effizienten Verwaltung übergeordneter und untergeordneter Aufgaben. In diesem Tutorial führen wir Sie durch den Prozess der Verwendung von Aspose.Tasks für Java, um Ihre Projektaufgaben zu optimieren.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der Java-Programmierung.
-  Aspose.Tasks für Java-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/java/).
- Eine Java Integrated Development Environment (IDE), die auf Ihrem System eingerichtet ist.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt. Diese Pakete ermöglichen eine nahtlose Integration mit Aspose.Tasks für Java-Funktionen.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Schritt 1: Projektstartdatum festlegen
Legen Sie zunächst das Startdatum des Projekts und andere relevante Parameter fest.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Hier kann zusätzlicher Code für Paketimporte hinzugefügt werden
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Schritt 2: Übergeordnete Aufgabe hinzufügen (Aufgabe 1)
Erstellen Sie eine übergeordnete Aufgabe mit dem Namen „Aufgabe 1“ und konfigurieren Sie ihre Eigenschaften.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Schritt 3: Übergeordnete Aufgabe (Aufgabe 2) mit untergeordneten Aufgaben hinzufügen
Fügen Sie nun eine weitere übergeordnete Aufgabe mit dem Namen „Aufgabe 2“ hinzu und schließen Sie untergeordnete Aufgaben (Aufgabe 3 und Aufgabe 4) ein.
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Fügen Sie untergeordnete Aufgaben zu Aufgabe 2 hinzu
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Hier können zusätzliche Konfigurationen für Task 3 und Task 4 hinzugefügt werden
```
## Schritt 4: Untergeordnete Aufgaben konfigurieren
Geben Sie Startdaten, Dauer und Einschränkungen für Aufgabe 3 und Aufgabe 4 an.
```java
// Konfigurieren Sie Aufgabe 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Konfigurieren Sie Aufgabe 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Schritt 5: Aktualisieren Sie den Prozentsatz der Aufgabenerfüllung
Passen Sie den Abschlussprozentsatz für Aufgabe 3 und Aufgabe 4 an.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Schritt 6: Speichern Sie das Projekt
Speichern Sie abschließend das Projekt mit den vorgenommenen Änderungen.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Diese Schritt-für-Schritt-Anleitung zeigt, wie Sie übergeordnete und untergeordnete Aufgaben mit Aspose.Tasks für Java effektiv verwalten. Experimentieren Sie mit verschiedenen Konfigurationen entsprechend den Anforderungen Ihres Projekts.
## Abschluss
Zusammenfassend lässt sich sagen, dass Aspose.Tasks für Java Entwicklern die effiziente Bearbeitung von Projektaufgaben ermöglicht und eine nahtlose Organisation und Nachverfolgung gewährleistet. Implementieren Sie die beschriebenen Schritte, um Ihre Projektmanagementfähigkeiten zu verbessern.
## FAQs
### Ist Aspose.Tasks für Java mit verschiedenen Projektdateiformaten kompatibel?
Ja, Aspose.Tasks für Java unterstützt verschiedene Projektdateiformate, einschließlich MPP und XML.
### Kann ich Aufgabeneigenschaften über das hinausgehen, was in diesem Tutorial behandelt wird, anpassen?
Absolut! Aspose.Tasks für Java bietet umfangreiche Anpassungsoptionen für Aufgabeneigenschaften.
### Gibt es ein Community-Forum für Aspose.Tasks, in dem ich Unterstützung suchen kann?
 Ja, Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für die Unterstützung der Gemeinschaft.
### Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich eine umfassende Dokumentation für Aspose.Tasks für Java?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
