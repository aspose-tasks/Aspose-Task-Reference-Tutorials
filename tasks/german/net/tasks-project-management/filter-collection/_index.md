---
title: Verwalten Sie MS Project-Filter effizient mit Aspose.Tasks
linktitle: Verwalten der Filtersammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Filter-MS-Project-Sammlungen mit Aspose.Tasks für .NET effektiv verwalten.
weight: 17
url: /de/net/tasks-project-management/filter-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten Sie MS Project-Filter effizient mit Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Filter-MS-Project-Sammlungen mithilfe von Aspose.Tasks für .NET effektiv verwalten. Die Verwaltung von Filtern ist für die effiziente Organisation und Analyse von Projektdaten von entscheidender Bedeutung. Aspose.Tasks bietet robuste Funktionalität zur nahtlosen Handhabung von Aufgaben- und Ressourcenfiltern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Installation von Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET von herunter und installieren Sie es[Download-Link](https://releases.aspose.com/tasks/net/).
2. Zugriff auf die .NET-Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine .NET-Entwicklungsumgebung für die Arbeit mit Aspose.Tasks eingerichtet haben.

## Namespaces importieren
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Schritt 1: Projektdatei laden
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## Schritt 2: Durchlaufen Sie die Aufgabenfilter
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## Schritt 3: Iterieren Sie über Ressourcenfilter
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## Schritt 4: Filter löschen und kopieren
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Löschen Sie die Filter anderer Projekte
otherProject.TaskFilters.Clear();
// Kopieren Sie Filter in ein anderes Projekt
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## Schritt 5: Benutzerdefinierten Aufgabenfilter hinzufügen
```csharp
// Benutzerdefinierten Aufgabenfilter hinzufügen
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## Schritt 6: Alle Filter entfernen
```csharp
// Entfernen Sie alle Filter
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
Wenn Sie diese Schritte befolgen, können Sie Filter-MS-Project-Sammlungen mithilfe von Aspose.Tasks für .NET effizient verwalten.

## Abschluss
Die effektive Verwaltung von Filtern in MS Project-Sammlungen ist für die Organisation und Analyse von Projektdaten von entscheidender Bedeutung. Aspose.Tasks für .NET bietet umfassende Funktionen zur nahtlosen Handhabung von Aufgaben- und Ressourcenfiltern und ermöglicht Entwicklern so die effiziente Optimierung von Projektmanagementaufgaben.
## FAQs
### F: Kann Aspose.Tasks komplexe Projektstrukturen verarbeiten?
A: Aspose.Tasks bietet robuste Funktionen zur Handhabung verschiedener Projektstrukturen, auch komplexer, und gewährleistet so umfassende Projektmanagementfunktionen.
### F: Ist Aspose.Tasks mit verschiedenen Versionen von MS Project-Dateien kompatibel?
A: Ja, Aspose.Tasks unterstützt eine Vielzahl von MS Project-Dateiformaten und gewährleistet so die Kompatibilität zwischen verschiedenen Versionen.
### F: Kann ich Filter entsprechend spezifischer Projektanforderungen anpassen?
A: Auf jeden Fall! Mit Aspose.Tasks können Entwickler benutzerdefinierte Filter erstellen, die auf individuelle Projektanforderungen zugeschnitten sind und so die Flexibilität und Effizienz erhöhen.
### F: Bietet Aspose.Tasks Dokumentation und Supportressourcen?
A: Ja, Aspose.Tasks bietet umfangreiche Dokumentation, Tutorials und ein spezielles Support-Forum, um Entwickler bei jedem Schritt ihrer Projektimplementierung zu unterstützen.
### F: Gibt es eine Testversion für Aspose.Tasks?
A: Ja, Entwickler können auf eine kostenlose Testversion von Aspose.Tasks zugreifen, um die Funktionen zu erkunden, bevor sie eine Kaufentscheidung treffen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
