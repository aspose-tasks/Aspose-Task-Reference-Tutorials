---
title: Definieren Sie Wochentage im Kalender mit Aspose.Tasks
linktitle: Definieren Sie Wochentage im Kalender mit Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Wochentage im MS Project-Kalender definieren. Passen Sie Arbeitstage und -zeiten mühelos an.
type: docs
weight: 12
url: /de/java/calendars/define-weekdays/
---
## Einführung
In diesem Tutorial werden wir den Prozess der Definition von Wochentagen in einem MS Project-Kalender mit Aspose.Tasks für Java durchgehen. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es hier herunterladen[Oracle-Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) falls Sie es noch nicht getan haben.
2.  Aspose.Tasks for Java-Bibliothek: Laden Sie die Aspose.Tasks for Java-Bibliothek von herunter und installieren Sie sie[Download-Seite](https://releases.aspose.com/tasks/java/). Befolgen Sie die Installationsanweisungen in der Dokumentation.

## Pakete importieren
Importieren Sie zunächst die notwendigen Pakete, die für die Arbeit mit Aspose.Tasks in Ihrem Java-Projekt erforderlich sind:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Schritt 1: Erstellen Sie eine Projektinstanz
Instanziieren Sie ein Project-Objekt, das die MS Project-Datei darstellt, mit der Sie arbeiten werden:
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Schritt 2: Kalender definieren
Erstellen Sie eine neue Kalenderinstanz und fügen Sie sie dem Projekt hinzu:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Schritt 3: Arbeitstage hinzufügen
Definieren Sie die Arbeitstage, indem Sie Montag bis Donnerstag mit Standardzeiten hinzufügen:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Schritt 4: Legen Sie einen benutzerdefinierten Arbeitstag fest
Definieren Sie Samstag und Sonntag als Arbeitstage:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Schritt 5: Legen Sie einen kurzen Arbeitstag fest
Legen Sie den Freitag als kurzen Arbeitstag mit benutzerdefinierten Arbeitszeiten fest:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## Schritt 6: Speichern Sie das Projekt
Speichern Sie das geänderte Projekt in einer XML-Datei:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Abschluss
Glückwunsch! Sie haben mit Aspose.Tasks für Java erfolgreich Wochentage in einem MS Project-Kalender definiert. Sie können diese Funktionalität jetzt in Ihre Java-Anwendungen integrieren, um MS Project-Dateien programmgesteuert zu bearbeiten.
## FAQs
### F1: Kann ich mit Aspose.Tasks für Java benutzerdefinierte arbeitsfreie Tage definieren?
 A: Ja, Sie können benutzerdefinierte arbeitsfreie Tage definieren, indem Sie Folgendes festlegen`DayWorking` Eigentum zu`false` für den jeweiligen Wochentag.
### F2: Wie kann ich Feiertage zum Kalender hinzufügen?
 A: Sie können Feiertage hinzufügen, indem Sie Instanzen davon erstellen`CalendarExceptions`und Angabe der arbeitsfreien Tage.
### F3: Ist Aspose.Tasks mit verschiedenen Versionen von MS Project-Dateien kompatibel?
A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von MS Project-Dateien, einschließlich der Formate MPP, MPT und XML.
### F4: Kann ich vorhandene Kalender in einer MS Project-Datei ändern?
A: Ja, Sie können ein vorhandenes Projekt mit Kalendern laden, Änderungen vornehmen und die Änderungen dann wieder in der Originaldatei speichern.
### F5: Bietet Aspose.Tasks Unterstützung für wiederkehrende Aufgaben?
A: Ja, Aspose.Tasks ermöglicht Ihnen die Arbeit mit wiederkehrenden Aufgaben, einschließlich der Definition ihrer Wiederholungsmuster und -dauer.