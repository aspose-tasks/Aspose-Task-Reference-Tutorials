---
date: 2026-02-26
description: Erfahren Sie, wie Sie ein Projekt als PDF speichern und ein Aufgabenblatt
  mit Aspose.Tasks für Java rendern. Exportieren Sie MPP schnell in PDF mit dieser
  Schritt‑für‑Schritt‑Anleitung.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt als PDF speichern – Aufgabenblatt mit Aspose.Tasks für Java rendern
url: /de/java/task-properties/render-task-sheet/
weight: 27
---

.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt als PDF speichern – Task Sheet in Aspose.Tasks rendern

## Einführung
In diesem umfassenden Leitfaden erfahren Sie, wie Sie **save project as PDF** nutzen und ein Task Sheet mit Aspose.Tasks für Java erzeugen. Egal, ob Sie eine MPP‑Datei in PDF für Stakeholder‑Reviews exportieren müssen oder einfach ein übersichtliches Task Sheet für Berichte rendern wollen, führt Sie dieses Tutorial durch jeden Schritt, erklärt, warum jede Einstellung wichtig ist, und zeigt den genauen Code, den Sie ausführen müssen.

## Schnelle Antworten
- **Was macht “save project as pdf”?** Es konvertiert eine Microsoft‑Project‑Datei (MPP) in ein PDF‑Dokument und formatiert sie optional als Task Sheet.  
- **Welches Format wird für ein Task‑Sheet‑PDF verwendet?** Die Option `PresentationFormat.TaskSheet` in `PdfSaveOptions`.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion funktioniert für die Evaluierung.  
- **Was sind die wichtigsten Voraussetzungen?** Java JDK, Aspose.Tasks für Java‑Bibliothek und eine gültige Projektdatei (z. B. *.mpp).  
- **Kann ich das PDF‑Layout anpassen?** Ja, Aspose.Tasks bietet zahlreiche `PdfSaveOptions`‑Eigenschaften für Styling und Seiteneinrichtung.

## Was ist “save project as pdf”?
Das Speichern eines Projekts als PDF wandelt die internen Projektdaten in ein portables, schreibgeschütztes Dokument um. Das ist ideal, um Zeitpläne, Task Sheets oder Statusberichte mit Stakeholdern zu teilen, die Microsoft Project nicht installiert haben.

## Warum ein Task Sheet rendern?
Ein Task Sheet stellt jede Aufgabe in einer tabellarischen Ansicht dar und zeigt IDs, Namen, Start‑/Enddaten sowie weitere Felder. Die Ausgabe als PDF sorgt für einheitliche Formatierung über Plattformen hinweg und erleichtert das Drucken oder Einbetten in andere Dokumente.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – neueste Version installiert und `java`/`javac` im PATH verfügbar.  
2. **Aspose.Tasks for Java** – Laden Sie die Bibliothek von der offiziellen Seite [here](https://releases.aspose.com/tasks/java/).  
3. Eine gültige **Projektdatei** (`*.mpp`), die Sie konvertieren möchten, z. B. `NewProductDev.mpp`.  

## Pakete importieren
Importieren Sie zunächst die erforderlichen Aspose.Tasks‑Klassen. Diese Importe geben Ihnen Zugriff auf PDF‑Speicheroptionen, Präsentationsformate und das Kern‑`Project`‑Objekt.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Dokumentverzeichnis festlegen
Definieren Sie den Ordner, in dem die Quell‑MPP‑Datei liegt und in den das erzeugte PDF geschrieben wird. Sowohl ein absoluter als auch ein relativer Pfad funktionieren; stellen Sie lediglich sicher, dass der Ordner existiert.

```java
String dataDir = "Your Document Directory";
```

### Schritt 2: Projektdatei laden
Erstellen Sie eine `Project`‑Instanz, indem Sie die vorhandene MPP‑Datei laden. Dieses Objekt repräsentiert die gesamte Projektstruktur im Speicher.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Schritt 3: Speicheroptionen konfigurieren – MPP nach PDF exportieren
Instanziieren Sie `PdfSaveOptions` und teilen Sie Aspose.Tasks mit, dass das PDF als **task sheet** gerendert werden soll. Dies ist der zentrale Schritt für den Anwendungsfall *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Schritt 4: Projekt als Task Sheet speichern – Projekt als PDF speichern
Rufen Sie die `save`‑Methode des `Project`‑Objekts auf und übergeben Sie den Zieldateinamen sowie die konfigurierten Optionen. Diese Aktion **konvertiert die MPP‑Datei in ein PDF**, das als Task Sheet formatiert ist.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Schritt 5: Ergebnis überprüfen
Navigieren Sie zu dem von Ihnen angegebenen Verzeichnis (`dataDir`). Sie sollten `taskSheet.pdf` sehen, das eine ordentlich formatierte Liste aller Aufgaben enthält. Öffnen Sie die Datei mit einem beliebigen PDF‑Betrachter, um zu prüfen, ob die Konvertierung erfolgreich war.

## Häufige Probleme und Lösungen
- **FileNotFoundException** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`/` oder `\\`) endet und der MPP‑Dateiname korrekt ist.  
- **LicenseException** – Wenn Lizenzfehler auftreten, wenden Sie vor dem Aufruf einer Aspose.Tasks‑API eine temporäre oder gekaufte Lizenz an.  
- **Blank PDF** – Prüfen Sie, ob das Projekt tatsächlich Aufgaben enthält; ein leeres Projekt erzeugt ein leeres PDF.

## Häufig gestellte Fragen

**Q: Ist Aspose.Tasks mit allen Java‑Versionen kompatibel?**  
A: Ja, Aspose.Tasks funktioniert mit einer breiten Palette von Java‑Versionen. Siehe die [Dokumentation](https://reference.aspose.com/tasks/java/) für Details.

**Q: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Absolut! Erkunden Sie die kostenlose Testversion [here](https://releases.aspose.com/).

**Q: Wo finde ich Support für Aspose.Tasks?**  
A: Treten Sie der Aspose.Tasks‑Community im [Forum](https://forum.aspose.com/c/tasks/15) bei, um Unterstützung und Diskussionen zu erhalten.

**Q: Wie erhalte ich eine temporäre Lizenz für Aspose.Tasks?**  
A: Holen Sie Ihre temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/).

**Q: Wo kann ich Aspose.Tasks für Java kaufen?**  
A: Kaufen Sie Aspose.Tasks für Java [here](https://purchase.aspose.com/buy).

## Fazit
Durch das Befolgen dieser Schritte haben Sie gelernt, wie man **save project as PDF** verwendet, speziell ein Task Sheet rendert, mit Aspose.Tasks für Java. Diese Fähigkeit ermöglicht es Ihnen, *MPP nach PDF* schnell zu exportieren, lesbare Projekt‑Snapshots zu teilen und Projektdaten in umfassendere Reporting‑Workflows zu integrieren.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}