---
date: 2025-12-17
description: Erfahren Sie, wie Sie ein Projekt mit Aspose.Tasks für Java in PDF exportieren,
  den Fußzeilenabstand reduzieren und das Projekt als Bild speichern. Optimieren Sie
  Ihr MS Project‑Layout mühelos.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt als PDF exportieren und Abstand zwischen Aufgabenliste und Fußzeile
  in Aspose.Tasks reduzieren
url: /de/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt in PDF exportieren und Abstand zwischen Aufgabenliste und Fußzeile in Aspose.Tasks reduzieren

## Einleitung  
In diesem Tutorial entdecken Sie **wie man ein Projekt in PDF exportiert**, während Sie gleichzeitig den unerwünschten Abstand zwischen der Aufgabenliste und der Fußzeile in Microsoft‑Project‑Dateien reduzieren. Am Ende des Leitfadens können Sie saubere PDFs, PNG‑Bilder und HTML‑Seiten mit einem kompakten Layout mithilfe von Aspose.Tasks für Java erzeugen. Lassen Sie uns den Vorgang Schritt für Schritt durchgehen.

## Schnelle Antworten  
- **Was bedeutet „Projekt in PDF exportieren“?** Es konvertiert eine MPP‑Datei in ein PDF‑Dokument und bewahrt dabei Aufgaben, Zeitpläne und Formatierung.  
- **Warum den Fußzeilenabstand reduzieren?** Ein kleinerer Abstand erzeugt kompaktere, professioneller aussehende Berichte, insbesondere für gedruckte oder im Web angezeigte Dokumente.  
- **Kann ich das Projekt auch als Bild speichern?** Ja – Aspose.Tasks unterstützt PNG, JPEG und weitere Bildformate.  
- **Benötige ich eine spezielle Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher funktioniert mit der aktuellen Aspose.Tasks‑Bibliothek.

## Was bedeutet „Projekt in PDF exportieren“?  
Ein Projekt in PDF zu exportieren wandelt die interne MPP‑Struktur in ein portables Dokument um, das auf jedem Gerät geöffnet werden kann, ohne Microsoft Project zu benötigen. Dies ist ideal zum Teilen von Statusberichten, Stakeholder‑Updates oder zur Archivierung von Projektplänen.

## Warum den Fußzeilenabstand reduzieren?  
Der standardmäßige Fußzeilenabstand kann unnötigen Weißraum hinzufügen, was zu Seitenumbruchsproblemen und einem unausgewogenen Erscheinungsbild führt. Durch die Reduzierung des Abstands wird sichergestellt, dass Ihr Inhalt die Seite effizient nutzt, wodurch das endgültige PDF oder Bild besser lesbar wird.

## Wie reduziert man den Abstand zwischen Aufgabenliste und Fußzeile?  
Aspose.Tasks bietet die Option `setReduceFooterGap(true)` für Bild‑, PDF‑ und HTML‑Speichervorgänge. Das Aktivieren dieses Flags weist die Engine an, den Abstand zwischen der letzten Aufgabenzeile und der Seitenfußzeile zu komprimieren.

## Projekt als Bild mit Aspose.Tasks speichern  
Wenn Sie einen visuellen Schnappschuss Ihres Zeitplans benötigen, können Sie **Projekt als Bild speichern** (PNG), während Sie dieselben Einstellungen zur Abstandreduzierung anwenden.

## Java‑Projektexport nach PDF  
Die folgenden Abschnitte führen Sie durch einen vollständigen **Java‑Projekt‑Export**‑Workflow, vom Laden der MPP‑Datei bis zum Speichern in drei verschiedenen Formaten.

## Voraussetzungen
1. Java Development Kit (JDK) – Version 8 oder höher.  
2. Aspose.Tasks for Java Bibliothek – laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.

## Pakete importieren
Bevor Sie in den Code-Teil eintauchen, importieren wir die notwendigen Pakete:
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
Stellen Sie sicher, dass Sie `"Your Data Directory"` durch den Pfad zu Ihrem tatsächlichen Datenverzeichnis ersetzen, in dem sich Ihre Microsoft‑Project‑Datei (`HomeMovePlan.mpp` in diesem Beispiel) befindet.
```java
String dataDir = "Your Data Directory";
```

## Schritt 2: MPP‑Datei lesen
Diese Codezeile liest die Microsoft‑Project‑Datei mit dem Namen `HomeMovePlan.mpp`.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Schritt 3: ImageSaveOptions festlegen (Projekt als Bild speichern)
Konfigurieren Sie die Bildspeicheroptionen und setzen Sie `ReduceFooterGap` auf `true`, um den Abstand zwischen der Aufgabenliste und der Fußzeile zu reduzieren.
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```

## Schritt 4: Als Bild speichern
Speichern Sie das Projekt als Bild mit den konfigurierten Optionen.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```

## Schritt 5: PdfSaveOptions festlegen (Projekt in PDF exportieren)
Definieren Sie die PDF‑Speicheroptionen und stellen Sie sicher, dass `ReduceFooterGap` auf `true` gesetzt ist.
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```

## Schritt 6: Als PDF speichern
Speichern Sie das Projekt als PDF mit den konfigurierten Optionen.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```

## Schritt 7: HtmlSaveOptions festlegen
Geben Sie die HTML‑Speicheroptionen an und setzen Sie `ReduceFooterGap` auf `true`.
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```

## Schritt 8: Als HTML speichern
Speichern Sie das Projekt als HTML‑Datei mit den konfigurierten Optionen.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```

## Fazit  
Zusammenfassend lässt sich sagen, dass das Reduzieren des Abstands zwischen Aufgabenliste und Fußzeile in Microsoft‑Project‑Dateien mit Aspose.Tasks für Java ein einfacher Vorgang ist. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie effizient **Projekt in PDF exportieren**, es als Bild speichern oder HTML erzeugen, wobei das Layout kompakt und professionell bleibt.

## FAQ

### Q: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?
Aspose.Tasks unterstützt die Formate von Microsoft Project 2003‑2019 und gewährleistet damit die Kompatibilität mit verschiedenen Versionen.

### Q: Kann ich das Aussehen der Fußzeile in meinen Projektdokumenten anpassen?
Ja, Aspose.Tasks bietet umfangreiche Optionen zur Anpassung des Aussehens von Fußzeilen, einschließlich der Reduzierung von Abständen und der Anpassung der Inhaltsposition.

### Q: Unterstützt Aspose.Tasks das Speichern von Projekten in anderen Formaten als PNG, PDF und HTML?
Ja, Aspose.Tasks unterstützt eine Vielzahl von Formaten, darunter XLSX, XML und MPP sowie weitere.

### Q: Gibt es eine Testversion von Aspose.Tasks?
Ja, Sie können eine kostenlose Testversion von Aspose.Tasks von [hier](https://releases.aspose.com/) herunterladen.

### Q: Wo kann ich Unterstützung erhalten, wenn ich bei der Verwendung von Aspose.Tasks auf Probleme stoße?
Sie können Unterstützung im Aspose.Tasks‑Community‑Forum [hier](https://forum.aspose.com/c/tasks/15) erhalten.

## Häufig gestellte Fragen (Zusätzlich)

**Q: Wie wirkt sich das Reduzieren des Fußzeilenabstands auf die Seitennummerierung aus?**  
A: Es minimiert den Leerraum am unteren Rand jeder Seite, sodass mehr Aufgaben auf eine einzelne Seite passen und die Gesamtseitenzahl reduziert wird.

**Q: Kann ich die gleiche Abstand‑Reduzierungseinstellung nur auf eine einzelne Seite anwenden?**  
A: Ja, indem Sie `setRenderToSinglePage(true)` in `ImageSaveOptions` setzen, können Sie die Seitennummerierung steuern und gleichzeitig den Abstand reduzieren.

**Q: Ist die Option `setReduceFooterGap` für andere Ausgabeformate verfügbar?**  
A: Derzeit wird sie für PNG-, PDF- und HTML‑Exporte unterstützt. Für andere Formate müssen Sie das Layout möglicherweise manuell anpassen.

**Q: Was passiert, wenn mein Projekt benutzerdefinierte Felder enthält – werden diese erhalten?**  
A: Alle benutzerdefinierten Felder bleiben beim Export erhalten; die Layout‑Anpassungen betreffen nur den Abstand, nicht die Daten.

**Q: Kann die Bibliothek große Projekte effizient verarbeiten?**  
A: Aspose.Tasks streamt Daten und kann große MPP‑Dateien verarbeiten; stellen Sie jedoch sicher, dass ausreichend Speicher vorhanden ist, wenn Sie in hochauflösende Bilder exportieren.

**Zuletzt aktualisiert:** 2025-12-17  
**Getestet mit:** Aspose.Tasks 24.11 für Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}