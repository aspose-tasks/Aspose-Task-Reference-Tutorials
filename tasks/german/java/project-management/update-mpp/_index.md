---
date: 2025-12-28
description: Erfahren Sie, wie Sie Aufgaben hinzufügen und MPP‑Dateien mit Aspose.Tasks
  für Java, einer Java‑Projektmanagement‑Bibliothek, aktualisieren. Folgen Sie unserer
  Schritt‑für‑Schritt‑Anleitung, um Aufgaben in MPP zu erstellen und das Projekt als
  MPP zu speichern.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Aufgaben hinzufügt und die MPP-Datei in Aspose.Tasks aktualisiert
url: /de/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Aufgabe hinzufügt und die MPP‑Datei in Aspose.Tasks aktualisiert

## Einführung
In diesem Tutorial zeigen wir Ihnen **wie man eine Aufgabe hinzufügt** und eine MPP‑Datei mit Aspose.Tasks für Java, einer führenden **java project management library**, aktualisiert. Egal, ob Sie einen eigenen Scheduler entwickeln oder vorhandene Projektpläne programmgesteuert ändern müssen – diese Anleitung führt Sie Schritt für Schritt vom Laden der Datei bis zum Speichern der Änderungen als neue MPP‑Datei.

## Schnelle Antworten
- **Was bedeutet „how to add task“ in diesem Kontext?** Es bezieht sich auf das programmgesteuerte Erstellen einer neuen Aufgabe in einer bestehenden Microsoft Project (MPP)‑Datei.  
- **Welche Bibliothek führt die Operation aus?** Aspose.Tasks für Java, eine robuste java project management library.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das Ergebnis als MPP speichern?** Ja – verwenden Sie `project.save(..., SaveFileFormat.Mpp)`, um **save project as mpp** auszuführen.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher.

## Was bedeutet „how to add task“ in einer MPP‑Datei?
Eine Aufgabe hinzuzufügen bedeutet, ein neues Arbeitselement in die Projekt‑Hierarchie einzufügen, dessen Start‑/Enddaten festzulegen und die Änderung zurück in die MPP‑Datei zu schreiben. Aspose.Tasks abstrahiert die low‑level Dateiformat‑Details, sodass Sie sich auf die Geschäftslogik konzentrieren können.

## Warum Aspose.Tasks für Java verwenden?
- **Vollständige Kompatibilität** mit Microsoft Project 2007‑2021‑Dateien.  
- **Kein COM‑ oder Office‑Installationsbedarf** – reine Java‑API.  
- **Umfangreicher Funktionsumfang**: Aufgabenverknüpfungen, Ressourcenzuweisungen, benutzerdefinierte Felder und mehr.  
- **Hohe Performance** bei großen Projektdaten, ideal für serverseitige Automatisierung.

## Voraussetzungen
1. **Java‑Entwicklungsumgebung** – JDK 8+ installiert und konfiguriert.  
2. **Aspose.Tasks für Java** – Download von der [download page](https://releases.aspose.com/tasks/java/).  
3. **Grundkenntnisse in Java** – Vertrautheit mit Klassen, Objekten und Datumsverarbeitung.  

## Pakete importieren
Zuerst importieren Sie die Klassen, die Sie benötigen. So erhalten Sie Zugriff auf Projektmanipulation, Aufgabeneigenschaften und Datumsverarbeitung.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Schritt 1: Datenverzeichnis definieren
```java
String dataDir = "Your Data Directory";
```
Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad, in dem sich Ihre Quell‑MPP‑Datei befindet.

## Schritt 2: Vorhandenes Projekt lesen
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
Der `Project`‑Konstruktor lädt **SampleMSP2010.mpp** und stellt Ihnen ein manipulierbares Objektmodell zur Verfügung.

## Schritt 3: Neue Aufgabe erstellen (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Diese Zeile **creates task in mpp** durch Hinzufügen eines Child‑Elements namens *Task1* zur Root‑Aufgabe.

## Schritt 4: Start‑ und Enddaten festlegen
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Hier definieren Sie den Zeitplan für die neu hinzugefügte Aufgabe. Passen Sie die Daten an Ihren Projektzeitplan an.

## Schritt 5: Projekt speichern (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Das aktualisierte Projekt, das nun die neue Aufgabe enthält, wird als **AfterLinking.mpp** gespeichert.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Datei nicht gefunden** | Stellen Sie sicher, dass `dataDir` mit einem Pfadtrenner (`/` oder `\\`) endet und der Dateiname korrekt ist. |
| **Falsche Daten** | Denken Sie daran, dass `Calendar`‑Monate nullbasiert sind; `Calendar.JULY` steht für Juli. |
| **Lizenz‑Ausnahme** | Installieren Sie eine gültige Aspose.Tasks‑Lizenz, bevor Sie irgendeine API aufrufen, um Wasserzeichen im Evaluierungsmodus zu vermeiden. |

## FAQ's
### Q: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet robuste Funktionen, um komplexe Projektstrukturen effizient zu handhaben.  
### Q: Gibt es eine kostenlose Testversion von Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion von der [website](https://releases.aspose.com/) herunterladen.  
### Q: Unterstützt Aspose.Tasks für Java verschiedene Versionen von Microsoft Project‑Dateien?
A: Absolut, Aspose.Tasks für Java unterstützt diverse Versionen von Microsoft Project‑Dateien, einschließlich MPP, MPT und XML‑Formate.  
### Q: Kann ich temporäre Lizenzen für Aspose.Tasks für Java erhalten?
A: Ja, temporäre Lizenzen stehen für Testzwecke zur Verfügung. Sie erhalten sie auf der [temporary license page](https://purchase.aspose.com/temporary-license/).  
### Q: Wo kann ich Hilfe oder Support zu Aspose.Tasks für Java finden?
A: Besuchen Sie das [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) für Unterstützung oder Fragen.

## Häufig gestellte Fragen
**Q: Wie füge ich mehrere Aufgaben gleichzeitig hinzu?**  
A: Durchlaufen Sie eine Sammlung von Aufgabennamen und wiederholen Sie den „create task“-Block innerhalb der Schleife.

**Q: Kann ich benutzerdefinierte Felder für die neue Aufgabe setzen?**  
A: Ja – verwenden Sie `task.set(Tsk.CUSTOM_FIELD_x, value)`, wobei *x* der Feldindex ist.

**Q: Ist es möglich, eine vorhandene Aufgabe als Vorlage zu kopieren?**  
A: Klonen Sie die Quellaufgabe (`Task cloned = sourceTask.clone();`) und fügen Sie sie dem gewünschten übergeordneten Element hinzu.

**Q: Was, wenn ich eine bestehende Aufgabe aktualisieren statt eine neue hinzuzufügen?**  
A: Rufen Sie die Aufgabe per ID ab (`Task existing = project.getRootTask().getChildren().getById(id);`) und ändern Sie deren Eigenschaften.

**Q: Unterstützt Aspose.Tasks das Speichern in anderen Formaten wie PDF oder PNG?**  
A: Ja – verwenden Sie `project.save("output.pdf", SaveFileFormat.Pdf);` oder `SaveFileFormat.Png` für visuelle Darstellungen.

---

**Zuletzt aktualisiert:** 2025-12-28  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}