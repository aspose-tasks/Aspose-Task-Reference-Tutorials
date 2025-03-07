---
title: Speichern von MS Project-Dateien in verschiedenen Formaten in Aspose.Tasks
linktitle: Speichern von Dateien in verschiedenen Formaten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Dateien mit Aspose.Tasks für .NET in verschiedenen Formaten speichern. Einfache Schritte für effizientes Projektmanagement.
weight: 17
url: /de/net/rate-recurring-tasks/save-file-formats/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Speichern von MS Project-Dateien in verschiedenen Formaten in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Microsoft Project-Dateien mit Aspose.Tasks für .NET in verschiedenen Formaten speichern. Aspose.Tasks ist eine leistungsstarke API, die es Entwicklern ermöglicht, Projektdateien programmgesteuert zu bearbeiten und zu verwalten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung ein, z. B. Visual Studio.
3. Grundkenntnisse von C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.

## Namespaces importieren
Stellen Sie sicher, dass Sie die erforderlichen Namespaces am Anfang Ihrer C#-Datei importieren:
```csharp

using Aspose.Tasks.Saving;
```
## Schritt 1: Erstellen Sie ein Projektobjekt
Erstellen Sie zunächst ein Projektobjekt und laden Sie Ihre Microsoft Project-Datei.
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Schritt 2: Projekt im CSV-Format speichern
Speichern wir nun das Projekt im CSV-Format. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Schritt 3: Entdecken Sie andere Formate
 Aspose.Tasks unterstützt verschiedene Formate zum Speichern von Projektdateien, wie XML, PDF, XLSX und mehr. Sie können diese Formate erkunden, indem Sie einfach die ändern`SaveFileFormat` Parameter in der`Save` Methode.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Tasks für .NET ganz einfach Microsoft Project-Dateien in verschiedenen Formaten speichern.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man MS Project-Dateien mit Aspose.Tasks für .NET in verschiedenen Formaten speichert. Aspose.Tasks vereinfacht den Prozess der programmgesteuerten Bearbeitung von Projektdateien und bietet Entwicklern Flexibilität und Effizienz.
## FAQs
### F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?
A: Aspose.Tasks unterstützt die Formate Microsoft Project 2003 XML, Microsoft Project 2007 MPP und Microsoft Project 2010 MPP.
### F: Kann ich Aspose.Tasks vor dem Kauf testen?
 A: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### F: Wie kann ich Unterstützung für Aspose.Tasks erhalten?
A: Sie können Unterstützung vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).
### F: Sind temporäre Lizenzen für Aspose.Tasks verfügbar?
 A: Ja, zu Evaluierungszwecken stehen temporäre Lizenzen zur Verfügung. Sie können eines erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wie hoch sind die Preise für Aspose.Tasks?
 A: Preisinformationen finden Sie auf der Kaufseite von Aspose.Tasks[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
