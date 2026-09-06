---
date: 2026-08-29
description: Erfahren Sie, wie Sie Linktypen festlegen und Aufgabenabhängigkeiten
  mit Aspose.Tasks für Java in einer Schritt‑für‑Schritt‑Anleitung verwalten.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Wie man Linktypen in Aspose.Tasks für Java festlegt
og_description: Erfahren Sie, wie Sie Linktypen festlegen und Aufgabenabhängigkeiten
  mit Aspose.Tasks für Java verwalten. Schritt‑für‑Schritt‑Leitfaden für Entwickler.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Wie man Linktypen in Aspose.Tasks für Java festlegt
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Wie man Linktypen in Aspose.Tasks für Java festlegt
url: /de/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Linktypen in Aspose.Tasks für Java festlegt

## Einführung
Wenn Sie sich fragen, **wie man einen Link** zwischen Aufgaben setzt, während Sie *Aufgabenabhängigkeiten verwalten* in einem Projekt, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch das Erstellen eines neuen Projekts, das Hinzufügen von Aufgaben und das Definieren des Linktyps (Start‑zu‑Start, Ende‑zu‑Start usw.) mit Aspose.Tasks für Java. Am Ende fühlen Sie sich sicher im Anpassen von Aufgabenbeziehungen, um reale Terminplanungsanforderungen zu erfüllen, und Sie sehen, wie die API groß angelegte Pläne mit bis zu 10.000 Aufgaben verarbeitet.

## Schnelle Antworten
- **Welche Klasse repräsentiert eine Abhängigkeit?** `TaskLink` ist das Kernobjekt, das einen Link zwischen zwei Aufgaben modelliert.  
- **Welches Enum definiert den Beziehungstyp?** `TaskLinkType` (z. B. `StartToStart`, `FinishToStart`).  
- **Kann ich vorhandene Linktypen auslesen?** Ja – iterieren Sie über `Project.getTaskLinks()` und rufen Sie `getLinkType()` auf.  
- **Benötige ich eine Lizenz für diesen Code?** Eine temporäre Lizenz reicht für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Ist das mit Java 8+ kompatibel?** Absolut – Aspose.Tasks unterstützt Java 8 bis Java 21 und deckt damit 13 Hauptversionen ab.

## Was ist ein Aufgabenlink?
Ein **Aufgabenlink** modelliert eine Abhängigkeit zwischen zwei Aufgaben in einem Projektzeitplan.  
Sie können ein `TaskLink` erstellen, ändern oder löschen, um Vorgänger‑Nachfolger‑Beziehungen widerzuspiegeln, wodurch der Scheduler Start‑ und Enddaten automatisch berechnen kann.

## Warum Aspose.Tasks‑Linktypen verwenden?
Aspose.Tasks unterstützt **30+ Eingabe‑ und Ausgabeformate** und kann Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Diese quantifizierte Fähigkeit sorgt für schnelle Leistung selbst bei Unternehmens‑Skalen‑Plänen, und die Bibliothek bewahrt alle Microsoft‑Project‑Funktionen wie benutzerdefinierte Felder und Ressourcenzuweisungen.

## Voraussetzungen
- **Java‑Entwicklungsumgebung** – JDK 8 oder neuer installiert und konfiguriert.  
- **Aspose.Tasks‑Bibliothek** – Laden Sie das neueste JAR von dem [download link](https://releases.aspose.com/tasks/java/).  
- **Dokumentenverzeichnis** – Erstellen Sie einen Ordner auf Ihrem Rechner, in dem Sie die Beispiel‑Projektdateien ablegen.

## Pakete importieren
Wir beginnen mit dem Import der wesentlichen Aspose.Tasks‑Klassen. Dies bereitet die IDE darauf vor, die API‑Aufrufe zu erkennen, die wir später verwenden werden.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Wie man Linktypen in Aspose.Tasks für Java festlegt?
Laden Sie eine frische `Project`‑Instanz, fügen Sie zwei Aufgaben hinzu und erstellen Sie dann ein `TaskLink` mit dem gewünschten `TaskLinkType`. Dieses zweistufige Muster ermöglicht es Ihnen, jeden der vier Standard‑Abhängigkeitstypen in einem einzigen Aufruf zu definieren. `Project` repräsentiert die gesamte Projektdatei und ihren Zeitplan. `Task` ist ein einzelnes Arbeitselement innerhalb des Projekts. `TaskLink` verbindet eine Vorgänger‑Aufgabe mit einer Nachfolger‑Aufgabe. `TaskLinkType` ist ein Aufzählungstyp, der die Beziehung (Start‑zu‑Start, Ende‑zu‑Start usw.) spezifiziert.

### Schritt 1: Festlegen eines Linktyps
`TaskLink` stellt eine Abhängigkeit zwischen zwei Aufgaben dar, während `TaskLinkType` die möglichen Beziehungstypen wie `StartToStart` aufzählt. In diesem Schritt erstellen wir ein frisches Projekt, fügen zwei Aufgaben hinzu und verknüpfen sie mit der **Start‑zu‑Start**‑Beziehung.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Profi‑Tipp:** Sie können `StartToStart` durch `FinishToStart`, `StartToFinish` oder `FinishToFinish` ersetzen, je nach der Abhängigkeit, die Sie **Aufgabenabhängigkeiten verwalten** müssen.

### Schritt 2: Abrufen eines Linktyps
`Project.getTaskLinks()` gibt eine Sammlung aller `TaskLink`‑Objekte im Zeitplan zurück. Durch Iteration dieser Sammlung können Sie den `TaskLinkType` jedes Links auslesen und prüfen, ob die korrekte Beziehung gespeichert wurde.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

Die Konsole gibt Werte wie `StartToStart`, `FinishToStart` usw. aus und bestätigt damit den zuvor gesetzten Linktyp.

## Häufige Probleme & Lösungen
- **NullPointerException beim Hinzufügen von Links** – Stellen Sie sicher, dass sowohl Vorgänger‑ als auch Nachfolger‑Aufgaben dem Projekt hinzugefügt wurden, bevor Sie ein `TaskLink` erstellen.  
- **Falscher Linktyp nach dem Speichern** – Rufen Sie immer `project.save("output.mpp")` (oder ein anderes unterstütztes Format) auf, nachdem Sie den Linktyp gesetzt haben, um Änderungen zu persistieren.  
- **Lizenz nicht gefunden** – Platzieren Sie Ihre Aspose.Tasks‑Lizenzdatei im Klassenpfad des Projekts und laden Sie sie mit `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Häufig gestellte Fragen

**F: Ist Aspose.Tasks mit verschiedenen Java‑Umgebungen kompatibel?**  
A: Ja, Aspose.Tasks integriert sich in Standard‑Java SE, Java EE und Android‑Entwicklungskits ohne zusätzliche Abhängigkeiten.

**F: Kann ich Linktypen basierend auf den Anforderungen meines Projekts anpassen?**  
A: Absolut. Das `TaskLinkType`‑Enum bietet vier Standardtypen, und Sie können sie mit Lag‑Werten kombinieren, um komplexe Zeitpläne zu modellieren.

**F: Wo finde ich die ausführliche Dokumentation für Aspose.Tasks für Java?**  
A: Siehe die [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) für detaillierte Anleitungen, API‑Referenz und Code‑Beispiele.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?**  
A: Besuchen Sie die [temporary license page](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz für Testzwecke zu erhalten.

**F: Wo kann ich Unterstützung für Aspose.Tasks‑bezogene Anfragen erhalten?**  
A: Treten Sie der Aspose.Tasks‑Community im [support forum](https://forum.aspose.com/c/tasks/15) bei für Hilfe und Diskussionen.

**F: Kann ich einen Linktyp ändern, nachdem das Projekt gespeichert wurde?**  
A: Ja. Laden Sie das Projekt, holen Sie das `TaskLink`, rufen Sie `setLinkType()` mit dem neuen Enum‑Wert auf und speichern Sie das Projekt erneut.

**F: Unterstützt Aspose.Tasks das Lesen von Microsoft Project (MPP)-Dateien?**  
A: Ja. Verwenden Sie `new Project("file.mpp")`, um MPP‑Dateien zu laden und deren Aufgabenlinks wie im obigen XML‑Beispiel zu bearbeiten.

---

**Zuletzt aktualisiert:** 2026-08-29  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Cross‑Projekt‑Aufgabenlink in Aspose.Tasks erstellen](/tasks/java/task-links/create-cross-project-task-link/)
- [Projektstartdatum festlegen und Eltern‑ und Kindaufgaben in Aspose.Tasks verwalten](/tasks/java/task-properties/parent-child-tasks/)
- [MPP‑Datei in Java laden – Projekteigenschaften mit Aspose.Tasks verwalten](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}