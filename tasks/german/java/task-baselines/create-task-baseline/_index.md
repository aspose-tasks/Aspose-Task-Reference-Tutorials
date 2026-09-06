---
date: 2026-08-29
description: Erfahren Sie, wie Sie in Java task zu project hinzufügen, eine task list
  erstellen und einen baseline festlegen, ohne Microsoft Project zu verwenden, mit
  Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Erstellen einer Task Baseline in Aspose.Tasks
og_description: Erfahren Sie, wie Sie in Java task zu project hinzufügen und einen
  baseline mit Aspose.Tasks festlegen. Dieser Leitfaden zeigt Schritt‑für‑Schritt‑Code,
  ohne Microsoft Project zu benötigen.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Wie man in Java task zu project hinzufügt und einen baseline festlegt
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Wie man in Java task zu project hinzufügt und einen baseline festlegt
url: /de/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Aufgabe zu einem Projekt in Java hinzufügt und einen Basisplan festlegt

## Einführung
In diesem Tutorial werden Sie **add task to project** programmgesteuert hinzufügen, einen Microsoft Project Aufgaben‑Baseline erzeugen und die Datei speichern – alles, ohne Microsoft Project zu öffnen. Aspose.Tasks für Java bietet Ihnen eine reine Java‑API, die auf jeder Plattform funktioniert und sich ideal für automatisierte Build‑Pipelines, Reporting‑Dienste oder jede serverseitige Lösung eignet, die .mpp‑Dateien manipulieren muss.

## Schnelle Antworten
- **What does Aspose.Tasks do?** Es stellt eine Java‑API zum Erstellen, Lesen und Bearbeiten von Microsoft Project‑Dateien bereit, ohne dass Microsoft Project erforderlich ist.  
- **Do I need Microsoft Project installed?** Nein, die Bibliothek arbeitet vollständig unabhängig.  
- **Which Java version is required?** JDK 8 oder höher.  
- **Can I set a baseline for a single task?** Ja – rufen Sie `setBaseline` für eine Liste auf, die nur die gewünschten Aufgaben enthält.  
- **Is a license needed for production?** Ja, eine kommerzielle Lizenz entfernt Evaluationsbeschränkungen und schaltet alle Funktionen frei.

## Was ist ein Aufgaben‑Baseline?
Ein Aufgaben‑Baseline erfasst das ursprünglich geplante Start‑ und Enddatum sowie den Arbeitsaufwand einer Aufgabe zum Zeitpunkt der ersten Speicherung des Zeitplans. Dieser Schnappschuss dient als Referenzpunkt, sodass Projektmanager den tatsächlichen Fortschritt und die Kosten mit dem ursprünglichen Plan vergleichen und Abweichungen für Leistungsanalysen berechnen können.

## Warum Aspose.Tasks verwenden, um eine Aufgabe zu einem Projekt in Java hinzuzufügen?
Sie können Aufgaben erstellen, ändern und einen Basisplan festlegen, ohne eine Desktop‑Installation, was vollständig automatisierte Workflows ermöglicht. Aspose.Tasks unterstützt **50+ Eingabe‑ und Ausgabeformate** und kann Projekte mit **Hunderten von Aufgaben** verarbeiten, während der Speicherverbrauch unter 200 MB bleibt – ideal für Cloud‑Dienste und CI/CD‑Pipelines.

## Voraussetzungen
1. **Java Development Kit (JDK)** – installieren Sie JDK 8 oder neuer.  
2. **Aspose.Tasks for Java** – laden Sie die Bibliothek über den [download link](https://releases.aspose.com/tasks/java/) herunter.  

## Pakete importieren
Um mit Aspose.Tasks in Ihrem Java‑Projekt zu arbeiten, importieren Sie die erforderlichen Pakete:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Schritt 1: ein Projektobjekt erstellen
Die Klasse `Project` ist Aspose.Tasks' Top‑Level‑Objekt, das eine Microsoft Project‑Datei im Speicher repräsentiert. Durch die Instanziierung erhalten Sie ein leeres Projekt, das Sie mit Aufgaben, Ressourcen und Kalendern füllen können.

```java
Project project = new Project();
```
Hier instanziieren wir ein neues `Project`‑Objekt – dies stellt die MS‑Project‑Datei dar, die unsere Aufgabenliste enthält.

## Schritt 2: eine Aufgabe zum Projekt hinzufügen
Die Klasse `Task` repräsentiert ein einzelnes Arbeitselement im Projektzeitplan. Jeder `Task` kann eigene Dauer, Startdatum und Ressourcenzuweisungen besitzen.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Mit `getRootTask()` greifen wir auf die Wurzel der Projekt‑Hierarchie zu und **add task to Microsoft Project**. Der String `"Task"` ist der Aufgabenname; Sie können ihn durch jede gewünschte Beschreibung ersetzen.

## Schritt 3: Basisplan für bestimmte Aufgaben festlegen
`BaselineType` ist eine Aufzählung, die definiert, welchen Basisplan‑Slot (Baseline, Baseline1 … Baseline10) Sie schreiben möchten. Durch Übergabe einer Aufgabenliste können Sie nur die ausgewählten Elemente baseline‑setzen.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Um **set baseline without MS Project** zu erreichen, erstellen Sie eine Liste der Aufgaben, die Sie baseline‑setzen wollen (hier `myList`) und übergeben Sie sie an `setBaseline`. Befüllen Sie `myList` mit den hinzugefügten Aufgaben, falls Sie nur einen selektiven Basisplan benötigen.

## Schritt 4: Basisplan für das gesamte Projekt festlegen
`setBaseline` schreibt die ausgewählten Basisplan‑Werte in jede Aufgabe des Projekts.  
Wenn Sie das gesamte Projekt in einem Aufruf baseline‑setzen möchten, rufen Sie einfach `setBaseline` mit dem gewünschten `BaselineType` auf.

```java
project.setBaseline(BaselineType.Baseline);
```
Dieser Aufruf schreibt die gewählten Basisplan‑Werte für **every task** im Projekt, wodurch ein vollständiger Schnappschuss des ursprünglichen Zeitplans entsteht.

## Wie man mit Aspose.Tasks eine Aufgabe zu Microsoft Project hinzufügt
`add()` erstellt eine neue Unteraufgabe unter der angegebenen übergeordneten Aufgabe und gibt das neu erstellte `Task`‑Objekt zurück.  
Sie fügen eine Aufgabe hinzu, indem Sie `add()` an einem übergeordneten `Task`‑Objekt (in der Regel die Wurzelaufgabe) aufrufen. Die Methode liefert eine neue `Task`‑Instanz, die Sie weiter konfigurieren können – Dauer, Startdatum, Ressourcen oder benutzerdefinierte Felder – bevor Sie die Projektdatei speichern.

## Wie man einen Basisplan ohne MS Project festlegt
Aspose.Tasks ermöglicht die Erstellung von Baselines vollständig über Code. Wählen Sie einen `BaselineType` (z. B. `BaselineType.Baseline`) und rufen Sie `setBaseline` auf. Sie können dies mit `Baseline1`‑`Baseline10` wiederholen, um mehrere Revisions‑Baselines zu behalten, alles ohne Microsoft Project zu öffnen.

## Häufige Probleme und Lösungen
- **Baseline not appearing:** Stellen Sie sicher, dass Sie `project.save("output.mpp")` nach dem Setzen des Baselines aufrufen (Speicherschritt hier aus Gründen der Kürze weggelassen).  
- **Task list appears empty:** Vergewissern Sie sich, dass Sie Aufgaben dem richtigen übergeordneten Element (`getRootTask()` oder einem Unter‑Task) hinzufügen.  
- **Version mismatch errors:** Verwenden Sie die neueste Aspose.Tasks‑JAR, um die Kompatibilität mit neueren .mpp‑Formaten zu gewährleisten.

## Häufig gestellte Fragen

**Q: Can I use Aspose.Tasks for Java without Microsoft Project installed?**  
A: Ja, Aspose.Tasks arbeitet unabhängig und erfordert Microsoft Project nicht auf dem Host‑Rechner.

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project?**  
A: Absolut. Die Bibliothek unterstützt Projektdateien von 2007 bis zu den neuesten 2024‑Versionen.

**Q: Can I manipulate project resources using Aspose.Tasks for Java?**  
A: Ja, Sie können Ressourcen programmgesteuert hinzufügen, aktualisieren und löschen, genau wie Aufgaben.

**Q: Does Aspose.Tasks for Java support setting task dependencies?**  
A: Ja, Sie können Vorgänger‑Nachfolger‑Beziehungen über die Klasse `TaskLink` definieren.

**Q: Is technical support available for Aspose.Tasks for Java?**  
A: Ja, Sie erhalten Hilfe über das [support forum](https://forum.aspose.com/c/tasks/15), wo Aspose‑Mitarbeiter und die Community Anfragen beantworten.

## Fazit
Durch Befolgen dieser Schritte haben Sie gelernt, wie man **add task to project** in Java durchführt, eine Aufgabenliste erstellt und **set baseline without MS Project** mit Aspose.Tasks festlegt. Dieser Ansatz rationalisiert die Projekt‑Automatisierung, eliminiert die Notwendigkeit von Desktop‑Project‑Installationen und gibt Ihnen die volle programmgesteuerte Kontrolle über jeden Aspekt Ihres Zeitplans.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Verwandte Tutorials

- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [How to Set Baseline Duration in Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Create Tasks Aspose Java – Task Properties](/tasks/java/task-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}