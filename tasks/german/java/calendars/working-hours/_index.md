---
title: Rufen Sie mit Aspose.Tasks die Arbeitszeiten aus dem Kalender ab
linktitle: Rufen Sie mit Aspose.Tasks die Arbeitszeiten aus dem Kalender ab
second_title: Aspose.Tasks Java-API
description: Extrahieren Sie ganz einfach Arbeitsstunden aus MS Project-Kalendern mit Aspose.Tasks für Java. Vereinfachen Sie Projektmanagementaufgaben.
weight: 13
url: /de/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rufen Sie mit Aspose.Tasks die Arbeitszeiten aus dem Kalender ab

## Einführung
Das Verwalten von Projektkalendern und das Extrahieren von Arbeitszeiten ist für ein effektives Projektmanagement unerlässlich. Aspose.Tasks für Java bietet robuste Funktionen zum mühelosen Abrufen von Arbeitsstunden aus MS Project-Kalendern. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK) auf Ihrem System installiert.
2.  Aspose.Tasks für Java-Bibliothek heruntergeladen und Ihrem Projekt hinzugefügt. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
3. Grundlegendes Verständnis der Programmiersprache Java.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete, um mit Aspose.Tasks für Java zu arbeiten:
```java
import com.aspose.tasks.*;
```
## Schritt 1: Projektdatei laden
Laden Sie zunächst Ihre MS Project-Datei:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Schritt 2: Aufgaben- und Kalenderinformationen abrufen
Extrahieren Sie Aufgaben- und Kalenderdetails aus dem Projekt:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Schritt 3: Definieren Sie Start- und Enddatum
Legen Sie Start- und Enddatum für die Aufgabe fest:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Schritt 4: Iterieren Sie die Daten
Iterieren Sie die Daten innerhalb der Aufgabendauer:
```java
java.util.Calendar tempDate = calStartDate;
```
## Schritt 5: Dauer berechnen
Berechnen Sie die Dauer in Minuten, Stunden und Tagen:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Abschluss
In diesem Tutorial haben wir behandelt, wie Sie mit Aspose.Tasks für Java Arbeitsstunden aus einem MS Project-Kalender abrufen. Wenn Sie diese Schritte befolgen, können Sie Projektzeitpläne effizient verwalten und die Aufgabendauer problemlos berechnen.
## FAQs
### F: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet umfassende Unterstützung für die Handhabung komplexer Projektstrukturen, einschließlich Aufgaben, Ressourcen und Kalender.
### F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?
A: Auf jeden Fall unterstützt Aspose.Tasks für Java verschiedene Versionen von MS Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### F: Kann ich Arbeitszeiten und Feiertage in Projektkalendern anpassen?
A: Ja, Sie können Arbeits- und Feiertage ganz einfach an Ihre Projektanforderungen anpassen, indem Sie Aspose.Tasks für Java-APIs verwenden.
### F: Bietet Aspose.Tasks für Java Support und Dokumentation?
A: Ja, Aspose.Tasks für Java bietet umfangreiche Dokumentation und spezielle Support-Foren, um Entwickler bei der effektiven Nutzung seiner Funktionen zu unterstützen.
### F: Gibt es eine Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können auf eine kostenlose Testversion von Aspose.Tasks für Java zugreifen[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
