---
date: 2026-03-21
description: Erfahren Sie, wie Sie ein Bild exportieren und die BitmapInvalidSizeException
  beim Speichern eines Projekts als Bild in Aspose.Tasks für .NET behandeln. Enthält
  Schritte zum Speichern des Projekts als Bild und zum Exportieren des Projekts als
  PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man ein Bild exportiert und die Ausnahme bei ungültiger Größe handhabt
url: /de/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So exportieren Sie ein Bild – Behandlung der Invalid Size Exception für Bitmap in Aspose.Tasks

In diesem Tutorial lernen Sie **wie Sie ein Bild** aus einer Microsoft‑Project‑Datei mit Aspose.Tasks für .NET exportieren und, noch wichtiger, wie Sie die `BitmapInvalidSizeException` abfangen, die dabei auftreten kann. Das Exportieren eines Projekts als Bild ist ein häufiges Bedürfnis für Reporting‑Dashboards, Dokumentationen oder einfach zum Teilen eines visuellen Schnappschusses eines Zeitplans. Am Ende dieses Leitfadens können Sie **ein Projekt zuverlässig als Bild speichern** und sogar **ein Projekt in das PNG‑Format exportieren**, ohne unerwartete Abstürze.

## Schnelle Antworten
- **Welche Ausnahme kann beim Exportieren eines Bildes auftreten?** `BitmapInvalidSizeException`  
- **Welches Format wird im Beispiel verwendet?** PNG (`SaveFileFormat.Png`)  
- **Benötige ich eine spezielle Lizenz?** Für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich die Zeitskala ändern?** Ja – Sie können die Zeitskala‑Einheit (Minuten, Stunden, Tage usw.) festlegen.  
- **Ist der Code mit .NET Core kompatibel?** Absolut – dieselbe API funktioniert sowohl unter .NET Framework als auch unter .NET Core.

## Was ist die BitmapInvalidSizeException?
`BitmapInvalidSizeException` wird ausgelöst, wenn die für das Bild berechneten Bitmap‑Abmessungen außerhalb des unterstützten Bereichs liegen (z. B. Breite oder Höhe ist null oder überschreitet interne Grenzen). Dies geschieht in der Regel, wenn die Zeitskala‑ oder Ansichtseinstellungen ein Bild erzeugen, das zu groß oder zu klein ist.

## Warum ein Projekt als Bild exportieren?
- **Visuelles Reporting** – Gantt‑Diagramme in PDFs, Word‑Dokumente oder Webseiten einbetten.  
- **Plattformübergreifendes Teilen** – PNG‑Dateien können auf jedem Gerät angezeigt werden, ohne dass Microsoft Project benötigt wird.  
- **Performance** – Bilder sind leichter als komplette Projektdateien und eignen sich gut für schnelle Vorschauen.

## Voraussetzungen
1. Grundkenntnisse in C# und .NET‑Entwicklung.  
2. Aspose.Tasks für .NET installiert (NuGet‑Paket `Aspose.Tasks`).  
3. Eine Beispiel‑Microsoft‑Project‑Datei (z. B. `Blank2010.mpp`).  

## Namespaces importieren
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt initialisieren und Ansicht auswählen
Zuerst erstellen Sie eine `Project`‑Instanz und wählen die Ansicht, die Sie rendern möchten (hier verwenden wir die erste Gantt‑Chart‑Ansicht).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Schritt 2: Bild‑Speicheroptionen konfigurieren (Projekt nach PNG exportieren)
Legen Sie das gewünschte Bildformat fest und teilen Sie Aspose.Tasks mit, die in der Ansicht definierte Zeitskala zu verwenden.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Schritt 3: Zeitskala‑Einheit anpassen (Bildgröße steuern)
Das Ändern der Zeitskala beeinflusst die Bitmap‑Abmessungen. In diesem Beispiel verwenden wir **Minuten**, um die Bildgröße handhabbar zu halten.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Schritt 4: Versuch, das Projekt als Bild zu speichern
Diese Zeile führt die eigentliche **save project as image**‑Operation aus.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Schritt 5: BitmapInvalidSizeException abfangen und behandeln
Umhüllen Sie den Speicheraufruf mit einem `try / catch`‑Block, damit Ihre Anwendung elegant reagieren kann, wenn die Bitmap‑Größe ungültig ist.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|----------|--------|
| Ausnahme wird trotz Anpassung der Zeitskala weiterhin ausgelöst | Zeitskala erzeugt immer noch zu große Bitmap | `view.MiddleTimescaleTier.Count` reduzieren oder zu einer gröberen `TimescaleUnit` (z. B. Stunden) wechseln. |
| Ausgabedatei ist leer | Falscher Dateipfad oder fehlende Schreibrechte | Sicherstellen, dass `DataDir` auf einen beschreibbaren Ordner zeigt und der Dateiname bei geänderten Format mit `.png` endet. |
| Bildqualität ist schlecht | Standard‑DPI ist zu niedrig | `options.DpiX` und `options.DpiY` auf höhere Werte (z. B. 300) setzen. |

## Häufig gestellte Fragen

**F: Was verursacht die BitmapInvalidSizeException in Aspose.Tasks?**  
A: Sie tritt auf, wenn die berechneten Bitmap‑Abmessungen ungültig sind – typischerweise weil die Zeitskala ein Bild erzeugt, das zu groß ist oder eine Breite/Höhe von null hat.

**F: Kann ich die Zeitskala beim Exportieren eines Bildes anpassen?**  
A: Ja. Sie können `view.MiddleTimescaleTier.Unit` und `Count` nach Bedarf ändern, wie im Tutorial gezeigt.

**F: Unterstützt Aspose.Tasks neben PNG weitere Bildformate?**  
A: Absolut. `SaveFileFormat` enthält außerdem JPEG, BMP, GIF und TIFF. Ändern Sie einfach den Enum‑Wert in `ImageSaveOptions`.

**F: Ist für den Bild‑Export in einer Produktionsumgebung eine Lizenz erforderlich?**  
A: Ja. Im Evaluierungsmodus funktioniert die Bibliothek, aber eine kommerzielle Lizenz entfernt Evaluierungsbeschränkungen und bietet vollen Support.

**F: Wie kann ich die Qualität des exportierten PNG verbessern?**  
A: Erhöhen Sie die DPI‑Einstellungen (`options.DpiX` und `options.DpiY`) oder passen Sie die Zeitskala der Ansicht an, um eine größere Bitmap zu erzeugen.

## Fazit
Nachdem Sie die obigen Schritte befolgt haben, wissen Sie jetzt **wie Sie ein Bild** aus einer Projektdatei exportieren, **wie Sie ein Projekt als Bild speichern** und wie Sie die `BitmapInvalidSizeException` elegant behandeln. Diese Techniken machen Ihre Reporting‑Pipelines robuster und stellen sicher, dass visuelle Exporte zuverlässig für unterschiedliche Projektgrößen und Zeitskalen funktionieren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-21  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

---