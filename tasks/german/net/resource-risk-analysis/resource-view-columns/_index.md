---
title: Passen Sie die Spalten der MS Project-Ressourcenansicht in Aspose.Tasks an
linktitle: Anpassen der Ressourcenansichtsspalten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie die Spalten der MS Project-Ressourcenansicht mithilfe von Aspose.Tasks für .NET effizient anpassen. Erstellen Sie maßgeschneiderte Ansichten für ein besseres Projektmanagement.
weight: 17
url: /de/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Passen Sie die Spalten der MS Project-Ressourcenansicht in Aspose.Tasks an

## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten. Eine häufige Aufgabe im Projektmanagement besteht darin, Ansichten anzupassen, um bestimmte Informationen anzuzeigen. In diesem Tutorial erfahren Sie, wie Sie die Spalten der MS Project-Ressourcenansicht mithilfe von Aspose.Tasks für .NET anpassen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks für .NET-Bibliothek: Sie können es herunterladen von[Hier](https://releases.aspose.com/tasks/net/).
2. Microsoft Project-Datei: Halten Sie zum Testen eine Beispiel-MS Project-Datei bereit.
3. Entwicklungsumgebung: Eine mit .NET Framework eingerichtete Entwicklungsumgebung.
## Namespaces importieren
Importieren wir zunächst die notwendigen Namespaces in unser Projekt:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Schritt 1: Laden Sie die Projektdatei
Laden Sie die MS Project-Datei mit der Aspose.Tasks-API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Schritt 2: Ressource abrufen und Optionen definieren
Rufen Sie als Nächstes die Ressource ab, deren Ansichtsspalten Sie anpassen möchten, und definieren Sie die PDF-Speicheroptionen:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Schritt 3: Benutzerdefinierte Spalten definieren
Definieren Sie nun benutzerdefinierte Spalten für die Ressourcenansicht. Sie können verschiedene Felder angeben und sogar Delegaten für benutzerdefinierte Berechnungen verwenden:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Schritt 4: Über Spalten iterieren
Durchlaufen Sie die definierten Spalten und zeigen Sie deren Eigenschaften an:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Schritt 5: Speichern Sie die benutzerdefinierte Ansicht
Legen Sie abschließend die benutzerdefinierte Ansicht fest und speichern Sie sie als PDF-Datei:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Wenn Sie diese Schritte befolgen, können Sie die Spalten der MS Project-Ressourcenansicht mithilfe von Aspose.Tasks für .NET effizient anpassen.
## Abschluss
Das Anpassen der Spalten in der MS Project-Ressourcenansicht ist für die Anzeige relevanter Informationen, die auf die Anforderungen Ihres Projekts zugeschnitten sind, von entscheidender Bedeutung. Mit Aspose.Tasks für .NET wird diese Aufgabe unkompliziert und effizient, sodass Sie mühelos benutzerdefinierte Ansichten erstellen können.
## FAQs
### Kann ich Ansichten für andere Elemente außer Ressourcen anpassen?
Ja, Aspose.Tasks ermöglicht auch die Anpassung von Aufgaben, Zuweisungen und anderen Projektelementen.
### Unterstützt Aspose.Tasks das Speichern von Ansichten in anderen Formaten als PDF?
Ja, Sie können Ansichten in verschiedenen Formaten wie XLSX, HTML und Bildern speichern.
### Ist es möglich, Formatierungen auf die benutzerdefinierte Ansicht anzuwenden?
Aspose.Tasks bietet auf jeden Fall umfangreiche Formatierungsoptionen, um das Erscheinungsbild Ihrer benutzerdefinierten Ansichten zu verbessern.
### Kann ich die benutzerdefinierte Ansicht basierend auf sich ändernden Projektdaten dynamisch aktualisieren?
Ja, Sie können die benutzerdefinierte Ansicht aktualisieren und neu generieren, wenn sich die zugrunde liegenden Projektdaten ändern.
### Unterstützt Aspose.Tasks die plattformübergreifende Entwicklung?
Aspose.Tasks für .NET zielt hauptsächlich auf .NET-Plattformen ab, es sind jedoch auch Versionen für Java und andere Plattformen verfügbar.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
