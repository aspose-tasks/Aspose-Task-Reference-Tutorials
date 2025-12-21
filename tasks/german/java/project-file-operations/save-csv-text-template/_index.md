---
date: 2025-12-21
description: Erfahren Sie, wie Sie ein Projekt als Vorlage speichern, MPP in CSV exportieren
  und MPP in Text konvertieren, indem Sie Aspose.Tasks für Java verwenden.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Projekt als Vorlage, CSV und Text mit Aspose.Tasks für Java speichern
url: /de/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt als Vorlage, CSV und Text mit Aspise.Tasks speichern

## Einführung
In diesem Tutorial erfahren Sie **wie man ein Projekt als Vorlage speichert** und wie Sie Ihre Microsoft Project (MPP)-Dateien mit der Aspose.Tasks‑Bibliothek für Java in CSV‑ und Nur‑Text‑Formate exportieren können. Egal, ob Sie eine wiederverwendbare Projektvorlage erstellen, CSV‑Berichte für Analysen generieren oder einfache Textauszüge für die Integration erzeugen möchten, diese Schritte führen Sie schnell und effizient durch den Prozess.

## Schnellantworten
- **Kann ich MPP nach CSV exportieren?** Ja – verwenden Sie `project.save(..., SaveFileFormat.CSV)`.  
- **Wie exportiere ich Text?** Speichern Sie mit `SaveFileFormat.TEXT`.  
- **Was bewirkt „Projekt als Vorlage speichern“?** Es erstellt eine `.mpt`‑Datei, die die tatsächlichen und Basislinienwerte entfernt und zur Wiederverwendung bereitsteht.  
- **Benötige ich eine Lizenz?** Eine Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8+ wird unterstützt.

## Was bedeutet „Projekt als Vorlage speichern“?
Das Speichern eines Projekts als Vorlage (`.mpt`) erfasst die Struktur, die Aufgabenhierarchie und die Ressourcenzuweisungen, während die tatsächlichen Start‑/Enddaten und Basisliniendaten entfernt werden. Dadurch eignet sich die Vorlage ideal, um ein standardisiertes Projektlayout in mehreren neuen Projekten wiederzuverwenden.

## Warum Aspose.Tasks für Java verwenden?
Aspose.Tasks ermöglicht es Ihnen, Microsoft‑Project‑Dateien zu manipulieren, ohne Microsoft Project selbst zu installieren. Es unterstützt **wie man MPP exportiert**, **wie man Text exportiert** und **wie man MPP in CSV konvertiert**, alles aus reinem Java‑Code, was sich perfekt für serverseitige Automatisierung, CI‑Pipelines oder Desktop‑Dienstprogramme eignet.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Java Development Kit (JDK) 8 oder höher installiert.  
2. Aspose.Tasks for Java‑Bibliothek zu Ihrem Projekt hinzugefügt. Laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. Grundlegende Kenntnisse der Java‑Syntax sowie der Maven/Gradle‑Projektkonfiguration.

## Pakete importieren
Importieren Sie zunächst die benötigten Klassen in Ihrer Java‑Quelldatei:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Projekt als CSV speichern (MPP nach CSV exportieren)
Das Exportieren einer MPP‑Datei nach CSV ist nützlich für Datenanalysen in Excel oder BI‑Tools.

### Schritt 1: Projekt laden
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Schritt 2: Als CSV speichern
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Projekt als Text speichern (Wie man Text exportiert)
Wenn Sie eine reine Textdarstellung von Aufgaben, Ressourcen oder Zuweisungen benötigen, speichern Sie das Projekt als Textdatei.

### Schritt 1: Projekt laden
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Schritt 2: Als Text speichern
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Projekt als Vorlage speichern (Projektvorlage in Java erstellen)
Das Erstellen einer wiederverwendbaren Vorlage entfernt tatsächliche Daten und Basislinien und hinterlässt ein sauberes Gerüst für neue Projekte.

### Schritt 1: Projekt laden
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Schritt 2: Vorlagenoptionen festlegen
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Schritt 3: Als Vorlage speichern
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Häufige Probleme & Tipps
- **Datei nicht gefunden:** Stellen Sie sicher, dass der Pfad zu `YourProject.mpp` korrekt ist, oder verwenden Sie einen absoluten Pfad.  
- **Lizenzausnahmen:** Ohne gültige Lizenz läuft die Bibliothek im Evaluierungsmodus und kann Wasserzeichen hinzufügen. Setzen Sie Ihre Lizenz früh im Code (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Große Projekte:** Bei sehr großen MPP‑Dateien sollten Sie die JVM‑Heap‑Größe erhöhen (`-Xmx2g`), um `OutOfMemoryError` zu vermeiden.

## Fazit
Wir haben **wie man ein Projekt als Vorlage speichert**, sowie **wie man MPP nach CSV exportiert** und **wie man MPP in Text konvertiert** mit Aspose.Tasks für Java behandelt. Diese Funktionen ermöglichen es Ihnen, die Projektdatenverarbeitung zu automatisieren, wiederverwendbare Vorlagen zu erstellen und Projektinformationen in andere Systeme zu integrieren – und das alles, ohne Microsoft Project zu installieren.

## FAQ
### Q: Kann Aspose.Tasks für Java komplexe Projektdateien verarbeiten?
A: Absolut! Aspose.Tasks für Java kann Projekte unterschiedlicher Komplexität mühelos verarbeiten und bietet umfassende Unterstützung für Microsoft‑Project‑Dateiformate.

### Q: Gibt es eine Testversion von Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von [hier](https://releases.aspose.com/) erhalten.

### Q: Wo finde ich Support für Aspose.Tasks für Java?
A: Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen, um Unterstützung oder Fragen zu Aspose.Tasks für Java zu erhalten.

### Q: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?
A: Ja, Sie können eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) erwerben, um das volle Potenzial der Bibliothek zu evaluieren.

### Q: Ist Aspose.Tasks für Java mit verschiedenen Betriebssystemen kompatibel?
A: Ja, Aspose.Tasks für Java ist mit verschiedenen Betriebssystemen kompatibel, einschließlich Windows, macOS und Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose