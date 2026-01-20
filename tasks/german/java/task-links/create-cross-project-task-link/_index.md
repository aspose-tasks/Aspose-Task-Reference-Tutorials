---
date: 2026-01-20
description: Erfahren Sie, wie Sie Projekte verknüpfen und Aufgaben projektübergreifend
  mit Aspose.Tasks für Java verknüpfen. Folgen Sie der Schritt‑für‑Schritt‑Anleitung,
  um projektübergreifende Aufgabenverknüpfungen zu erstellen.
linktitle: Create Cross-Project Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Wie man Projekte verknüpft: Erstellen eines projektübergreifenden Aufgabenlinks
  in Aspose.Tasks'
url: /de/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Projekte verknüpft: Erstellen eines projektübergreifenden Aufgabenlinks in Aspose.Tasks

## Wie man Projekte mit Aspose schnellleb für Java bietet Ihnen eine leistungsstarke API zum Erstellen projektübergreifender Aufgabenlinks, mit der Sie **Aufgaben über Projekte hinweg verknüpfen** können, und das mit nur wenigen Codezeilen. In diesem Tutorial lernen Sie die genauen Schritte, sehen die erforderlichen Code‑Snippets und verstehen, warum diese Technik die Zusammenarbeit im Team dramatisch verbessern  
- Ungef Ja – die API unterstützt MPP, XML und weitere Formate.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:

- Praktische Kenntnisse in der Java‑Programmierung.  
- Aspose.Tasks für Java installiert. Sie können es von der [Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/) herunterladen.  
- Grundlegendes Verständnis von Projektmanagement‑Konzepten wie Aufgabenabhängigkeiten und Zusammenfassungsaufgaben.

## Pakete importieren
Importieren Sie zunächst die Klassen, die Sie benötigen. Dadurch erhalten Sie Zugriff auf die Kernfunktionalität von Aspose.Tasks:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

## Schritt 1: Richten Sie Ihre Umgebung ein
Stellen Sie sicher, dass Java auf Ihrem Rechner installiert ist und die Aspose.Tasks‑JAR zu Ihrem Projekt‑Classpath hinzugefügt wurde. Dieser Schritt ist entscheidend, damit der Code ohne Fehler kompiliert.

## Schritt 2: Erstellen Sie eine Projektinstanz
Erzeugen Sie ein neues `Project`‑Objekt, das die Aufgaben und Links enthält:

```java
Project project = new Project();
```

## Schritt 3: Fügen Sie eine Zusammenfassungsaufgabe hinzu
Eine Zusammenfassungsaufgabe dient als Container für die Aufgaben, die Sie verknüpfen. Sie macht die Struktur beim späteren Betrachten des Projekts klarer:

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

## Schritt 4: Fügen Sie eine externe Aufgabe hinzu
Fügen Sie nun eine externe Aufgabe hinzu, die auf eine Aufgabe in einer anderen Projektdatei verweist. Dies ist die „Quell‑“Seite des projektübergreifenden Links:

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

## Schritt 5: Fügen Sie eine lokale Aufgabe hinzu
Erstellen Sie die lokale Aufgabe, die mit der externen verknüpft wird. Dies ist die „Ziel‑“Seite der Beziehung:

```java
Task t = summary.getChildren().add("Task");
```

## Schritt 6: Erstellen Sie den Aufgabenlink
Stellen Sie die Verknüpfung zwischen der externen Aufgabe und der lokalen Aufgabe her. Durch Setzen von `CrossProject` auf `true` wird Aspose.Tasks mitgeteilt, dass der Link über zwei verschiedene Projektdateien hinweg reicht:

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

## Schritt 7: Ergebnisse anzeigen
Geben Sie schließlich eine einfache Bestätigung aus, damit Sie wissen, dass der Vorgang ohne Ausnahmen abgeschlossen wurde:

```java
System.out.println("Process completed Successfully");
```

## Warum Aufgaben über Projekte hinweg verknüpfen?
Das Verknüpfen von Aufgaben über Projekte hinweg ermöglicht Ihnen:

- Abhängige Arbeitselemente ohne manuelle Aktualisierungen synchron zu halten.  
- Reduzierung von doppelter Arbeit, wenn dieselbe Aufgabe in mehreren Plänen vorkommt.  
- Bereitstellung einer einzigen Wahrheitsquelle für die Meilensteinverfolgung über Teams hinweg.  

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| Externe Aufgabe nicht gefunden | Überprüfen Sie, ob der Pfad `EXTERNAL_TASK_PROJECT` und `EXTERNAL_ID` korrekt sind. |
| Linktyp stimmt nicht überein | Stellen Sie sicher, dass `TaskLinkType` der gewünschten Abhängigkeit entspricht (z. B. Finish‑to‑Start). |
| Lizenz‑Ausnahme | Installieren Sie eine gültige Aspose.Tasks‑Lizenz, bevor Sie die Projektinstanz erstellen. |

## Häufig gestellte Fragen

**Q: Kann ich Aufgaben aus mehreren externen Projekten in derselben Zusammenfassungsaufgabe verknüpfen?**  
A: Ja, Sie können Aufgaben aus verschiedenen externen Projekten innerhalb derselben Zusammenfassungsaufgabe verknüpfen, indem Sie einen ähnlichen Vorgang befolgen.

**Q: Was passiert, wenn die externe Aufgabe im verknüpften Projekt geändert wird?**  
A: Änderungen an der externen Aufgabe werden in der verknüpften Aufgabe Ihres aktuellen Projekts widergespiegelt.

**Q: Ist es möglich, Links zwischen Aufgaben in verschiedenen Dateiformaten zu erstellen?**  
A: Ja, Aspose.Tasks für Java unterstützt das Verknüpfen von Aufgaben zwischen Projekten in verschiedenen Dateiformaten.

**Q: Kann ich Aufgaben wieder entkoppeln, sobald sie projektübergreifend verknüpft sind?**  
A: Ja, Sie können Aufgaben entkoppeln, indem Sie den Aufgabenlink mit den entsprechenden Aspose.Tasks‑Methoden entfernen.

**Q: Gibt es Beschränkungen für die Anzahl der Aufgaben, die projektübergreifend verknüpft werden können?**  
A: Die Anzahl der verknüpfbaren Aufgaben hängt von den Fähigkeiten und Beschränkungen Ihrer Aspose.Tasks‑Lizenz ab.

## Fazit
Sie wissen jetzt, **wie man Projekte verknüpft** und **Aufgaben über Projekte hinweg verknüpft** mit:** estet mit:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}