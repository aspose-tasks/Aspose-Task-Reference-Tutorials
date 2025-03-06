---
title: MS Project-Formeln mit Aspose.Tasks für Java
linktitle: Arbeiten Sie mit Formeln in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie MS Project-Dateien in Java mithilfe der Aspose.Tasks-Bibliothek bearbeiten. Erstellen, ändern und berechnen Sie Attribute ganz einfach.
weight: 11
url: /de/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project-Formeln mit Aspose.Tasks für Java

## Einführung
In diesem Tutorial befassen wir uns intensiv mit der Arbeit mit MS Project-Formeln mithilfe von Aspose.Tasks für Java. Aspose.Tasks ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten. Mit seinen umfangreichen Funktionen können Sie Projektdateien in Java-Anwendungen einfach erstellen, lesen, ändern und konvertieren.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### Java-Entwicklungsumgebung
Stellen Sie sicher, dass auf Ihrem System ein Java Development Kit (JDK) installiert ist. Sie können das neueste JDK von der Oracle-Website herunterladen und installieren.
### Aspose.Tasks-Bibliothek
Sie müssen die Aspose.Tasks-Bibliothek zu Ihrem Java-Projekt hinzufügen. Sie können die Bibliothek unter herunterladen[Aspose.Tasks für Java-Downloadseite](https://releases.aspose.com/tasks/java/) und fügen Sie es in die Abhängigkeiten Ihres Projekts ein.

## Pakete importieren
Bevor Sie sich mit den Beispielen befassen, importieren Sie die erforderlichen Pakete in Ihren Java-Code:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte unterteilen:
## Schritt 1: Erstellen Sie ein Testprojekt mit benutzerdefiniertem Feld
```java
Project project = CreateTestProjectWithCustomField();
```
 Erstellen Sie zunächst ein Testprojekt mit einem benutzerdefinierten Feld mithilfe von`CreateTestProjectWithCustomField()` Methode. Diese Methode gibt ein Project-Objekt zurück, das das neu erstellte Projekt darstellt.
## Schritt 2: Definieren Sie eine erweiterte Attributdefinition
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Rufen Sie die erweiterte Attributdefinition aus dem Projekt ab und legen Sie deren Alias und Formel fest. In diesem Beispiel definieren wir ein Attribut, um die Anzahl der Tage vom Enddatum bis zum Abgabetermin zu berechnen.
## Schritt 3: Legen Sie eine Frist für eine Aufgabe fest
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Erstellen Sie ein Kalenderobjekt und legen Sie das Stichtagsdatum fest. Rufen Sie dann eine Aufgabe aus dem Projekt ab und legen Sie deren Frist mithilfe des Kalenderobjekts fest.
## Schritt 4: Speichern Sie das Projekt
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Speichern Sie abschließend das Projekt in einer Datei mit dem angegebenen Namen und Format. In diesem Fall speichern wir es als MPP-Datei.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java mit MS Project-Formeln arbeitet. Wenn Sie diese Schritte befolgen, können Sie Projektdateien effektiv programmgesteuert bearbeiten, indem Sie benutzerdefinierte Felder hinzufügen und Attribute basierend auf Formeln berechnen.

## FAQs
### F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
A: Ja, Aspose.Tasks unterstützt verschiedene Programmiersprachen, darunter Java, .NET und mehr.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks herunterladen[Hier](https://releases.aspose.com/).
### F: Wo finde ich Dokumentation für Aspose.Tasks?
 A: Sie finden die Dokumentation für Aspose.Tasks[Hier](https://reference.aspose.com/tasks/java/).
### F: Wie kann ich Unterstützung für Aspose.Tasks erhalten?
 A: Für Unterstützung können Sie die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
### F: Benötige ich eine temporäre Lizenz für die Nutzung von Aspose.Tasks?
A: Wenn Sie zusätzliche Funktionen benötigen, können Sie eine temporäre Lizenz von erhalten[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
