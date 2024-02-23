---
title: Arten von Ressourcen in Aspose.Tasks
linktitle: Arten von Ressourcen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie in einem Schritt-für-Schritt-Tutorial, wie Sie mit verschiedenen Arten von Ressourcen in Aspose.Tasks für .NET arbeiten, einschließlich Arbeits-, Material- und Kostenressourcen.
type: docs
weight: 14
url: /de/net/resource-risk-analysis/resource-types/
---
## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten. Unabhängig davon, ob Sie Aufgaben, Ressourcen oder Zeitpläne verwalten, vereinfacht Aspose.Tasks den Prozess durch die Bereitstellung eines umfassenden Satzes von APIs. In diesem Tutorial befassen wir uns mit den verschiedenen Arten von Ressourcen, die Sie in Ihren Projekten mit Aspose.Tasks für .NET nutzen können.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Visual Studio: Installieren Sie Visual Studio, eine leistungsstarke integrierte Entwicklungsumgebung (IDE) für die .NET-Entwicklung.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse von C#: Machen Sie sich mit C# vertraut, der Programmiersprache, die für die .NET-Entwicklung verwendet wird.

## Namespaces importieren
Importieren wir zunächst die notwendigen Namespaces, um auf die Funktionalitäten von Aspose.Tasks für .NET zuzugreifen:
```csharp
    
```

## Schritt 1: Erstellen Sie eine neue Projektinstanz
```csharp
var project = new Project();
```
Diese Zeile initialisiert ein neues Projektobjekt, das als Container für alle projektbezogenen Daten und Vorgänge dient.
## Schritt 2: Fügen Sie eine Arbeitsressource hinzu
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Hier erstellen wir eine neue Arbeitsressource mit dem Namen „Arbeitsressource“ und geben ihren Typ als ResourceType.Work an.
## Schritt 3: Fügen Sie eine Materialressource hinzu
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
In diesem Schritt wird eine Materialressource mit dem Namen „Materialressource“ hinzugefügt, deren Typ auf „ResourceType.Material“ festgelegt ist. Zusätzlich geben wir auf dem Materialetikett „kg“ an, um die Maßeinheit anzugeben.
## Schritt 4: Fügen Sie eine Kostenressource hinzu
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Schließlich fügen wir eine Kostenressource mit dem Namen „Kostenressource“ hinzu und legen ihren Typ auf „ResourceType.Cost“ fest. Darüber hinaus legen wir den Kostenwert auf 59,99 fest, was den mit dieser Ressource verbundenen Geldwert darstellt.

## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie in Aspose.Tasks für .NET mit verschiedenen Arten von Ressourcen arbeiten, einschließlich Arbeits-, Material- und Kostenressourcen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Ressourcen in Ihren Projekten effektiv und programmgesteuert verwalten.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit anderen Projektmanagement-Softwareformaten verwenden?
A: Ja, Aspose.Tasks unterstützt verschiedene Formate, darunter Microsoft Project (MPP), Primavera P6 und mehr.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wie erhalte ich technischen Support für Aspose.Tasks für .NET?
 A: Sie können das Aspose.Tasks-Forum besuchen[Hier](https://forum.aspose.com/c/tasks/15) für technische Hilfe.
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks für .NET erwerben?
 A: Ja, Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
### F: Bietet Aspose.Tasks für .NET Dokumentation als Referenz?
 A: Ja, Sie können die Dokumentation finden[Hier](https://reference.aspose.com/tasks/net/).