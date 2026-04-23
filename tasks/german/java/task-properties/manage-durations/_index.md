---
date: 2026-02-20
description: Erkunden Sie, wie Sie Aufgaben zu einem Projekt hinzufügen und die Dauer
  mit Aspose.Tasks für Java verwalten. Erfahren Sie, wie Sie die Dauer festlegen und
  sie einfach konvertieren.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aufgabe zum Projekt hinzufügen und Zeitdauern mit Aspose.Tasks verwalten
url: /de/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aufgabe zum Projekt hinzufügen und Dauer verwalten mit Aspose.Tasks

## Einleitung
In diesem Tutorial lernen Sie **wie man eine Aufgabe zum Projekt hinzufügt** und deren Dauer mit Aspose.Tasks für Java steuert. Egal, ob Sie ein neues Projektplanungs‑Tool erstellen oder eine bestehende Lösung erweitern, das Beherrschen der Handhabung von Aufgaben‑Dauern ist entscheidend für genaue Zeitplanung und Berichterstattung.

## Schnelle Antworten
- **Was bedeutet „Aufgabe zum Projekt hinzufügen“?** Es erstellt ein neues Task‑Objekt unter der Wurzel eines Projekts oder unter einer bestimmten Zusammenfassungs‑Aufgabe.  
- **Welche Klasse repräsentiert eine Dauer?** `com.aspose.tasks.Duration`.  
- **Wie setzt man die Dauer?** Verwenden Sie `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Kann ich eine Dauer in eine andere Einheit umwandeln?** Ja, rufen Sie `duration.convert(TimeUnitType.Hour)` oder einen anderen `TimeUnitType` auf.  
- **Benötige ich eine Lizenz für die Produktion?** Eine gültige Aspose.Tasks‑Lizenz ist für die kommerzielle Nutzung erforderlich.

## Was bedeutet „Aufgabe zum Projekt hinzufügen“?
Eine Aufgabe zu einem Projekt hinzuzufügen bedeutet, ein `Task`‑Objekt zu erstellen und es in die Aufgaben‑Hierarchie des Projekts einzufügen. Dieser Vorgang ist der erste Schritt, bevor Sie Arbeit, Ressourcen oder die Dauer für diese Aufgabe definieren können.

## Warum Aufgaben‑Dauern verwalten?
Genaue Dauern ermöglichen realistische Zeitpläne, Ressourcenallokation und Kritischer‑Pfad‑Analysen. Mit Aspose.Tasks können Sie Dauern programmatisch setzen, lesen, umwandeln und anpassen, wodurch Sie die volle Kontrolle über Projektzeitpläne erhalten.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem Rechner installiert ist. Sie können es [hier](https://www.oracle.com/java/technologies/javase-downloads.html) herunterladen.
- Aspose.Tasks Bibliothek: Laden Sie die Aspose.Tasks‑Bibliothek herunter und binden Sie sie in Ihr Projekt ein. Sie finden die Bibliothek [hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
In Ihrem Java‑Projekt importieren Sie die notwendigen Pakete, um mit Aspose.Tasks zu arbeiten:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Schritt 1: Projekt einrichten
```java
// Create a new project
Project project = new Project();
```

## Schritt 2: Neue Aufgabe hinzufügen (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Wie man die Dauer festlegt
Jetzt, wo die Aufgabe existiert, können Sie ihre Länge definieren. Standardmäßig werden Dauern in Tagen angegeben.

## Schritt 3: Aufgaben‑Dauer abrufen und umwandeln
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Wie man die Dauer umwandelt
Die `convert`‑Methode ermöglicht es, eine `Duration` von einem `TimeUnitType` in einen anderen zu übersetzen (z. B. Tage → Stunden, Wochen → Tage).

## Schritt 4: Aufgaben‑Dauer auf 1 Woche aktualisieren
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Schritt 5: Aufgaben‑Dauer verringern
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Durch das Befolgen dieser Schritte haben Sie erfolgreich **eine Aufgabe zu einem Projekt hinzugefügt** und ihre Dauer mit Aspose.Tasks für Java verwaltet.

## Häufige Fallstricke & Tipps
- **Fallstrick:** Das Vergessen, die Dauer vor arithmetischen Operationen umzuwandeln, kann zu falschen Ergebnissen führen. Überprüfen Sie stets die Einheit mit `duration.getTimeUnit()`.
- **Tipp:** Verwenden Sie `project.getDuration(value, TimeUnitType)`, um Dauern in der gewünschten Einheit zu erstellen, anstatt sie später umzuwandeln.
- **Fallstrick:** Das Setzen einer negativen Dauer löst eine Ausnahme aus. Stellen Sie sicher, dass Sie Eingabewerte validieren.

## Fazit
In diesem Leitfaden haben wir behandelt, wie man **eine Aufgabe zum Projekt hinzufügt**, ihre Standarddauer liest, **die Dauer setzt** und **die Dauer** in verschiedene Zeiteinheiten **umwandelt**. Sie können diese Techniken nun in umfangreichere Planungsanwendungen integrieren, um präzise Projektplanung zu ermöglichen.

## FAQs
### Ist Aspose.Tasks mit allen Java‑Versionen kompatibel?
Aspose.Tasks ist mit Java 6 und späteren Versionen kompatibel.

### Kann ich Aspose.Tasks für kommerzielle Projekte verwenden?
Ja, Sie können Aspose.Tasks sowohl für private als auch für kommerzielle Projekte nutzen. Besuchen Sie [hier](https://purchase.aspose.com/buy) für Lizenzdetails.

### Wo finde ich zusätzliche Unterstützung und Ressourcen?
Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Support und Diskussionen.

### Wie kann ich eine temporäre Lizenz für Testzwecke erhalten?
Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) für Tests und Evaluation erhalten.

### Gibt es eine kostenlose Testversion für Aspose.Tasks?
Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen, um Aspose.Tasks vor einem Kauf zu erkunden.

## Häufig gestellte Fragen

**Q: Wie ändere ich die Dauer einer Aufgabe, nachdem sie gesetzt wurde?**  
A: Rufen Sie die aktuelle Dauer mit `task.get(Tsk.DURATION)` ab, ändern Sie sie (z. B. `add`, `subtract` oder `convert`) und setzen Sie sie anschließend mit `task.set(Tsk.DURATION, newDuration)` zurück.

**Q: Kann ich eine Dauer in Minuten festlegen?**  
A: Ja, verwenden Sie `TimeUnitType.Minute`, wenn Sie `project.getDuration(value, TimeUnitType.Minute)` aufrufen.

**Q: Aktualisiert das Ändern der Dauer automatisch die Start‑ und Enddaten der Aufgabe?**  
A: Nur wenn der Planungsmodus des Projekts auf automatisch gestellt ist. Andernfalls müssen Sie den Zeitplan ggf. mit `project.calculateCriticalPath()` neu berechnen.

**Q: Ist es möglich, die Dauer als Rohzahl abzurufen?**  
A: Rufen Sie `duration.getTimeSpan()` auf, um den numerischen Wert in der aktuellen Zeiteinheit zu erhalten.

**Q: Was passiert, wenn ich mehr als die aktuelle Dauer subtrahiere?**  
A: Die API wirft eine `ArgumentOutOfRangeException`. Validieren Sie stets, dass die resultierende Dauer positiv bleibt.

---

**Zuletzt aktualisiert:** 2026-02-20  
**Getestet mit:** Aspose.Tasks für Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}