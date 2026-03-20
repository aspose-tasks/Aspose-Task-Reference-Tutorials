---
date: 2025-12-17
description: Erfahren Sie, wie Sie ein Projekt als Bild speichern und die Bildauflösung
  in Java mit Aspose.Tasks für Java ändern. Diese Schritt‑für‑Schritt‑Anleitung zeigt
  die Darstellung von MS‑Project‑Daten im 24bppRgb‑Format.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Projekt als Bild speichern – 24bppRgb-Format mit Aspose.Tasks
url: /de/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt als Bild speichern – 24bppRgb-Format mit Aspose.Tasks

## Einleitung
In diesem Tutorial lernen Sie, wie Sie **save project as image** mit dem 24bppRgb-Pixel-Format mit Aspose.Tasks für Java verwenden. Das Rendern von MS Project-Daten in ein Bild ist praktisch, wenn Sie einen visuellen Schnappschuss eines Zeitplans teilen, eine Zeitleiste in einen Bericht einbetten oder Miniaturansichten für ein Projekt‑Portal erzeugen müssen. Wir zeigen Ihnen außerdem, wie Sie **change image resolution java** anpassen können, um Ihre Qualitätsanforderungen zu erfüllen.

## Kurze Antworten
- **Kann ich ein Projekt als Bild rendern?** Ja, Aspose.Tasks ermöglicht das Speichern eines Projekts als TIFF, PNG, JPEG usw.  
- **Welches Pixel-Format bietet die beste Farbtiefe?** `Format24bppRgb` liefert True‑Color‑Bilder (24‑Bit).  
- **Wie kann ich die Bildauflösung anpassen?** Verwenden Sie `setHorizontalResolution` und `setVerticalResolution` auf `ImageSaveOptions`.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist für den Nicht‑Evaluations‑Einsatz erforderlich.  
- **Ist dies mit allen Java‑Versionen kompatibel?** Funktioniert mit Java 8 und neuer.

## Was bedeutet „Projekt als Bild speichern“?
Das Speichern eines Projekts als Bild konvertiert die visuelle Darstellung einer Microsoft Project‑Datei (`.mpp`) in ein Rasterformat (z. B. TIFF). Die resultierende Datei kann in Browsern angezeigt, in Dokumente eingefügt oder gedruckt werden, ohne dass die ursprüngliche Project‑Anwendung erforderlich ist.

## Warum das 24bppRgb‑Format verwenden?
Das 24bppRgb‑Pixel‑Format speichert jedes Pixel mit 8 Bit für Rot, Grün und Blau und liefert True‑Color‑Qualität ohne Alphakanal. Dies ist ideal für hochauflösende Berichte, bei denen Farbtreue wichtig ist, während die Dateigröße im Vergleich zu 32‑Bit‑Formaten vernünftig bleibt.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – JDK 8 oder neuer, auf Ihrem Rechner installiert.  
2. **Aspose.Tasks for Java** – Downloaden und installieren Sie von [here](https://releases.aspose.com/tasks/java/).  
3. **Grundlegende Java‑Kenntnisse** – Vertrautheit mit Java‑Syntax und Projekt‑Setup hilft Ihnen, den Code‑Beispielen zu folgen.

## Importieren von Paketen
Zuerst importieren Sie die erforderlichen Aspose.Tasks‑Klassen in Ihr Java‑Projekt:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis definieren
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad, in dem sich Ihre `.mpp`‑Datei befindet.

### Schritt 2: Projektdatei laden
```java
Project project = new Project(dataDir + "project.mpp");
```
Diese Zeile liest die Microsoft Project‑Datei (`project.mpp`) und erstellt ein `Project`‑Objekt, das Aspose.Tasks manipulieren kann.

### Schritt 3: Bild‑Speicheroptionen konfigurieren
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Hier setzen wir das Ausgabeformat auf TIFF, geben eine **72 dpi**‑Auflösung an (Sie können diese Werte nach Bedarf anpassen – hier können Sie **change image resolution java**), und wählen das 24bppRgb‑Pixel‑Format für True‑Color‑Ausgabe.

### Schritt 4: Projektdaten als Bild speichern
```java
project.save(dataDir + "resFile.tif", options);
```
Die `save`‑Methode schreibt das gerenderte Bild nach `resFile.tif` unter Verwendung der oben definierten Optionen.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|---------|-------|--------|
| **Leeres Bild** | Die Projektansicht könnte leer sein. | Rufen Sie `project.setDefaultView(ViewType.Gantt);` vor dem Speichern auf. |
| **Bild mit niedriger Qualität** | Die Auflösung ist zu niedrig eingestellt. | Erhöhen Sie `setHorizontalResolution` und `setVerticalResolution` (z. B. 150 dpi). |
| **Nicht unterstütztes Pixel-Format** | Verwendung einer älteren Aspose.Tasks‑Version. | Aktualisieren Sie auf die neueste Aspose.Tasks‑Version für Java. |

## Fazit
Sie wissen jetzt, wie Sie ein **save project as image** mit dem 24bppRgb‑Format verwenden und die Auflösung mit Aspose.Tasks für Java anpassen können. Dieser Ansatz ermöglicht es Ihnen, klare, farbgenaue visuelle Darstellungen Ihrer Projektzeitpläne zum Teilen, Berichten oder Archivieren zu erzeugen.

## FAQ

### Q: Kann ich Projektdaten in anderen Bildformaten rendern?
A: Ja, Aspose.Tasks unterstützt das Rendern von Projektdaten in verschiedene Bildformate wie PNG, JPEG, BMP usw.

### Q: Ist Aspose.Tasks mit verschiedenen Versionen von MS Project kompatibel?
A: Ja, Aspose.Tasks unterstützt mehrere Versionen von MS Project, darunter 2003, 2007, 2010, 2013 und 2016.

### Q: Kann ich die Auflösung und das Pixel-Format des gerenderten Bildes anpassen?
A: Ja, Sie können die Auflösung und das Pixel-Format nach Ihren Anforderungen mit Aspose.Tasks anpassen.

### Q: Benötigt Aspose.Tasks eine Lizenz für die kommerzielle Nutzung?
A: Ja, Sie müssen eine Lizenz für die kommerzielle Nutzung von Aspose.Tasks erwerben. Sie können eine temporäre Lizenz für Testzwecke von [here](https://purchase.aspose.com/temporary-license/) erhalten.

### Q: Wo kann ich Unterstützung für Aspose.Tasks erhalten?
A: Sie können Unterstützung für Aspose.Tasks im [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) erhalten.

---

**Zuletzt aktualisiert:** 2025-12-17  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}