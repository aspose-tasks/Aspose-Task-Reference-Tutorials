---
title: Schreiben Sie aktualisierte Ressourcendaten in Aspose.Tasks
linktitle: Schreiben Sie aktualisierte Ressourcendaten in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java mühelos Ressourcendaten in MS Project-Dateien aktualisieren.
weight: 21
url: /de/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schreiben Sie aktualisierte Ressourcendaten in Aspose.Tasks

## Einführung
In diesem Tutorial führen wir Sie durch die Aktualisierung von Microsoft Project-Ressourcendaten mit Aspose.Tasks für Java. Aspose.Tasks ist eine leistungsstarke Java-API, mit der Sie Microsoft Project-Dateien bearbeiten können, ohne dass Microsoft Project auf Ihrem System installiert sein muss.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Java Development Kit (JDK) auf Ihrem System installiert.
2.  Aspose.Tasks für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
3. Grundkenntnisse der Java-Programmierung.

## Pakete importieren

Zuerst müssen Sie die notwendigen Pakete importieren, um mit Aspose.Tasks in Ihrem Java-Code zu arbeiten. Fügen Sie Ihrer Java-Datei die folgenden Importanweisungen hinzu:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt 1: Richten Sie Ihr Datenverzeichnis ein

Definieren Sie das Verzeichnis, in dem sich Ihre Datendateien befinden:

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Geben Sie Eingabe- und Ausgabedateien an

Definieren Sie die Pfade für die Eingabe-MS-Project-Datei und die resultierende aktualisierte Datei:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Testdatei mit einem zu aktualisierenden RSC
String resultFile = dataDir + "OutputMPP.mpp"; // Datei zum Schreiben des Testprojekts
```

## Schritt 3: Laden Sie das Projekt

 Laden Sie die MS Project-Datei in ein`Project` Objekt:

```java
Project project = new Project(file);
```

## Schritt 4: Fügen Sie eine Ressource hinzu und legen Sie Attribute fest

Fügen Sie dem Projekt eine neue Ressource hinzu und legen Sie deren Attribute wie Standardsatz, Überstundensatz und Gruppe fest:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Schritt 5: Speichern Sie das Projekt

Speichern Sie das aktualisierte Projekt mit den geänderten Ressourcendaten:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Abschluss

In diesem Tutorial haben wir gezeigt, wie Sie MS Project-Ressourcendaten mit Aspose.Tasks für Java aktualisieren. Wenn Sie diese Schritte befolgen, können Sie Ressourceninformationen in Ihren MS Project-Dateien effizient programmgesteuert bearbeiten.

## FAQs

### F1: Kann ich mit Aspose.Tasks für Java mehrere Ressourcen im selben Projekt aktualisieren?

A1: Ja, Sie können mehrere Ressourcen aktualisieren, indem Sie sie durchlaufen und ihre Attribute entsprechend festlegen.

### F2: Unterstützt Aspose.Tasks neben MS Project auch andere Dateiformate?

A2: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate, darunter XML, MPP und mehr.

### F3: Ist Aspose.Tasks mit verschiedenen Java-Versionen kompatibel?

A3: Aspose.Tasks ist mit Java-Versionen 6 und höher kompatibel.

### F4: Kann ich mit Aspose.Tasks andere Vorgänge an MS Project-Dateien ausführen?

A4: Ja, Sie können eine Vielzahl von Vorgängen ausführen, z. B. Lesen, Schreiben und Bearbeiten von Aufgaben, Ressourcen und Kalendern.

### F5: Wo finde ich zusätzliche Hilfe oder Unterstützung für Aspose.Tasks?

 A5: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für jegliche Hilfe oder Fragen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
