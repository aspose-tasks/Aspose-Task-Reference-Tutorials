---
date: 2026-03-05
description: Erfahren Sie, wie Sie Bilder speichern, HTML mit Bildern erzeugen und
  den Bildexport mit Aspose.Tasks für .NET anpassen. Schritt‑für‑Schritt‑Anleitung
  zum Speichern eines Projekts als HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Wie man Bilder mit Aspose.Tasks für .NET speichert
url: /de/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Bilder mit Aspose.Tasks für .NET speichert

## Einführung

In diesem Tutorial erfahren Sie **wie man Bilder** aus Microsoft Project‑Dateien mit der Aspose.Tasks‑API für .NET speichert. Egal, ob Sie Diagramme in Berichte einbetten, HTML‑Seiten erzeugen möchten, die Projektvisualisierungen enthalten, oder einfach diagrammatische Ressourcen exportieren wollen, die nachstehenden Schritte führen Sie durch den gesamten Prozess – vom Einrichten des Projektobjekts bis zur Anpassung der Bild‑Export‑Callbacks.

## Schnelle Antworten
- **Was bedeutet „how to save images“ in Aspose.Tasks?**  
  Es bezieht sich auf die Verwendung des `IImageSavingCallback`‑Interface, um zu steuern, wo und wie visuelle Ressourcen auf die Festplatte geschrieben werden.
- **Kann ich ein Projekt als HTML mit eingebetteten Bildern speichern?**  
  Ja, indem Sie `HtmlSaveOptions` zusammen mit Bild‑Speicher‑Callbacks verwenden, können Sie **ein Projekt als HTML speichern**, das alle erzeugten Bilder enthält.
- **Benötige ich eine Lizenz für den Bildexport?**  
  Eine temporäre Evaluationslizenz funktioniert für Tests; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.
- **Welche .NET‑Versionen werden unterstützt?**  
  Aspose.Tasks für .NET unterstützt .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6+.
- **Ist es möglich, den Bildexport (Format, Ordner, Benennung) anzupassen?**  
  Absolut – das Callback gibt Ihnen die vollständige Kontrolle über Dateinamen, Format und Zielort.

## Was bedeutet „how to save images“ im Kontext von Aspose.Tasks?

Bilder zu speichern bedeutet, visuelle Elemente (Diagramme, Gantt‑Balken, Ressourcen‑Grafiken) aus einer Projektdatei zu extrahieren und in Bilddateien (PNG, JPEG usw.) zu schreiben. Aspose.Tasks stellt einen flexiblen Callback‑Mechanismus bereit, mit dem Sie den genauen Speicherort, das Benennungsschema und sogar das Bildformat festlegen können.

## Warum Aspose.Tasks zum Speichern von Bildern verwenden?

- **Vollständige programmgesteuerte Kontrolle** – keine manuelle UI‑Interaktion erforderlich.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS via .NET Core.  
- **Hochwertige Wiedergabe** – Bilder behalten die gleiche Qualität wie die ursprüngliche Projektansicht.  
- **Einfache HTML‑Generierung** – kombinieren Sie `HtmlSaveOptions` mit Bild‑Callbacks, um **automatisch HTML mit Bildern** zu erzeugen.

## Voraussetzungen

1. Visual Studio ist auf Ihrem Entwicklungsrechner installiert.  
2. Aspose.Tasks für .NET wurde von [hier](https://releases.aspose.com/tasks/net/) heruntergeladen.  
3. Grundlegende Kenntnisse in C# und der .NET‑Projektstruktur.

## Namespaces importieren

Zuerst fügen Sie die benötigten Namespaces in Ihre Quelldatei ein:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt 1: Ein Projektobjekt erstellen

Laden Sie die Microsoft Project‑Datei, mit der Sie arbeiten möchten:

```csharp
var project = new Project("Project1.mpp");
```

## Schritt 2: Speicheroptionen definieren

Erstellen Sie die HTML‑Speicheroptionen, die auch unsere Bild‑Speicher‑Callbacks enthalten:

```csharp
var options = GetSaveOptions(1);
```

## Schritt 3: Das Projekt als HTML speichern (save project as html)

Exportieren Sie nun das Projekt in eine HTML‑Datei. Die im HTML referenzierten Bilder werden durch das Callback erzeugt, das wir als Nächstes definieren:

```csharp
project.Save("document_out.html", options);
```

## Schritt 4: Bild‑Speicher‑Callback implementieren (customize image export)

Implementieren Sie das `IImageSavingCallback`‑Interface. Hier können Sie das Verhalten des **Bildexports** anpassen:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Schritt 5: Bilder in ein angegebenes Verzeichnis speichern

Im `ImageSaving`‑Methodenteil entscheiden Sie, wo jedes Bild gespeichert werden soll. Das nachstehende Beispiel unterscheidet PNG‑Ressourcen von anderen Formaten:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Schritt 6: Speicheroptionen festlegen (inklusive Callbacks)

Binden Sie die Callbacks für Schriftarten, CSS und Bilder ein. Dadurch wird sichergestellt, dass jedes visuelle Element konsistent behandelt wird:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|-----|
| Bilder erscheinen nicht im erzeugten HTML | Callback weist keinen gültigen Dateipfad zu | Stellen Sie sicher, dass `args.Path` auf einen beschreibbaren Ordner zeigt und `args.ImageStream` korrekt gesetzt ist. |
| PNG‑Dateien werden mit falscher Erweiterung gespeichert | Bedingte Logik prüft nur das Suffix „png“ | Verwenden Sie `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` für eine robuste Erkennung. |
| HTML‑Verweise sind nach dem Verschieben von Dateien kaputt | Relative Pfade haben sich nach dem Verschieben des Ausgabeverzeichnisses geändert | Halten Sie HTML‑ und Bildordner zusammen oder passen Sie `options.ImageFolder` entsprechend an. |

## Fazit

Durch das Befolgen dieser Schritte wissen Sie jetzt, **wie man Bilder** aus einer Projektdatei speichert, **ein Projekt als HTML speichert** und **den Bildexport** an die Ordnerstruktur Ihrer Anwendung anpasst. Dieser Ansatz ermöglicht es Ihnen, **HTML mit Bildern** zu erzeugen, das nahtlos in Berichte, Dokumentationsportale oder Web‑Dashboards eingebettet werden kann.

## Häufig gestellte Fragen

**F1: Kann ich Aspose.Tasks verwenden, um Projektdateien in anderen Formaten als HTML zu manipulieren?**  
A1: Ja, Aspose.Tasks unterstützt verschiedene Formate wie PDF, XLSX und MPP.

**F2: Bietet Aspose.Tasks Unterstützung für die Integration von Cloud‑Speicher?**  
A2: Ja, Aspose.Tasks bietet APIs für die Arbeit mit gängigen Cloud‑Speicherdiensten wie Amazon S3 und Google Drive.

**F3: Ist Aspose.Tasks mit .NET Core kompatibel?**  
A3: Ja, Aspose.Tasks ist mit .NET Core kompatibel, sodass Sie plattformübergreifende Anwendungen entwickeln können.

**F4: Kann ich das Aussehen der gespeicherten Bilder anpassen?**  
A4: Ja, Sie können das Aussehen der gespeicherten Bilder anpassen, indem Sie die Logik zum Bildspeichern innerhalb der Callback‑Methoden ändern.

**F5: Bietet Aspose.Tasks Testversionen für Evaluierungszwecke an?**  
A5: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks unter [hier](https://releases.aspose.com/) erhalten.

---

**Letzte Aktualisierung:** 2026-03-05  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}