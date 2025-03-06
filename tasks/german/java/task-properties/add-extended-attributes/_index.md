---
title: Fügen Sie Aufgaben in Aspose.Tasks erweiterte Attribute hinzu
linktitle: Fügen Sie Aufgaben in Aspose.Tasks erweiterte Attribute hinzu
second_title: Aspose.Tasks Java-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Tasks Java beim Anpassen von Microsoft Project-Dateien mit erweiterten Attributen. Erweitern Sie mühelos Ihre Projektmanagementfähigkeiten.
weight: 11
url: /de/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie Aufgaben in Aspose.Tasks erweiterte Attribute hinzu

## Einführung
Die Verbesserung Ihrer Projektmanagementfähigkeiten ist für eine effiziente Aufgabenverfolgung und Ressourcenverwaltung von entscheidender Bedeutung. Aspose.Tasks für Java bietet Java-Entwicklern eine leistungsstarke Lösung zur nahtlosen Bearbeitung von Microsoft Project-Dateien. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java erweiterte Attribute zu Aufgaben hinzufügen, sodass Sie Ihre Projektdaten entsprechend Ihren spezifischen Anforderungen anpassen und organisieren können.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Tasks für Java-Bibliothek installiert. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/tasks/java/).
- Eine auf Ihrem System installierte Java Integrated Development Environment (IDE).
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete, um auf die Funktionen von Aspose.Tasks zuzugreifen:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Lassen Sie uns nun jedes Beispiel in mehrere Schritte unterteilen:
## 1. Hinzufügen eines Nur-Text-Attributs
1. Legen Sie den Pfad zum Dokumentverzeichnis fest:
```java
String dataDir = "Your Document Directory";
```
2. Erstellen Sie ein neues Projekt:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Erstellen Sie eine erweiterte Attributdefinition vom Typ Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Fügen Sie die Definition zur Sammlung erweiterter Attribute des Projekts hinzu:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Fügen Sie dem Projekt eine Aufgabe hinzu:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Erstellen Sie ein erweitertes Attribut aus der Attributdefinition:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Weisen Sie dem generierten erweiterten Attribut einen Wert zu:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Fügen Sie der Aufgabe das erweiterte Attribut hinzu:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Speichern Sie das Projekt:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Textattribut mit Suchoption hinzufügen
Befolgen Sie die gleichen Schritte wie oben, ersetzen Sie Text1 durch Text2 und passen Sie die Suchwerte an.
## 3. Hinzufügen eines Dauerattributs mit der Suchoption
Befolgen Sie die gleichen Schritte wie oben, ersetzen Sie Text1 durch Duration2 und passen Sie die Suchwerte an.
## Abschluss
Durch Befolgen dieser Schritt-für-Schritt-Anleitung haben Sie gelernt, wie Sie Aspose.Tasks für Java nutzen können, um Aufgaben in Ihren Microsoft Project-Dateien erweiterte Attribute hinzuzufügen. Durch diese Anpassung können Sie Ihren Projektmanagementansatz individuell anpassen und so die Flexibilität und Effizienz steigern.
## Häufig gestellte Fragen
### F: Kann ich Aspose.Tasks für Java mit anderen Java-Bibliotheken verwenden?
A: Ja, Aspose.Tasks für Java lässt sich nahtlos in Ihre Java-Projekte integrieren und funktioniert gut mit anderen Java-Bibliotheken.
### F: Ist Aspose.Tasks für Java für umfangreiche Projektmanagementanwendungen geeignet?
A: Absolut, Aspose.Tasks für Java ist für die Bearbeitung von Projekten unterschiedlicher Größe, einschließlich umfangreicher Anwendungen, konzipiert.
### F: Gibt es lizenzrechtliche Überlegungen für die Verwendung von Aspose.Tasks für Java in einem kommerziellen Projekt?
 A: Ja, lesen Sie sich unbedingt die Lizenzinformationen durch[Aspose.Tasks-Website](https://purchase.aspose.com/buy).
### F: Wie kann ich Unterstützung oder Hilfe zu Aspose.Tasks für Java erhalten?
 A: Besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und Diskussionen.
### F: Kann ich Aspose.Tasks für Java vor dem Kauf testen?
 A: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
