---
date: 2026-02-28
description: Erfahren Sie, wie Sie Aspose.Tasks für Java verwenden, um zeitphasierte
  Aufgabendaten zu verwalten, die Bibliothek herunterladen, sie kostenlos testen und
  die Projektverfolgung optimieren.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Aspose.Tasks zur Verwaltung von zeitphasenbezogenen Aufgabendaten verwendet
  (Java)
url: /de/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So verwenden Sie Aspose.Tasks für zeitbezogene Aufgabendaten

## Einführung
Wenn Sie **wie man Aspose verwendet** suchen, um Ihr Projektzeitplan fest im Griff zu haben, sind Sie hier genau richtig. Das präzise Verfolgen von zeitbezogenen Aufgabendaten ist ein Grundpfeiler erfolgreichen Projektmanagements, und Aspose.Tasks für Java liefert Ihnen die Werkzeuge, die Sie benötigen, um diesen Prozess zu automatisieren. In diesem Tutorial führen wir Sie durch ein vollständiges, End‑zu‑End‑Beispiel, das zeigt, wie Sie Aspose.Tasks verwenden, um ein Projekt zu erstellen, Ressourcen zuzuweisen, Basislinien zu setzen und schließlich zeitbezogene Daten abzurufen und anzuzeigen.

## Schnelle Antworten
- **Was bedeutet „zeitbezogene Daten“?** Es handelt sich um Daten, die nach Zeitintervallen (Tage, Wochen, Monate) aufgeschlüsselt sind und Arbeit, Kosten oder verbleibende Arbeit über den Projektzeitplan hinweg anzeigen.  
- **Welche Bibliothek stellt diese Fähigkeit bereit?** Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher.  
- **Kann ich die Ergebnisse nach Excel exportieren?** Ja – Sie können die `TimephasedData`‑Sammlung iterieren und die Werte in jedes gewünschte Format schreiben.

## Was sind zeitbezogene Aufgabendaten?
Zeitbezogene Aufgabendaten stellen die Menge an Arbeit (oder Kosten) dar, die für eine Aufgabe in jedem Zeitabschnitt des Projektkalenders geplant ist. Sie ermöglichen es Ihnen, zu sehen, wie Arbeit verteilt ist, Überlastungen zu erkennen und geplanten mit tatsächlichem Fortschritt zu vergleichen.

## Warum Aspose.Tasks zur Verwaltung zeitbezogener Daten verwenden?
- **Vollständige Kontrolle** – programmatisch zeitbezogene Informationen erstellen, ändern und abfragen, ohne Microsoft Project zu öffnen.  
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **Keine COM‑Abhängigkeiten** – ideal für serverseitige Automatisierung.  
- **Umfangreiche API** – unterstützt Basislinien, Arbeitskonturen und benutzerdefinierte Felder sofort out of the box.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java‑Entwicklungsumgebung** – JDK 8+ installiert und `JAVA_HOME` konfiguriert.  
- **Aspose.Tasks für Java Bibliothek** – Laden Sie die Aspose.Tasks‑Bibliothek herunter und binden Sie sie in Ihr Projekt ein. Sie finden die Bibliothek [hier](https://releases.aspose.com/tasks/java/).  
- **Dokumentenverzeichnis** – Ein Ordner auf Ihrem Rechner, in dem die Beispieldatei (`project.xml`) gelesen und geschrieben wird.

## Pakete importieren
In Ihrem Java‑Projekt importieren Sie die notwendigen Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Schritt 1: Projektstartdatum festlegen
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Erklärung:* Wir erstellen eine `Project`‑Instanz, initialisieren einen `Calendar` mit dem gewünschten Startdatum und weisen ihn der `START_DATE`‑Eigenschaft des Projekts zu.

## Schritt 2: Aufgabe und Ressource definieren
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Erklärung:* Eine neue Aufgabe mit dem Namen **Task** wird unter der Stammaufgabe hinzugefügt. Außerdem erstellen wir eine Ressource namens **Rsc** und setzen deren Standard‑ und Überstundensätze.

## Schritt 3: Aufgabendauer festlegen
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Erklärung:* Die Aufgabe wird für eine Dauer von **6 Tagen** geplant.

## Schritt 4: Ressource der Aufgabe zuweisen
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Erklärung:* Die zuvor definierte Ressource wird über eine `ResourceAssignment` mit der Aufgabe verknüpft.

## Schritt 5: Ressourcenzuweisung konfigurieren
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Erklärung:* Wir setzen die Stop‑ und Wiederaufnahme‑Daten der Zuweisung (mit einem Platzhalterwert) und wenden eine **Back‑Loaded**‑Arbeitskontur an, die mehr Arbeit zum Ende der Zuweisung verschiebt.

## Schritt 6: Basislinie festlegen
```java
project.setBaseline(BaselineType.Baseline);
```
*Erklärung:* Das Erfassen einer Basislinie ermöglicht es Ihnen, später geplante mit tatsächlichen Werten zu vergleichen.

## Schritt 7: Aufgabenerfüllung aktualisieren
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Erklärung:* Die Aufgabe wird mit **50 % abgeschlossen** markiert, was die Berechnung der verbleibenden Arbeit beeinflusst.

## Schritt 8: Zeitbezogene Daten abrufen
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Erklärung:* Dieser Aufruf holt die **verbleibende Arbeit** für die Zuweisung, aufgeschlüsselt nach den Zeitintervallen des Projekts.

## Schritt 9: Zeitbezogene Daten anzeigen
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Erklärung:* Wir geben einfach die Anzahl der zeitbezogenen Einträge und den Wert des ersten Eintrags aus. In einem realen Szenario würden Sie die Liste iterieren und die Daten in einen Bericht oder eine Benutzeroberfläche exportieren.

## Häufige Probleme und Lösungen
- **NullPointerException bei `getTimephasedData`** – Stellen Sie sicher, dass die `START`‑ und `FINISH`‑Daten der Zuweisung gesetzt sind, bevor Sie die Methode aufrufen.  
- **Falsche Arbeitskontur** – Prüfen Sie, ob der von Ihnen gewählte `WorkContourType` zu Ihrer Planungsstrategie passt; `BackLoaded` ist nur eine von mehreren Optionen.  
- **Basislinie spiegelt Änderungen nicht wider** – Denken Sie daran, `project.setBaseline` *nach* dem Definieren von Aufgaben, Ressourcen und Zuweisungen aufzurufen.

## Häufig gestellte Fragen
### Q: Kann ich Aspose.Tasks für Java in jedem Java‑Projekt verwenden?
A: Ja, Aspose.Tasks für Java ist mit jedem Java‑basierten Projekt kompatibel.

### Q: Wo finde ich zusätzliche Unterstützung für Aspose.Tasks für Java?
A: Besuchen Sie das [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) für Support und Diskussionen.

### Q: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erkunden.

### Q: Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

### Q: Wo kann ich Aspose.Tasks für Java kaufen?
A: Sie können Aspose.Tasks für Java [hier](https://purchase.aspose.com/buy) erwerben.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks für Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}