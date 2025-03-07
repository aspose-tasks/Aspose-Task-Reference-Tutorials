---
title: Berechnungstyp in Aspose.Tasks
linktitle: Berechnungstyp in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Wertberechnungen in .NET-Projekten mit dem Berechnungstyp in der Aspose.Tasks-Bibliothek anpassen.
weight: 30
url: /de/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Berechnungstyp in Aspose.Tasks

## Einführung

In diesem Tutorial erkunden wir die Funktion „Berechnungstyp“ in Aspose.Tasks für .NET. Aspose.Tasks ist eine leistungsstarke Bibliothek, die es .NET-Entwicklern ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project auf ihren Systemen installiert sein muss. Mit dem Berechnungstyp können wir definieren, wie Werte für Aufgaben und Sammelaufgaben innerhalb eines Projekts berechnet werden.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Grundkenntnisse in C# und .NET Framework.
2. Visual Studio ist auf Ihrem System installiert.
3.  Aspose.Tasks für .NET-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
4.  Zugriff auf die Dokumentation zu Aspose.Tasks für .NET als Referenz verfügbar[Hier](https://reference.aspose.com/tasks/net/).

## Namespaces importieren

Bevor Sie sich mit dem Beispiel befassen, stellen Sie sicher, dass Sie die erforderlichen Namespaces importieren:

```csharp
using Aspose.Tasks;
using System;


```

## Schritt 1: Erstellen Sie ein neues Projekt

Erstellen wir zunächst ein neues Projektobjekt:

```csharp
var project = new Project();
```

## Schritt 2: Fügen Sie eine Aufgabe hinzu

Fügen wir nun unserem Projekt eine Aufgabe hinzu:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Schritt 3: Berechnungstyp für ein erweitertes Attribut definieren

Wir erstellen eine erweiterte Attributdefinition, wobei der Berechnungstyp auf Formel festgelegt ist:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Schritt 4: Berechnungstyp für Zusammenfassungszeilen definieren

Als Nächstes erstellen wir eine weitere erweiterte Attributdefinition, in der Werte für Sammelaufgaben mithilfe des Rollup-Typs „Durchschnitt“ berechnet werden:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit dem Berechnungstyp in Aspose.Tasks für .NET arbeitet. Durch die Definition von Berechnungstypen für erweiterte Attribute können wir anpassen, wie Werte für Aufgaben und Sammelaufgaben innerhalb eines Projekts berechnet werden, was für mehr Flexibilität und Kontrolle sorgt.

## FAQs

### F1: Was ist der Berechnungstyp in Aspose.Tasks?

A1: Der Berechnungstyp in Aspose.Tasks bestimmt, wie Werte für Aufgaben und Sammelaufgaben innerhalb eines Projekts berechnet werden, und bietet Optionen wie Formel und Rollup.

### F2: Wie lege ich den Berechnungstyp für ein erweitertes Attribut fest?

A2: Sie können den Berechnungstyp für ein erweitertes Attribut festlegen, indem Sie dessen CalculationType-Eigenschaft entsprechend definieren.

### F3: Kann ich den Berechnungstyp für Zusammenfassungszeilen in einem Projekt anpassen?

A3: Ja, mit Aspose.Tasks können Sie den Berechnungstyp für Zusammenfassungszeilen angeben, sodass Sie Wertberechnungen basierend auf Ihren Anforderungen anpassen können.

### F4: Gibt es verschiedene Rollup-Typen für Sammelaufgabenberechnungen?

A4: Ja, Aspose.Tasks bietet verschiedene Rollup-Typen wie Durchschnitt, Summe und Anzahl zum Berechnen von Werten von Sammelaufgaben.

### F5: Wo finde ich weitere Ressourcen zu Aspose.Tasks für .NET?

 A5: Sie können die Dokumentation und die Community-Supportforen erkunden, die auf der Website verfügbar sind[Aspose.Tasks für .NET](https://reference.aspose.com/tasks/net/) für umfassende Beratung und Unterstützung.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
