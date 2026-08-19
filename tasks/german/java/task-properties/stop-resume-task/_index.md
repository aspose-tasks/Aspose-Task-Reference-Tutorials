---
date: 2026-02-26
description: Erfahren Sie, wie Sie Aufgaben in Aspose.Tasks für Java fortsetzen und
  stoppen, einschließlich der Filterung von Aufgaben nach Datum für eine präzise Projektsteuerung.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man eine Aufgabe in Aspose.Tasks fortsetzt und stoppt
url: /de/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Aufgaben wiederaufnimmt und stoppt in Aspose.Tasks

## Einführung
Wenn Sie eine Java‑basierte Projektmanagement‑Lösung entwickeln, müssen Sie häufig eine Aufgabe vorübergehend **pausieren** und später **fortsetzen**. Aspose.Tasks for Java macht dies einfach mit integrierten Eigenschaften zum Stoppen und Wiederaufnehmen von Aufgaben. In diesem Tutorial erfahren Sie, **wie man eine Aufgabe wiederaufnimmt** und **wie man eine Aufgabe stoppt** programmgesteuert, und Sie sehen außerdem, wie man **Aufgaben nach Datum filtert**, sodass Sie nur mit den relevanten Elementen Ihres Zeitplans arbeiten.

## Schnelle Antworten
- **Was bedeutet „stop“ für eine Aufgabe?** Es setzt ein Stopp‑Datum und pausiert die Arbeit nach diesem Zeitpunkt.  
- **Wie kann ich eine gestoppte Aufgabe wiederaufnehmen?** Indem man ein Wiederaufnahme‑Datum zuweist, das später als das Stopp‑Datum liegt.  
- **Kann ich die Operation auf einen Datumsbereich beschränken?** Ja – verwenden Sie ein Mindestdatum, um Aufgaben zu filtern.  
- **Welche Bibliotheksversion wird benötigt?** Jede aktuelle Aspose.Tasks for Java‑Version (die API bleibt stabil).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich.

## Was bedeutet „how to resume task“ in Aspose.Tasks?
Das Wiederaufnehmen einer Aufgabe bedeutet einfach, ein **RESUME**‑Datum auf einem `Task`‑Objekt anzugeben. Wenn die Projekt‑Engine den Zeitplan verarbeitet, wird die Arbeit ab diesem Datum fortgesetzt. Dies ist besonders nützlich, um Unterbrechungen wie Ressourcen‑Unverfügbarkeit oder externe Abhängigkeiten zu handhaben.

## Warum das Stop‑/Resume‑Feature verwenden?
- **Kontrolle über Zeitpläne:** Arbeit pausieren, ohne die Aufgabe zu löschen.  
- **Genaues Reporting:** Realistische Start‑/Enddaten in Gantt‑Diagrammen anzeigen.  
- **Einfache Automatisierung:** Mit Datumsfiltern kombinieren, um viele Aufgaben gleichzeitig zu aktualisieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie:

- Ein fundiertes Verständnis der Java‑Grundlagen.  
- JDK auf Ihrem Rechner installiert.  
- Die Aspose.Tasks for Java‑Bibliothek zu Ihrem Projekt hinzugefügt (herunterladen von [hier](https://releases.aspose.com/tasks/java/)).  

## Pakete importieren
Zuerst bringen Sie die erforderlichen Klassen in den Gültigkeitsbereich, damit Sie mit Projekten und Aufgaben arbeiten können.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Schritt 1: Projekt und Sammler initialisieren
Erstellen Sie eine `Project`‑Instanz, die auf Ihre MPP‑Datei verweist, und richten Sie einen `ChildTasksCollector` ein, um jede Aufgabe in der Hierarchie zu sammeln.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Schritt 2: Mindestdatum für Filterung definieren
Wenn Sie nur mit Aufgaben arbeiten möchten, die sinnvolle Stopp‑ oder Wiederaufnahme‑Daten haben, definieren Sie ein **Mindestdatum**. Dies ist das Kernstück der *Aufgaben‑nach‑Datum‑filtern*‑Technik.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Schritt 3: Durchlaufen, prüfen und Stopp‑/Wiederaufnahme‑Werte anzeigen
Durchlaufen Sie nun die gesammelten Aufgaben, wenden Sie die **how to stop task**‑Logik an und geben Sie die Daten aus. Der Code demonstriert außerdem **how to resume task**, indem er die `RESUME`‑Eigenschaft ausliest.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Pro Tipp:** Ersetzen Sie die Aufrufe von `System.out.println` durch Ihre eigene Logik (z. B. Aktualisieren der Daten, Protokollierung in eine Datei oder Ändern der Aufgabenobjekte), um Aufgaben bei Bedarf tatsächlich zu *stoppen* oder *wiederaufzunehmen*.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | Aufgabe hat kein Stopp‑Datum gesetzt. | Prüfen Sie auf `null`, bevor Sie `.before(minDate)` aufrufen. |
| Dates appear as `NA` even after setting | Mindestdatum ist zu aktuell. | Verwenden Sie ein früheres `minDate` oder entfernen Sie den Filter. |
| Changes not reflected in the saved MPP | Projekt wurde nach Änderungen nicht gespeichert. | Rufen Sie `project.save("output.mpp");` nach dem Aktualisieren der Aufgaben auf. |

## Häufig gestellte Fragen

### Ist Aspose.Tasks for Java für Großprojekte geeignet?
Absolut! Aspose.Tasks for Java ist darauf ausgelegt, Projekte unterschiedlicher Größe zu bewältigen und dabei Effizienz und Zuverlässigkeit zu gewährleisten.

### Kann ich das Datum für das Stoppen und Wiederaufnehmen von Aufgaben anpassen?
Ja, das bereitgestellte Beispiel ermöglicht Flexibilität beim Festlegen des Mindestdatums gemäß Ihren Projektanforderungen.

### Wo finde ich zusätzlichen Support für Aspose.Tasks for Java?
Besuchen Sie das [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) für Community‑Support und Diskussionen.

### Gibt es eine kostenlose Testversion für Aspose.Tasks for Java?
Ja, Sie können die [kostenlose Testversion](https://releases.aspose.com/) nutzen, um die Funktionen vor dem Kauf zu erkunden.

### Wie kann ich eine temporäre Lizenz für Aspose.Tasks for Java erhalten?
Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) für Testzwecke erhalten.

**Zusätzliche Fragen & Antworten**

**F: Wie setze ich tatsächlich ein neues Stopp‑Datum für eine Aufgabe?**  
A: Verwenden Sie `tsk.set(Tsk.STOP, new Date(...));` und speichern Sie anschließend das Projekt.

**F: Kann ich Aufgaben nach einem bestimmten Bereich statt nur nach einem Mindestdatum filtern?**  
A: Ja – vergleichen Sie sowohl `before` als auch `after` mit Ihren Start‑ und Enddaten.

**F: Berechnet die API den Zeitplan automatisch neu, nachdem Stopp‑/Wiederaufnahme‑Daten geändert wurden?**  
A: Nach dem Ändern der Daten rufen Sie `project.calculateCriticalPath();` auf, um den Zeitplan zu aktualisieren.

## Fazit
In diesem Leitfaden haben wir **how to resume task** und **how to stop task** mit Aspose.Tasks for Java behandelt, zusammen mit einer praktischen Methode zum **filter tasks by date**. Durch die Integration dieser Snippets in Ihre Anwendung erhalten Sie eine feinkörnige Kontrolle über Projektzeitpläne und können Zeitplananpassungen selbstbewusst automatisieren.

---

**Zuletzt aktualisiert:** 2026-02-26  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}