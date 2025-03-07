---
title: Sammlung von Ressourcenzuweisungen in Aspose.Tasks
linktitle: Sammlung von Ressourcenzuweisungen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Ressourcenzuweisungen in Microsoft Project mit Aspose.Tasks für .NET verwalten. Schritt-für-Schritt-Anleitung mit Codebeispielen.
weight: 12
url: /de/net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sammlung von Ressourcenzuweisungen in Aspose.Tasks

## Einführung
Willkommen zu diesem umfassenden Tutorial zum Verwalten von Ressourcenzuweisungen in Microsoft Project mit Aspose.Tasks für .NET. In diesem Tutorial befassen wir uns Schritt für Schritt mit dem Prozess und stellen sicher, dass Sie ein solides Verständnis dafür haben, wie Sie Ressourcenzuweisungen effizient bearbeiten. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieser Leitfaden führt Sie durch alles, was Sie wissen müssen.
## Voraussetzungen
Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
1.  Aspose.Tasks für .NET installiert: Stellen Sie sicher, dass Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert ist. Wenn nicht, können Sie es hier herunterladen[Hier](https://releases.aspose.com/tasks/net/).
2. Grundkenntnisse von C#: In diesem Tutorial wird davon ausgegangen, dass Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen.
3. Microsoft Project-Datei: Halten Sie zu Testzwecken eine Microsoft Project-Datei bereit. Wenn Sie noch keine haben, können Sie eine Beispieldatei erstellen.

## Namespaces importieren
Importieren wir zunächst die notwendigen Namespaces:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Schritt 1: Laden Sie die Projektdatei
Beginnen Sie mit dem Laden der Microsoft Project-Datei:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Schritt 2: Aufgabe und Ressource hinzufügen
Fügen wir nun dem Projekt eine Aufgabe und eine Ressource hinzu:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Schritt 3: Ressource einer Aufgabe zuweisen
Als Nächstes weisen wir die Ressource der Aufgabe zu:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Schritt 4: Arbeiten mit verschiedenen Aufgabentypen
Sie können auch mit Zuweisungen arbeiten, die Einheiten oder Kosten betreffen:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Legen Sie Eigenschaften für Zuweisungen mit Einheiten und Kosten fest, ähnlich wie in Schritt 3 gezeigt
```
## Schritt 5: Aufgaben drucken
Drucken Sie die Aufgaben für das Projekt aus:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Auftragsdetails drucken
}
```
## Schritt 6: Zuweisung nach UID abrufen
Sie können Aufgaben nach UID abrufen:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Schritt 7: Überprüfen Sie den schreibgeschützten Status
Überprüfen Sie, ob die Ressourcenzuweisungssammlung schreibgeschützt ist:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Schritt 8: Sammlung in Liste konvertieren und iterieren
Konvertieren Sie die Sammlung in eine Liste und iterieren Sie darüber:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Abschluss
Glückwunsch! Sie haben gelernt, wie Sie Ressourcenzuweisungen in Microsoft Project mithilfe von Aspose.Tasks für .NET verwalten. Wenn Sie diese Schritte befolgen, können Sie Aufgaben und Ressourcen effizient bearbeiten und so das Projektmanagement zum Kinderspiel machen.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit verschiedenen Versionen von Microsoft Project-Dateien verwenden?
A: Ja, Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich MPP-, MPT- und XML-Formate.
### F: Gibt es vor dem Kauf von Aspose.Tasks für .NET eine Testversion?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET unter erhalten[Hier](https://releases.aspose.com/).
### F: Wie kann ich Unterstützung erhalten, wenn bei der Verwendung von Aspose.Tasks für .NET Probleme auftreten?
 A: Sie können Unterstützung im Aspose.Tasks-Forum suchen[Hier](https://forum.aspose.com/c/tasks/15).
### F: Kann ich temporäre Lizenzen für Aspose.Tasks für .NET verwenden?
 A: Ja, zu Evaluierungszwecken stehen temporäre Lizenzen zur Verfügung. Sie können eines von bekommen[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich eine Volllizenz für Aspose.Tasks für .NET erwerben?
 A: Sie können eine Volllizenz im Aspose-Onlineshop erwerben[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
