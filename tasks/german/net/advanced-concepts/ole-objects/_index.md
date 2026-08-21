---
date: 2026-03-16
description: Erfahren Sie, wie Sie OLE‑Objekte mit Aspose.Tasks für .NET entfernen,
  und entdecken Sie, wie Sie OLE verwalten und OLE in Ihren Projekten effizient bereinigen
  können.
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Wie man OLE‑Objekte in Aspose.Tasks für .NET entfernt
url: /de/net/advanced-concepts/ole-objects/
weight: 22
---

Make sure to keep code block placeholders unchanged.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man OLE-Objekte in Aspose.Tasks für .NET entfernt

## Einführung

Aspose.Tasks für .NET gibt Ihnen die volle Kontrolle über OLE (Object Linking and Embedding)-Objekte, die in Microsoft Project-Dateien gespeichert sind. In diesem Tutorial lernen Sie **wie man OLE-Objekte entfernt**, wie man **OLE**‑Inhalte verwaltet und die genauen Schritte, um **OLE**‑Daten zu **löschen**, wenn sie nicht mehr benötigt werden. Am Ende können Sie eine Projektdatei laden, ihre eingebetteten OLE-Objekte inspizieren, sie sicher löschen und das bereinigte Projekt speichern – alles mit sauberem, lesbarem C#‑Code.

## Schnelle Antworten
- **Was ist die primäre Methode, um OLE-Objekte zu entfernen?** Verwenden Sie `project.OleObjects.Clear()` und speichern Sie anschließend das Projekt.  
- **Benötige ich eine spezielle Lizenz?** Für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kann ich OLE-Inhalte vor dem Entfernen inspizieren?** Ja, iterieren Sie über `project.OleObjects`, um Eigenschaften oder Inhaltsbytes zu lesen.  
- **Ist das Löschen von OLE-Objekten in großen Projekten sicher?** Absolut – der Vorgang ist schnell und beeinträchtigt keine anderen Projektdaten.

## Was bedeutet „OLE-Objekte entfernen“ im Kontext von Aspose.Tasks?

Das Entfernen von OLE-Objekten bedeutet das Löschen der eingebetteten Dateien (Bilder, Excel‑Tabellen, Word‑Dokumente usw.), die in einer Microsoft Project‑Datei (.mpp) gespeichert sind. Dies ist nützlich, wenn Sie die Dateigröße reduzieren, veraltete Verweise entfernen oder Datenschutz‑ bzw. Aufbewahrungsrichtlinien einhalten möchten.

## Warum OLE-Objekte mit Aspose.Tasks verwalten?

- **Feinkörnige Kontrolle** – Greifen Sie auf die ID, den Namen und die Rohbytes jedes OLE‑Objekts zu.  
- **Automatisierung** – Bereinigen Sie programmgesteuert Dutzende von Projekten, ohne sie in Microsoft Project zu öffnen.  
- **Cross‑Version‑Unterstützung** – Funktioniert mit Project‑Dateien von 2007 bis zu den neuesten 2023‑Versionen.  

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Tasks für .NET** installiert. Sie können es von [hier](https://releases.aspose.com/tasks/net/) herunterladen.  
2. Grundkenntnisse in **C#** und dem **.NET**‑Ökosystem.  
3. Eine Entwicklungsumgebung wie **Visual Studio** (Community oder höher).  

## Namespaces importieren

Importieren Sie zunächst die Namespaces, die die Aspose.Tasks‑API bereitstellen:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Wie man OLE-Objekte verwaltet – Schritt‑für‑Schritt‑Anleitung

Im Folgenden gehen wir drei gängige Szenarien durch:

- **Untersuchen von OLE-Objekten** – lesen Sie deren Eigenschaften und einen Ausschnitt des Binärinhalts.  
- **Alle OLE-Objekte löschen** – die Kernoperation „OLE-Objekte entfernen“.  
- **Visuelle Platzierungsinformationen lesen** – nützlich, wenn Sie anpassen müssen, wie OLE-Objekte im Gantt‑Diagramm oder anderen Ansichten erscheinen.

### Szenario 1: OLE-Objekte inspizieren

#### Schritt 1: Projektdatei laden  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Schritt 2: Auf OLE-Objekte zugreifen  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### Schritt 3: Durch OLE-Objekte iterieren  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### Schritt 4: Einen kleinen Teil des Binärinhalts abrufen (optional)  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### Szenario 2: OLE löschen – alle eingebetteten Objekte entfernen

#### Schritt 1: Projektdatei laden  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Schritt 2: OLE-Objekte löschen  
```csharp
project.OleObjects.Clear();
```

#### Schritt 3: Das bereinigte Projekt speichern  
```csharp
project.Save("ClearedProject.mpp");
```

> **Pro Tipp:** Nach dem Löschen von OLE-Objekten können Sie `project.Save` mit einem anderen Dateinamen aufrufen, um das Original unverändert zu lassen.

### Szenario 3: Visuelle Platzierungseigenschaften von Objekten abrufen

#### Schritt 1: Projektdatei laden  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Schritt 2: Auf das erste OLE-Objekt und dessen Platzierung in der Gantt‑Ansicht zugreifen  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### Schritt 3: Platzierungseigenschaften abrufen  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Häufige Fallstricke und Fehlerbehebung

| Problem | Grund | Lösung |
|-------|--------|-----|
| `project.OleObjects` ist leer | Die Quell‑ .mpp‑Datei enthält keine OLE‑Objekte. | Stellen Sie sicher, dass die Projektdatei tatsächlich OLE‑Daten einbettet (z. B. ein angehängtes Excel‑Blatt). |
| `project.Save` wirft eine Ausnahme | Datei ist gesperrt oder Sie haben keine Schreibrechte. | Schließen Sie alle geöffneten Instanzen der Datei und stellen Sie sicher, dass das Zielverzeichnis beschreibbar ist. |
| Inhaltsbytes sehen beschädigt aus | Sie lesen das gesamte Byte‑Array als Text. | Verwenden Sie `Get10Bytes` oder schreiben Sie die Bytes in eine Datei, um sie in einem geeigneten Viewer zu prüfen. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks verschiedene OLE-Objektformate verarbeiten?**  
A: Ja, es unterstützt Bilder, Office‑Dokumente, PDFs und viele andere OLE‑Formate.

**F: Ist die API mit älteren Microsoft-Project-Versionen kompatibel?**  
A: Absolut – Aspose.Tasks funktioniert mit Projektdateien von 2007 bis zu den neuesten 2023‑Versionen.

**F: Wie entferne ich nur bestimmte OLE-Objekte, anstatt alle zu löschen?**  
A: Finden Sie das gewünschte `OleObject` über dessen `Id` oder `Name` und rufen Sie `project.OleObjects.Remove(oleObject)` vor dem Speichern auf.

**F: Beeinflusst das Löschen von OLE-Objekten Aufgabenabhängigkeiten oder Zeitpläne?**  
A: Nein. OLE-Objekte sind unabhängige visuelle Elemente; ihr Entfernen ändert keine Aufgabenbeziehungen.

**F: Wo finde ich weitere Beispiele zur OLE-Manipulation?**  
A: Sehen Sie sich die offizielle Aspose.Tasks-Dokumentation und die API-Referenz für die Klassen `OleObject` und `VisualObjectsPlacements` an.

## Fazit

Wir haben alles behandelt, was Sie benötigen, um **OLE-Objekte zu entfernen** und OLE‑Inhalte in Aspose.Tasks für .NET zu verwalten. Durch die Schritt‑für‑Schritt‑Beispiele können Sie OLE‑Objekte inspizieren, löschen und deren visuelle Platzierung anpassen, sodass Ihre Projektdateien schlank und fokussiert bleiben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-16  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose