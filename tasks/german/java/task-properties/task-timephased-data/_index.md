---
title: Aufgabenzeitphasendaten in Aspose.Tasks
linktitle: Aufgabenzeitphasendaten in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Entdecken Sie Aspose.Tasks für Java und meistern Sie die zeitphasengesteuerte Datenverwaltung von Aufgaben. Laden Sie die Bibliothek herunter, genießen Sie eine kostenlose Testversion und optimieren Sie Ihre Projektverfolgung.
weight: 34
url: /de/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aufgabenzeitphasendaten in Aspose.Tasks

## Einführung
Im Bereich des Projektmanagements ist die genaue Verfolgung von Aufgabenzeitphasendaten für eine effiziente Projektabwicklung von entscheidender Bedeutung. Aspose.Tasks für Java erweist sich als leistungsstarkes Tool zur Rationalisierung dieses Prozesses und bietet robuste Funktionen und Flexibilität. Dieses Tutorial führt Sie durch die Verwendung von Aspose.Tasks für Java, um Aufgabenzeitphasendaten effektiv zu verwalten.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java-Entwicklungsumgebung: Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
-  Aspose.Tasks für Java-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein. Sie finden die Bibliothek[Hier](https://releases.aspose.com/tasks/java/).
- Dokumentenverzeichnis: Richten Sie ein Verzeichnis für Ihre Projektdokumente ein.
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete für Aspose.Tasks:
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
// Zusätzlicher Code für Paketimporte
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Erläuterung: Initialisieren Sie ein Kalenderobjekt, legen Sie das Startdatum fest und wenden Sie es auf das Projekt an.
## Schritt 2: Aufgabe und Ressource definieren
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Erläuterung: Erstellen Sie eine Aufgabe und eine Ressource und legen Sie Sätze für Standard- und Überstunden fest.
## Schritt 3: Legen Sie die Aufgabendauer fest
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Erläuterung: Definieren Sie die Dauer der Aufgabe (z. B. 6 Tage).
## Schritt 4: Ressource einer Aufgabe zuweisen
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Erläuterung: Ordnen Sie die Ressource der Aufgabe zu.
## Schritt 5: Konfigurieren Sie die Ressourcenzuweisung
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Erläuterung: Legen Sie Parameter wie Stopp, Wiederaufnahme und Arbeitskontur für die Ressourcenzuweisung fest.
## Schritt 6: Basislinie festlegen
```java
project.setBaseline(BaselineType.Baseline);
```
Erläuterung: Legen Sie eine Basislinie für das Projekt fest.
## Schritt 7: Abschluss der Aktualisierungsaufgabe
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Erläuterung: Geben Sie den Abschlussprozentsatz der Aufgabe an.
## Schritt 8: Zeitphasendaten abrufen
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Erläuterung: Zeitphasendaten für die verbleibende Zuweisungsarbeit abrufen.
## Schritt 9: Zeitphasendaten anzeigen
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Zusätzlicher Code zur Anzeige anderer Werte
```
Erläuterung: Zeitphasendaten ausgeben und anzeigen.
## Abschluss
Die effektive Verwaltung von Aufgabenzeitphasendaten ist für den Projekterfolg unerlässlich. Aspose.Tasks für Java vereinfacht diesen Prozess und bietet einen umfassenden Satz an Funktionalitäten. Wenn Sie diesem Tutorial folgen, können Sie Aspose.Tasks nahtlos in Ihr Java-Projekt integrieren und so eine präzise Kontrolle über Projektzeitpläne und Ressourcenzuweisung gewährleisten.
## Häufig gestellte Fragen
### F: Kann ich Aspose.Tasks für Java in jedem Java-Projekt verwenden?
A: Ja, Aspose.Tasks für Java ist mit jedem Java-basierten Projekt kompatibel.
### F: Wo finde ich zusätzliche Unterstützung für Aspose.Tasks für Java?
 A: Besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung und Diskussionen.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion ausprobieren[Hier](https://releases.aspose.com/).
### F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
 A: Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich Aspose.Tasks für Java kaufen?
 A: Sie können Aspose.Tasks für Java erwerben[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
