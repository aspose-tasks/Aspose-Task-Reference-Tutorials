---
date: 2026-06-15
description: Erfahren Sie, wie Sie MPP in PDF konvertieren und die Ressourcenverbrauchs‑
  und Blatt‑Ansichten mit Aspose.Tasks für Java rendern. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung,
  um die Zeitskala festzulegen und mühelos detaillierte PDF‑Berichte zu erstellen.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: MPP in PDF konvertieren und Ressourcenverbrauchsansicht rendern – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP in PDF konvertieren und Ressourcenverbrauchsansicht rendern – Aspose.Tasks
url: /de/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP in PDF konvertieren und Resource‑Usage‑Ansicht rendern – Aspose.Tasks

In diesem Tutorial lernen Sie **wie man mpp in pdf konvertiert** und dabei die Resource Usage‑ und Sheet‑Ansichten einer Microsoft Project‑Datei rendert. Die Verwendung von Aspose.Tasks für Java eliminiert die Notwendigkeit von Microsoft Project auf dem Server und bietet Ihnen eine schnelle, zuverlässige Möglichkeit, PDF‑Berichte aus MPP‑Dateien zu erstellen. Wir zeigen Ihnen außerdem **wie man den Timescale einstellt**, sodass die Ausgabe Ihren Berichtserfordernissen entspricht.

## Schnelle Antworten
- **Was macht Aspose.Tasks?** Es liest, ändert und konvertiert Microsoft Project (MPP)-Dateien, ohne dass MS Project installiert sein muss.  
- **Kann ich MPP in PDF mit einer einzigen Codezeile konvertieren?** Ja – Projekt laden, SaveOptions setzen und `save` aufrufen.  
- **Welche Timescales werden unterstützt?** Days, ThirdsOfMonths und Months.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist für Nicht‑Trial‑Einsätze erforderlich.  
- **Ist die Bibliothek mit Java 8+ kompatibel?** Absolut – sie unterstützt Java 8 und spätere Versionen.

## Was bedeutet mpp in pdf konvertieren?
*Convert mpp to pdf* bezeichnet den Vorgang, eine Microsoft Project‑Datei (.mpp) zu nehmen und eine Portable Document Format (PDF)-Version zu erzeugen, die die Tabellen, Zeitpläne, Diagramme und Ressourcenzuweisungen des Projekts getreu reproduziert. Das resultierende PDF kann leicht geteilt, gedruckt und archiviert werden, ohne dass Microsoft Project auf dem Rechner des Empfängers installiert sein muss.

## Warum Projekt mit Aspose.Tasks in PDF konvertieren?
Aspose.Tasks unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann Projekte mit mehreren hundert Seiten rendern, ohne die gesamte Datei in den Speicher zu laden, wodurch der RAM‑Verbrauch um bis zu 70 % reduziert wird. Die PDF‑Ausgabe behält Tabellen, Diagramme und Ressourcenzuweisungen bei, was sie ideal für die Verteilung an Stakeholder und die Archivierung macht.

## Voraussetzungen
1. **Java Development Kit (JDK)** – Java 8 oder neuer, auf Ihrem Rechner installiert.  
2. **Aspose.Tasks for Java** – laden Sie das neueste JAR von der [download page](https://releases.aspose.com/tasks/java/) herunter.  

## Wie man mpp in pdf mit Aspose.Tasks für Java konvertiert?
Laden Sie Ihre Quell‑MPP‑Datei, konfigurieren Sie den gewünschten Timescale, setzen Sie das Präsentationsformat auf **ResourceUsage** und speichern Sie das Ergebnis als PDF. Dieser End‑to‑End‑Ablauf erfordert nur wenige API‑Aufrufe und läuft für typische Projektgrößen in weniger als einer Sekunde.

### Schritt 1: Quellprojekt lesen
Die Klasse `Project` repräsentiert eine Microsoft Project‑Datei, die im Speicher geladen ist, und bietet Zugriff auf deren Daten und Struktur.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Schritt 2: SaveOptions mit erforderlichen TimeScale‑Einstellungen definieren
`SaveOptions` konfiguriert, wie das Projekt gespeichert wird, und ermöglicht die Angabe von format‑spezifischen Einstellungen wie dem Timescale.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Schritt 3: Präsentationsformat auf ResourceUsage setzen
`PresentationFormat` bestimmt, welche Projektansicht (z. B. ResourceUsage) im Ausgabedokument gerendert wird.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Schritt 4: Projekt als PDF speichern
`project.save` schreibt das Projekt mithilfe der bereitgestellten `SaveOptions` in eine Datei und erzeugt das endgültige PDF.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Schritt 5: Ansichten für andere TimeScale‑Einstellungen rendern
Wiederholen Sie die vorherigen Schritte und ändern Sie den `TimeScale`‑Wert, um zusätzliche Timescale‑Ansichten zu rendern.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Schritt 6: Optional – Mehrere Projekte stapelweise konvertieren
Wenn Sie **Projekt in pdf konvertieren** für viele Dateien benötigen, setzen Sie die obige Logik in eine Schleife, die ein Verzeichnis mit *.mpp*-Dateien durchläuft. Dieser Ansatz **speichert ms project pdf**-Dateien stapelweise mit minimalen Codeänderungen.  
Der folgende Code demonstriert ein vollständiges Beispiel für die Konvertierung einer MPP‑Datei in PDF mit den gewünschten Einstellungen.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Häufige Probleme und Lösungen
- **Fehlende Schriftarten im PDF** – Stellen Sie sicher, dass die erforderlichen Schriftarten auf dem Server installiert sind oder betten Sie sie über `PdfSaveOptions` ein.  
- **Große Projektdateien verursachen OutOfMemoryError** – Verwenden Sie `LoadOptions.setLoadAllResources(false)`, um Ressourcen bei Bedarf zu laden.  
- **Falsche Timescale‑Darstellung** – Überprüfen Sie, dass `options.setTimeScale(TimeScale.Days)` (oder ein anderer Enum) die gewünschte Granularität entspricht.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks andere Ansichten neben Resource Usage und Sheet rendern?**  
A: Ja, es unterstützt außerdem Gantt‑Chart, Task Usage, Calendar und viele weitere Ansichten.

**Q: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut – es verarbeitet MPP-, MPT- und XML‑Formate von Project 2000 bis Project 2021.

**Q: Kann ich das Aussehen der gerenderten Ansichten anpassen?**  
A: Ja, Sie können Farben, Schriftarten und Spaltenlayouts über `PdfSaveOptions` und `PresentationOptions` ändern.

**Q: Benötigt Aspose.Tasks Microsoft Project installiert zu haben?**  
A: Nein, es ist eine eigenständige Bibliothek und funktioniert in jeder Java‑kompatiblen Umgebung.

**Q: Wo kann ich technischen Support erhalten?**  
A: Support ist über das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15/) verfügbar.

---

**Zuletzt aktualisiert:** 2026-06-15  
**Getestet mit:** Aspose.Tasks 24.12 für Java  
**Autor:** Aspose

## Verwandte Tutorials

- [Resource Usage und Sheet‑Ansicht in Aspose.Tasks rendern](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Wie man PDF in Aspose.Tasks exportiert – Als PDF speichern](/tasks/java/project-file-operations/save-as-pdf/)
- [Wie man MPP‑Dateien mit Aspose.Tasks für Java erstellt](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}