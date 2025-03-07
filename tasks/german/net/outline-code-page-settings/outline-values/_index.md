---
title: Beherrschen der Gliederungswerte von MS Project mit Aspose.Tasks
linktitle: Verwalten von Gliederungswerten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Gliederungswerte mit Aspose.Tasks für .NET effizient verwalten. Passen Sie Projektskizzen ganz einfach an.
weight: 16
url: /de/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beherrschen der Gliederungswerte von MS Project mit Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Microsoft Project-Gliederungswerte mithilfe der Aspose.Tasks-Bibliothek für .NET verwalten. Mit Aspose.Tasks können Sie Gliederungscodes einfach bearbeiten, neue Gliederungswerte erstellen und Projektgliederungen entsprechend Ihren Anforderungen anpassen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Installation von Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Hier](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung wie Visual Studio mit .NET Framework-Kompatibilität eingerichtet haben.
3. Grundlegendes Verständnis der C#-Programmierung: Machen Sie sich mit den Grundlagen der C#-Programmiersprache vertraut, da wir C# für die Arbeit mit der Aspose.Tasks-Bibliothek verwenden werden.

## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihren C#-Code:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Schritt 1: Laden Sie die Projektdatei
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Dieser Schritt initialisiert ein neues Projektobjekt und lädt die Microsoft Project-Datei aus dem angegebenen Verzeichnis.
## Schritt 2: Definieren Sie Gliederungscodedefinitionen
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Hier definieren wir zwei OutlineCodeDefinition-Objekte und fügen sie der OutlineCodes-Sammlung des Projekts hinzu.
## Schritt 3: Konturmaske definieren
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Dieser Schritt richtet eine OutlineMask für die Gliederungscodedefinition ein.
## Schritt 4: Umrisswerte erstellen
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
In diesem Schritt erstellen wir zwei OutlineValue-Objekte und legen deren Eigenschaften wie Wert, Wert-ID, Typ, Beschreibung und Reduzierungsstatus fest.

## Abschluss
Die Verwaltung von MS Project-Gliederungswerten mit Aspose.Tasks für .NET ist dank der bereitgestellten Funktionalitäten unkompliziert. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Gliederungscodes und -werte effizient bearbeiten, um Projektgliederungen entsprechend Ihren Anforderungen anzupassen.
## FAQs
### F: Kann ich Aspose.Tasks mit anderen .NET-Frameworks verwenden?
A: Ja, Aspose.Tasks ist mit verschiedenen .NET-Frameworks kompatibel und sorgt so für Flexibilität in Ihrer Entwicklungsumgebung.
### F: Gibt es eine Testversion für Aspose.Tasks?
 A: Ja, Sie können auf eine kostenlose Testversion von Aspose.Tasks zugreifen[Hier](https://releases.aspose.com/).
### F: Wie kann ich Unterstützung für Aspose.Tasks erhalten?
 A: Für Unterstützung und Unterstützung können Sie das Aspose.Tasks-Forum besuchen[Hier](https://forum.aspose.com/c/tasks/15).
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks erwerben?
A: Ja, Sie können eine temporäre Lizenz für Aspose.Tasks erwerben bei[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo finde ich eine ausführliche Dokumentation zu Aspose.Tasks?
 A: Sie können auf die umfassende verfügbare Dokumentation zurückgreifen[Hier](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
