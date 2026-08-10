---
date: 2026-03-24
description: Erfahren Sie, wie Sie Out-of-Memory-Probleme behandeln und ein Projektbild
  mit dem Aspose.Tasks Layout Builder in .NET speichern. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Out-of-Memory-Behandlung mit Aspose.Tasks Layout Builder (C#)
url: /de/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Speicherüberlaufbehandlung mit Aspose.Tasks Layout Builder

## Einführung

Die Speicherüberlaufbehandlung ist ein kritischer Bestandteil beim Erstellen zuverlässiger .NET‑Anwendungen, die mit großen Projektdateien arbeiten. Wenn Sie Visualisierungen mit Aspose.Tasks Layout Builder erzeugen, können schnell speicherbezogene Ausnahmen auftreten, insbesondere bei komplexen Gantt‑Diagrammen. In diesem Tutorial zeigen wir Ihnen, wie Sie **Speicherausnahmen behandeln**, **die Gantt‑Ansicht anpassen** und **das Projektbild** sicher speichern, sodass Ihre Anwendung auch bei riesigen Zeitplänen reaktionsfähig bleibt.

## Schnellantworten
- **Was ist Speicherüberlaufbehandlung?** Verwaltung der Speichernutzung und Abfangen von `OutOfMemoryException`‑artigen Fehlern beim Verarbeiten großer Datenmengen.
- **Welche API hilft?** Aspose.Tasks Layout Builder für .NET.
- **Typisches Szenario?** Rendern eines hochauflösenden Gantt‑Diagramms als PNG.
- **Wichtige Voraussetzung?** .NET (Framework 4.5+ oder .NET 6) mit installiertem Aspose.Tasks.
- **Wie Fehler abfangen?** Verwenden Sie `try…catch`‑Blöcke für `ApsLayoutBuilderOutOfMemoryException` und verwandte Ausnahmen.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **C#‑Grundkenntnisse** – Sie sollten mit der Standard‑C#‑Syntax vertraut sein.
2. **Aspose.Tasks für .NET** installiert. Falls Sie es noch nicht hinzugefügt haben, laden Sie es [hier](https://releases.aspose.com/tasks/net/) herunter.
3. **Eine IDE** wie Visual Studio (oder VS Code mit der C#‑Erweiterung) zum Kompilieren und Ausführen des Beispiels.

## Namespaces importieren

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt laden

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Diese Zeile lädt **Blank2010.mpp** in eine `Project`‑Instanz und bereitet sie für die Visualisierung vor.

### Schritt 2: Gantt‑Diagramm‑Ansicht anpassen

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Hier **passen wir die Gantt‑Ansicht** an, indem wir die mittleren und unteren Zeitskalen‑Ebenen ändern. Das Reduzieren dieser Ebenen verringert die Menge der gleichzeitig gerenderten Daten und kann den Speicherdruck mindern.

### Schritt 3: Bild‑Speicheroptionen konfigurieren

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` teilt Aspose.Tasks mit, wie das Diagramm gerendert werden soll. Wir wählen PNG als Ausgabeformat und binden die Zeitskala an die gerade angepasste Ansicht.

### Schritt 4: Projekt als Bild speichern

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

Der Aufruf `Save` **speichert das Projektbild** mit den oben definierten Optionen. Wenn das Projekt sehr groß ist, ist dies der Punkt, an dem ein Out‑of‑Memory‑Zustand am wahrscheinlichsten auftritt.

### Schritt 5: Ausnahmen behandeln

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Durch das Abfangen von `ApsLayoutBuilderOutOfMemoryException` **behandeln Sie Speicher‑Ausnahmen** elegant und geben eine klare Meldung aus, anstatt die Anwendung abstürzen zu lassen. Der zweite Catch‑Block kümmert sich um Bitmap‑Größen‑Probleme, die beim Rendern riesiger Diagramme ebenfalls auftreten können.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **OutOfMemoryException** | Das Rendern eines sehr hochauflösenden Bildes verbraucht mehr RAM, als der Prozess zuweisen kann. | Bildabmessungen reduzieren, Zeitskalen‑Ebenen vereinfachen oder das Diagramm in mehrere Bilder aufteilen. |
| **BitmapInvalidSizeException** | Die angeforderte Bitmap‑Größe überschreitet das maximale Limit der Plattform. | Breite/Höhe in `ImageSaveOptions` begrenzen oder segmentweise rendern. |
| **Langsame Leistung** | Große Projektdateien erfordern viel Verarbeitung. | `project.Set(Prj.SaveToCache, true)` vor dem Rendern aktivieren oder einen Hintergrund‑Thread verwenden. |

## FAQ's

### Q1: Was ist Aspose.Tasks für .NET?

A1: Aspose.Tasks für .NET ist eine leistungsstarke API, die Entwicklern ermöglicht, Microsoft‑Project‑Dateien programmgesteuert in .NET‑Anwendungen zu manipulieren.

### Q2: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?

A2: Sie können eine temporäre Lizenz für Aspose.Tasks erhalten, indem Sie [diesen Link](https://purchase.aspose.com/temporary-license/) besuchen.

### Q3: Eignet sich Aspose.Tasks für den Umgang mit großen Projektdateien?

A3: Ja, Aspose.Tasks bietet Funktionen und Optimierungen, um große Projektdateien effizient zu verarbeiten, jedoch sollten Entwickler weiterhin Speicher‑Management‑Strategien berücksichtigen.

### Q4: Kann ich das Aussehen von Gantt‑Diagrammen mit Aspose.Tasks anpassen?

A4: Absolut! Aspose.Tasks stellt umfangreiche Möglichkeiten bereit, das Aussehen und Layout von Gantt‑Diagrammen nach Ihren Anforderungen zu individualisieren.

### Q5: Wo finde ich weitere Hilfe und Support für Aspose.Tasks?

A5: Weitere Hilfe und Support sowie den Austausch mit der Community finden Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

## Häufig gestellte Fragen

**F: Wie kann ich den Speicherverbrauch beim Speichern eines Projektbildes reduzieren?**  
A: Reduzieren Sie die Bildauflösung, begrenzen Sie den Zeitskalen‑Bereich oder speichern Sie das Diagramm in mehreren kleineren Segmenten.

**F: Ist es möglich, das Bild direkt in eine Web‑Antwort zu streamen?**  
A: Ja, Sie können `project.Save(stream, options)` verwenden und den Stream in die HTTP‑Antwort schreiben.

**F: Unterstützt Aspose.Tasks .NET Core und .NET 5/6?**  
A: Die Bibliothek ist vollständig kompatibel mit .NET Core, .NET 5 und .NET 6.

**F: Was soll ich tun, wenn ich nach Optimierungen weiterhin einen Out‑of‑Memory‑Fehler erhalte?**  
A: Erwägen Sie, das Projekt auf einer Maschine mit mehr RAM zu verarbeiten oder das Rendering an einen Hintergrund‑Dienst auszulagern.

**F: Kann ich das Gantt‑Diagramm in andere Formate als PNG exportieren?**  
A: Ja, `ImageSaveOptions` unterstützt neben PNG auch JPEG, BMP und TIFF.

---

**Zuletzt aktualisiert:** 2026-03-24  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}