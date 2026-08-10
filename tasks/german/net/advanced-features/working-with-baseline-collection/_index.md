---
date: 2026-04-06
description: Erfahren Sie, wie Sie alle Grundlinien löschen und Grundlinien‑Sammlungen
  in Aspose.Tasks für .NET mit Schritt‑für‑Schritt‑Codebeispielen verwalten.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Alle Baselines mit Aspose.Tasks Baseline Collection löschen
second_title: Aspose.Tasks .NET API
title: Alle Baselines mit Aspose.Tasks Baseline Collection löschen
url: /de/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alle Baselines mit Aspose.Tasks Baseline Collection löschen

## Einführung

Aspose.Tasks for .NET ermöglicht es Ihnen, Microsoft Project‑Dateien direkt aus Ihren .NET‑Anwendungen zu manipulieren. Eine der leistungsstärksten Funktionen ist die Möglichkeit, **alle Baselines** für eine Ressource zu **löschen**, was unerlässlich ist, wenn Sie die Tracking‑Daten eines Projekts zurücksetzen oder einen neuen Baseline‑Zeitraum beginnen möchten. In diesem Tutorial führen wir Sie durch den gesamten Prozess – vom Laden einer Projektdatei bis zum Entfernen jeder an einer bestimmten Ressource angehängten Baseline – mit klaren, dialogorientierten Erklärungen und sofort ausführbarem C#‑Code.

## Schnelle Antworten
- **Was bewirkt „delete all baselines“?** Es entfernt jeden gespeicherten Baseline‑Datensatz für eine ausgewählte Ressource und löscht historische Kosten‑ und Arbeitsdaten.  
- **Warum könnte ich das benötigen?** Um das Tracking nach einer größeren Projektänderung zurückzusetzen oder wenn die ursprünglichen Baselines nicht mehr relevant sind.  
- **Welche Bibliothek stellt diese Funktion bereit?** Aspose.Tasks for .NET.  
- **Benötige ich eine Lizenz?** Eine gültige Aspose.Tasks‑Lizenz ist für den Produktionseinsatz erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Ist der Code mit .NET 6+ kompatibel?** Ja, die API funktioniert mit .NET Framework 4.5+, .NET Core 3.1+, und .NET 5/6.

## Was ist eine Baseline und warum alle Baselines löschen?

Eine Baseline erfasst den ursprünglichen Plan für Kosten, Arbeit und Zeitplan zu einem bestimmten Zeitpunkt. Im Verlauf eines Projekts können Sie mehrere Baselines (Baseline 1, Baseline 2 usw.) erstellen, um den tatsächlichen Fortschritt mit verschiedenen Planungs‑Snapshots zu vergleichen. Es gibt jedoch Szenarien – etwa eine Projekt‑Neuausrichtung oder einen frischen Start – in denen das Beibehalten dieser historischen Baselines verwirrend wird. Das Löschen aller Baselines gibt Ihnen ein sauberes Blatt und ermöglicht das Setzen neuer Baselines, die die aktuelle Realität widerspiegeln.

## Voraussetzungen

1. **Visual Studio** – jede aktuelle Edition (Community, Professional oder Enterprise).  
2. **Aspose.Tasks for .NET** – herunterladen von dem [download link](https://releases.aspose.com/tasks/net/).  
3. **Grundlegende C#‑Kenntnisse** – Sie sollten mit Variablen, Schleifen und Konsolenausgabe vertraut sein.  
4. **Eine Microsoft‑Project‑Datei** (`.mpp`) – eine Beispieldatei namens *WorkWithBaselineCollection.mpp* wird in den Beispielen verwendet.

## Namespaces importieren

Zuerst bringen wir die notwendigen Namespaces in den Gültigkeitsbereich, damit der Compiler weiß, wo die Klassen zu finden sind, die wir verwenden werden.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Schritt 1: Projektdatei laden

Wir beginnen damit, eine vorhandene Projektdatei zu laden. Passen Sie `DataDir` so an, dass es auf den Ordner zeigt, der Ihre `.mpp`‑Datei enthält.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Schritt 2: Zielressource abrufen

Zur Demonstration holen wir die Ressource mit UID = 1. In einer realen Situation würden Sie die Ressource nach Namen oder einem anderen Identifier suchen.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Schritt 3: Vorhandene Baseline‑Informationen anzeigen

Bevor etwas gelöscht wird, ist es hilfreich zu sehen, welche Baselines derzeit an die Ressource angehängt sind. Das gibt Ihnen Sicherheit, dass Sie die richtigen Daten entfernen.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Schritt 4: Durch alle Baselines iterieren

Hier iterieren wir über jede Baseline und geben Schlüsselkennzahlen wie Kosten, Arbeit und Earned Value (BCWP/BCWS) aus. Dieser Schritt ist optional, aber nützlich für Protokoll‑ oder Prüfzwecke.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Alle Baselines löschen

Jetzt führen wir die Kernaktion aus: **alle Baselines** für die ausgewählte Ressource **löschen**. Wir kopieren zunächst die Sammlung in eine Liste, um zu vermeiden, dass die Sammlung während der Iteration modifiziert wird, und entfernen dann jede Baseline einzeln.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Nach dem Ausführen dieses Blocks wird `resource.Baselines.Count` `0` sein, was bestätigt, dass alle Baseline‑Datensätze gelöscht wurden.

## Häufige Probleme und Tipps

- **NullReferenceException** – Stellen Sie sicher, dass die Projektdatei die Zielressource tatsächlich enthält; andernfalls gibt `GetByUid` `null` zurück.  
- **Lizenzierung** – Ohne eine gültige Aspose.Tasks‑Lizenz sehen Sie ein Wasserzeichen in der Ausgabe und eingeschränkte Funktionalität.  
- **Performance** – Bei sehr großen Projekten sollten Sie das Iterieren mit `Parallel.ForEach` in Betracht ziehen, um den Entfernungsprozess zu beschleunigen, aber beachten Sie, dass die zugrunde liegende Sammlung nicht thread‑sicher ist.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks große Projektdateien verarbeiten?**  
A: Ja, Aspose.Tasks ist für Leistung optimiert und kann mehrgigabyte‑große `.mpp`‑Dateien effizient verarbeiten.

**Q: Ist die Bibliothek mit allen Microsoft‑Project‑Versionen kompatibel?**  
A: Aspose.Tasks unterstützt Project 2000 bis Project 2024 und deckt sowohl ältere `.mpp`‑Formate als auch die neueren XML‑basierten Dateien ab.

**Q: Kann ich Baselines vor dem Löschen anpassen?**  
A: Absolut. Sie können jede Baseline‑Eigenschaft (Kosten, Arbeit, Daten) lesen oder ändern, bevor Sie entscheiden, sie zu entfernen.

**Q: Funktioniert Aspose.Tasks auf Cloud‑Plattformen?**  
A: Ja, die API läuft in jeder .NET‑kompatiblen Umgebung, einschließlich Azure App Service, AWS Lambda (via .NET Core) und Docker‑Containern.

**Q: Wo kann ich die Community um Hilfe bitten?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15), um mit anderen Entwicklern und dem Aspose‑Team in Kontakt zu treten.

## Fazit

In diesem Leitfaden haben wir gezeigt, wie man **alle Baselines** einer Ressource mit Aspose.Tasks for .NET **löscht**. Durch Befolgen des Schritt‑für‑Schritt‑Codes können Sie Baseline‑Daten zurücksetzen, Ihr Projekt‑Tracking sauber halten und Ihren Zeitplan für einen neuen Planungszyklus vorbereiten. Experimentieren Sie gern damit, nach dem Löschen neue Baselines zu erstellen, um zu sehen, wie die Bibliothek die Projektdatei aktualisiert.

---

**Zuletzt aktualisiert:** 2026-04-06  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}