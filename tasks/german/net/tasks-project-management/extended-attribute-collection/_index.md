---
title: Verwalten Sie die MS Project-Attributsammlung in Aspose.Tasks
linktitle: Verwalten der erweiterten Attributsammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie erweiterte MS Project-Attribute mit Aspose.Tasks für .NET effizient verwalten. Bearbeiten Sie Aufgabenattribute nahtlos mit einer Schritt-für-Schritt-Anleitung.
weight: 12
url: /de/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten Sie die MS Project-Attributsammlung in Aspose.Tasks

## Einführung
Möchten Sie die erweiterten Attribute von MS Project mithilfe von Aspose.Tasks für .NET effizient verwalten? In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess. Lass uns eintauchen!
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Visual Studio: Installieren Sie Visual Studio auf Ihrem System.
2.  Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.

## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr Projekt:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Schritt 1: Projektdatei laden
Laden Sie zunächst die MS Project-Datei mit dem folgenden Codeausschnitt:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Schritt 2: Greifen Sie auf Aufgaben- und erweiterte Attribute zu
Greifen Sie auf eine bestimmte Aufgabe und ihre erweiterten Attribute zu:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Schritt 3: Erweiterte Attribute löschen
Löschen Sie bei Bedarf vorhandene erweiterte Attribute:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Schritt 4: Erstellen Sie erweiterte Attributdefinitionen
Erstellen Sie Definitionen für neue erweiterte Attribute:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Schritt 5: Iterieren Sie die erweiterten Aufgabenattribute
Iterieren Sie über die erweiterten Aufgabenattribute:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Schritt 6: Erweiterte Attribute hinzufügen
Fügen Sie der Aufgabe neue erweiterte Attribute hinzu:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Schritt 7: Arbeiten Sie mit erweiterten Attributen
Führen Sie nach Bedarf Vorgänge für erweiterte Attribute aus.
## Schritt 8: Erweiterte Attribute entfernen
Erweiterte Attribute nach Index oder bedingt entfernen:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Schritt 9: Attribute in eine andere Aufgabe kopieren
Kopieren Sie Attribute in eine andere Aufgabe innerhalb desselben oder eines anderen Projekts:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Abschluss
Die Verwaltung erweiterter Attributsammlungen von MS Project wird mit Aspose.Tasks für .NET nahtlos. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie erweiterte Attribute effizient verwalten und so Ihre Projektmanagementfähigkeiten verbessern.
## FAQs
### F: Kann ich erweiterte Attribute über mehrere Projekte hinweg bearbeiten?
A: Ja, Sie können mit Aspose.Tasks für .NET erweiterte Attribute zwischen Aufgaben in verschiedenen Projekten kopieren.
### F: Gibt es Beschränkungen hinsichtlich der Anzahl erweiterter Attribute pro Aufgabe?
A: Aspose.Tasks für .NET unterliegt keinen inhärenten Beschränkungen hinsichtlich der Anzahl erweiterter Attribute pro Aufgabe.
### F: Kann ich benutzerdefinierte erweiterte Attributfelder erstellen?
A: Auf jeden Fall! Mit Aspose.Tasks für .NET können Sie benutzerdefinierte erweiterte Attributfelder definieren, die auf Ihre Projektanforderungen zugeschnitten sind.
### F: Unterstützt Aspose.Tasks für .NET das Lesen und Schreiben in MS Project-Dateien verschiedener Versionen?
A: Ja, Aspose.Tasks für .NET unterstützt MS Project-Dateiformate in verschiedenen Versionen.
### F: Gibt es eine Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
