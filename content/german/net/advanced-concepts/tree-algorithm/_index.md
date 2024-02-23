---
title: Verwendung des Baumalgorithmus in Aspose.Tasks
linktitle: Verwendung des Baumalgorithmus in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Aufgabenhierarchien in Ihren .NET-Projekten mithilfe des Baumalgorithmus von Aspose.Tasks effektiv manipulieren.
type: docs
weight: 13
url: /de/net/advanced-concepts/tree-algorithm/
---
## Einführung

Aspose.Tasks für .NET bietet leistungsstarke Funktionen für die Arbeit mit Projektmanagementaufgaben, Ressourcen und Zeitplänen. Eine dieser Funktionen ist der Baumalgorithmus, der es Benutzern ermöglicht, Aufgabenhierarchien effizient zu manipulieren. In diesem Tutorial erfahren Sie, wie Sie den Baumalgorithmus in Aspose.Tasks für .NET verwenden, um allgemeine Arbeiten zu sammeln und Arbeitswerte innerhalb eines Projekts zu aktualisieren.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist.
2.  Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis von C#: Um den Beispielen folgen zu können, sind Kenntnisse der Programmiersprache C# erforderlich.

## Namespaces importieren

Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um mit den Aspose.Tasks-Funktionen zu arbeiten:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Lassen Sie uns nun jedes Beispiel in mehrere Schritte unterteilen:

## Schritt 1: Projektdatei laden

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Laden Sie die Projektdatei mit in den Speicher`Project` Klasse.

## Schritt 2: Aufgabenhierarchie definieren

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definieren Sie die Aufgabenhierarchie, indem Sie übergeordnete und untergeordnete Aufgaben hinzufügen.

## Schritt 3: Aufgabeneigenschaften festlegen

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Legen Sie Eigenschaften wie Startdatum, Dauer und Enddatum für Aufgaben fest.

## Schritt 4: Ressource hinzufügen

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Fügen Sie Ressourcen zum Projekt hinzu und weisen Sie sie nach Bedarf Aufgaben zu.

## Schritt 5: Baumalgorithmus anwenden

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Initialisieren Sie die`WorkAccumulator` Klasse und wenden Sie den Baumalgorithmus an, um gemeinsame Arbeiten zu sammeln.

## Schritt 6: Aufgabenarbeit aktualisieren

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Aktualisieren Sie die Arbeitswerte für Aufgaben basierend auf den gesammelten Informationen.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man den Baumalgorithmus in Aspose.Tasks für .NET nutzt, um Aufgabenhierarchien effektiv zu manipulieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Aufgaben und Ressourcen innerhalb Ihrer Projekte effizient verwalten.

## FAQs

### F1: Was ist Aspose.Tasks für .NET?

A1: Aspose.Tasks für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert mit C# zu bearbeiten.

### F2: Kann ich eine kostenlose Testversion von Aspose.Tasks für .NET herunterladen?

 A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET herunterladen unter[Hier](https://releases.aspose.com/).

### F3: Wo finde ich Dokumentation für Aspose.Tasks für .NET?

 A3: Sie finden die Dokumentation für Aspose.Tasks für .NET[Hier](https://reference.aspose.com/tasks/net/).

### F4: Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?

 A4: Für Unterstützung im Zusammenhang mit Aspose.Tasks für .NET können Sie die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).

### F5: Gibt es eine temporäre Lizenz für Testzwecke?

 A5: Ja, Sie können eine temporäre Lizenz zu Testzwecken bei erhalten[Hier](https://purchase.aspose.com/temporary-license/).