---
title: Konvertieren Sie MS Project in Java in SVG
linktitle: Als SVG in Aspose.Tasks speichern
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Microsoft Project-Dateien mithilfe der Aspose.Tasks-Bibliothek als SVG in Java speichern. Schritt-für-Schritt-Anleitung mit Codebeispielen.
type: docs
weight: 18
url: /de/java/project-file-operations/save-as-svg/
---
## Einführung
Aspose.Tasks für Java ist eine leistungsstarke Bibliothek für die Arbeit mit Projektverwaltungsdateien, die es Entwicklern ermöglicht, Projektdaten zu bearbeiten, verschiedene Vorgänge auszuführen und Berichte effizient zu erstellen. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java ein Projekt als SVG speichern. SVG (Scalable Vector Graphics) ist ein weit verbreitetes Format zur Darstellung von Vektorgrafiken im Web und bietet Skalierbarkeit und hochwertige Darstellung.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
### Java-Entwicklungsumgebung
Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist. Sie können JDK von der Oracle-Website herunterladen und installieren.
### Aspose.Tasks für Java-Bibliothek
 Laden Sie die Aspose.Tasks für Java-Bibliothek von der Website herunter und installieren Sie sie. Den Download-Link finden Sie in der bereitgestellten Dokumentation[Hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihr Java-Programm importieren, um mit den Aspose.Tasks-Funktionen arbeiten zu können.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte unterteilen:
## Schritt 2: Datenverzeichnis definieren
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"`mit dem Pfad zu dem Verzeichnis, in dem sich Ihre Projektdatei befindet.
## Schritt 3: Projektdatei laden
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Dieser Schritt lädt die Projektdatei mit dem Namen „HomeMovePlan.mpp“ aus dem angegebenen Datenverzeichnis.
## Schritt 4: Als SVG speichern
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Dieser Schritt speichert das geladene Projekt im SVG-Format mit dem Namen „project5.svg“ im angegebenen Datenverzeichnis.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java ein Projekt als SVG speichert. Indem Sie die bereitgestellten Schritte befolgen, können Sie Projektdateien effizient in das SVG-Format konvertieren und so eine nahtlose Integration mit webbasierten Anwendungen oder Visualisierungstools ermöglichen.
## FAQs
### Ist Aspose.Tasks für Java mit allen Versionen von Microsoft Project-Dateien kompatibel?
Ja, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich der Formate MPP, MPT und XML.
### Kann ich das Erscheinungsbild der SVG-Ausgabe anpassen?
Ja, Sie können das Erscheinungsbild der SVG-Ausgabe anpassen, indem Sie Parameter wie Schriftarten, Farben und Layoutkonfigurationen anpassen.
### Benötigt Aspose.Tasks für Java eine Lizenz für die kommerzielle Nutzung?
 Ja, für die kommerzielle Nutzung von Aspose.Tasks für Java ist eine gültige Lizenz erforderlich. Eine Lizenz erhalten Sie auf der Website[Hier](https://purchase.aspose.com/temporary-license/).
### Kann ich Aspose.Tasks für Java vor dem Kauf testen?
 Ja, Sie können auf der Website eine kostenlose Testversion von Aspose.Tasks für Java anfordern[Hier](https://purchase.aspose.com/buy) um seine Eigenschaften und Fähigkeiten zu bewerten.
### Wo erhalte ich Unterstützung für Aspose.Tasks für Java?
 Sie können Unterstützung für Aspose.Tasks für Java erhalten, indem Sie das Forum besuchen[Hier](https://forum.aspose.com/c/tasks/15), wo Sie Fragen stellen und mit der Community interagieren können.