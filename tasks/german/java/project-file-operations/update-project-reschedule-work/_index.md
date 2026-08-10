---
date: 2026-03-29
description: Lernen Sie, wie Sie nicht abgeschlossene Arbeiten neu planen, Projektarbeiten
  aktualisieren und MS Project‑Dateien als XML mit Aspose.Tasks für Java speichern.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Nicht erledigte Arbeit neu planen und MS‑Project‑Dateien mit Aspose.Tasks aktualisieren
url: /de/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Unvollständige Arbeit neu planen und MS Project-Dateien mit Aspose.Tasks aktualisieren

## Einführung
Microsoft Project ist ein weit verbreitetes Projektmanagement‑Tool, das Teams dabei unterstützt, Aufgaben zu planen, Ressourcen zuzuweisen und Zeitpläne zu verfolgen. Aspose.Tasks für Java bietet Entwicklern eine umfangreiche API, um Microsoft Project‑Dateien programmgesteuert zu manipulieren. In diesem Tutorial lernen Sie, wie man **Projektarbeit aktualisiert**, **unvollständige Arbeit neu plant** und die **MS Project‑Datei** im XML‑Format mit Aspose.Tasks für Java speichert.

## Schnelle Antworten
- **Was bedeutet „unvollständige Arbeit neu planen“?** Es verschiebt die verbleibende Aufgabenarbeit so, dass sie nach einem gewählten Datum beginnt, wobei bereits abgeschlossene Teile unverändert bleiben.  
- **Welche Methode markiert Arbeit als abgeschlossen?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Wie speichere ich die Änderungen?** Verwenden Sie `project.save(<path>, SaveFileFormat.Xml)`.  
- **Benötige ich eine Lizenz für die Produktion?** Ja, für die kommerzielle Nutzung ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 und höher werden vollständig unterstützt.

## Was bedeutet „unvollständige Arbeit neu planen“?
Das NeupLANen unvollständiger Arbeit passt die Startdaten aller noch nicht abgeschlossenen Aufgaben an und verschiebt sie so, dass sie nach einem festgelegten Stichtag beginnen. Dies ist nützlich, wenn sich der Projektzeitplan aufgrund von Verzögerungen oder Änderungen im Umfang verschiebt.

## Warum Aspose.Tasks zum Aktualisieren von Projektarbeit und NeupLANen von Aufgaben verwenden?
- **Feinkörnige Kontrolle:** Direkt Prozentsätze und Daten der Arbeitsfertigstellung festlegen.  
- **Keine Benutzeroberfläche erforderlich:** Massenaktualisierungen über viele Projektdateien automatisieren.  
- **Plattformübergreifend:** Funktioniert auf jedem System, das Java ausführt.  
- **Erhält Datenintegrität:** Alle Abhängigkeiten, Einschränkungen und Ressourcen bleiben konsistent.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:
1. Java Development Kit (JDK) auf Ihrem System installiert.  
2. Aspose.Tasks für Java‑Bibliothek. Sie können sie von [hier](https://releases.aspose.com/tasks/java/) herunterladen.  
3. Grundlegendes Verständnis der Programmiersprache Java.

## Pakete importieren
Zuerst importieren Sie die erforderlichen Pakete in Ihrem Java‑Code:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Schritt 1: Projekt einrichten
Initialisieren Sie ein neues `Project`‑Objekt, definieren Sie Aufgaben, setzen Sie Dauern und stellen Sie Abhängigkeiten her. Dies erstellt das Basisprojekt, das wir später aktualisieren und neu planen werden.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Schritt 2: Projektarbeit aktualisieren
Markieren Sie die Arbeit bis zu einem bestimmten Datum als abgeschlossen. Dieser Schritt demonstriert die **Projektarbeit‑Aktualisierung**‑Operation, die häufig die erste Maßnahme vor dem NeupLANen ist.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Schritt 3: Unvollständige Arbeit neu planen
Jetzt verschieben wir die verbleibende (unvollständige) Arbeit, sodass sie nach demselben Stichtag beginnt. Dies ist die Kernfunktionalität zum **NeupLANen unvollständiger Arbeit**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Fazit
In diesem Tutorial haben wir behandelt, wie man **Projektarbeit aktualisiert**, **unvollständige Arbeit neu plant** und die **MS Project‑Datei** als XML mit Aspose.Tasks für Java speichert. Diese Fähigkeiten sind entscheidend, wenn Projektzeitpläne basierend auf dem tatsächlichen Fortschritt oder sich ändernden geschäftlichen Prioritäten angepasst werden müssen.

## Häufig gestellte Fragen
### Frage: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet robuste APIs, um Aufgaben, Abhängigkeiten, Ressourcen und andere Projektelemente effizient zu verwalten.  
### Frage: Gibt es eine Testversion von Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) erhalten.  
### Frage: Wie kann ich Support für Aspose.Tasks für Java erhalten?
A: Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung oder Fragen besuchen.  
### Frage: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?
A: Ja, temporäre Lizenzen können [hier](https://purchase.aspose.com/temporary-license/) erworben werden.  
### Frage: Wo finde ich detaillierte Dokumentation für Aspose.Tasks für Java?
A: Sie können die Dokumentation [hier](https://reference.aspose.com/tasks/java/) für umfassende Anleitungen und API‑Referenzen einsehen.

## Weitere häufig gestellte Fragen

**Frage: Wie stelle ich sicher, dass die gespeicherte Datei mit älteren Versionen von Microsoft Project kompatibel ist?**  
A: Speichern Sie das Projekt mit `SaveFileFormat.Xml`; XML wird von den meisten Project‑Versionen unterstützt.

**Frage: Kann ich nur einen Teil der Aufgaben statt des gesamten Projekts neu planen?**  
A: Ja, Sie können über bestimmte Aufgaben iterieren und `task.setStart(date)` aufrufen, nachdem Sie das neue Startdatum berechnet haben.

**Frage: Was passiert mit den Ressourcenallokationen, wenn ich unvollständige Arbeit neu plane?**  
A: Ressourcen‑Zuweisungen werden automatisch angepasst, um den neuen Aufgaben‑Startdaten zu entsprechen, wodurch die Zuweisungslogik erhalten bleibt.

**Frage: Ist es möglich, eine NeupLAN‑Operation programmgesteuert rückgängig zu machen?**  
A: Sie können die ursprüngliche Projektdatei (oder ein Backup) neu laden, um Änderungen rückgängig zu machen.

**Frage: Unterstützt Aspose.Tasks das Speichern in anderen Formaten wie .mpp?**  
A: Absolut. Verwenden Sie `SaveFileFormat.MPP`, um im nativen Microsoft Project‑Format zu speichern.

---

**Zuletzt aktualisiert:** 2026-03-29  
**Getestet mit:** Aspose.Tasks für Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}