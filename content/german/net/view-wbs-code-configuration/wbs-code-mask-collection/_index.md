---
title: Beherrschen von WBS-Codemasken mit Aspose.Tasks für .NET
linktitle: Sammlung von WBS-Codemasken in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Verbessern Sie das Projektmanagement mit Aspose.Tasks für .NET. Erfahren Sie in diesem umfassenden Tutorial, wie Sie WBS-Codemasken mühelos erstellen, verwalten und übertragen.
type: docs
weight: 15
url: /de/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Einführung
In der dynamischen Welt des Projektmanagements ist die effiziente Organisation von Aufgaben von entscheidender Bedeutung. Aspose.Tasks für .NET bietet eine leistungsstarke Lösung zur mühelosen Verwaltung von Projektstrukturplan-Codes (WBS). In diesem Tutorial befassen wir uns mit der Sammlung von WBS-Codemasken und untersuchen, wie diese mithilfe von Aspose.Tasks für .NET implementiert und bearbeitet werden.
## Voraussetzungen
Bevor wir uns auf die Codierungsreise begeben, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Programmiersprache C#.
-  Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert. Wenn nicht, laden Sie es herunter[Hier](https://releases.aspose.com/tasks/net/).
- Ein Code-Editor wie Visual Studio für ein nahtloses Codierungserlebnis.
## Namespaces importieren
Importieren wir zunächst die erforderlichen Namespaces:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Initialisieren Sie die Projekt- und WBS-Codedefinition
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definieren Sie WBS-Codemasken
Löschen Sie alle vorhandenen Codemasken und fügen Sie neue hinzu:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Informationen zu Codemasken anzeigen
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Fügen Sie dem Projekt Aufgaben hinzu
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Aufgabeninformationen abrufen
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Codemasken manipulieren
Entfernen Sie eine Codemaske und stellen Sie sicher, dass sie entfernt wird:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Codemasken in ein anderes Projekt kopieren
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Codemasken in einem anderen Projekt anzeigen
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Fügen Sie Aufgaben zum anderen Projekt hinzu
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. PSP-Codes im anderen Projekt anzeigen
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Abschluss
Mit Aspose.Tasks für .NET wird die Verwaltung von WBS-Codes zu einer mühelosen Aufgabe. Dieses Tutorial behandelt die Erstellung, Bearbeitung und Übertragung von WBS-Codemasken und bietet Ihnen einen umfassenden Leitfaden zur Verbesserung Ihrer Projektmanagementerfahrung.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit anderen Programmiersprachen verwenden?
A: Aspose.Tasks unterstützt hauptsächlich .NET-Sprachen, Sie können jedoch Interoperabilitätsoptionen mit anderen Sprachen erkunden.
### F: Gibt es eine Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können die Testversion herunterladen[Hier](https://releases.aspose.com/).
### F: Wie kann ich Hilfe suchen oder Probleme mit Aspose.Tasks für .NET melden?
 A: Besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung und Diskussionen.
### F: Welchen Zweck haben WBS-Codes im Projektmanagement?
A: WBS-Codes helfen bei der hierarchischen Organisation und Strukturierung von Projektaufgaben und bieten einen systematischen Ansatz für die Projektplanung.
### F: Kann ich das Format von WBS-Codes in Aspose.Tasks für .NET anpassen?
A: Auf jeden Fall haben Sie mit Aspose.Tasks für .NET die volle Kontrolle über das Format und die Struktur von WBS-Codes.