---
title: Sammlung von Zuweisungsbasislinien in Aspose.Tasks
linktitle: Sammlung von Zuweisungsbasislinien in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Aufgabenbasislinien im Projektmanagement effizient verwalten. Steigern Sie Produktivität und Genauigkeit.
type: docs
weight: 15
url: /de/net/advanced-features/assignment-baseline-collection/
---
## Einführung

Im Bereich des Projektmanagements ist die Verfolgung und Verwaltung der Auftragsbasispläne von entscheidender Bedeutung, um den Projekterfolg und die Einhaltung von Zeitplänen sicherzustellen. Aspose.Tasks für .NET bietet eine Reihe robuster Funktionen, um die effiziente Handhabung von Zuweisungsbasislinien innerhalb von Projekten zu erleichtern. In diesem Tutorial befassen wir uns mit den Feinheiten der Arbeit mit Assignment Baseline Collections mithilfe von Aspose.Tasks für .NET.

## Voraussetzungen

Bevor Sie mit diesem Tutorial fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Grundkenntnisse der Programmiersprache C#.
2. Visual Studio ist auf Ihrem System installiert.
3.  Aspose.Tasks für .NET-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).

## Namespaces importieren

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;


```

## Schritt 1: Laden Sie die Projektdatei

Zuerst müssen wir die Projektdatei laden, die die Zuweisungsbasislinien enthält.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## Schritt 2: Zuweisungsgrundsätze lesen

Als Nächstes durchlaufen wir jede Ressourcenzuweisung im Projekt, um auf ihre jeweiligen Baselines zuzugreifen.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## Schritt 3: Zuweisungsbasislinien löschen

In diesem Schritt zeigen wir, wie Sie alle Zuweisungsbasispläne aus dem Projekt löschen.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## Abschluss

Eine effiziente Verwaltung der Auftragsbasispläne ist im Projektmanagement von größter Bedeutung, um die Einhaltung von Zeitplänen sicherzustellen und den Projektfortschritt genau zu verfolgen. Mit Aspose.Tasks für .NET wird die Bearbeitung von Zuweisungsbaselines nahtlos und stellt Entwicklern die notwendigen Tools zur Optimierung von Projektmanagementprozessen zur Verfügung.

## FAQs

### F1: Kann Aspose.Tasks Zuweisungsbasislinien für verschiedene Projektdateiformate verarbeiten?

A1: Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate, einschließlich MPP, XML und MPX, sodass Sie Aufgabenbasislinien mühelos über verschiedene Dateitypen hinweg verwalten können.

### F2: Ist Aspose.Tasks mit allen Versionen von .NET Framework kompatibel?

A2: Aspose.Tasks für .NET ist mit mehreren Versionen des .NET Framework kompatibel und gewährleistet so Kompatibilität und Flexibilität für Entwickler in verschiedenen Umgebungen.

### F3: Kann ich Zuweisungsbasislinien programmgesteuert mit Aspose.Tasks bearbeiten?

A3: Absolut, Aspose.Tasks bietet eine umfassende API, die es Entwicklern ermöglicht, Zuweisungsbasislinien gemäß den Projektanforderungen programmgesteuert zu erstellen, zu lesen, zu aktualisieren und zu löschen.

### F4: Bietet Aspose.Tasks technischen Support für Entwickler?

A4: Ja, Aspose.Tasks bietet über sein Community-Forum umfassenden technischen Support, in dem Entwickler Hilfe suchen, Wissen austauschen und mit Kollegen zusammenarbeiten können.

### F5: Kann ich Aspose.Tasks testen, bevor ich einen Kauf tätige?

A5: Ja, Aspose.Tasks bietet eine kostenlose Testversion an, die es Entwicklern ermöglicht, die Features und Funktionalitäten zu erkunden, bevor sie eine Kaufentscheidung treffen.