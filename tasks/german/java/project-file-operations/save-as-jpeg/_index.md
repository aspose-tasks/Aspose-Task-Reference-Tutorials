---
title: Konvertieren Sie MS Project als JPEG in Aspose.Tasks
linktitle: Speichern Sie das Projekt als JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java ganz einfach Microsoft Project-Dateien in JPEG-Bilder konvertieren. Steigern Sie Ihre Produktivität.
weight: 20
url: /de/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren Sie MS Project als JPEG in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java eine Microsoft Project-Datei als JPEG-Bild speichern. Dies kann besonders nützlich sein, um Projektvisualisierungen zu teilen oder Projektdaten in Berichte oder Präsentationen zu integrieren.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können die neueste Version von herunterladen und installieren[Java-Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks für Java: Laden Sie Aspose.Tasks für Java herunter und richten Sie es ein, indem Sie den Anweisungen im folgen[Dokumentation](https://reference.aspose.com/tasks/java/).

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihre Java-Datei:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Schritt 1: Datenverzeichnis definieren
Legen Sie den Pfad zu Ihrem Datenverzeichnis fest, in dem sich Ihre MS Project-Datei befindet.
```java
String dataDir = "Your Data Directory";
```
## Schritt 2: MS Project-Datei laden
Laden Sie die MS Project-Datei mit Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Schritt 3: JPEG-Qualität konfigurieren (optional)
 Wenn Sie die JPEG-Qualität anpassen möchten, können Sie sie mit einstellen`ImageSaveOptions` Klasse. Die Qualität reicht von 0 bis 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Stellen Sie die JPEG-Qualität auf 50 ein
```
## Schritt 4: Projekt als JPEG speichern
Speichern Sie die MS Project-Datei als JPEG-Bild.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java eine Microsoft Project-Datei als JPEG-Bild speichert. Diese Funktion ermöglicht den einfachen Austausch und die Integration von Projektdaten in verschiedene Dokumente und Präsentationen.
## FAQs
### F: Kann ich die Qualität des JPEG-Bilds anpassen?
 A: Ja, Sie können die Qualität mit anpassen`setJpegQuality()` Methode mit einem Bereich von 0 bis 100.
### F: Was passiert, wenn ich die JPEG-Qualität nicht spezifiziere?
A: Wenn Sie die Qualität nicht angeben, wird die Standardqualität verwendet.
### F: Ist die Nutzung von Aspose.Tasks für Java kostenlos?
 A: Aspose.Tasks für Java ist eine kommerzielle Bibliothek, Sie können ihre Funktionen jedoch mit einer kostenlosen Testversion erkunden. Besuche den[kostenlose Testseite](https://releases.aspose.com/) für mehr Informationen.
### F: Wo erhalte ich Unterstützung für Aspose.Tasks für Java?
A: Sie können Unterstützung vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks erwerben?
 A: Ja, Sie können eine temporäre Lizenz bei erwerben[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
