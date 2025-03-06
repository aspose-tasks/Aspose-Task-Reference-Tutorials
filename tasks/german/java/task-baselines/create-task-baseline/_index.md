---
title: Erstellen Sie eine MS Project-Aufgabenbasislinie in Aspose.Tasks
linktitle: Erstellen einer Aufgabenbasislinie in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks, einer leistungsstarken Bibliothek zur mühelosen Verwaltung von Projektdaten, eine Microsoft Project-Aufgabenbasislinie in Java erstellen.
weight: 11
url: /de/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie eine MS Project-Aufgabenbasislinie in Aspose.Tasks

## Einführung
In diesem Tutorial befassen wir uns mit dem Prozess der Erstellung einer Microsoft Project-Aufgabenbasislinie mithilfe von Aspose.Tasks für Java. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die es Entwicklern ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project installiert werden muss. Mit Aspose.Tasks können Sie Projektdaten, einschließlich Aufgaben, Ressourcen und Kalender, mühelos bearbeiten, um Projektmanagementaufgaben zu optimieren.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Für Aspose.Tasks für Java muss JDK auf Ihrem System installiert sein. Sie können JDK von der Oracle-Website herunterladen und installieren.
2.  Aspose.Tasks für Java-Bibliothek: Laden Sie die Aspose.Tasks für Java-Bibliothek von herunter[Download-Link](https://releases.aspose.com/tasks/java/) bereitgestellt.

## Pakete importieren
Um mit Aspose.Tasks in Ihrem Java-Projekt zu arbeiten, importieren Sie die erforderlichen Pakete:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Schritt 1: Erstellen Sie ein Projektobjekt
```java
Project project = new Project();
```
 Erstellen Sie zunächst ein neues`Project` Objekt. Dieses Objekt stellt die Microsoft Project-Datei dar, mit der Sie arbeiten werden.
## Schritt 2: Fügen Sie dem Projekt eine Aufgabe hinzu
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Verwendung der`getRootTask()` Greifen Sie mit der Methode auf die Stammaufgabe des Projekts zu und fügen Sie ihr dann eine neue Aufgabe hinzu`add()` Methode. Geben Sie in den Klammern einen Namen für die Aufgabe ein.
## Schritt 3: Legen Sie die Basislinie für bestimmte Aufgaben fest
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Um eine Baseline für bestimmte Aufgaben festzulegen, erstellen Sie eine Aufgabenliste (`myList` (in diesem Fall) und füllen Sie es mit den Aufgaben, für die Sie die Grundlinie festlegen möchten. Dann verwenden Sie die`setBaseline()` -Methode unter Angabe des Basistyps und der Liste der Aufgaben.
## Schritt 4: Legen Sie die Basislinie für das gesamte Projekt fest
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternativ können Sie eine Baseline für das gesamte Projekt festlegen, indem Sie einfach die aufrufen`setBaseline()` Methode mit dem angegebenen Basislinientyp.

## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Tasks für Java eine Microsoft Project-Aufgabenbasislinie erstellen. Wenn Sie die oben beschriebenen Schritte befolgen, können Sie Projektdaten effizient verwalten und Projektmanagementaufgaben mühelos rationalisieren.
## FAQs
### Kann ich Aspose.Tasks für Java verwenden, ohne dass Microsoft Project installiert ist?
Ja, mit Aspose.Tasks für Java können Sie mit Microsoft Project-Dateien arbeiten, ohne dass Microsoft Project auf Ihrem System installiert sein muss.
### Ist Aspose.Tasks für Java mit verschiedenen Versionen von Microsoft Project kompatibel?
Ja, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### Kann ich Projektressourcen mit Aspose.Tasks für Java manipulieren?
Absolut, Aspose.Tasks für Java bietet robuste Funktionen zum Bearbeiten von Projektressourcen, einschließlich des Hinzufügens, Aktualisierens und Entfernens von Ressourcen nach Bedarf.
### Unterstützt Aspose.Tasks für Java das Festlegen von Aufgabenabhängigkeiten?
Ja, Sie können mit Aspose.Tasks für Java mühelos Aufgabenabhängigkeiten festlegen und so die Reihenfolge der Aufgaben in Ihrem Projekt festlegen.
### Ist technischer Support für Aspose.Tasks für Java verfügbar?
 Ja, Sie können über das auf den technischen Support für Aspose.Tasks für Java zugreifen[Hilfeforum](https://forum.aspose.com/c/tasks/15), wo Sie Fragen stellen und Hilfe von der Community und den Aspose-Supportmitarbeitern erhalten können.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
