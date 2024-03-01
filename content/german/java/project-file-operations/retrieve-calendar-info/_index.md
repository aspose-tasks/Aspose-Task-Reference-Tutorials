---
title: Rufen Sie MS Project-Kalenderinformationen in Aspose.Tasks ab
linktitle: Kalenderinformationen in Aspose.Tasks abrufen
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java MS Project-Kalenderinformationen abrufen. Schritt-für-Schritt-Anleitung für den programmgesteuerten Zugriff auf Kalenderdetails.
type: docs
weight: 14
url: /de/java/project-file-operations/retrieve-calendar-info/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Tasks for Java-Bibliothek Kalenderinformationen aus Microsoft Project-Dateien abrufen. Aspose.Tasks bietet leistungsstarke Funktionen zur Bearbeitung von Projektdaten, einschließlich des Zugriffs auf Kalenderdetails wie Arbeitstage und -stunden.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Java-Programmierung.
- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Tasks für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihren Java-Code importieren, um die Funktionen von Aspose.Tasks nutzen zu können.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Lassen Sie uns nun zum besseren Verständnis das bereitgestellte Beispiel in mehrere Schritte aufteilen.
## Schritt 1: Datenverzeichnis festlegen
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrem Projektdateiverzeichnis.
## Schritt 2: Zeiteinheiten definieren
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Diese Konstanten stellen Zeiteinheiten in Mikrosekunden dar.
## Schritt 3: Projektinstanz erstellen
```java
Project project = new Project(dataDir + "project.mpp");
```
 Diese Zeile erstellt eine Instanz von`Project` Klasse, initialisieren Sie sie mit dem Pfad zur Projektdatei (`project.mpp`).
## Schritt 4: Kalenderinformationen abrufen
```java
CalendarCollection alCals = project.getCalendars();
```
Hier rufen wir eine Sammlung von Kalendern ab, die in der Projektdatei vorhanden sind.
## Schritt 5: Kalender durchlaufen
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Kalenderinformationen
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Durch WeekDays iterieren
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Zeit in Millisekunden
            double time = ts / (OneHour); // In Stunden umrechnen
            if (wd.getDayWorking()) {
                // Arbeitstage und -stunden anzeigen
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Diese Schleife durchläuft jeden Kalender und gibt dessen UID, Namen und Arbeitstage mit den jeweiligen Arbeitszeiten aus.
## Schritt 6: Abschlussmeldung anzeigen
```java
System.out.println("Process completed Successfully");
```
Abschließend wird eine Meldung angezeigt, die den Abschluss des Vorgangs anzeigt.
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java Kalenderinformationen aus MS Project-Dateien abruft. Wenn Sie diese Schritte befolgen, können Sie in Ihren Java-Anwendungen effizient auf Projektdaten zugreifen und diese bearbeiten.

## FAQs
### F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
A: Ja, Aspose.Tasks unterstützt mehrere Plattformen und Programmiersprachen, einschließlich .NET, C++, Python und Java.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks?
 A: Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### F: Wie kann ich Unterstützung für Aspose.Tasks erhalten?
A: Sie können Unterstützung vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks erwerben?
 A: Ja, temporäre Lizenzen können erworben werden[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo finde ich eine ausführliche Dokumentation zu Aspose.Tasks?
 A: Sie können sich auf die Dokumentation beziehen[Hier](https://reference.aspose.com/tasks/java/).