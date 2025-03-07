---
title: Verwalten der Projektressourcensammlung in Aspose.Tasks
linktitle: Verwalten der Ressourcensammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Ressourcensammlungen in .NET mithilfe der Aspose.Tasks-API effizient verwalten. Steigern Sie Produktivität und Flexibilität.
weight: 13
url: /de/net/resource-risk-analysis/managing-resource-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten der Projektressourcensammlung in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Microsoft Project-Ressourcensammlungen mithilfe von Aspose.Tasks für .NET effektiv verwalten. Aspose.Tasks ist eine leistungsstarke API, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten und so eine nahtlose Integration und Bearbeitung von Projektdaten zu ermöglichen.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Kenntnisse in C# und .NET Framework: Dieses Tutorial setzt Vertrautheit mit der Programmiersprache C# und .NET Framework voraus.
2. Installation von Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
3. Einrichtung der Entwicklungsumgebung: Richten Sie Ihre Entwicklungsumgebung mit Visual Studio oder einer anderen bevorzugten IDE ein.

## Namespaces importieren
Bevor wir beginnen, importieren Sie die erforderlichen Namespaces, um auf die Aspose.Tasks-Funktionen zuzugreifen:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Schritt 1: Laden Sie die Projektdatei
Laden Sie zunächst die Microsoft Project-Datei in das Projektobjekt Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Schritt 2: Leere Ressource hinzufügen
Als Nächstes fügen wir dem Projekt eine leere Ressource hinzu:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Schritt 3: Ressource mit einem Namen hinzufügen
Fügen Sie nun eine Ressource mit einem angegebenen Namen zum Projekt hinzu:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Schritt 4: Ressource vor einer anderen Ressource hinzufügen
Fügen Sie eine Ressource mit einem angegebenen Namen vor einer anderen Ressource basierend auf ihrer ID hinzu:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Schritt 5: Zugriff auf Ressourcen per ID oder UID
Sie können auf Ressourcen entweder über ihre ID oder UID zugreifen:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Schritt 6: Ressourceninformationen drucken
Informationen zu den Projektressourcen ausdrucken:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Schritt 7: Ressourcen löschen
Ressourcen aus dem Projekt löschen:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Abschluss
Durch die Verwaltung von Microsoft Project-Ressourcensammlungen mit Aspose.Tasks für .NET steht Entwicklern ein robuster Satz an Tools zur effizienten programmgesteuerten Verwaltung von Projektressourcen zur Verfügung. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Ressourcen in Ihren Projekten nahtlos bearbeiten und so die Produktivität und Flexibilität bei Projektmanagementaufgaben steigern.
## FAQs
### F: Kann Aspose.Tasks große Projektdateien verarbeiten?

A: Ja, Aspose.Tasks ist darauf ausgelegt, große Projektdateien effizient zu verarbeiten und bietet hohe Leistung und Zuverlässigkeit.

### F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?

A: Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.

### F: Kann ich Ressourceneigenschaften mit Aspose.Tasks anpassen?

A: Absolut, Aspose.Tasks bietet umfangreiche Möglichkeiten, Ressourceneigenschaften entsprechend spezifischer Projektanforderungen anzupassen.

### F: Unterstützt Aspose.Tasks Multithreading für gleichzeitige Vorgänge?

A: Ja, Aspose.Tasks unterstützt Multithreading und ermöglicht so gleichzeitige Vorgänge an Projektdaten, um die Leistung zu verbessern.

### F: Ist technischer Support für Aspose.Tasks-Benutzer verfügbar?

 A: Ja, Aspose.Tasks-Benutzer können über das Forum auf technischen Support zugreifen[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
