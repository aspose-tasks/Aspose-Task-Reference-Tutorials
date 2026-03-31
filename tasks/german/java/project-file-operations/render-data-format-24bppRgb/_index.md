---
date: 2026-03-21
description: Erfahren Sie, wie Sie die Bildqualität erhöhen, indem Sie ein Projekt
  als 24‑bpp‑Rgb‑Bild speichern und die Bildauflösung in Java mit Aspose.Tasks ändern.
  Dieser Leitfaden zeigt außerdem, wie Sie Projekt‑Bildformate speichern.
linktitle: Increase Image Quality – Save Project Image (24bppRgb)
second_title: Aspose.Tasks Java API
title: Bildqualität erhöhen – Projektbild speichern (24bppRgb)
url: /de/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bildqualität erhöhen – Projektbild speichern (24bppRgb) mit Aspose.Tasks

## Einführung
In diesem Tutorial lernen Sie, wie Sie die **Bildqualität erhöhen** können, indem Sie ein Projekt als Bild im 24bppRgb-Pixelformat mit Aspose.Tasks für Java speichern. Das Rendern von MS Project-Daten in ein Bild ist praktisch, wenn Sie einen visuellen Schnappschuss eines Zeitplans teilen, eine Zeitleiste in einen Bericht einbetten oder Miniaturansichten für ein Projekt‑Portal erstellen müssen. Wir zeigen Ihnen außerdem, wie Sie **Bildauflösung in Java ändern** können, damit die Ausgabe Ihren genauen Qualitätsanforderungen entspricht.

## Schnelle Antworten
- **Kann ich ein Projekt als Bild rendern?** Ja, Aspose.Tasks ermöglicht das Speichern eines Projekts als TIFF, PNG, JPEG usw.  
- **Welches Pixelformat bietet die beste Farbtiefe?** `Format24bppRgb` liefert True‑Color‑Bilder (24‑Bit).  
- **Wie stelle ich die Bildauflösung ein?** Verwenden Sie `setHorizontalResolution` und `setVerticalResolution` auf `ImageSaveOptions`.  
- **Benötige ich eine Lizenz für die Produktion?** Für den nicht‑Evaluations‑Einsatz ist eine kommerzielle Lizenz erforderlich.  
- **Ist dies mit allen Java‑Versionen kompatibel?** Funktioniert mit Java 8 und neuer.

## Was bedeutet „Projektbild speichern“?
Das Speichern eines Projekts als Bild konvertiert die visuelle Darstellung einer Microsoft Project‑Datei (`.mpp`) in ein Rasterformat (z. B. TIFF). Die resultierende Datei kann in Browsern angezeigt, in Dokumente eingefügt oder gedruckt werden, ohne dass die ursprüngliche Project‑Anwendung erforderlich ist.

## Warum das 24bppRgb‑Format zur **Erhöhung der Bildqualität** verwenden?
Das 24bppRgb‑Pixelformat speichert jeden Pixel mit 8 Bit für Rot, Grün und Blau und liefert True‑Color‑Qualität ohne Alphakanal. Das ist ideal für hochauflösende Berichte, bei denen Farbtreue wichtig ist, und hält gleichzeitig die Dateigröße im Vergleich zu 32‑Bit‑Formaten angemessen.

## Häufige Anwendungsfälle
- **Gantt‑Diagrammbild speichern** für Projektstatus‑Dashboards.  
- **Projekt‑Miniaturbild erzeugen** für Vorschau‑Panels in Web‑Portalen.  
- **Projektbild** Ausgabeauflösung für Druck oder hoch‑DPI‑Displays anpassen.  
- **Projektbild speichern** in verschiedenen Formaten (TIFF, PNG, JPEG) für die Dokumentation.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – JDK 8 oder neuer auf Ihrem Rechner installiert.  
2. **Aspose.Tasks for Java** – Downloaden und installieren Sie von [hier](https://releases.aspose.com/tasks/java/).  
3. **Grundlegende Java‑Kenntnisse** – Vertrautheit mit Java‑Syntax und Projekt‑Setup hilft Ihnen, den Code‑Beispielen zu folgen.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Aspose.Tasks‑Klassen in Ihr Java‑Projekt:

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
Diese Zeile liest die Microsoft Project‑Datei (`project.mpp`) ein und erstellt ein `Project`‑Objekt, das von Aspose.Tasks manipuliert werden kann.

### Schritt 3: Bildspeicheroptionen konfigurieren
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Hier setzen wir das Ausgabeformat auf TIFF, geben eine Auflösung von **72 dpi** an (Sie können diese Werte an Ihre Bedürfnisse anpassen – hier ändern Sie die **Bildauflösung in Java**), und wählen das 24bppRgb‑Pixelformat für True‑Color‑Ausgabe.

### Schritt 4: Projektdaten als Bild speichern
```java
project.save(dataDir + "resFile.tif", options);
```
Die Methode `save` schreibt das gerenderte Bild nach `resFile.tif` unter Verwendung der oben definierten Optionen.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|-----|
| **Leeres Bild** | Die Projektansicht könnte leer sein. | Rufen Sie `project.setDefaultView(ViewType.Gantt);` vor dem Speichern auf. |
| **Bild mit niedriger Qualität** | Auflösung zu niedrig eingestellt. | Erhöhen Sie `setHorizontalResolution` und `setVerticalResolution` (z. B. 150 dpi). |
| **Nicht unterstütztes Pixelformat** | Verwendung einer älteren Aspose.Tasks‑Version. | Aktualisieren Sie auf die neueste Aspose.Tasks‑Version für Java. |

## Fazit
Sie wissen jetzt, wie Sie die **Bildqualität erhöhen** können, indem Sie ein Projekt als Bild im 24bppRgb‑Format speichern und die Auflösung mit Aspose.Tasks für Java anpassen. Dieser Ansatz ermöglicht es Ihnen, klare, farbgenaue visuelle Darstellungen Ihrer Projektpläne für das Teilen, Berichten oder Archivieren zu erzeugen.

## Häufig gestellte Fragen

**Q: Kann ich Projektdaten in anderen Bildformaten rendern?**  
A: Ja, Aspose.Tasks unterstützt das Rendern von Projektdaten in verschiedene Bildformate wie PNG, JPEG, BMP usw.

**Q: Ist Aspose.Tasks mit verschiedenen Versionen von MS Project kompatibel?**  
A: Ja, Aspose.Tasks unterstützt mehrere Versionen von MS Project, darunter 2003, 2007, 2010, 2013 und 2016.

**Q: Kann ich die Auflösung und das Pixelformat des gerenderten Bildes anpassen?**  
A: Ja, Sie können die Auflösung und das Pixelformat nach Ihren Anforderungen mit Aspose.Tasks anpassen.

**Q: Benötigt Aspose.Tasks eine Lizenz für die kommerzielle Nutzung?**  
A: Ja, Sie müssen eine Lizenz für die kommerzielle Nutzung von Aspose.Tasks erwerben. Sie können eine temporäre Lizenz für Testzwecke von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo kann ich Unterstützung für Aspose.Tasks erhalten?**  
A: Unterstützung für Aspose.Tasks erhalten Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

---

**Zuletzt aktualisiert:** 2026-03-21  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}