---
title: Verwalten von Projektsammlungen in Aspose.Tasks
linktitle: Gruppensammlung in Aspose.Tasks verwalten
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Sammlungen mit Aspose.Tasks für .NET effizient verwalten. Folgen Sie unserer Schritt-für-Schritt-Anleitung.
type: docs
weight: 26
url: /de/net/tasks-project-management/group-collection/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie MS Project-Gruppensammlungen mit Aspose.Tasks für .NET verwalten. Die Verwaltung von Gruppensammlungen ist für die effiziente Organisation und Bearbeitung von Aufgaben und Ressourcen in Ihrem Projekt von entscheidender Bedeutung.
## Voraussetzungen
Bevor Sie mit diesem Tutorial fortfahren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek von herunter und installieren Sie sie[Download-Link](https://releases.aspose.com/tasks/net/).
2. Grundkenntnisse von C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut, da dieses Tutorial das Codieren in C# beinhaltet.
3. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung wie Visual Studio oder eine andere IDE ein, die die .NET-Entwicklung unterstützt.

## Namespaces importieren
Importieren wir zunächst die notwendigen Namespaces, um mit den Aspose.Tasks-Funktionen in unserem C#-Code zu arbeiten.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Schritt 1: Laden Sie das Projekt
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Dieser Schritt beinhaltet das Laden der MS Project-Datei in das Aspose.Tasks-Projektobjekt, sodass wir Vorgänge daran ausführen können.
## Schritt 2: Iterieren Sie über Aufgabengruppen
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Hier durchlaufen wir Aufgabengruppen innerhalb des Projekts und drucken Details wie Index, Name und Sichtbarkeit im Menü für jede Gruppe.
## Schritt 3: Iterieren Sie über Ressourcengruppen
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
In ähnlicher Weise werden in diesem Schritt Ressourcengruppen durchlaufen und deren Index, Name und Sichtbarkeit im Menü angezeigt.
## Schritt 4: Gruppen löschen und in ein anderes Projekt kopieren
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Löschen Sie die Gruppen anderer Projekte
otherProject.TaskGroups.Clear();
// Gruppen in anderes Projekt kopieren
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Hier löschen wir die Gruppen eines anderen Projekts und kopieren dann Gruppen aus dem ursprünglichen Projekt dorthin.
## Schritt 5: Fügen Sie eine benutzerdefinierte Aufgabengruppe hinzu
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
In diesem Schritt erstellen wir eine benutzerdefinierte Aufgabengruppe und fügen sie dem anderen Projekt hinzu, falls sie noch nicht vorhanden ist.
## Schritt 6: Alle Gruppen entfernen
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Abschließend entfernen wir alle Gruppen aus dem anderen Projekt.

## Abschluss
Das Verwalten von MS Project-Gruppensammlungen in Aspose.Tasks für .NET ist für die effiziente Organisation und Bearbeitung von Projektdaten unerlässlich. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Aufgaben- und Ressourcengruppen in Ihren Projekten effektiv verwalten und so das gesamte Projektmanagement verbessern.
## FAQs
### Ist Aspose.Tasks für .NET mit allen Versionen von MS Project kompatibel?
Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project, einschließlich 2003, 2007, 2010, 2013, 2016 und 2019.
### Kann ich Gruppeneigenschaften mit Aspose.Tasks für .NET anpassen?
Ja, Sie können Gruppeneigenschaften wie Name und Sichtbarkeit mit Aspose.Tasks für .NET anpassen.
### Bietet Aspose.Tasks für .NET plattformübergreifende Kompatibilität?
Aspose.Tasks für .NET zielt hauptsächlich auf das .NET-Framework ab, kann jedoch in plattformübergreifenden Szenarien mit .NET Core und .NET Standard verwendet werden.
### Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?
 Unterstützung für Aspose.Tasks für .NET erhalten Sie über die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
### Gibt es eine Testversion für Aspose.Tasks für .NET?
 Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET herunterladen[Webseite](https://releases.aspose.com/).