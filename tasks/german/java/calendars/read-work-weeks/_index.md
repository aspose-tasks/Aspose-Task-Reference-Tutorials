---
title: Lesen Sie Arbeitswochen aus dem MS Project-Kalender mit Aspose.Tasks
linktitle: Lesen Sie Arbeitswochen aus dem Kalender mit Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Arbeitswochen aus dem MS Project-Kalender lesen. Erhalten Sie Schritt-für-Schritt-Anleitungen in diesem umfassenden Tutorial.
weight: 15
url: /de/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lesen Sie Arbeitswochen aus dem MS Project-Kalender mit Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java Arbeitswocheninformationen aus einem Microsoft Project-Kalender lesen. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, mit der Sie Microsoft Project-Dokumente programmgesteuert bearbeiten und verwalten können.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK) auf Ihrem System installiert.
2.  Aspose.Tasks für Java-Bibliothek heruntergeladen und installiert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Importieren wir zunächst die notwendigen Pakete, um mit unserem Code zu beginnen:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Schritt 1: Richten Sie Ihr Datenverzeichnis ein
Richten Sie den Verzeichnispfad ein, in dem sich Ihre MS Project-Datei befindet:
```java
String dataDir = "Your Data Directory";
```
## Schritt 2: Projektinstanz erstellen und auf Kalender zugreifen
Erstellen Sie eine neue Instanz der Project-Klasse und greifen Sie auf die Kalender- und Arbeitswochensammlung zu:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Schritt 3: Arbeitswochen durchlaufen
Durchlaufen Sie die Sammlung der Arbeitswochen und zeigen Sie deren Informationen an:
```java
for (WorkWeek workWeek : collection) {
    // Zeigt den Namen der Arbeitswoche sowie das Von- und Bis-Datum an
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Greifen Sie auf Wochentage und Arbeitszeiten zu
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Weitere Bearbeitungszeiten bei Bedarf
    }
}
```
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java Arbeitswocheninformationen aus einem Microsoft Project-Kalender liest. Diese leistungsstarke Bibliothek ermöglicht die nahtlose Bearbeitung von Projektdateien und ermöglicht Entwicklern die effiziente Automatisierung verschiedener Aufgaben.
## FAQs
### Kann ich die Informationen zur Arbeitswoche mit Aspose.Tasks für Java ändern?
Ja, Aspose.Tasks bietet APIs zum Ändern, Hinzufügen oder Löschen von Arbeitswochen und den damit verbundenen Informationen.
### Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project-Dateien kompatibel?
Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich MPP- und XML-Formate.
### Kann ich Aspose.Tasks mit anderen Java-Frameworks integrieren?
Aspose.Tasks kann auf jeden Fall nahtlos in andere Java-Frameworks und -Bibliotheken integriert werden, um die Funktionalität zu erweitern.
### Gibt es eine Testversion für Aspose.Tasks?
 Ja, Sie können eine kostenlose Testversion von Aspose.Tasks herunterladen unter[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Tasks?
Unterstützung und Hilfe finden Sie im Aspose.Tasks-Forum[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
