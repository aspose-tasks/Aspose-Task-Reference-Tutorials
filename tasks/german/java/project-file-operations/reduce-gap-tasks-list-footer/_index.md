---
date: 2026-05-20
description: Erfahren Sie, wie Sie ein Projekt mit Aspose.Tasks für Java in PDF exportieren,
  den Fußzeilenabstand verringern und das Projekt als Bild speichern. Optimieren Sie
  mühelos das Layout von MS Project.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Projekt in PDF exportieren und Abstand zwischen Aufgabenliste und Fußzeile
  in Aspose.Tasks reduzieren
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Projekt in PDF exportieren und Abstand zwischen Aufgabenliste und Fußzeile
  in Aspose.Tasks reduzieren
url: /de/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt in PDF exportieren und Abstand zwischen Aufgabenliste und Fußzeile reduzieren in Aspose.Tasks

## Einleitung
In diesem Tutorial entdecken Sie **wie man ein Projekt in PDF exportiert**, während Sie gleichzeitig den unerwünschten Abstand zwischen der Aufgabenliste und der Fußzeile in Microsoft‑Project‑Dateien reduzieren. Am Ende der Anleitung können Sie saubere PDFs, PNG‑Bilder und HTML‑Seiten mit einem kompakten Layout mithilfe von Aspose.Tasks für Java erzeugen. Lassen Sie uns den Prozess Schritt für Schritt durchgehen, und Sie werden sehen, warum das für professionelle Berichte wichtig ist.

## Schnelle Antworten
- **Was bedeutet „Projekt in PDF exportieren“?** Es konvertiert eine MPP‑Datei in ein PDF‑Dokument und bewahrt dabei Aufgaben, Zeitpläne und Formatierungen.  
- **Warum den Fußzeilenabstand reduzieren?** Ein kleinerer Abstand erzeugt kompaktere, professioneller aussehende Berichte, insbesondere für gedruckte oder im Web angezeigte Dokumente.  
- **Kann ich das Projekt auch als Bild speichern?** Ja – Aspose.Tasks unterstützt PNG, JPEG und andere Bildformate.  
- **Benötige ich eine spezielle Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher funktioniert mit der aktuellen Aspose.Tasks‑Bibliothek.  

## Was bedeutet „Projekt in PDF exportieren“?
Das Exportieren eines Projekts in PDF wandelt die interne MPP‑Struktur in ein portables Dokument um, das auf jedem Gerät geöffnet werden kann, ohne dass Microsoft Project erforderlich ist. Dies ist ideal zum Teilen von Statusberichten, Stakeholder‑Updates oder zur Archivierung von Projektplänen. Es bewahrt das ursprüngliche Layout, die Farben und die Aufgabenhierarchie und stellt sicher, dass das PDF identisch zum Ausgangsdatei aussieht.

## Warum den Fußzeilenabstand reduzieren?
Der standardmäßige Fußzeilenabstand kann unnötigen Weißraum hinzufügen, was zu Seitenumbruchsproblemen und einem unausgewogenen Erscheinungsbild führt. Das Reduzieren des Abstands stellt sicher, dass Ihr Inhalt die Seite effizient nutzt, wodurch das endgültige PDF oder Bild besser lesbar wird. Ein kompakteres Layout reduziert zudem die Gesamtseitenzahl, was die Druckkosten senken und die Navigation auf dem Bildschirm verbessern kann.

## Wie reduziert man den Abstand zwischen Aufgabenliste und Fußzeile?
`setReduceFooterGap` ist eine boolesche Eigenschaft, die den Fußzeilenabstand beim Export steuert.  
Aspose.Tasks bietet die Option `setReduceFooterGap(true)` für Bild-, PDF‑ und HTML‑Speichervorgänge. Das Aktivieren dieses Flags weist die Engine an, den Raum zwischen der letzten Aufgabenzeile und der Seitenfußzeile zu komprimieren. Wenn es auf true gesetzt ist, schneidet der Renderer automatisch den Rand zu, ohne Aufgaben‑Daten abzuschneiden, was zu einem saubereren Seitenlayout führt.

## Projekt als Bild mit Aspose.Tasks speichern
`ImageSaveOptions` konfiguriert, wie ein Projekt in eine Bilddatei gerendert wird.  
Die Klasse `ImageSaveOptions` ermöglicht es, einen Schnappschuss des Zeitplans als PNG, JPEG oder BMP zu exportieren. Wenn Sie zusätzlich `setReduceFooterGap(true)` aktivieren, spiegelt das erzeugte Bild das kompakte PDF‑Layout wider und liefert Ihnen eine klare Visualisierung für Präsentationen oder Dashboards.

## Java‑Projektexport nach PDF
Die folgenden Abschnitte führen Sie durch einen vollständigen **Java‑Projekt‑Export**‑Workflow, vom Laden der MPP‑Datei bis zum Speichern in drei verschiedenen Formaten.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK) – Version 8 oder höher.  
2. Aspose.Tasks für Java‑Bibliothek – laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.

## Pakete importieren
Bevor wir in den Code‑Teil eintauchen, importieren wir die notwendigen Pakete:

```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Schritt 1: Pfad zu Ihrem Datenverzeichnis angeben
```java
String dataDir = "Your Data Directory";
```  
Stellen Sie sicher, dass Sie `"Your Data Directory"` durch den Pfad zu Ihrem tatsächlichen Datenverzeichnis ersetzen, in dem sich Ihre Microsoft‑Project‑Datei (`HomeMovePlan.mpp` in diesem Beispiel) befindet.

## Schritt 2: MPP‑Datei lesen
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Diese Codezeile liest die Microsoft‑Project‑Datei mit dem Namen `HomeMovePlan.mpp`.

## Schritt 3: ImageSaveOptions festlegen (Projekt als Bild speichern)
`ImageSaveOptions` konfiguriert, wie ein Projekt in eine Bilddatei gerendert wird.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Konfigurieren Sie die Bildspeicheroptionen und setzen Sie `ReduceFooterGap` auf `true`, um den Abstand zwischen Aufgabenliste und Fußzeile zu reduzieren.

## Schritt 4: Als Bild speichern
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Speichern Sie das Projekt als Bild mit den konfigurierten Optionen.

## Schritt 5: PdfSaveOptions festlegen (Projekt in PDF exportieren)
`PdfSaveOptions` gibt Einstellungen für den Export eines Projekts in das PDF‑Format an.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Definieren Sie die PDF‑Speicheroptionen und stellen Sie sicher, dass `ReduceFooterGap` auf `true` gesetzt ist.

## Schritt 6: Als PDF speichern
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Speichern Sie das Projekt als PDF mit den konfigurierten Optionen.

## Schritt 7: HtmlSaveOptions festlegen
`HtmlSaveOptions` steuert die Konvertierung eines Projekts zu HTML, einschließlich Stil‑ und Layout‑Optionen.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Geben Sie die HTML‑Speicheroptionen an und setzen Sie `ReduceFooterGap` auf `true`.

## Schritt 8: Als HTML speichern
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Speichern Sie das Projekt als HTML‑Datei mit den konfigurierten Optionen.

## Häufige Anwendungsfälle und Tipps
- **Stakeholder‑Berichterstattung:** Exportieren Sie in PDF mit reduziertem Fußzeilenabstand, um Berichte kompakt und druckerfreundlich zu halten.  
- **Dashboard‑Schnappschüsse:** Verwenden Sie den Bildexport, wenn Sie eine schnelle Visualisierung für Power BI oder Confluence benötigen.  
- **Web‑Veröffentlichung:** Der HTML‑Export bewahrt Interaktivität und kann direkt in Intranet‑Portale eingebettet werden.  
- **Pro‑Tipp:** Bei sehr großen Projekten erhöhen Sie die `Resolution` in `ImageSaveOptions` auf 300 dpi, um die Klarheit zu erhalten und gleichzeitig vom reduzierten Abstand zu profitieren.

## Häufig gestellte Fragen (Zusätzlich)

**Q: Wie wirkt sich das Reduzieren des Fußzeilenabstands auf die Seitennummerierung aus?**  
A: Es minimiert den Leerraum am unteren Rand jeder Seite, sodass mehr Aufgaben auf eine einzelne Seite passen und die Gesamtseitenzahl reduziert wird.

**Q: Kann ich die gleiche Abstand‑Reduzierungseinstellung nur auf eine einzelne Seite anwenden?**  
A: Ja, indem Sie `setRenderToSinglePage(true)` in `ImageSaveOptions` setzen, können Sie die Seitennummerierung steuern und gleichzeitig den Abstand reduzieren.

**Q: Ist die Option `setReduceFooterGap` für andere Ausgabeformate verfügbar?**  
A: Derzeit wird sie für PNG-, PDF- und HTML‑Exporte unterstützt. Für andere Formate müssen Sie das Layout möglicherweise manuell anpassen.

**Q: Was passiert, wenn mein Projekt benutzerdefinierte Felder enthält – werden diese erhalten?**  
A: Alle benutzerdefinierten Felder bleiben beim Export erhalten; die Layout‑Anpassungen betreffen nur den Abstand, nicht die Daten.

**Q: Verarbeitet die Bibliothek große Projekte effizient?**  
A: Aspose.Tasks streamt Daten und kann mehrseitige MPP‑Dateien verarbeiten, ohne die gesamte Datei in den Speicher zu laden; jedoch sollten Sie beim Export hochauflösender Bilder ausreichend Heap‑Speicher bereitstellen.

**Zuletzt aktualisiert:** 2026-05-20  
**Getestet mit:** Aspose.Tasks 24.11 für Java  
**Autor:** Aspose

## Verwandte Tutorials
- [Projekt als Bild speichern – 24bppRgb-Format mit Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Projekt als Vorlage, CSV und Text speichern mit Aspose.Tasks für Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Wie man eine MPP‑Datei erstellt – Leeres Projekt im MPP‑Format erstellen und speichern mit Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}