---
date: 2026-02-26
description: Erfahren Sie, wie Sie Enddaten von Aufgaben aufteilen und Projektzeitpläne
  mit Aspose.Tasks für Java verwalten. Dieser Leitfaden zeigt, wie man Aufgaben effizient
  aufteilt.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projektzeitpläne verwalten – Aufteilen des Enddatums einer Aufgabe in Aspose.Tasks
url: /de/java/task-properties/split-task-finish-date/
weight: 28
---

ose.Tasks". Keep same heading level.

Similarly subheadings.

Translate paragraphs.

Need to keep code block placeholders unchanged.

Also bullet points.

Let's produce translation.

Be careful with "Aspose.Tasks for Java" keep as is.

Also "API" keep.

Let's translate.

Will produce final markdown.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aufteilen des Aufgabenschlussdatums in Aspose.Tasks

## Einführung
Effektives **Verwalten von Projektzeitplänen** ist ein Grundpfeiler für eine erfolgreiche Projektabwicklung. Wenn sich die Dauer einer Aufgabe ändert, muss ihr Enddatum neu berechnet werden, um den Zeitplan genau zu halten. In diesem Tutorial zeigen wir Ihnen **wie man das Aufgabenschlussdatum** mit Aspose.Tasks für Java aufteilt, sodass Sie die Projektzeitlinie präzise steuern können.

## Schnellantworten
- **Was bewirkt das Aufteilen eines Aufgabenschlussdatums?** Es ermöglicht Ihnen, das Enddatum für jede gegebene Dauer zu berechnen und den Zeitplan bei Bedarf anzupassen.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (von der offiziellen Website herunterladbar).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz reicht für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich das mit jedem Projektkalender verwenden?** Ja, die API nutzt den Projektkalender, um Arbeitstage und Feiertage zu berücksichtigen.  
- **Wie viele Code‑Zeilen werden benötigt?** Weniger als zehn Zeilen, um das Enddatum für jede Dauer zu erhalten.

## Was bedeutet „Projektzeitpläne verwalten“ im Kontext von Aspose.Tasks?
Projektzeitpläne verwalten bedeutet, die Start‑ und Enddaten jeder Aufgabe mit dem Gesamtkalender synchron zu halten, wobei Kalender, Ressourcen und Aufgabenabhängigkeiten berücksichtigt werden. Präzise Berechnungen des Enddatums sind entscheidend für realistische Prognosen und das Vertrauen der Stakeholder.

## Warum das Aufgabenschlussdatum aufteilen?
- **Flexibilität:** Schnell sehen, wie unterschiedliche Stundenzuweisungen die Lieferung beeinflussen.  
- **Risikobewertung:** „Was‑wenn‑“‑Szenarien evaluieren, ohne den ursprünglichen Plan zu ändern.  
- **Ressourcenplanung:** Aufgaben­dauern an die Teamkapazität und Kalenderbeschränkungen anpassen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:
- Grundkenntnisse in Java‑Programmierung.  
- Aspose.Tasks für Java Bibliothek installiert. Sie können sie [hier](https://releases.aspose.com/tasks/java/) herunterladen.  
- Eine eingerichtete Java‑Entwicklungsumgebung.

## Pakete importieren
Binden Sie die notwendigen Pakete in Ihr Java‑Projekt ein:
```java
import com.aspose.tasks.*;
```

## Schritt 1: Aufgeteilte Aufgabe finden
Lokalisieren Sie die Aufgabe, die Sie im Projekt aufteilen möchten:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Schritt 2: Projektkalender finden
Rufen Sie den Projektkalender für genaue Datumsberechnungen ab:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Schritt 3: Aufgabenschlussdatum mit verschiedenen Dauern berechnen
Berechnen Sie nun das Aufgabenschlussdatum für verschiedene Dauern.

### Schritt 3.1: Dauer von 8 Stunden
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*Wiederholen Sie den obigen Code für unterschiedliche Dauern, passen Sie die Stunden entsprechend an, um zu sehen, wie jede Änderung das Enddatum beeinflusst.*

## Häufige Probleme und Lösungen
- **Falscher Kalender‑Verweis:** Stellen Sie sicher, dass Sie den Projekt‑Kalender (`project.get(Prj.CALENDAR)`) abrufen und nicht einen neuen erstellen.  
- **Falsche Aufgaben‑UID:** Die UID muss zu einer tatsächlich vorhandenen Aufgabe passen; andernfalls gibt `getByUid` `null` zurück und führt zu einer `NullPointerException`.  
- **Zeitzonen‑Mismatches:** Die API arbeitet mit der Zeitzone des Kalenders; prüfen Sie die Standard‑Zeitzone Ihres Systems, wenn die Ergebnisse ungewöhnlich erscheinen.

## Fazit
Die Kunst des **Verwaltens von Projektzeitplänen** durch Aufteilen von Aufgabenschlussdaten zu beherrschen, ist entscheidend für ein effektives Projektmanagement. Aspose.Tasks für Java vereinfacht diesen Prozess und ermöglicht es Ihnen, Ihre Zeitpläne mühelos zu optimieren.

## FAQs
### Q1: Wie kann ich Aspose.Tasks für Java herunterladen?
A1: Sie können es [hier](https://releases.aspose.com/tasks/java/) herunterladen.

### Q2: Wo finde ich die Dokumentation für Aspose.Tasks?
A2: Sie finden die Dokumentation [hier](https://reference.aspose.com/tasks/java/).

### Q3: Wie erhalte ich eine temporäre Lizenz für Aspose.Tasks?
A3: Eine temporäre Lizenz erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

### Q4: Wo kann ich Support für Aspose.Tasks erhalten?
A4: Besuchen Sie das Support‑Forum [hier](https://forum.aspose.com/c/tasks/15).

### Q5: Kann ich Aspose.Tasks kaufen?
A5: Ja, Sie können es [hier](https://purchase.aspose.com/buy) erwerben.

## Weitere häufig gestellte Fragen

**F: Kann ich diese Technik mit einem benutzerdefinierten Kalender verwenden?**  
A: Absolut. Ersetzen Sie einfach `project.get(Prj.CALENDAR)` durch Ihre eigene `Calendar`‑Instanz.

**F: Berücksichtigt die Methode nicht‑arbeitende Tage?**  
A: Ja, die Arbeitszeitdefinitionen des Kalenders werden bei der Berechnung des Enddatums angewendet.

**F: Gibt es eine Möglichkeit, das Enddatum für Bruchteile von Stunden (z. B. 3,5 Stunden) abzurufen?**  
A: Übergeben Sie einen `double`‑Wert wie `3.5d` an `getTaskFinishDateFromDuration`; die API verarbeitet Bruchdauern.

**F: Wie formatiere ich das Ausgabedatum?**  
A: Verwenden Sie `java.time.format.DateTimeFormatter` auf dem zurückgegebenen `Date`‑Objekt, um es in Ihrem gewünschten Format anzuzeigen.

---

**Zuletzt aktualisiert:** 2026-02-26  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}