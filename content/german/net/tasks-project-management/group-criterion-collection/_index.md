---
title: Verwalten Sie MS Project-Gruppenkriterien mit Aspose.Tasks
linktitle: Verwalten der Sammlung von Gruppenkriterien in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie die Group Criterion MS Project-Sammlung mit Aspose.Tasks für .NET verwalten. Schritt-für-Schritt-Anleitung für Entwickler.
type: docs
weight: 28
url: /de/net/tasks-project-management/group-criterion-collection/
---
## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten. In diesem Tutorial erfahren Sie, wie Sie die Group Criterion-Sammlung in MS Project mithilfe von Aspose.Tasks verwalten.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1.  Aspose.Tasks für .NET: Stellen Sie sicher, dass die Aspose.Tasks-Bibliothek in Ihrem .NET-Projekt installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).

2. Microsoft Project-Datei: Halten Sie eine Microsoft Project-Datei (MPP) bereit, mit der Sie arbeiten können.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren. Dieser Schritt ist entscheidend für den Zugriff auf die von Aspose.Tasks bereitgestellten Funktionen.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Schritt 1: Laden Sie die Projektdatei

 Initialisieren Sie a`Project` Objekt durch Laden der MPP-Datei. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Schritt 2: Greifen Sie auf die Gruppenkriterien zu

Rufen Sie die Gruppe aus dem Projekt ab und greifen Sie auf ihre Kriterien zu.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Schritt 3: Iterieren Sie die Gruppenkriterien

Durchlaufen Sie jedes Kriterium in der Gruppe und zeigen Sie seine Eigenschaften an.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Schritt 4: Gruppenkriterien löschen

Löschen Sie vorhandene Gruppenkriterien, wenn diese nicht schreibgeschützt sind.

```csharp
group.GroupCriteria.Clear();
```

## Schritt 5: Neues Kriterium hinzufügen

Erstellen Sie ein neues Gruppenkriterium und fügen Sie es der Gruppe hinzu.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Schritt 6: Kriterien in eine andere Gruppe kopieren

Kopieren Sie die Kriterien von einer Gruppe in eine andere.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Abschluss

In diesem Tutorial haben wir gelernt, wie man die Group Criterion MS Project-Sammlung mit Aspose.Tasks für .NET verwaltet. Wenn Sie diese Schritte befolgen, können Sie Gruppenkriterien in Ihren Microsoft Project-Dateien effektiv programmgesteuert bearbeiten.

## FAQs

### F1: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?

A: Ja, Aspose.Tasks unterstützt Microsoft Project-Dateien verschiedener Versionen, einschließlich 2003, 2007, 2010, 2013 und 2016.

### F2: Kann ich mehrere Kriterien auf eine einzelne Gruppe anwenden?

A: Auf jeden Fall können Sie einer Gruppe mehrere Kriterien hinzufügen, indem Sie jedes durchgehen und sie entsprechend hinzufügen.

### F3: Gibt es eine Testversion für Aspose.Tasks?

 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks unter erhalten[Hier](https://releases.aspose.com/).

### F4: Wo finde ich Dokumentation für Aspose.Tasks?

 A: Sie können sich auf die Dokumentation beziehen[Hier](https://reference.aspose.com/tasks/net/).

### F5: Wie kann ich Support erhalten, wenn ich auf Probleme stoße?

 A: Wenn Sie Fragen haben oder auf Probleme stoßen, können Sie im Aspose.Tasks-Forum Unterstützung suchen[Hier](https://forum.aspose.com/c/tasks/15).