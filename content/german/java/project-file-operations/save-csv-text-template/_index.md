---
title: Als CSV, Text und Vorlage in Aspose.Tasks speichern
linktitle: Als CSV, Text und Vorlage in Aspose.Tasks speichern
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Microsoft Project-Dateien mit Aspose.Tasks für Java in den Formaten CSV, Text und Vorlage speichern.
type: docs
weight: 16
url: /de/java/project-file-operations/save-csv-text-template/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie Projektdateien in verschiedenen Formaten wie CSV, Text und Vorlage mit Aspose.Tasks für Java speichern. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die es Entwicklern ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project installiert werden muss.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK) auf Ihrem System installiert.
2.  Aspose.Tasks für Java-Bibliothek heruntergeladen und in Ihrem Java-Projekt konfiguriert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
3. Grundkenntnisse der Programmiersprache Java.

## Pakete importieren
Zuerst müssen Sie die notwendigen Pakete in Ihre Java-Datei importieren:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Projekt als CSV speichern
Lassen Sie uns die Schritte zum Speichern eines Projekts als CSV aufschlüsseln:
### Schritt 1: Laden Sie das Projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Schritt 2: Als CSV speichern
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Projekt als Text speichern
So können Sie ein Projekt als Text speichern:
### Schritt 1: Laden Sie das Projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Schritt 2: Als Text speichern
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Projekt als Vorlage speichern
Das Speichern eines Projekts als Vorlage umfasst die folgenden Schritte:
### Schritt 1: Laden Sie das Projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Schritt 2: Legen Sie die Vorlagenoptionen fest
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Schritt 3: Als Vorlage speichern
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Microsoft Project-Dateien mit Aspose.Tasks für Java als CSV, Text und Vorlage speichert. Mit diesen einfachen Schritten können Sie Ihre Projektdateien in verschiedenen Formaten effizient verwalten und so Ihre Produktivität als Java-Entwickler steigern.
## FAQs
### F: Kann Aspose.Tasks für Java komplexe Projektdateien verarbeiten?
A: Auf jeden Fall! Aspose.Tasks für Java kann problemlos Projekte unterschiedlicher Komplexität bewältigen und bietet umfassende Unterstützung für Microsoft Project-Dateiformate.
### F: Gibt es eine Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java erhalten[Hier](https://releases.aspose.com/).
### F: Wo finde ich Unterstützung für Aspose.Tasks für Java?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für jegliche Unterstützung oder Fragen zu Aspose.Tasks für Java.
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?
 A: Ja, Sie können eine temporäre Lizenz bei erwerben[Hier](https://purchase.aspose.com/temporary-license/)So können Sie das volle Potenzial der Bibliothek auswerten.
### F: Ist Aspose.Tasks für Java mit verschiedenen Betriebssystemen kompatibel?
A: Ja, Aspose.Tasks für Java ist mit verschiedenen Betriebssystemen kompatibel, darunter Windows, macOS und Linux.