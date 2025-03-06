---
title: Enddatum der Aufgabe in Aspose.Tasks aufteilen
linktitle: Enddatum der Aufgabe in Aspose.Tasks aufteilen
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java mühelos Aufgabenendtermine aufteilen. Verbessern Sie das Projektmanagement mit genauen Zeitplänen.
type: docs
weight: 28
url: /de/java/task-properties/split-task-finish-date/
---
## Einführung
Im Projektmanagement ist das Verständnis der Aufgabenzeitpläne entscheidend für den erfolgreichen Projektabschluss. Aspose.Tasks für Java bietet leistungsstarke Funktionen zur effizienten Bearbeitung von Projektaufgaben. In diesem Tutorial befassen wir uns mit der Aufteilung von Aufgabenendterminen mithilfe von Aspose.Tasks, um Ihnen bei der effektiven Verwaltung von Projektzeitplänen zu helfen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Tasks für Java-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/java/).
- Einrichtung einer Java-Entwicklungsumgebung.
## Pakete importieren
Fügen Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt ein:
```java
import com.aspose.tasks.*;
```
## Schritt 1: Finden Sie eine geteilte Aufgabe
Suchen Sie die Aufgabe, die Sie im Projekt aufteilen möchten:
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Projekt lesen
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Schritt 2: Suchen Sie den Projektkalender
Rufen Sie den Projektkalender für genaue Datumsberechnungen ab:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Schritt 3: Berechnen Sie das Enddatum der Aufgabe mit unterschiedlichen Dauern
Berechnen Sie nun das Enddatum der Aufgabe für verschiedene Dauern:
## Schritt 3.1: Dauer von 8 Stunden
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Wiederholen Sie den obigen Code für verschiedene Dauern und passen Sie die Stunden entsprechend an.
## Abschluss
Die Beherrschung der Kunst, die Endtermine von Aufgaben zu manipulieren, ist für ein effektives Projektmanagement von entscheidender Bedeutung. Aspose.Tasks für Java vereinfacht diesen Prozess und ermöglicht Ihnen eine mühelose Optimierung Ihrer Projektzeitpläne.
## FAQs
### F1: Wie kann ich Aspose.Tasks für Java herunterladen?
 A1: Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/java/).
### F2: Wo finde ich Dokumentation für Aspose.Tasks?
 A2: Sehen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/tasks/java/).
### F3: Wie erhalte ich eine temporäre Lizenz für Aspose.Tasks?
 A3: Besorgen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).
### F4: Wo kann ich Unterstützung für Aspose.Tasks suchen?
 A4: Besuchen Sie das Support-Forum[Hier](https://forum.aspose.com/c/tasks/15).
### F5: Kann ich Aspose.Tasks kaufen?
 A5: Ja, Sie können es kaufen[Hier](https://purchase.aspose.com/buy).