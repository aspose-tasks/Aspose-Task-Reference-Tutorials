---
title: Aktualisieren Sie die MPP-Datei in Aspose.Tasks
linktitle: Aktualisieren Sie die MPP-Datei in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie MPP-Dateien mit Aspose.Tasks für Java nahtlos aktualisieren. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine effiziente Bearbeitung von Projektdateien.
type: docs
weight: 19
url: /de/java/project-management/update-mpp/
---
## Einführung
Im Bereich des Projektmanagements ist die Handhabung und Aktualisierung von Projektdateien eine entscheidende Aufgabe. Aspose.Tasks für Java bietet Java-Entwicklern eine leistungsstarke Lösung zur nahtlosen Bearbeitung von Microsoft Project-Dateien. In diesem Tutorial befassen wir uns mit der Aktualisierung von MPP-Dateien mithilfe von Aspose.Tasks für Java.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java: Laden Sie Aspose.Tasks für Java von herunter und installieren Sie es[Download-Seite](https://releases.aspose.com/tasks/java/).
3. Grundkenntnisse von Java: Um den Beispielen folgen zu können, sind Kenntnisse der Programmiersprache Java erforderlich.

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren, um die Funktionalitäten von Aspose.Tasks effektiv nutzen zu können.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Diese Codezeile importiert alle wesentlichen Klassen und Methoden aus der Aspose.Tasks-Bibliothek, sodass Sie mühelos mit Microsoft Project-Dateien arbeiten können.

Lassen Sie uns nun den Prozess der Aktualisierung einer MPP-Datei mit Aspose.Tasks für Java in überschaubare Schritte unterteilen.
## Schritt 2: Datenverzeichnis definieren
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem tatsächlichen Pfad, in dem sich Ihre MPP-Datei befindet.
## Schritt 3: Vorhandenes Projekt lesen
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Dieser Code liest eine vorhandene MPP-Projektdatei mit dem Namen`SampleMSP2010.mpp` aus dem angegebenen Datenverzeichnis.
## Schritt 4: Erstellen Sie eine neue Aufgabe
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Hier fügen wir eine neue Aufgabe mit dem Namen „Task1“ zur Stammaufgabe des Projekts hinzu.
## Schritt 5: Legen Sie Start- und Enddatum fest
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Diese Codezeilen legen das Startdatum und das Enddatum für die neu erstellte Aufgabe fest.
## Schritt 6: Speichern Sie das Projekt
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Schließlich speichert dieser Schritt das aktualisierte Projekt mit der neu hinzugefügten Aufgabe in einer neuen MPP-Datei mit dem Namen`AfterLinking.mpp`.

## Abschluss
In diesem Tutorial haben wir untersucht, wie man MPP-Dateien mit Aspose.Tasks für Java aktualisiert. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Microsoft Project-Dateien in Ihren Java-Anwendungen effizient bearbeiten.
## FAQs
### F: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet robuste Funktionen zur effizienten Handhabung komplexer Projektstrukturen.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion herunterladen[Webseite](https://releases.aspose.com/).
### F: Unterstützt Aspose.Tasks für Java verschiedene Versionen von Microsoft Project-Dateien?
A: Absolut, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich der Formate MPP, MPT und XML.
### F: Kann ich temporäre Lizenzen für Aspose.Tasks für Java erhalten?
 A: Ja, zu Testzwecken stehen temporäre Lizenzen zur Verfügung. Sie können sie bei der erhalten[temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich Hilfe oder Unterstützung zu Aspose.Tasks für Java suchen?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für jegliche Hilfe oder Fragen.