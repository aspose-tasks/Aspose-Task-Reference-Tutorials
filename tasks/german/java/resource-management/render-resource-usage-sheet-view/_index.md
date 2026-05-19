---
date: 2026-01-15
description: Erfahren Sie, wie Sie ein Projekt als PDF speichern und die Ressourcen‑
  und Blatt‑Ansichten von MS Project mit Aspose.Tasks für Java rendern. Folgen Sie
  unserer Schritt‑für‑Schritt‑Anleitung, um das Projekt mühelos als PDF zu exportieren.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt als PDF speichern – Ressourcenauslastung und Blattansicht in Aspose.Tasks
  rendern
url: /de/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt als PDF speichern – Ressourcennutzung und Blattansicht in Aspose.Tasks rendern

## Einführung
In diesem Tutorial erfahren Sie, wie Sie **Projekt als PDF speichern** können, während Sie die Ressourcennutzungs- und Blattansichten einer Microsoft Project‑Datei rendern. Egal, ob Sie einen druckbaren Bericht für Stakeholder erstellen oder MPP‑Dateien in ein universell anzeigbares Format konvertieren müssen, Aspose.Tasks für Java macht den Vorgang unkompliziert – keine Installation von Microsoft Project erforderlich.

## Schnelle Antworten
- **Was macht „Projekt als PDF speichern“?** Es konvertiert eine Projektdatei (MPP) in ein PDF‑Dokument und bewahrt dabei die ausgewählte Ansicht.  
- **Welche Ansicht kann exportiert werden?** Ressourcennutzung, Blatt, Gantt, Aufgaben‑Nutzung und mehr.  
- **Kann ich die Zeitskala im PDF ändern?** Ja – Optionen umfassen Tage, DrittelMonate und Monate.  
- **Benötige ich Microsoft Project installiert?** Nein, Aspose.Tasks arbeitet eigenständig.  
- **Ist für die Produktion eine Lizenz erforderlich?** Ja, für den Einsatz außerhalb der Testphase ist eine kommerzielle Lizenz erforderlich.

## Was ist „Projekt als PDF speichern“?
Das Speichern eines Projekts als PDF erzeugt eine statische, hochauflösende Darstellung einer ausgewählten Projektansicht. Dies ist ideal zum Teilen mit Kunden, zur Archivierung oder zum Drucken, ohne die zugrunde liegende Projektdatei offenzulegen.

## Warum Aspose.Tasks zum Exportieren eines Projekts als PDF verwenden?
- **Keine externen Abhängigkeiten** – funktioniert auf jeder Plattform, die Java unterstützt.  
- **Feinkörnige Kontrolle** – Sie können Ansicht, Zeitskala und Layout auswählen.  
- **Hohe Treue** – das PDF spiegelt das Aussehen der ursprünglichen Projektansicht wider.  
- **Automatisierungs‑bereit** – Integration in CI‑Pipelines, Reporting‑Dienste oder Batch‑Konverter.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – die neueste empfohlene Version.  
2. **Aspose.Tasks für Java** – Download von der [Download-Seite](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Zuerst importieren Sie die erforderlichen Klassen in Ihr Java‑Projekt:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Quellprojekt lesen
Laden Sie die MPP‑Datei, die Sie konvertieren möchten.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Schritt 2: SaveOptions mit erforderlicher Zeitskala definieren (Projekt als PDF exportieren)
Konfigurieren Sie die PDF‑Exportoptionen und setzen Sie die gewünschte Zeitskala.  
*Hier verwenden wir **Tage** als Beispiel.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Schritt 3: Präsentationsformat auf ResourceUsage setzen
Wählen Sie die Ansicht, die Sie rendern möchten. In diesem Fall die **Resource Usage**‑Ansicht.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Schritt 4: Projekt speichern (MPP in PDF konvertieren)
Führen Sie die Konvertierung aus und erzeugen Sie die PDF‑Datei.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Schritt 5: Ansichten für andere Zeitskala‑Einstellungen rendern (Zeitskala‑PDF ändern)
Wiederholen Sie die vorherigen Schritte, um PDFs mit unterschiedlichen Zeitskalen wie **ThirdsOfMonths** und **Months** zu erzeugen.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Häufige Probleme und Lösungen
- **Datei‑nicht‑gefunden‑Fehler** – Stellen Sie sicher, dass `dataDir` auf den richtigen Ordner verweist und der MPP‑Dateiname exakt übereinstimmt.  
- **Leere PDF‑Ausgabe** – Stellen Sie sicher, dass das `PresentationFormat` einer Ansicht entspricht, die Daten enthält (z. B. ResourceUsage).  
- **Falsche Zeitskala** – Überprüfen Sie, dass `options.setTimescale()` vor jedem `project.save()` aufgerufen wird.

## Häufig gestellte Fragen

### Kann Aspose.Tasks andere Ansichten als Resource Usage und Sheet rendern?
Aspose.Tasks unterstützt das Rendern verschiedener Ansichten wie Gantt‑Diagramm, Task Usage und Kalenderansichten, unter anderem.

### Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?
Ja, Aspose.Tasks unterstützt eine breite Palette von Microsoft Project‑Dateiformaten, einschließlich MPP, MPT und XML‑Formaten.

### Kann ich das Aussehen gerenderter Ansichten mit Aspose.Tasks anpassen?
Absolut! Aspose.Tasks bietet umfangreiche Optionen zur Anpassung des Aussehens und Layouts gerenderter Ansichten, um Ihren spezifischen Anforderungen gerecht zu werden.

### Benötigt Aspose.Tasks Microsoft Project auf dem System installiert?
Nein, Aspose.Tasks ist eine eigenständige Bibliothek und erfordert keine Installation von Microsoft Project für die Funktionsweise.

### Ist technischer Support für Aspose.Tasks‑Benutzer verfügbar?
Ja, Aspose.Tasks‑Benutzer können technischen Support über das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) erhalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---