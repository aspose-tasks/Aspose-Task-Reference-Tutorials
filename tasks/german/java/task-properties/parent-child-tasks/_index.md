---
date: 2026-02-23
description: Erfahren Sie, wie Sie das Projektstartdatum festlegen, die Aufgabendauer
  einstellen und das Projekt als MPP mit Aspose.Tasks für Java speichern. Verwalten
  Sie Eltern‑ und Unteraufgaben effizient.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt‑Startdatum festlegen und übergeordnete sowie untergeordnete Aufgaben
  in Aspose.Tasks verwalten
url: /de/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektstartdatum festlegen und Eltern‑ und Kindaufgaben in Aspose.Tasks verwalten

## Einführung
Eine effektive Aufgabenorganisation ist das Rückgrat eines erfolgreichen Projektmanagements, und **das Festlegen des Projektstartdatums** ist der erste Schritt zu einem gut strukturierten Zeitplan. In diesem Tutorial sehen Sie, wie Sie **das Projektstartdatum festlegen**, Aufgabendauern konfigurieren und Eltern‑Kind‑Beziehungen mit Aspose.Tasks für Java verwalten. Am Ende sind Sie bereit, **das Projekt als MPP zu speichern**, den Fertigstellungsgrad von Aufgaben zu aktualisieren und Aufgabeneigenschaften anzupassen, um jede reale Situation abzudecken.

## Schnellantworten
- **Wie lege ich das Projektstartdatum fest?** Verwenden Sie `proj.set(Prj.START_DATE, startDate);` nach der Initialisierung des `Project`‑Objekts.  
- **Kann ich Kindaufgaben unter einer Elternaufgabe hinzufügen?** Ja – rufen Sie `parentTask.getChildren().add("Child Task")` auf.  
- **In welchem Format speichert Aspose.Tasks die Datei?** Verwenden Sie `SaveFileFormat.Mpp`, um **das Projekt als MPP zu speichern**.  
- **Wie aktualisiere ich den Aufgabenerfüllungsgrad?** Setzen Sie `Tsk.PERCENT_COMPLETE` am Aufgabenobjekt.  
- **Wo kann ich eine temporäre Lizenz erhalten?** Besuchen Sie die temporäre Lizenz‑Seite, die in den FAQs verlinkt ist.

## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der Java‑Programmierung.  
- Aspose.Tasks für Java‑Bibliothek installiert. Sie können sie [hier](https://releases.aspose.com/tasks/java/) herunterladen.  
- Eine Java‑Integrated Development Environment (IDE) ist auf Ihrem System eingerichtet.

## Pakete importieren
Um zu beginnen, importieren Sie die notwendigen Pakete in Ihr Java‑Projekt. Diese Pakete ermöglichen eine nahtlose Integration der Aspose.Tasks‑Funktionen für Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Schritt 1: Projektstartdatum festlegen
Legen Sie das Startdatum des Projekts und weitere relevante Parameter fest.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Schritt 2: Elternaufgabe hinzufügen (Aufgabe 1)
Erstellen Sie eine Elternaufgabe mit dem Namen „Task 1“ und konfigurieren Sie deren Eigenschaften, einschließlich **Aufgabendauer festlegen**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Schritt 3: Elternaufgabe hinzufügen (Aufgabe 2) mit Kindaufgaben
Fügen Sie nun eine weitere Elternaufgabe mit dem Namen „Task 2“ hinzu und integrieren Sie Kindaufgaben (Task 3 und Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Schritt 4: Kindaufgaben konfigurieren
Geben Sie Startdaten, Dauern und Einschränkungen für Task 3 und Task 4 an.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Schritt 5: Aufgabenerfüllungsgrad aktualisieren
Passen Sie den Fertigstellungsgrad für Task 3 und Task 4 an – so **aktualisieren Sie die Aufgabenerfüllung**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Schritt 6: Projekt speichern
Abschließend **das Projekt als MPP speichern** mit den vorgenommenen Änderungen.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie Eltern‑ und Kindaufgaben effektiv mit Aspose.Tasks für Java verwalten. Experimentieren Sie mit verschiedenen Konfigurationen, um die Anforderungen Ihres Projekts zu erfüllen.

## Warum Aufgabeneigenschaften anpassen?
Das Anpassen von Aufgabeneigenschaften wie Startdaten, Dauern, Einschränkungen und Fertigstellungsgraden gibt Ihnen eine feinkörnige Kontrolle über das Verhalten des Zeitplans. Egal, ob Sie Aufgaben an die Verfügbarkeit von Ressourcen anpassen oder Geschäftsregeln durchsetzen müssen – Aspose.Tasks ermöglicht es Ihnen, **Aufgabeneigenschaften programmgesteuert anzupassen**.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Startdatum wird nicht übernommen** | Stellen Sie sicher, dass Sie `proj.set(Prj.START_DATE, …)` **nach** dem Erstellen des `Project`‑Objekts und **vor** dem Hinzufügen von Aufgaben aufrufen. |
| **Kindaufgaben erben falsche Einschränkungen** | Setzen Sie für jedes Kind explizit `ConstraintType` und `ConstraintDate`, wie in Schritt 4 gezeigt. |
| **Gespeicherte Datei lässt sich nicht in MS Project öffnen** | Vergewissern Sie sich, dass Sie die neueste Aspose.Tasks‑Version verwenden und mit `SaveFileFormat.Mpp` speichern. |
| **Prozentsatz wird in der UI nicht angezeigt** | Nachdem Sie `Tsk.PERCENT_COMPLETE` gesetzt haben, rufen Sie `proj.calculateTaskSchedule()` auf, falls Sie neu berechnete Daten benötigen. |

## FAQs
### Ist Aspose.Tasks für Java mit verschiedenen Projektdateiformaten kompatibel?
Ja, Aspose.Tasks für Java unterstützt verschiedene Projektdateiformate, darunter MPP und XML.

### Kann ich Aufgabeneigenschaften über das in diesem Tutorial behandelte Maß hinaus anpassen?
Absolut! Aspose.Tasks für Java bietet umfangreiche Anpassungsmöglichkeiten für Aufgabeneigenschaften.

### Gibt es ein Community‑Forum für Aspose.Tasks, in dem ich Unterstützung finden kann?
Ja, Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Support besuchen.

### Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Wo finde ich umfassende Dokumentation für Aspose.Tasks für Java?
Die Dokumentation ist [hier](https://reference.aspose.com/tasks/java/) verfügbar.

**Zusätzliche Fragen & Antworten**

**F: Wie erhalte ich programmgesteuert eine temporäre Lizenz?**  
A: Laden Sie die temporäre Lizenzdatei mit `License license = new License(); license.setLicense("Aspose.Tasks.lic");` .

**F: Kann ich die Standard‑Einheit für Aufgabendauern ändern?**  
A: Ja – passen Sie das Argument `TimeUnitType` in `proj.getDuration(value, TimeUnitType.YourChoice)` an.

**F: Welche Version von Aspose.Tasks ist erforderlich, um `SaveFileFormat.Mpp` zu verwenden?**  
A: Alle aktuellen Versionen (2022‑2026) unterstützen das Speichern als MPP; prüfen Sie die Release‑Notes auf eventuelle Breaking Changes.

---

**Zuletzt aktualisiert:** 2026-02-23  
**Getestet mit:** Aspose.Tasks für Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}