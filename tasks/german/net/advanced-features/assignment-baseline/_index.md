---
date: 2026-03-19
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Projektbaselines festlegen
  und Zuordnungsbaselines effizient verwalten, um eine genaue Verfolgung des Projektfortschritts
  zu gewährleisten.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projekt‑Baseline festlegen – Verwaltung der Zuordnungs‑Baseline in Aspose.Tasks
url: /de/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt-Baseline festlegen – Verwaltung von Zuordnungs-Baselines in Aspose.Tasks

## Einleitung

Bei der Arbeit an Projektmanagement‑Aufgaben ist das **Festlegen einer Projekt‑Baseline** entscheidend, um den tatsächlichen Fortschritt mit dem ursprünglichen Plan zu messen. Aspose.Tasks für .NET ermöglicht nicht nur das **Festlegen einer Projekt‑Baseline**, sondern gibt Ihnen auch die volle Kontrolle über Zuordnungs‑Baselines, was eine präzise Leistungsnachverfolgung ermöglicht. In diesem Tutorial führen wir Sie durch den gesamten Prozess – Laden eines Projekts, Festlegen einer Baseline, Auslesen von Zuordnungs‑Baseline‑Daten und Vergleich von Baselines – damit Sie Ihre Projekte sicher überwachen können.

## Schnelle Antworten
- **Was bedeutet „Projekt‑Baseline festlegen“?** Sie zeichnet den ursprünglichen Zeitplan und Kostendaten für einen späteren Vergleich mit der tatsächlichen Leistung auf.  
- **Welche API‑Methode legt eine Baseline fest?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Erfordern Zuordnungs‑Baselines einen separaten Aufruf?** Nein, sie werden automatisch gespeichert, wenn Sie eine Projekt‑Baseline festlegen.  
- **Welche Formate werden unterstützt?** MPP, XML, MPX und weitere über Aspose.Tasks.  
- **Ist für den Produktionseinsatz eine Lizenz erforderlich?** Ja, für die Nutzung außerhalb der Testversion wird eine kommerzielle Lizenz benötigt.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in C#-Programmierung.  
- Visual Studio (beliebige aktuelle Version).  
- Aspose.Tasks für .NET Bibliothek zu Ihrem Projekt hinzugefügt. Sie können sie von [hier](https://releases.aspose.com/tasks/net/) herunterladen.  
- Zugriff auf eine Projektdatei im MPP-Format (z. B. `AssignmentBaseline2007.mpp`).

## Namespaces importieren

Fügen Sie die erforderlichen Namespaces am Anfang Ihrer C#‑Datei hinzu, damit der Compiler weiß, wo die Aspose.Tasks‑Klassen zu finden sind.

```csharp
using Aspose.Tasks;
using System;
```

## Schritt 1: Projekt laden und Projekt‑Baseline festlegen

Laden Sie zunächst die vorhandene MPP‑Datei und rufen Sie anschließend `SetBaseline` auf, um die **Projekt‑Baseline** für das gesamte Projekt **festzulegen**.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Schritt 2: Zuordnungs‑Baseline‑Informationen auslesen

Nachdem die Baseline festgelegt wurde, enthält jede Ressourcenzuordnung ihre eigenen Baseline‑Einträge. Die nachstehende Schleife extrahiert und gibt diese Details aus, einschließlich Start‑/Enddatum, Kosten, Arbeit und etwaiger zeitlich aufgeschlüsselter Daten.

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

## Schritt 3: Zuordnungs‑Baselines vergleichen

Sie können Baselines verschiedener Zuordnungen mithilfe der integrierten Gleichheits‑ und Vergleichsoperatoren vergleichen. Das ist praktisch, wenn Sie Terminverschiebungen oder Kostenüberschreitungen zwischen Aufgaben erkennen müssen.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|----------------|-----|
| **Baseline‑Daten sind leer** | Die Projektdatei wurde im Nur‑Lese‑Modus geöffnet oder die Baseline wurde nie festgelegt. | Rufen Sie `project.SetBaseline(BaselineType.Baseline)` auf, bevor Sie Zuordnungs‑Baselines auslesen. |
| **`NullReferenceException` bei `TimephasedData`** | Nicht alle Baselines enthalten zeitlich aufgeschlüsselte Einträge. | Prüfen Sie stets `baseline.TimephasedData != null` (wie im Code gezeigt). |
| **Falscher UID‑Abruf** | UID‑Werte unterscheiden sich zwischen Dateiversionen. | Verwenden Sie `ResourceAssignments.GetByUid` mit der korrekten UID oder iterieren Sie, um die benötigte Zuordnung zu finden. |

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks mehrere Baselines für eine einzelne Zuordnung verarbeiten?**  
A: Ja, Aspose.Tasks unterstützt mehrere Baselines für jede Zuordnung, was eine umfassende Verfolgung des Projektfortschritts im Laufe der Zeit ermöglicht.

**Q: Ist Aspose.Tasks mit verschiedenen Projektdateiformaten außer MPP kompatibel?**  
A: Ja, Aspose.Tasks unterstützt eine Vielzahl von Projektdateiformaten, einschließlich XML, MPX und MPP, und gewährleistet die Kompatibilität mit verschiedenen Projektmanagement‑Tools.

**Q: Kann ich Baseline‑Informationen programmgesteuert mit Aspose.Tasks ändern?**  
A: Absolut, Aspose.Tasks stellt umfangreiche APIs bereit, um Baseline‑Informationen dynamisch gemäß den Projektanforderungen zu ändern, und bietet Flexibilität und Kontrolle über Projektmanagement‑Prozesse.

**Q: Bietet Aspose.Tasks Dokumentations‑ und Support‑Ressourcen für Entwickler?**  
A: Ja, Entwickler können auf umfassende Dokumentation, Tutorials und Foren auf der Aspose.Tasks‑Website zugreifen, was eine reibungslose Integration und Fehlersuche ermöglicht.

**Q: Gibt es eine Testversion von Aspose.Tasks für .NET?**  
A: Ja, Entwickler können eine kostenlose Testversion von Aspose.Tasks für .NET von [hier](https://releases.aspose.com/) erhalten, um die Funktionen und Fähigkeiten vor einer Kaufentscheidung zu evaluieren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose