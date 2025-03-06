---
title: Beherrschen Sie erweiterte Attributdefinitionen von MS Project in Aspose.Tasks
linktitle: Sammlung erweiterter Attributdefinitionen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie erweiterte Attributdefinitionen in Microsoft Project mit Aspose.Tasks für .NET verwalten. Passen Sie Ihre Projektdaten mühelos an und verbessern Sie sie.
type: docs
weight: 14
url: /de/net/tasks-project-management/extended-attribute-definition-collection/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für .NET mit erweiterten Attributdefinitionen in Microsoft Project arbeiten. Erweiterte Attribute bieten eine flexible Möglichkeit, Projektdaten anzupassen und zu verbessern, sodass Benutzer zusätzliche Felder hinzufügen können, die über die standardmäßig bereitgestellten Felder hinausgehen. Mit Aspose.Tasks können Sie diese erweiterten Attribute mühelos verwalten, um Ihre Projektmanagementanforderungen individuell anzupassen.
## Voraussetzungen
Bevor Sie fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen installiert sind:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um auf Aspose.Tasks-Klassen und -Methoden in Ihrem .NET-Projekt zuzugreifen. Folge diesen Schritten:
## Schritt 1: Öffnen Sie Ihr .NET-Projekt
Öffnen Sie Ihr .NET-Projekt in Ihrer bevorzugten IDE, z. B. Visual Studio.
## Schritt 2: Aspose.Tasks-Namespace hinzufügen
Fügen Sie die folgende Zeile am Anfang Ihrer Codedatei hinzu, um den Aspose.Tasks-Namespace zu importieren:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Lassen Sie uns nun die bereitgestellten Codebeispiele für ein umfassendes Verständnis in mehrere Schritte aufteilen:
## Schritt 1: Laden Sie die Projektdatei
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Schritt 2: Vorhandene erweiterte Attributdefinitionen löschen (optional)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Schritt 3: Erstellen Sie eine erweiterte Attributdefinition für eine Aufgabe und fügen Sie sie hinzu
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Schritt 4: Durchlaufen Sie die erweiterten Aufgabenattribute
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Schritt 5: Erstellen Sie eine erweiterte Attributdefinition für eine Ressource und fügen Sie sie hinzu
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Schritt 6: Fügen Sie eine Definition eines erweiterten Ressourcenattributs ein
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Schritt 7: Entfernen Sie ein erweitertes Attribut nach Index
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Abschluss
In diesem Tutorial haben wir die Grundlagen der Arbeit mit erweiterten Attributdefinitionen in Microsoft Project mithilfe von Aspose.Tasks für .NET behandelt. Wenn Sie diese Schritte befolgen, können Sie erweiterte Attribute effizient verwalten und an Ihre Projektmanagementanforderungen anpassen.
## FAQs
### F: Kann ich vorhandene erweiterte Attributdefinitionen ändern?
A: Ja, Sie können vorhandene erweiterte Attributdefinitionen entsprechend Ihren Anforderungen ändern oder neue erstellen.
### F: Werden erweiterte Attribute in allen Versionen von Microsoft Project unterstützt?
A: Ja, erweiterte Attribute werden in den meisten Versionen von Microsoft Project unterstützt, auch in den neueren.
### F: Kann ich erweiterte Attribute zum Berechnen benutzerdefinierter Felder verwenden?
A: Auf jeden Fall können erweiterte Attribute verwendet werden, um benutzerdefinierte Felder basierend auf bestimmten, von Ihnen definierten Kriterien zu berechnen.
### F: Ist Aspose.Tasks mit anderen .NET-Frameworks kompatibel?
A: Aspose.Tasks ist mit verschiedenen .NET-Frameworks kompatibel und gewährleistet so Flexibilität und einfache Integration.
### F: Wo finde ich weitere Ressourcen und Unterstützung für Aspose.Tasks?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung und erkunden Sie die Dokumentation[Hier](https://reference.aspose.com/tasks/net/).