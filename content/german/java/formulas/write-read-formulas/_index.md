---
title: Schreiben und Lesen von MS Project-Formeln in Aspose.Tasks
linktitle: Schreiben und lesen Sie Formeln in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Lernen Sie mit Aspose.Tasks für Java, MS Project-Formeln effizient zu schreiben und zu lesen. Verbessern Sie Ihre Projektmanagementfähigkeiten.
type: docs
weight: 12
url: /de/java/formulas/write-read-formulas/
---
## Einführung
Im Bereich des Projektmanagements ist der effektive Umgang mit Daten von größter Bedeutung. Aspose.Tasks für Java ist eine robuste Lösung, die die Bearbeitung und Extraktion von Daten aus Microsoft Project-Dateien erleichtert. Eine leistungsstarke Funktion ist die Möglichkeit, MS Project-Formeln zu schreiben und zu lesen. Dieses Tutorial führt Sie durch den Prozess der Nutzung dieser Funktionalität zur Verbesserung Ihrer Projektmanagementaufgaben.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java: Laden Sie Aspose.Tasks für Java herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie Ihre bevorzugte IDE für die Java-Entwicklung.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Schritt 1: Datenverzeichnis einrichten
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
```
Definieren Sie in diesem Schritt das Verzeichnis, in dem sich Ihre MS Project-Dateien befinden.
## Schritt 2: Projektdatei laden
```java
Project project = new Project(dataDir + "project.mpp");
```
Laden Sie hier die MS Project-Datei in ein`Project` Objekt zur Manipulation.
## Schritt 3: Benutzerdefinierte Formel definieren
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
In diesem Schritt wird ein benutzerdefiniertes Feld mit einer Formel erstellt, die die Aufgabenkosten verdoppelt.
## Schritt 4: Aufgabe hinzufügen und Kosten festlegen
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Hier wird eine neue Aufgabe hinzugefügt und deren Kosten auf 100 gesetzt.
## Schritt 5: Projektdatei speichern
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Speichern Sie abschließend die geänderte Projektdatei.

## Abschluss
In diesem Tutorial haben wir untersucht, wie man MS Project-Formeln mit Aspose.Tasks für Java schreibt und liest. Wenn Sie diese Schritte befolgen, können Sie Projektdaten effizient bearbeiten, um Ihre spezifischen Anforderungen zu erfüllen.
## FAQs
### Ist Aspose.Tasks mit allen Versionen von MS Project kompatibel?
Aspose.Tasks bietet Kompatibilität mit verschiedenen Versionen von MS Project und gewährleistet so Flexibilität für Benutzer.
### Kann ich Aspose.Tasks in mein bestehendes Java-Projekt integrieren?
Absolut! Aspose.Tasks bietet eine nahtlose Integration mit Java-Projekten durch einfache API-Nutzung.
### Gibt es irgendwelche Einschränkungen hinsichtlich der Arten von Formeln, die ich erstellen kann?
Mit Aspose.Tasks haben Sie umfassende Flexibilität bei der Erstellung benutzerdefinierter Formeln, die auf Ihre Projektanforderungen zugeschnitten sind.
### Unterstützt Aspose.Tasks die Bereitstellung auf mehreren Plattformen?
Ja, Aspose.Tasks unterstützt die Bereitstellung auf mehreren Plattformen und erhöht so seine Vielseitigkeit.
### Wie erhalte ich technischen Support für Aspose.Tasks?
 Für technische Hilfe und Community-Unterstützung besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).