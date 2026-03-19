---
date: 2026-03-19
description: Lernen Sie, wie Sie Ressourcen zum Projekt hinzufügen, die Aufgabendauer
  mit dem Tree‑Algorithmus von Aspose.Tasks berechnen und Ressourcen Aufgaben in .NET
  zuweisen.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ressource zum Projekt mit Baumalgorithmus in Aspose.Tasks hinzufügen
url: /de/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ressource zum Projekt hinzufügen mit dem Baum-Algorithmus in Aspose.Tasks

## Einführung

In diesem Tutorial erfahren Sie **wie man eine Ressource zum Projekt hinzufügt**, indem Sie den leistungsstarken Baum-Algorithmus von Aspose.Tasks für .NET nutzen. Wir führen Sie durch das Erstellen einer Aufgabenhierarchie, das Berechnen der Aufgabendauer und das Zuweisen von Ressourcen zu Aufgaben – alles in einer klaren, schritt‑für‑Schritt‑Anleitung, die Sie in Ihre eigene Lösung übernehmen können.

## Schnelle Antworten
- **Was macht der Baum-Algorithmus?** Er durchläuft eine Aufgabenhierarchie, um Arbeitswerte effizient zu aggregieren.  
- **Welche Hauptoperation behandelt diese Anleitung?** Hinzufügen einer Ressource zu einem Projekt und Aktualisieren der Arbeitsgesamtwerte.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.  
- **Kann ich das mit .NET Core verwenden?** Ja, Aspose.Tasks unterstützt .NET Framework und .NET Core.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für eine einfache Projektdatei.

## Was bedeutet „Ressource zum Projekt hinzufügen“ in Aspose.Tasks?

Eine Ressource zu einem Projekt hinzuzufügen bedeutet, ein `Resource`‑Objekt zu erstellen, dessen Typ (z. B. Arbeit) festzulegen und es über `ResourceAssignments` mit einer oder mehreren Aufgaben zu verknüpfen. Dadurch kann der Scheduler Aufwand, Kosten und die Gesamtdauer des Projekts berechnen.

## Warum den Baum-Algorithmus für die Berechnung von Ressourcenarbeit verwenden?

Der Baum-Algorithmus durchläuft den Aufgabenbaum einmal und akkumuliert die Arbeit von Blattaufgaben bis zu deren Zusammenfassungsaufgaben. Dieser Ansatz ist weitaus effizienter als das Durchlaufen jeder Aufgabe einzeln, insbesondere bei großen Projekten mit tiefen Hierarchien. Außerdem wird sichergestellt, dass die zusammengefassten Arbeitswerte mit ihren Unteraufgaben synchron bleiben.

## Voraussetzungen

1. **Visual Studio** – jede aktuelle Edition (2019, 2022 oder neuer).  
2. **Aspose.Tasks for .NET** – herunterladen von [hier](https://releases.aspose.com/tasks/net/).  
3. **Grundkenntnisse in C#** – Sie sollten mit Klassen, Objekten und einfachem LINQ vertraut sein.

## Namespaces importieren

Importieren Sie in Ihrem C#‑Projekt die erforderlichen Namespaces, um mit den Funktionen von Aspose.Tasks zu arbeiten:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Jetzt zerlegen wir jedes Beispiel in mehrere Schritte:

## Schritt 1: Projektdatei laden

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Laden Sie die Projektdatei mit der `Project`‑Klasse in den Speicher.

## Schritt 2: Aufgabenhierarchie definieren

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definieren Sie die Aufgabenhierarchie, indem Sie übergeordnete und untergeordnete Aufgaben hinzufügen.

## Schritt 3: Aufgabeneigenschaften festlegen (inkl. **Aufgabendauer berechnen**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Hier **berechnen wir die Aufgabendauer**, indem wir Arbeitsstunden in ein `Duration`‑Objekt umwandeln und anschließend das Enddatum ableiten.

## Schritt 4: Ressource hinzufügen (**Ressourcen Aufgaben zuweisen**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Dieses Snippet **fügt dem Projekt eine Ressource hinzu** und **weist Ressourcen Aufgaben zu**, sodass der Scheduler weiß, wer für die Arbeit verantwortlich ist.

## Schritt 5: Baum-Algorithmus anwenden

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Initialisieren Sie die Klasse `WorkAccumulator` und wenden Sie den Baum-Algorithmus an, um die gesamte Arbeit über die Hierarchie hinweg zu sammeln.

## Schritt 6: Aufgabearbeit aktualisieren

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Aktualisieren Sie die Arbeitswerte der Aufgaben basierend auf den gesammelten Informationen.

## Häufige Probleme & Tipps

- **Fehlende Kalendereinstellungen:** Wenn das Enddatum nicht stimmt, stellen Sie sicher, dass der Projektkalender korrekt konfiguriert ist, bevor Sie `GetFinishDateByStartAndWork` aufrufen.  
- **Ressourcentyp‑Fehlanpassung:** Setzen Sie immer `Rsc.Type` auf `ResourceType.Work` für auf Aufwand basierende Ressourcen; andernfalls kann die Arbeitsakkumulation Null zurückgeben.  
- **Pro‑Tipp:** Nach dem Aktualisieren der Arbeit rufen Sie `project.Save("UpdatedProject.mpp")` auf, um die Änderungen zu speichern.

## Fazit

Wenn Sie diese Schritte befolgt haben, wissen Sie jetzt, wie man **Ressourcen zum Projekt hinzufügt**, **Aufgabendauer berechnet** und **Ressourcen Aufgaben zuweist** mithilfe des Baum-Algorithmus von Aspose.Tasks. Diese Methode vereinfacht die Verwaltung von Hierarchien und hält zusammengefasste Arbeitswerte mit minimalem Code genau.

## FAQ

### Q1: Was ist Aspose.Tasks für .NET?

A1: Aspose.Tasks für .NET ist eine leistungsstarke API, die Entwicklern ermöglicht, Microsoft‑Project‑Dateien programmgesteuert mit C# zu manipulieren.

### Q2: Kann ich eine kostenlose Testversion von Aspose.Tasks für .NET herunterladen?

A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET von [hier](https://releases.aspose.com/) herunterladen.

### Q3: Wo finde ich die Dokumentation für Aspose.Tasks für .NET?

A3: Sie finden die Dokumentation für Aspose.Tasks für .NET [hier](https://reference.aspose.com/tasks/net/).

### Q4: Wie kann ich Support für Aspose.Tasks für .NET erhalten?

A4: Für Support zu Aspose.Tasks für .NET können Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen.

### Q5: Gibt es eine temporäre Lizenz für Testzwecke?

A5: Ja, Sie können eine temporäre Lizenz für Testzwecke von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Häufig gestellte Fragen

**F: Kann ich diesen Ansatz mit einer bestehenden großen Projektdatei verwenden?**  
A: Absolut. Der Baum-Algorithmus funktioniert mit jeder `Project`‑Instanz, unabhängig von der Größe.

**F: Aktualisiert der Algorithmus auch Kostenwerte?**  
A: Das Beispiel konzentriert sich auf Arbeit, aber Sie können es erweitern, um Kosten zu aktualisieren, indem Sie `Tsk.Cost` in ähnlicher Weise akkumulieren.

**F: Welche .NET‑Versionen werden unterstützt?**  
A: Aspose.Tasks unterstützt .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ und .NET 6+.

**F: Wie gehe ich mit mehreren Ressourcen pro Aufgabe um?**  
A: Fügen Sie jede Ressource mit `project.ResourceAssignments.Add(task, resource)` hinzu; der Akkumulator summiert deren Arbeit automatisch.

**Zuletzt aktualisiert:** 2026-03-19  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}