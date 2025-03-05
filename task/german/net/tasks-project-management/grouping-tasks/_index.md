---
title: Effiziente MS Project-Aufgabengruppierung mit Aspose.Tasks
linktitle: Gruppieren von Aufgaben in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Aufgaben mithilfe von Aspose.Tasks für .NET effektiv gruppieren.
type: docs
weight: 25
url: /de/net/tasks-project-management/grouping-tasks/
---
## Einführung
Die Verwaltung von Aufgaben in Microsoft Project kann manchmal eine Herausforderung sein, insbesondere wenn es darum geht, sie effizient zu organisieren. Aspose.Tasks für .NET bietet hierfür eine umfassende Lösung, indem es Funktionen zur effektiven Gruppierung von Aufgaben bereitstellt. In diesem Tutorial erfahren Sie, wie Sie MS Project-Aufgaben mithilfe von Aspose.Tasks für .NET gruppieren.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek herunter und installieren Sie sie[Hier](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine .NET-Entwicklungsumgebung eingerichtet haben.
3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren, um die Funktionen von Aspose.Tasks nutzen zu können:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Schritt 1: MS Project-Datei laden
Laden Sie zunächst Ihre MS Project-Datei mit dem folgenden Code:
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Schritt 2: Auf Aufgabengruppen zugreifen
Als nächstes greifen wir auf die Aufgabengruppen innerhalb des Projekts zu:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## Schritt 3: Gruppeninformationen abrufen
Rufen Sie nun Informationen zur Aufgabengruppe ab:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Schritt 4: Greifen Sie auf die Gruppenkriterien zu
Greifen Sie auf die für die Aufgabengruppe festgelegten Kriterien zu:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Schritt 5: Kriteriumsinformationen abrufen
Rufen Sie detaillierte Informationen zu jedem Kriterium ab:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Wenn Sie diese Schritte befolgen, können Sie MS Project-Aufgaben mit Aspose.Tasks für .NET effektiv gruppieren und so die Organisation und Verwaltung Ihrer Projektdaten verbessern.

## Abschluss
Zusammenfassend lässt sich sagen, dass Aspose.Tasks für .NET leistungsstarke Funktionen zum Gruppieren von MS Project-Aufgaben bietet und so eine bessere Organisation und Verwaltung von Projektdaten ermöglicht. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie diese Funktionen in Ihren .NET-Anwendungen effizient nutzen.
## FAQs
### Kann ich Aufgaben nach benutzerdefinierten Kriterien gruppieren?
Ja, Sie können mit Aspose.Tasks für .NET benutzerdefinierte Kriterien zum Gruppieren von Aufgaben entsprechend Ihren spezifischen Anforderungen definieren.
### Unterstützt Aspose.Tasks verschiedene Versionen von MS Project-Dateien?
Ja, Aspose.Tasks unterstützt verschiedene Versionen von MS Project-Dateien und gewährleistet so Kompatibilität und nahtlose Integration.
### Gibt es eine Testversion für Aspose.Tasks für .NET?
 Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET unter erhalten[Hier](https://releases.aspose.com/).
### Kann ich das Erscheinungsbild gruppierter Aufgaben anpassen?
Aspose.Tasks bietet auf jeden Fall Optionen zum Anpassen des Erscheinungsbilds gruppierter Aufgaben, einschließlich Zellenfarben, Schriftarten und Stilen.
### Wo finde ich Unterstützung für Aspose.Tasks für .NET?
 Unterstützung und Unterstützung für Aspose.Tasks für .NET finden Sie im[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).