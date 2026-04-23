---
date: 2026-02-05
description: Erfahren Sie, wie Sie Arbeitstage bestimmen und die Aufgabendauer berechnen,
  indem Sie Arbeitszeiten aus MS Project‑Kalendern mit Aspose.Tasks für Java extrahieren.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Arbeitszeiten und Arbeitstage mit Aspose.Tasks bestimmen
url: /de/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestimmen von Arbeitstagen & Arbeitszeiten mit Aspose.Tasks

## Introduction
Das Verwalten von Projektkalendern ist ein zentraler Bestandteil einer erfolgreichen Projektplanung. In diesem Tutorial **bestimmen Sie Arbeitstage** für jede Aufgabe und **extrahieren Arbeitszeiten** aus einem MS Project‑Kalender mithilfe von Aspose.Tasks für Java. Am Ende der Anleitung können Sie **die Aufgabendauer berechnen**, Arbeitszeiten anpassen und zuverlässig **eine MPP‑Datei laden**, um die benötigten Daten abzurufen. Außerdem sehen Sie, wie Sie **MS Project‑Dateien lesen** können, ohne Microsoft Project installiert zu haben, sodass Automatisierung auf jeder Plattform möglich ist.

## Quick Answers
- **Was bedeutet „determine working days“?** Es bedeutet, die Kalendertage zu ermitteln, die für eine gegebene Aufgabe als Arbeitstage gelten.  
- **Welche Bibliothek sollte ich verwenden?** Aspose.Tasks für Java bietet eine voll ausgestattete API zum Arbeiten mit MS Project‑Dateien.  
- **Wie lange dauert die Implementierung?** In der Regel 10–15 Minuten für eine einfache Extraktion.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Arbeitszeiten anpassen?** Ja – Sie können Kalender ändern, Feiertage hinzufügen und benutzerdefinierte Arbeitszeit‑Bereiche festlegen.  

## What is “determine working days”?
Wenn eine Aufgabe geplant wird, definiert der Projektkalender, welche Tage Arbeitstage und welche Tage Nicht‑Arbeitstage (Wochenenden, Feiertage) sind. Das Bestimmen von Arbeitstagen bedeutet, diesen Kalender abzufragen, um genau zu wissen, wann Arbeit stattfinden kann – das ist entscheidend für präzise **calculate task duration**‑Berechnungen.

## Why use Aspose.Tasks to retrieve working hours?
- **Kein Microsoft Project erforderlich** – Sie können MS Project‑Dateien direkt aus Java‑Code lesen.  
- **Vollständige Kalenderunterstützung** – beinhaltet Standard‑, Ressourcen‑ und Aufgaben‑Kalender.  
- **Hohe Leistung** – große Projekte werden schnell verarbeitet.  
- **Umfangreiche Dokumentation** – Beispiele und API‑Referenz sind leicht verfügbar.

## Prerequisites
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder höher.  
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. Grundkenntnisse in Java‑Programmierung.  

## Import Packages
Zuerst importieren Sie den Kern‑Namespace von Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## How to load an MPP file with Aspose.Tasks?
Das Laden der Projektdatei ist der erste Schritt für jede Kalenderanalyse. Die API ermöglicht es Ihnen, **eine MPP‑Datei** in einer einzigen Code‑Zeile zu **laden**, ohne die MS Project‑Benutzeroberfläche zu benötigen.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Retrieve Task and Calendar Information
Wählen Sie die Aufgabe aus, die Sie analysieren möchten, und holen Sie den zugehörigen Kalender. Hier **holen wir die Arbeitszeiten** für die Aufgabe:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Define Start and End Dates
Richten Sie das Zeitfenster ein, für das Sie **Arbeitstage bestimmen** möchten. Die Verwendung der Start‑ und Enddaten der Aufgabe stellt sicher, dass Sie nur den relevanten Zeitraum auswerten.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterate Through Dates
Durchlaufen Sie jedes Datum in der Aufgabendauer. Diese Schleife hilft Ihnen später, **Arbeitszeiten anzupassen**, falls nötig:

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculate Duration
Während der Iteration prüfen wir, ob jeder Tag ein Arbeitstag ist, summieren die Arbeitsstunden und berechnen schließlich die Aufgabendauer in Minuten, Stunden und Tagen. Dieser Schritt zeigt, wie man **working days berechnet** und **task duration programmgesteuert berechnet**.

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

## How to customize working hours and holidays
Aspose.Tasks ermöglicht es Ihnen, die Arbeitszeit‑Bereiche des Kalenders zu ändern und Ausnahmen wie Feiertage hinzuzufügen. Sie können `taskCalendar.addWorkingTime()` oder `taskCalendar.addException()` aufrufen, um den Zeitplan an die Richtlinien Ihrer Organisation anzupassen. Das ist nützlich, wenn der Standard‑9‑bis‑5‑Plan nicht der Realität entspricht.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Task returns `null` for calendar** | Stellen Sie sicher, dass der Aufgabe tatsächlich ein Kalender zugewiesen ist; andernfalls erbt sie den Standard‑Kalender des Projekts. |
| **Incorrect duration because of holidays** | Prüfen Sie, ob Feiertage im Kalender der Aufgabe oder im Basis‑Kalender des Projekts definiert sind. |
| **Time zone mismatch** | Verwenden Sie `java.util.TimeZone`, um die Zeitzone des Kalenders bei Bedarf an Ihr System anzupassen. |

## Frequently Asked Questions
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Absolutely, Aspose.Tasks for Java supports various versions of MS Project, ensuring compatibility across different environments.

### Q: Can I customize working hours and holidays in project calendars?
A: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.

### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can access a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

## Conclusion
In this guide we demonstrated how to **determine working days**, **retrieve working hours**, and **calculate task duration** from an MS Project calendar using Aspose.Tasks for Java. By following the steps above you can automate schedule analysis, customize calendars, and keep your project plans accurate and up‑to‑date. You now have the tools to **read MS Project** data, **load an MPP file**, and perform precise duration calculations without the need for Microsoft Project itself.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}