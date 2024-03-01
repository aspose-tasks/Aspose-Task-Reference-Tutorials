---
title: Stoppen und Fortsetzen der Aufgabe in Aspose.Tasks
linktitle: Stoppen und Fortsetzen der Aufgabe in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Tasks für Java mit unserer Schritt-für-Schritt-Anleitung zum Anhalten und Fortsetzen von Aufgaben. Verbessern Sie das Projektmanagement nahtlos!
type: docs
weight: 30
url: /de/java/task-properties/stop-resume-task/
---
## Einführung
Im Bereich der Java-Entwicklung ist die effiziente Verwaltung von Aufgaben ein entscheidender Aspekt der Projektausführung. Aspose.Tasks für Java bietet mit seinen leistungsstarken Funktionen eine robuste Lösung für die Bearbeitung von Aufgaben. In diesem Tutorial befassen wir uns mit einer bestimmten Funktionalität – dem Stoppen und Fortsetzen von Aufgaben. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktion nahtlos in Ihre Java-Projekte integrieren.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der Java-Programmierung.
- Installiertes Java Development Kit (JDK) auf Ihrem System.
- Aspose.Tasks für Java-Bibliothek heruntergeladen und Ihrem Projekt hinzugefügt. Sie können es erhalten bei[Hier](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Stellen Sie zum Starten des Prozesses sicher, dass Sie die erforderlichen Pakete in Ihr Java-Projekt importieren:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## Schritt 1: Initialisierung
 Beginnen Sie mit der Initialisierung Ihres Projekts und der Erstellung eines`ChildTasksCollector` Instanz zum Sammeln aller Aufgaben.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Schritt 2: Mindestdatum festlegen
Definieren Sie ein Mindestdatum, um Aufgaben zu filtern, die gestoppt oder wieder aufgenommen werden müssen.
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## Schritt 3: Aufgaben anhalten und fortsetzen
Durchlaufen Sie Aufgaben, überprüfen und drucken Sie die Stopp- und Wiederaufnahmedaten.
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
Wiederholen Sie diese Schritte in Ihrem Java-Projekt, um die Stopp- und Wiederaufnahmefunktion mithilfe von Aspose.Tasks für Java nahtlos zu integrieren.
## Abschluss
In diesem Tutorial haben wir den Prozess des Stoppens und Fortsetzens von Aufgaben mit Aspose.Tasks für Java untersucht. Indem Sie die oben beschriebenen Schritte befolgen, können Sie Ihre Projektmanagementfähigkeiten verbessern und die Aufgabenausführung optimieren.
## Häufig gestellte Fragen
### Ist Aspose.Tasks für Java für Großprojekte geeignet?
Absolut! Aspose.Tasks für Java ist für die Abwicklung von Projekten unterschiedlicher Größe konzipiert und gewährleistet Effizienz und Zuverlässigkeit.
### Kann ich das Datum für das Stoppen und Wiederaufnehmen von Aufgaben anpassen?
Ja, das bereitgestellte Beispiel ermöglicht die flexible Festlegung des Mindesttermins entsprechend Ihren Projektanforderungen.
### Wo finde ich zusätzliche Unterstützung für Aspose.Tasks für Java?
 Besuche den[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und Diskussionen.
### Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
 Ja, Sie können darauf zugreifen[Kostenlose Testphase](https://releases.aspose.com/) um die Funktionen vor dem Kauf zu erkunden.
### Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
 Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/) zu Testzwecken.