---
title: Sammlung von Gliederungscodedefinitionen in Aspose.Tasks .NET
linktitle: Sammlung von Gliederungscodedefinitionen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Gliederungscodedefinitionen in Microsoft Project-Dokumenten mit Aspose.Tasks für .NET bearbeiten. Kategorisieren Sie Ihre Projektdaten mühelos.
weight: 13
url: /de/net/outline-code-page-settings/outline-code-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sammlung von Gliederungscodedefinitionen in Aspose.Tasks .NET

## Einführung
Aspose.Tasks ist eine leistungsstarke .NET-Bibliothek zur einfachen und effizienten Bearbeitung von Microsoft Project-Dokumenten. Eine seiner Hauptfunktionen ist die Möglichkeit, mit Gliederungscodedefinitionen zu arbeiten, sodass Benutzer Projektdaten effektiv organisieren und kategorisieren können. In diesem Tutorial erfahren Sie, wie Sie mithilfe von Aspose.Tasks für .NET mit Gliederungscodedefinitionen arbeiten.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Grundkenntnisse von C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.
2. Visual Studio: Installieren Sie Visual Studio oder eine andere bevorzugte C#-Entwicklungsumgebung.
3.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Schritt 1: Laden Sie ein Microsoft Project-Dokument
Laden Sie zunächst ein Microsoft Project-Dokument, um mit der Arbeit mit Gliederungscodedefinitionen zu beginnen:
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Schritt 2: Greifen Sie auf die Gliederungscodedefinitionen zu
Nun greifen wir auf die Gliederungscodedefinitionen innerhalb des Projekts zu:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Schritt 3: Fügen Sie benutzerdefinierte Gliederungscodedefinitionen hinzu
Sie können benutzerdefinierte Gliederungscodedefinitionen wie folgt hinzufügen:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Schritt 4: Gliederungscodedefinitionen ändern
Ändern Sie vorhandene Gliederungscodedefinitionen einfach:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Schritt 5: Gliederungscodedefinitionen entfernen
Entfernen Sie Gliederungscodedefinitionen, wenn sie nicht mehr benötigt werden:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Schritt 6: Änderungen speichern
Speichern Sie abschließend Ihre Änderungen am Projektdokument:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Abschluss
Zusammenfassend bietet Aspose.Tasks für .NET umfassende Funktionen zum Verwalten von Gliederungscodedefinitionen in Microsoft Project-Dokumenten. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Gliederungscodedefinitionen effizient bearbeiten, um Ihre Projektdaten effektiv zu organisieren und zu kategorisieren.
## FAQs
### F: Kann ich einem einzelnen Projekt mehrere Gliederungscodedefinitionen hinzufügen?
 A: Ja, Sie können je nach Ihren Anforderungen mehrere Gliederungscodedefinitionen zu einem Projekt hinzufügen. Nutzen Sie einfach die`Add` Methode für jede Definition, die Sie einschließen möchten.
### F: Ist es möglich, alle Gliederungscodedefinitionen auf einmal aus einem Projekt zu entfernen?
 A: Ja, Sie können mit dem alle Gliederungscodedefinitionen aus einem Projekt löschen`Clear` Methode.
### F: Was passiert, wenn ich versuche, eine schreibgeschützte Gliederungscodedefinition zu ändern?
A: Wenn eine Gliederungscodedefinition schreibgeschützt ist, können Sie sie nicht direkt ändern. Sie müssen den schreibgeschützten Status überprüfen, bevor Sie Änderungen vornehmen.
### F: Gibt es Einschränkungen hinsichtlich der Anzahl der Gliederungscodedefinitionen, die ich einem Projekt hinzufügen kann?
A: Aspose.Tasks für .NET legt keine besonderen Beschränkungen hinsichtlich der Anzahl der Gliederungscodedefinitionen fest, die Sie einem Projekt hinzufügen können. Berücksichtigen Sie jedoch die Auswirkungen auf die Leistung, wenn Sie mit einer großen Anzahl von Definitionen arbeiten.
### F: Kann ich Gliederungscodedefinitionen verwenden, um Aufgaben basierend auf benutzerdefinierten Kriterien zu gruppieren?
A: Ja, Gliederungscodedefinitionen ermöglichen Ihnen die Kategorisierung von Aufgaben anhand benutzerdefinierter Kriterien und bieten so Flexibilität bei der Organisation von Projektdaten.## Vollständiger Quellcode
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
