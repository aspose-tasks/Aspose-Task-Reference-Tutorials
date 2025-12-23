---
date: 2025-12-23
description: Erfahren Sie, wie Sie MS Project‑Dateien aktualisieren und nicht erledigte
  Arbeiten mit Aspose.Tasks für Java neu planen. Sehen Sie außerdem, wie Sie MS Project‑XML
  speichern.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project aktualisieren und Arbeit mit Aspose.Tasks neu planen
url: /de/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project aktualisieren und Arbeit neu planen mit Aspose.Tasks

## Einleitung
Microsoft Project ist ein weit verbreitetes Projekt‑Management‑Tool, das Teams hilft, Arbeit zu planen, zu verfolgen und termingerecht zu liefern. Wenn sich Zeitpläne ändern, muss man häufig **MS Project aktualisieren** — Arbeit als abgeschlossen markieren, verbleibende Aufgaben verschieben und die Projekt‑Baseline genau halten. Aspose.Tasks für Java bietet eine saubere, typensichere API, um genau das zu tun, ohne die GUI zu öffnen. In diesem Tutorial sehen Sie, wie ein Projekt aktualisiert wird, Arbeit bis zu einem bestimmten Datum als erledigt markiert wird und anschließend **wie MS Project neu zu planen**.

## Schnelle Antworten
- **Was bedeutet „MS Project aktualisieren“?** Es markiert Aufgaben bis zu einem angegebenen Datum als abgeschlossen und schreibt die Änderungen zurück in die Datei.  
- **Kann ich verbleibende Arbeit automatisch neu planen?** Ja – verwenden Sie `rescheduleUncompletedWorkToStartAfter`, um nicht abgeschlossene Aufgaben nach vorne zu verschieben.  
- **In welchem Dateiformat wird gespeichert?** Die Beispiele speichern das Projekt als XML (`SaveFileFormat.Xml`).  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** JDK 8 oder höher.

## Was bedeutet „MS Project aktualisieren“ im Code?
Ein Projekt zu aktualisieren bedeutet, Aufgaben‑Daten, -Dauern oder -Fertigstellungs‑Prozentsätze programmgesteuert zu ändern und diese Änderungen zu speichern. Aspose.Tasks stellt Methoden wie `updateProjectWorkAsComplete` bereit, die die Änderungen basierend auf einem von Ihnen angegebenen Referenz‑`Date` anwenden.

## Warum Aspose.Tasks für Java zum Aktualisieren von MS Project verwenden?
- **Keine UI‑Abhängigkeit** – automatisieren Sie Massenänderungen über viele Dateien.  
- **Hohe Treue** – die Bibliothek bewahrt alle nativen Project‑Daten (Ressourcen, Kalender, benutzerdefinierte Felder).  
- **Plattformübergreifend** – führen Sie denselben Code unter Windows, Linux oder macOS aus.  
- **MS Project XML speichern** – Sie können das aktualisierte Projekt in das weit verbreitete XML‑Format für nachgelagerte Werkzeuge exportieren.

## Voraussetzungen
1. Java Development Kit (JDK) installiert.  
2. Aspose.Tasks für Java‑Bibliothek – laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. Grundlegende Kenntnisse der Java‑Syntax und objektorientierter Konzepte.

## Pakete importieren
Zuerst importieren Sie die notwendigen Aspose.Tasks‑Klassen und Java‑Hilfsmittel:

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

## Schritt 1: Projekt einrichten
Erstellen Sie eine neue `Project`‑Instanz, definieren Sie einige Beispiel‑Aufgaben, setzen Sie deren Dauer und stellen Sie Abhängigkeiten her. Anschließend speichern Sie den Anfangszustand, damit Sie den Vorher‑Nachher‑Effekt sehen können.

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

## Schritt 2: Projektarbeit aktualisieren
Markieren Sie Arbeit bis zu einem bestimmten Stichtag als abgeschlossen. Dies ist der Kern von **MS Project aktualisieren** — die API passt den Aufgaben‑Fortschritt und die Daten automatisch an.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Schritt 3: Nicht abgeschlossene Arbeit neu planen
Nachdem Sie die erledigte Arbeit markiert haben, müssen Sie häufig die verbleibenden Aufgaben nach vorne verschieben. Der folgende Aufruf verschiebt jede nicht abgeschlossene Arbeit, sodass sie nach demselben Stichtag beginnt, und zeigt damit **wie MS Project neu zu planen**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|----------|--------|
| Aufgaben zeigen keine aktualisierten Daten | Das Projekt wurde in einem anderen Format gespeichert (z. B. `.mpp`) | Verwenden Sie `SaveFileFormat.Xml`, um die XML‑Struktur beizubehalten. |
| `updateProjectWorkAsComplete` scheint nichts zu tun | Das Referenzdatum liegt vor dem Projektstart | Stellen Sie sicher, dass das `Calendar`‑Datum innerhalb des Projektzeitraums liegt. |
| Neu geplante Aufgaben überschneiden sich | Kein Kalender oder keine Ressourcen‑Leveling‑Anwendung | Wenden Sie einen `Project`‑Kalender an oder setzen Sie `Task.setStart` manuell nach dem Neu‑Planen. |

## Häufig gestellte Fragen (Erweitert)

**Q: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?**  
A: Ja, Aspose.Tasks für Java bietet robuste APIs, um Aufgaben, Abhängigkeiten, Ressourcen und andere Projektelemente effizient zu verwalten.

**Q: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) erhalten.

**Q: Wie kann ich Support für Aspose.Tasks für Java erhalten?**  
A: Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung oder Fragen besuchen.

**Q: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?**  
A: Ja, temporäre Lizenzen können [hier](https://purchase.aspose.com/temporary-license/) erworben werden.

**Q: Wo finde ich ausführliche Dokumentation für Aspose.Tasks für Java?**  
A: Die Dokumentation finden Sie [hier](https://reference.aspose.com/tasks/java/) für umfassende Anleitungen und API‑Referenzen.

## Fazit
In diesem Tutorial haben wir den vollständigen Prozess des **MS Project aktualisieren** von Dateien, das Markieren von Arbeit als abgeschlossen und anschließend **wie MS Project neu zu planen** für noch nicht erledigte Aufgaben durchlaufen. Durch das Speichern des Projekts als XML behalten Sie die Kompatibilität zu anderen Werkzeugen und erhalten eine klare Änderungsnachverfolgung. Verwenden Sie diese Muster, um Zeitplananpassungen in großen Portfolios zu automatisieren, in CI‑Pipelines zu integrieren oder benutzerdefinierte Reporting‑Dashboards zu erstellen.

---

**Zuletzt aktualisiert:** 2025-12-23  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}