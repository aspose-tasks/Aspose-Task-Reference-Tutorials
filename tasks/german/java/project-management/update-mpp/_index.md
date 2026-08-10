---
date: 2026-06-25
description: Erfahren Sie, wie Sie Aufgaben hinzufügen und MPP-Dateien mit Aspose.Tasks
  für Java verwenden, einer Java-Projektmanagement-Bibliothek, die es Ihnen ermöglicht,
  Microsoft Project-Aufgabendateien zu erstellen und das Projekt als MPP zu speichern.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: So fügen Sie eine Aufgabe hinzu und aktualisieren die MPP-Datei in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: So fügen Sie eine Aufgabe hinzu und aktualisieren die MPP-Datei in Aspose.Tasks
url: /de/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Aufgabe hinzufügt und die MPP-Datei in Aspose.Tasks aktualisiert

## Einführung
In diesem Tutorial lernen Sie **wie man eine Aufgabe hinzufügt** zu einer bestehenden Microsoft Project (MPP)-Datei und anschließend den aktualisierten Zeitplan mit Aspose.Tasks für Java, einer führenden **java project management library**, speichert. Egal, ob Sie einen benutzerdefinierten Scheduler erstellen, Massen‑Updates automatisieren oder Projektdaten in ein größeres System integrieren – die nachfolgende Schritt‑für‑Schritt‑Anleitung zeigt genau, wie ein Projekt geladen, eine neue Aufgabe eingefügt, deren Termine gesetzt und das Ergebnis als neue MPP‑Datei gespeichert wird.

## Schnelle Antworten
- **Was bedeutet „how to add task“ in diesem Kontext?** Es bedeutet, programmgesteuert ein neues Arbeitselement in einer bestehenden MPP‑Datei zu erstellen.  
- **Welche Bibliothek führt die Operation aus?** Aspose.Tasks für Java, eine robuste java project management library.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das Ergebnis als MPP speichern?** Ja – verwenden Sie `project.save(..., SaveFileFormat.Mpp)`, um **project as mpp** zu **save project as mpp**.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher.

## Was bedeutet „how to add task“ in einer MPP‑Datei?
Eine Aufgabe hinzuzufügen bedeutet, ein neues Arbeitselement in die Projekt‑Hierarchie einzufügen, dessen Start‑/Enddaten zu definieren und die Änderung zurück in die MPP‑Datei zu schreiben. Aspose.Tasks abstrahiert die low‑level‑Dateiformat‑Details, sodass Sie sich auf die Geschäftslogik konzentrieren können, während Ressourcen‑Zuweisungen, Kalender und Abhängigkeitsberechnungen automatisch gehandhabt werden. Gleichzeitig werden zugehörige Zuweisungen aktualisiert und der Projekt‑Zeitplan neu berechnet, um Konsistenz über abhängige Aufgaben hinweg zu gewährleisten.

## Warum Aspose.Tasks für Java verwenden?
- **Vollständige Kompatibilität**: Unterstützt 100 % der Funktionen von Microsoft Project 2007‑2021 (über 150 Aufgabentypen und 200 Ressourcenfelder).  
- **Keine Abhängigkeiten**: Kein COM, Office oder native Bibliotheken nötig – reines Java‑API läuft überall dort, wo die JRE verfügbar ist.  
- **Umfangreicher Funktionsumfang**: Enthält Aufgaben‑Verknüpfungen, Ressourcen‑Zuweisung, benutzerdefinierte Felder und integrierte Berichte.  
- **Hohe Leistung**: Verarbeitet Projekte mit bis zu 10 000 Aufgaben bei weniger als 200 MB RAM, ideal für serverseitige Automatisierung.

## Voraussetzungen
1. **Java‑Entwicklungsumgebung** – JDK 8+ installiert und konfiguriert.  
2. **Aspose.Tasks für Java** – Download von der [download page](https://releases.aspose.com/tasks/java/).  
3. **Grundkenntnisse in Java** – Vertrautheit mit Klassen, Objekten und Datums‑Handling.  

## Pakete importieren
Zuerst importieren Sie die Klassen, die Sie benötigen. So erhalten Sie Zugriff auf Projekt‑Manipulation, Aufgabeneigenschaften und Datums‑Handling.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` repräsentiert eine Microsoft Project‑Datei, die im Speicher geladen ist. `SaveFileFormat` enumeriert die Formate, in die Sie speichern können, z. B. MPP oder PDF. `Task` modelliert ein einzelnes Arbeitselement innerhalb der Projekt‑Hierarchie. `Tsk` stellt Konstanten für Aufgabefelder bereit, die beim Setzen oder Abrufen von Werten verwendet werden. `Calendar` bietet Datums‑ und Zeit‑Hilfsfunktionen zur Definition von Zeitplänen.

## Schritt 1: Datenverzeichnis definieren
```java
String dataDir = "Your Data Directory";
```  
Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad, in dem sich Ihre Quell‑MPP‑Datei befindet.

## Schritt 2: Vorhandenes Projekt einlesen
Die Klasse `Project` ist das Kernobjekt von Aspose.Tasks, das eine Microsoft Project‑Datei im Speicher repräsentiert.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Der Konstruktor lädt **SampleMSP2010.mpp** und liefert Ihnen ein vollständig manipulierbares Objektmodell.

## Schritt 3: Neue Aufgabe erstellen (how to add task)
Die Klasse `Task` steht für ein einzelnes Arbeitselement innerhalb der Projekt‑Hierarchie.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Diese Zeile **creates task in mpp** durch Hinzufügen eines Kindes namens *Task1* zur Root‑Aufgabe.

## Schritt 4: Start‑ und Enddaten festlegen
Die Klasse `Calendar` liefert Datums‑ und Zeit‑Hilfsfunktionen; Monate sind nullbasiert (z. B. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Hier definieren wir den Zeitplan für die neu hinzugefügte Aufgabe. Passen Sie die Daten an Ihren Projekt‑Zeitplan an.

## Schritt 5: Projekt speichern (save project as mpp)
`SaveFileFormat.Mpp` weist Aspose.Tasks an, die Datei im nativen Microsoft Project‑Format zurückzuschreiben.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Das aktualisierte Projekt, das nun die neue Aufgabe enthält, wird als **AfterLinking.mpp** gespeichert.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Datei nicht gefunden** | Stellen Sie sicher, dass `dataDir` mit einem Pfad‑Trennzeichen (`/` oder `\\`) endet und der Dateiname korrekt ist. |
| **Falsche Daten** | Denken Sie daran, dass `Calendar`‑Monate nullbasiert sind; `Calendar.JULY` ist korrekt für Juli. |
| **Lizenz‑Ausnahme** | Installieren Sie eine gültige Aspose.Tasks‑Lizenz, bevor Sie irgendeine API aufrufen, um Wasserzeichen der Evaluation zu vermeiden. |

## Häufig gestellte Fragen
**Q: Wie füge ich mehrere Aufgaben gleichzeitig hinzu?**  
A: Durchlaufen Sie eine Sammlung von Aufgabennamen und wiederholen Sie den „Aufgabe erstellen“-Block innerhalb der Schleife.

**Q: Kann ich benutzerdefinierte Felder für die neue Aufgabe setzen?**  
A: Ja – verwenden Sie `task.set(Tsk.CUSTOM_FIELD_x, value)`, wobei *x* der Feldindex ist.

**Q: Ist es möglich, eine vorhandene Aufgabe als Vorlage zu kopieren?**  
A: Klonen Sie die Quellaufgabe (`Task cloned = sourceTask.clone();`) und fügen Sie sie dem gewünschten übergeordneten Element hinzu.

**Q: Was, wenn ich eine bestehende Aufgabe aktualisieren muss, anstatt eine neue hinzuzufügen?**  
A: Rufen Sie die Aufgabe per ID ab (`Task existing = project.getRootTask().getChildren().getById(id);`) und ändern Sie deren Eigenschaften.

**Q: Unterstützt Aspose.Tasks das Speichern in anderen Formaten wie PDF oder PNG?**  
A: Ja – verwenden Sie `project.save("output.pdf", SaveFileFormat.Pdf);` oder `SaveFileFormat.Png` für visuelle Darstellungen.

---

**Zuletzt aktualisiert:** 2026-06-25  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [How to Create Project – Set New Task Attributes with Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Create Task List Java – MS Project Baseline using Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}