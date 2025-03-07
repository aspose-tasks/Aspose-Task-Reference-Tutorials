---
title: Aufgabendauer in verschiedenen Einheiten mit Aspose.Tasks
linktitle: Aufgabendauer in verschiedenen Einheiten mit Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Entdecken Sie die Verwaltung der Aufgabendauer in Java-Projekten mit Aspose.Tasks. Berechnen Sie die Dauer genau und konvertieren Sie sie in Minuten, Tage, Stunden, Wochen und Monate.
weight: 32
url: /de/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aufgabendauer in verschiedenen Einheiten mit Aspose.Tasks

## Einführung
Im Bereich des Projektmanagements ist das Verständnis und die Verwaltung der Aufgabendauer ein entscheidender Aspekt. Aspose.Tasks für Java bietet ein leistungsstarkes Toolset, um dies effizient zu bewältigen. In diesem Tutorial führen wir Sie durch das Abrufen von Aufgabendauern in verschiedenen Einheiten mithilfe von Aspose.Tasks.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Java Development Kit (JDK) installiert
-  Aspose.Tasks für Java-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/java/)
- Ein grundlegendes Verständnis der Java-Programmierung
## Pakete importieren
Fügen Sie in Ihr Java-Projekt die Aspose.Tasks-Bibliothek ein. Fügen Sie die folgende Importanweisung am Anfang Ihres Codes hinzu:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Beginnen Sie mit der Erstellung eines neuen Java-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Stellen Sie sicher, dass Sie die Aspose.Tasks-Bibliothek in die Abhängigkeiten Ihres Projekts einbeziehen.
## Schritt 2: Projektvorlage lesen
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Lesen Sie die MS Project-Vorlagendatei
String fileName = dataDir + "project.xml";
// Lesen Sie die Eingabedatei als Projekt
Project project = new Project(fileName);
```
 Stellen Sie sicher, dass Sie es ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihren Projektdateien.
## Schritt 3: Eine Aufgabe abrufen
```java
// Erhalten Sie eine Aufgabe, um deren Dauer in verschiedenen Formaten zu berechnen
Task task = project.getRootTask().getChildren().getById(1);
```
 Hier erhalten wir eine Aufgabe aus dem Projekt. Anpassen`getById(1)` basierend auf der Aufgaben-ID Ihres Projekts.
## Schritt 4: Dauer in Minuten
```java
// Ermitteln Sie die Dauer in Minuten
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
In diesem Schritt wird die Aufgabendauer in Minuten berechnet.
## Schritt 5: Dauer in Tagen
```java
// Ermitteln Sie die Dauer in Tagen
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
In diesem Schritt wird die Aufgabendauer in Tagen berechnet.
## Schritt 6: Dauer in Stunden
```java
// Ermitteln Sie die Dauer in Stunden
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
In diesem Schritt wird die Aufgabendauer in Stunden berechnet.
## Schritt 7: Dauer in Wochen
```java
// Erhalten Sie die Dauer in Wochen
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
In diesem Schritt wird die Aufgabendauer in Wochen berechnet.
## Schritt 8: Dauer in Monaten
```java
// Ermitteln Sie die Dauer in Monaten
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
In diesem Schritt wird die Aufgabendauer in Monaten berechnet.
## Abschluss
Mit Aspose.Tasks für Java wird die Verwaltung der Aufgabendauer vereinfacht. Dieses Tutorial hat Sie Schritt für Schritt durch den Prozess geführt und Ihnen Klarheit über verschiedene Zeiteinheiten verschafft.
## Häufig gestellte Fragen
### F: Kann ich Aspose.Tasks für Java mit jeder Java-IDE verwenden?
Ja, Aspose.Tasks für Java ist mit jeder Java Integrated Development Environment (IDE) kompatibel.
### F: Wie kann ich die ID einer Aufgabe in einer Microsoft Project-Datei erhalten?
Sie können die Projektdatei überprüfen oder die Aspose.Tasks-API verwenden, um Aufgaben-IDs programmgesteuert abzurufen.
### F: Ist Aspose.Tasks für die Abwicklung großer Projekte geeignet?
Absolut. Aspose.Tasks wurde für die effiziente Abwicklung von Projekten unterschiedlicher Größe entwickelt.
### F: Wo finde ich weitere Dokumentation?
 Besuche den[Dokumentation](https://reference.aspose.com/tasks/java/)für umfassende Ressourcen.
### F: Kann ich Aspose.Tasks für Java vor dem Kauf testen?
 Ja, Sie können a erkunden[Kostenlose Testphase](https://releases.aspose.com/) seine Fähigkeiten zu bewerten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
