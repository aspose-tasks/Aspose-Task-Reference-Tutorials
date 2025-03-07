---
title: Aktualisieren und planen Sie MS Project in Aspose.Tasks neu
linktitle: Aktualisieren Sie das Projekt und planen Sie nicht abgeschlossene Arbeiten in Aspose.Tasks neu
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie MS Project-Dateien mit Aspose.Tasks für Java programmgesteuert aktualisieren und neu planen.
weight: 23
url: /de/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aktualisieren und planen Sie MS Project in Aspose.Tasks neu

## Einführung
Microsoft Project ist eine weit verbreitete Projektmanagementsoftware, mit der Benutzer Aufgaben, Ressourcen und Zeitpläne effizient verwalten können. Aspose.Tasks für Java bietet einen leistungsstarken Satz von APIs zur programmgesteuerten Bearbeitung von Microsoft Project-Dateien. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java MS Project-Dateien aktualisieren und nicht abgeschlossene Arbeiten neu planen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java Development Kit (JDK) auf Ihrem System installiert.
2.  Aspose.Tasks für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
3. Grundlegendes Verständnis der Programmiersprache Java.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihren Java-Code:
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
## Schritt 1: Richten Sie das Projekt ein
Initialisieren Sie ein neues Projektobjekt und definieren Sie darin Aufgaben sowie deren Dauer und Abhängigkeiten.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Definieren Sie Aufgaben und deren Dauer
// ...
// Definieren Sie Aufgabenabhängigkeiten
// ...
// Speichern Sie den Ausgangszustand des Projekts
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Schritt 2: Projektarbeit aktualisieren
Aktualisieren Sie die Projektarbeit, um sie bis zu einem bestimmten Datum als abgeschlossen zu markieren.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Speichern Sie das aktualisierte Projekt
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Schritt 3: Unerledigte Arbeiten neu planen
Planen Sie alle nicht abgeschlossenen Arbeiten so, dass sie nach einem bestimmten Datum beginnen.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Speichern Sie das neu geplante Projekt
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java MS Project-Dateien aktualisiert und nicht abgeschlossene Arbeiten neu plant. Dies kann besonders in Szenarien nützlich sein, in denen Projektzeitpläne basierend auf dem Fortschritt oder sich ändernden Prioritäten angepasst werden müssen.

## FAQs
### F: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet robuste APIs zur effizienten Verwaltung von Aufgaben, Abhängigkeiten, Ressourcen und anderen Projektelementen.
### F: Gibt es eine Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).
### F: Wie erhalte ich Unterstützung für Aspose.Tasks für Java?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für jegliche Hilfe oder Fragen.
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?
 A: Ja, temporäre Lizenzen können erworben werden[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo finde ich eine ausführliche Dokumentation zu Aspose.Tasks für Java?
 A: Sie können sich auf die Dokumentation beziehen[Hier](https://reference.aspose.com/tasks/java/) für umfassende Anleitungen und API-Referenzen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
