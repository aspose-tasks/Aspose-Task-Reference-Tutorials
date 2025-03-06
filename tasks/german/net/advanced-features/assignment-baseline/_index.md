---
title: Verwalten der Zuweisungsbasislinie in Aspose.Tasks
linktitle: Verwalten der Zuweisungsbasislinie in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Aufgabenbasislinien effizient verwalten und so eine genaue Verfolgung des Projektfortschritts und der Projektleistung gewährleisten.
weight: 14
url: /de/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten der Zuweisungsbasislinie in Aspose.Tasks

## Einführung

Bei der Arbeit an Projektmanagementaufgaben ist die Verwaltung der Zuweisungsbasislinien von entscheidender Bedeutung, um den Fortschritt genau verfolgen zu können. Aspose.Tasks für .NET bietet einen umfassenden Satz an Tools zur effizienten Handhabung von Zuweisungsbasislinien. In diesem Tutorial befassen wir uns Schritt für Schritt mit dem Prozess der Verwaltung von Zuweisungsbasislinien.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Visual Studio ist auf Ihrem System installiert.
- Aspose.Tasks für .NET-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
- Zugriff auf eine Projektdatei im MPP-Format.

## Namespaces importieren

Um mit Aspose.Tasks arbeiten zu können, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Fügen Sie am Anfang Ihrer C#-Datei die folgenden Namespaces hinzu:

```csharp
using Aspose.Tasks;
using System;


```

## Schritt 1: Projekt laden und Basisplan festlegen

 Laden Sie zunächst die Projektdatei mit`Project` Klasse von Aspose.Tasks. Legen Sie dann mithilfe von den Basistyp für das Projekt fest`SetBaseline` Methode.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Schritt 2: Lesen Sie die Basisinformationen zur Zuweisung

Durchlaufen Sie jede Ressourcenzuweisung im Projekt und rufen Sie Basisinformationen für jede Zuweisung ab.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Schritt 3: Überprüfen Sie die Basisgleichheit

Vergleichen Sie Basisinformationen für verschiedene Aufgaben mithilfe verschiedener Vergleichsmethoden, die von Aspose.Tasks bereitgestellt werden.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Überprüfen Sie die Grundliniengleichheit
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Überprüfen Sie den Basisvergleich
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Baseline-Hashcodes anzeigen
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Abschluss

Die Verwaltung von Zuweisungsbasislinien ist ein wesentlicher Bestandteil des Projektmanagements und ermöglicht eine genaue Verfolgung von Fortschritt und Leistung. Mit Aspose.Tasks für .NET wird die Bearbeitung von Zuweisungs-Baselines rationalisiert und effizient und bietet Entwicklern leistungsstarke Tools zur Verbesserung der Projektmanagement-Workflows.

## FAQs

### F1: Kann Aspose.Tasks mehrere Baselines für eine einzelne Aufgabe verarbeiten?

A1: Ja, Aspose.Tasks unterstützt mehrere Baselines für jede Aufgabe und ermöglicht so eine umfassende Verfolgung des Projektfortschritts im Laufe der Zeit.

### F2: Ist Aspose.Tasks mit verschiedenen anderen Projektdateiformaten als MPP kompatibel?

A2: Ja, Aspose.Tasks unterstützt eine Vielzahl von Projektdateiformaten, einschließlich XML, MPX und MPP, und gewährleistet so die Kompatibilität mit verschiedenen Projektmanagement-Tools.

### F3: Kann ich Basisinformationen programmgesteuert mit Aspose.Tasks ändern?

A3: Absolut, Aspose.Tasks bietet umfangreiche APIs, um Basisinformationen dynamisch entsprechend den Projektanforderungen zu ändern und bietet so Flexibilität und Kontrolle über Projektmanagementprozesse.

### F4: Bietet Aspose.Tasks Dokumentation und Supportressourcen für Entwickler?

A4: Ja, Entwickler können auf der Aspose.Tasks-Website auf umfassende Dokumentation, Tutorials und Foren zugreifen, was eine reibungslose Integration und Fehlerbehebung erleichtert.

### F5: Gibt es eine Testversion für Aspose.Tasks für .NET?

 A5: Ja, Entwickler können eine kostenlose Testversion von Aspose.Tasks für .NET unter erhalten[Hier](https://releases.aspose.com/)Dies ermöglicht es ihnen, die Funktionen und Fähigkeiten zu bewerten, bevor sie eine Kaufentscheidung treffen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
