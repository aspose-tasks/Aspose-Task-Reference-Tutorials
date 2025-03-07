---
title: Konfigurieren Sie die Gantt-Diagrammansicht in Aspose.Tasks-Projekten
linktitle: Konfigurieren Sie die Gantt-Diagrammansicht in Aspose.Tasks-Projekten
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie die Gantt MS Project-Diagrammansicht in Aspose.Tasks mit Java konfigurieren. Passen Sie Projekte an und visualisieren Sie sie Schritt für Schritt im Gantt-Diagramm.
weight: 10
url: /de/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurieren Sie die Gantt-Diagrammansicht in Aspose.Tasks-Projekten

## Einführung
In diesem Tutorial erfahren Sie, wie Sie die Gantt MS Project-Diagrammansicht in Aspose.Tasks-Projekten mit Java konfigurieren. Aspose.Tasks ist eine leistungsstarke Java-API, mit der Sie programmgesteuert mit Microsoft Project-Dateien arbeiten können. Wenn Sie diese Schritte befolgen, können Sie die Gantt-Diagrammansicht entsprechend den Anforderungen Ihres Projekts anpassen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
2.  Aspose.Tasks-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie eine IDE Ihrer Wahl. Dieses Tutorial verwendet IntelliJ IDEA, aber Sie können jede IDE verwenden, mit der Sie vertraut sind.
## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete importieren, um mit Aspose.Tasks in Ihrem Java-Projekt arbeiten zu können. Fügen Sie Ihrer Java-Datei die folgenden Importanweisungen hinzu:
```java
import com.aspose.tasks.*;
```
Lassen Sie uns nun den Prozess der Konfiguration der Gantt-MS-Projektdiagrammansicht in Schritt-für-Schritt-Anleitungen unterteilen:
## Schritt 1: Datenverzeichnis einrichten
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrem Projektdatenverzeichnis.
## Schritt 2: Projektdatei laden
```java
Project project = new Project(dataDir + "project.mpp");
```
Laden Sie Ihre Projektdatei (`project.mpp` in diesem Beispiel) mit der`Project` Klasse von Aspose.Tasks.
## Schritt 3: Neue Aktivität hinzufügen
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Erstellen Sie mit dem eine neue Aufgabe in Ihrem Projekt`Task` Klasse und fügen Sie sie den untergeordneten Elementen der Stammaufgabe hinzu.
## Schritt 4: Benutzerdefiniertes Attribut definieren
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Definieren Sie ein neues benutzerdefiniertes Attribut mithilfe von`ExtendedAttributeDefinition`Klasse und fügen Sie sie den erweiterten Attributen des Projekts hinzu.
## Schritt 5: Benutzerdefiniertes Attribut zur Aufgabe hinzufügen
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Fügen Sie das benutzerdefinierte Attribut mithilfe von zur erstellten Aufgabe hinzu`createExtendedAttribute` Methode.
## Schritt 6: Tabelle anpassen
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Passen Sie die Tabelle an, indem Sie das Textattributfeld mit der angegebenen Breite, dem angegebenen Titel und der angegebenen Ausrichtung hinzufügen.
## Schritt 7: Projekt speichern
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Speichern Sie das Projekt mit der konfigurierten Gantt-MS-Projektdiagrammansicht. Die resultierende Datei kann in Microsoft Project 2010 geöffnet werden.
## Abschluss
Glückwunsch! Sie haben die Gantt-MS-Projektdiagrammansicht in Aspose.Tasks-Projekten mit Java erfolgreich konfiguriert. Sie können jetzt Projektattribute anpassen und sie entsprechend den Anforderungen Ihres Projekts im Gantt-Diagramm visualisieren.
## FAQs
### F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
A: Ja, Aspose.Tasks ist für mehrere Programmiersprachen verfügbar, darunter .NET, Java und C++.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks?
 A: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### F: Wo finde ich Unterstützung für Aspose.Tasks?
A: Auf der finden Sie Unterstützung und können Fragen stellen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
### F: Wie kann ich eine Lizenz für Aspose.Tasks erwerben?
 A: Sie können eine Lizenz erwerben bei[Hier](https://purchase.aspose.com/buy).
### F: Benötige ich zu Testzwecken eine temporäre Lizenz?
 A: Ja, Sie können eine temporäre Lizenz erhalten von[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
