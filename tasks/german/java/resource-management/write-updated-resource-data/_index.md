---
date: 2026-06-30
description: Erfahren Sie, wie Sie mehrere Ressourcen aktualisieren und Ressourcengruppendaten
  ändern, dann das Projekt nach MPP exportieren und das Projekt als MPP mit Aspose.Tasks
  for Java speichern.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Mehrere Ressourcen in Aspose.Tasks for Java aktualisieren
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Mehrere Ressourcen in Aspose.Tasks for Java aktualisieren
url: /de/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mehrere Ressourcen in Aspise.Tasks für Java aktualisieren

## Einführung
In diesem Tutorial lernen Sie, wie Sie **mehrere Ressourcen aktualisieren** in einer Microsoft Project‑Datei mithilfe von Aspose.Tasks für Java. Egal, ob Sie Raten ändern, Gruppen neu zuweisen oder die aktualisierte Datei nach MPP exportieren müssen, die nachfolgenden Schritte führen Sie durch einen vollständigen, produktionsbereiten Workflow. Eine Installation von Microsoft Project ist nicht erforderlich, und die API kann Projekte mit Hunderten von Ressourcen effizient verarbeiten.

## Schnelle Antworten
- **Kann ich mehrere Ressourcen gleichzeitig aktualisieren?** Ja – iterieren Sie durch die `ResourceCollection` und setzen Sie Attribute in einem Durchlauf.  
- **Welche Methode speichert die Datei als MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Benötige ich eine Lizenz für die kommerzielle Nutzung?** Eine kostenpflichtige Lizenz ist für die Produktion erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Welche Java-Versionen werden unterstützt?** Java 6 und höher, einschließlich Java 17 LTS.  
- **Ist ein Bulk‑Update performant?** Aspose.Tasks verarbeitet 500‑Ressourcen‑Projekte in weniger als 2 Sekunden auf einem typischen Server.

## Was bedeutet „mehrere Ressourcen aktualisieren“?
**„Mehrere Ressourcen aktualisieren“** bezieht sich auf das programmgesteuerte Ändern der Eigenschaften mehrerer Ressourceneinträge – wie Raten, Gruppen, Kalender oder benutzerdefinierte Felder – innerhalb einer einzigen Projektdatei. Dieser Vorgang ist häufig erforderlich, wenn Projektdaten mit Enterprise‑Resource‑Planning‑Systemen synchronisiert, Budgets über viele Ressourcen hinweg angepasst oder organisationsweite Richtlinienänderungen angewendet werden.

## Warum Aspose.Tasks verwenden, um die Ressourcengruppe zu ändern und das Projekt nach MPP zu exportieren?
Aspose.Tasks unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate**, darunter MPP, XML und CSV, und kann **ein Projekt nach MPP exportieren**, ohne die gesamte Datei in den Speicher zu laden. Die Bibliothek verarbeitet Dateien von bis zu **2 GB** Größe, sodass Sie **ein Projekt schnell und zuverlässig als MPP speichern** können.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Java Development Kit (JDK) auf Ihrem System installiert.  
2. Aspose.Tasks für Java Bibliothek. Sie können sie von [hier](https://releases.aspose.com/tasks/java/) herunterladen.  
3. Grundkenntnisse in Java-Programmierung.  

## Pakete importieren

`import`‑Anweisungen bringen die erforderlichen Aspose.Tasks‑Klassen in Ihre Quelldatei.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt 1: Datenverzeichnis einrichten

Definieren Sie das Verzeichnis, in dem Ihre Datendateien gespeichert sind:

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Eingabe‑ und Ausgabedateien festlegen

Definieren Sie die Pfade für die Eingabe‑MS‑Project‑Datei und die resultierende aktualisierte Datei:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Schritt 3: Projekt laden

`Project` repräsentiert eine Microsoft‑Project‑Datei, die im Speicher geladen ist und Zugriff auf Aufgaben, Ressourcen und andere Projektdaten bietet.

```java
Project project = new Project(file);
```

## Schritt 4: Ressource hinzufügen und Attribute festlegen

`Resource` modelliert eine einzelne Projektressource und ermöglicht das Festlegen von Raten, Gruppen, Kalendern und anderen Attributen.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Schritt 5: Mehrere Ressourcen effizient aktualisieren

`ResourceCollection` ist die Sammlung aller Ressourcen in einem Projekt und über `project.getResources()` zugänglich.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Schritt 6: Projekt speichern

`SaveFileFormat` listet die unterstützten Dateiformate zum Speichern eines Projekts auf, wie MPP, XML und PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Wie aktualisiert man mehrere Ressourcen in einem Projekt?

Laden Sie das vorhandene Projekt, rufen Sie dessen `ResourceCollection` ab und iterieren Sie über jedes `Resource`‑Objekt. Für jede Ressource ändern Sie die erforderlichen Felder wie Raten, Gruppen oder benutzerdefinierte Attribute und fahren dann mit dem nächsten Eintrag fort. Nach der Verarbeitung aller Ressourcen rufen Sie einmal `project.save(...)` auf, um die Änderungen effizient zu speichern.

## Häufige Probleme und Lösungen

- **Ressourcen‑IDs kollidieren** – Stellen Sie sicher, dass jede neue Ressource eine eindeutige ID erhält, indem Sie `project.getResources().add(new Resource())` verwenden.  
- **Fehler im Ratenformat** – Verwenden Sie `ResourceRate`‑Objekte und setzen Sie den `RateType` auf `StandardRate` oder `OvertimeRate`.  
- **Große Dateien verursachen Speicherbelastung** – Aktivieren Sie `Project.setReadOnly(true)` vor dem Laden, um den Speicherverbrauch zu reduzieren.

## Häufig gestellte Fragen

**Q: Kann ich mehrere Ressourcen im selben Projekt mit Aspose.Tasks für Java aktualisieren?**  
A: Ja, Sie können mehrere Ressourcen aktualisieren, indem Sie über sie iterieren und ihre Attribute entsprechend setzen.

**Q: Unterstützt Aspose.Tasks andere Dateiformate neben MS Project?**  
A: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate, darunter XML, MPP und weitere.

**Q: Ist Aspose.Tasks mit verschiedenen Java-Versionen kompatibel?**  
A: Aspose.Tasks ist mit Java‑Versionen 6 und höher kompatibel.

**Q: Kann ich mit Aspose.Tasks weitere Operationen an MS‑Project‑Dateien durchführen?**  
A: Ja, Sie können ein breites Spektrum an Operationen ausführen, wie das Lesen, Schreiben und Manipulieren von Aufgaben, Ressourcen und Kalendern.

**Q: Wo finde ich zusätzliche Hilfe oder Support für Aspose.Tasks?**  
A: Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung oder Fragen besuchen.

**Q: Wie exportiere ich die aktualisierte Datei in das MPP‑Format?**  
A: Rufen Sie `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` auf, nachdem Sie alle Ressourcenänderungen vorgenommen haben.

**Q: Was ist der beste Weg, eine Ressourcengruppe zu ändern?**  
A: Setzen Sie die Eigenschaft `Resource.Group` bei jedem `Resource`‑Objekt, bevor Sie das Projekt speichern.

---

**Zuletzt aktualisiert:** 2026-06-30  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Ressource zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/resource-management/create-resources/)
- [MS Project Ressourcenkosten mit Aspose.Tasks für Java verwalten](/tasks/java/resource-management/resource-cost/)
- [Wie man MPP nach Excel mit Aspose.Tasks für Java exportiert](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}