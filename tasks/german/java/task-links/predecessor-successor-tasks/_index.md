---
date: 2026-09-20
description: Erfahren Sie, wie Sie Projektaufgabenabhängigkeiten mit Aspose.Tasks
  for Java verwalten. Dieser Leitfaden zeigt Ihnen, wie Sie predecessor links hinzufügen,
  task names ausgeben und task dependencies effizient festlegen.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Projektaufgabenabhängigkeiten mit Aspose.Tasks for Java verwalten
og_description: Erfahren Sie, wie Sie Projektaufgabenabhängigkeiten mit Aspose.Tasks
  for Java verwalten. Dieser Leitfaden zeigt Ihnen, wie Sie predecessor links hinzufügen,
  task names ausgeben und task dependencies effizient festlegen.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Projektaufgabenabhängigkeiten mit Aspose.Tasks for Java verwalten
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Projektaufgabenabhängigkeiten mit Aspose.Tasks for Java verwalten
url: /de/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektaufgabenabhängigkeiten verwalten mit Aspose.Tasks für Java

## Einleitung
Projektaufgabenabhängigkeiten sind das Rückgrat jedes realistischen Zeitplans und ermöglichen es Ihnen, zu modellieren, welche Arbeit abgeschlossen sein muss, bevor eine andere beginnen kann. In diesem Tutorial lernen Sie, wie Sie **project task dependencies** mit Aspose.Tasks für Java verwalten, einschließlich des Hinzufügens von Vorgänger‑Links, dem Ausgeben von Aufgabennamen und dem programmgesteuerten Festlegen von Aufgabendependencies.

## Schnelle Antworten
- **Was ist der erste Schritt?** Laden Sie Ihre MPP‑Datei in ein `Project`‑Objekt.  
- **Wie fügt man einen Vorgänger hinzu?** Erstellen Sie ein `TaskLink` und setzen Sie dessen `PredecessorTaskUid` und `SuccessorTaskUid`.  
- **Kann man alle Links auflisten?** Verwenden Sie `project.getTaskLinks()` und iterieren Sie über die Sammlung.  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz funktioniert für die Evaluierung; eine Voll‑Lizenz ist für die Produktion erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.

## Was sind Projektaufgabenabhängigkeiten?
Projektaufgabenabhängigkeiten definieren die logische Beziehung zwischen zwei Aufgaben, wie Finish‑to‑Start oder Start‑to‑Start, und bestimmen die Reihenfolge, in der Arbeiten ausgeführt werden müssen. Durch das Erstellen dieser Links respektiert der Zeitplan automatisch reale Einschränkungen, verhindert überlappende Aktivitäten und stellt sicher, dass nachgelagerte Aufgaben erst beginnen, wenn ihre Voraussetzungen erfüllt sind.

## Warum Aspose.Tasks für Java verwenden?
Aspose.Tasks für Java unterstützt mehr als dreißig Projektdateiformate, einschließlich der neuesten Microsoft‑Project‑Versionen, und kann Dateien bis zu zwei Gigabyte verarbeiten, ohne das gesamte Dokument in den Speicher zu laden. Diese Hochleistungskapazität ermöglicht es Ihnen, massive Zeitpläne zu manipulieren, Berichte zu erstellen und Massen‑Updates effizient durchzuführen, was es ideal für Unternehmens‑skalierte Projektmanagement‑Lösungen macht.

## Voraussetzungen
- Java-Entwicklungsumgebung: Java 8 oder neuer, auf Ihrem Rechner installiert.  
- Aspose.Tasks für Java Bibliothek: Laden Sie die Aspose.Tasks‑Bibliothek von der [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) herunter und installieren Sie sie.  
- Integrierte Entwicklungsumgebung (IDE): Eclipse, IntelliJ IDEA oder jede andere Java‑kompatible IDE Ihrer Wahl.

## Pakete importieren
Sie müssen die Kernklassen importieren, die die Projektmanipulation ermöglichen.

Die Klasse `Project` ist der Einstiegspunkt zum Laden und Speichern von Microsoft‑Project‑Dateien.  
Die Klasse `TaskLink` stellt eine Abhängigkeit zwischen zwei Aufgaben dar.

## Wie fügt man einen Vorgänger‑Link zwischen zwei Aufgaben hinzu?
Erstellen Sie eine `TaskLink`‑Instanz, weisen Sie die UID der Vorgängeraufgabe und die UID der Nachfolgeraufgabe zu, wählen Sie den passenden `TaskLinkType` wie Finish‑to‑Start und fügen Sie den Link dann zur Task‑Link‑Sammlung des Projekts hinzu. Sobald der Link hinzugefügt ist, spiegelt der Zeitplan die neue Abhängigkeitsbeziehung sofort wider.

### Schritt 1: Projektobjekt initialisieren
Erstellen Sie eine neue Instanz der Klasse `Project` und geben Sie den Pfad zu Ihrer Projektdatei an (z. B. `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### Schritt 2: Auf Task‑Links zugreifen
Rufen Sie alle Task‑Links aus dem Projekt mit der Methode `getTaskLinks()` ab.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 3: Durch Task‑Links iterieren
Verwenden Sie eine Schleife, um durch jeden Task‑Link in der Sammlung zu iterieren und Informationen über die Vorgänger‑ und Nachfolgeraufgaben auszugeben.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### Schritt 4: Neuen Vorgänger‑Link hinzufügen (optional)
Falls Sie eine neue Abhängigkeit erstellen müssen, instanziieren Sie ein `TaskLink`, setzen Sie dessen `PredecessorTaskUid`, `SuccessorTaskUid` und `LinkType` und fügen Sie es dann zur Link‑Sammlung des Projekts hinzu.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

Wiederholen Sie diese Schritte nach Bedarf für Ihre spezifischen Projektanforderungen.

## Häufige Probleme und Lösungen
- **Vorgänger fehlt nach dem Hinzufügen eines Links** – Stellen Sie sicher, dass Sie `project.updateTaskLinks()` aufrufen (oder speichern und neu laden), damit das interne Diagramm aktualisiert wird.  
- **Leistungsabfall bei großen Dateien** – Verwenden Sie `project.setReadOnly(true)` vor Massenoperationen, um den Speicheraufwand zu reduzieren.  
- **Falscher Linktyp** – Vergewissern Sie sich, dass Sie den korrekten `TaskLinkType`‑Enum‑Wert (z. B. `FinishToStart`) verwenden, der Ihrer Zeitplanlogik entspricht.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java in meinem bestehenden Java‑Projekt verwenden?**  
A: Ja, fügen Sie einfach die Aspose.Tasks‑JAR zu Ihrem Klassenpfad oder zu den Maven/Gradle‑Abhängigkeiten hinzu.

**Q: Ist Aspose.Tasks mit verschiedenen Projektdateiformaten kompatibel?**  
A: Ja, es unterstützt MPP, XML, CSV und mehr als 30 weitere Formate.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?**  
A: Erhalten Sie eine temporäre Lizenz von der [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Wo finde ich zusätzlichen Support für Aspose.Tasks?**  
A: Besuchen Sie das [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) für Community‑Support und Diskussionen.

**Q: Kann ich eine kostenlose Testversion von Aspose.Tasks für Java herunterladen?**  
A: Ja, laden Sie eine kostenlose Testversion von der [Aspose free trial page](https://releases.aspose.com/) herunter.

---

**Zuletzt aktualisiert:** 2026-09-20  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Projektmanagement‑Task‑Abhängigkeiten in Aspose.Tasks erstellen](/tasks/java/task-links/create-task-link/)
- [Projektstartdatum festlegen und Eltern‑ und Kind‑Aufgaben in Aspose.Tasks verwalten](/tasks/java/task-properties/parent-child-tasks/)
- [Task‑Prioritäten mit Aspose.Tasks für Java lesen und festlegen](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}