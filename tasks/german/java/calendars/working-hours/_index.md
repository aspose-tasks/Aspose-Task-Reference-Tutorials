---
date: 2025-12-05
description: Erfahren Sie, wie Sie Arbeitstage bestimmen und die Aufgabendauer berechnen,
  indem Sie Arbeitsstunden aus MS Project‑Kalendern mit Aspose.Tasks für Java extrahieren.
language: de
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Arbeitstage und Arbeitszeiten mit Aspose.Tasks bestimmen
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestimmen von Arbeitstagen & Arbeitszeiten mit Aspose.Tasks

## Einführung
Das Verwalten von Projektkalendern ist ein zentraler Bestandteil einer erfolgreichen Projektplanung. In diesem Tutorial **bestimmen Sie Arbeitstage** für jede Aufgabe und **extrahieren Arbeitszeiten** aus einem MS Project‑Kalender mithilfe von Aspose.Tasks für Java. Am Ende der Anleitung können Sie **die Aufgabendauer berechnen**, Arbeitszeiten anpassen und zuverlässig **eine MPP‑Datei laden**, um die benötigten Daten abzurufen.

## Schnelle Antworten
- **Was bedeutet „Arbeitstage bestimmen“?** Es bedeutet, die Kalendertage zu identifizieren, die für eine gegebene Aufgabe als Arbeitstage gelten.  
- **Welche Bibliothek sollte ich verwenden?** Aspose.Tasks für Java bietet eine voll ausgestattete API zum Arbeiten mit MS Project‑Dateien.  
- **Wie lange dauert die Implementierung?** In der Regel 10–15 Minuten für eine einfache Extraktion.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Arbeitszeiten anpassen?** Ja – Sie können Kalender ändern, Feiertage hinzufügen und benutzerdefinierte Arbeitszeitbereiche festlegen.

## Was bedeutet „Arbeitstage bestimmen“?
Wenn eine Aufgabe geplant wird, definiert der Projektkalender, welche Tage Arbeitstage und welche Tage Nicht‑Arbeitstage (Wochenenden, Feiertage) sind. Das Bestimmen von Arbeitstagen bedeutet, diesen Kalender abzufragen, um genau zu wissen, wann Arbeit stattfinden kann – das ist entscheidend für präzise **Aufgabendauer‑Berechnungen**.

## Warum Aspose.Tasks zum Abrufen von Arbeitszeiten verwenden?
- **Kein Microsoft Project erforderlich** – Arbeiten Sie mit .MPP‑Dateien auf jeder Plattform.  
- **Vollständige Kalenderunterstützung** – Enthält Standard‑, Ressourcen‑ und Aufgaben‑Kalender.  
- **Hohe Performance** – Große Projekte werden schnell verarbeitet.  
- **Umfangreiche Dokumentation** – Beispiele und API‑Referenz sind leicht verfügbar.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder höher.  
2. **Aspose.Tasks für Java** – Laden Sie das neueste JAR von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. Grundkenntnisse in Java‑Programmierung.  

## Pakete importieren
Zuerst importieren Sie den Kern‑Namespace von Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Schritt 1: MPP-Datei laden
Laden Sie Ihre Projektdatei (der **Load MPP File**‑Schritt), damit Sie mit deren Kalendern arbeiten können:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Schritt 2: Aufgaben- und Kalenderinformationen abrufen
Wählen Sie die Aufgabe aus, die Sie analysieren möchten, und holen Sie den zugehörigen Kalender. Hierbei **extrahieren wir die Arbeitszeiten** für die Aufgabe:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Schritt 3: Start- und Enddaten festlegen
Richten Sie das Zeitfenster ein, für das Sie **Arbeitstage bestimmen** möchten:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Schritt 4: Durch Daten iterieren
Durchlaufen Sie jedes Datum innerhalb der Aufgabendauer. Diese Schleife ermöglicht später das **Anpassen von Arbeitszeiten**, falls nötig:

```java
java.util.Calendar tempDate = calStartDate;
```

## Schritt 5: Dauer berechnen
Während der Iteration prüfen wir, ob jeder Tag ein Arbeitstag ist, summieren die Arbeitsstunden und berechnen schließlich die Aufgabendauer in Minuten, Stunden und Tagen:

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

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Aufgabe gibt `null` für Kalender zurück** | Stellen Sie sicher, dass der Aufgabe tatsächlich ein Kalender zugewiesen ist; andernfalls erbt sie den Standardkalender des Projekts. |
| **Falsche Dauer wegen Feiertagen** | Überprüfen Sie, ob Feiertage im Kalender der Aufgabe oder im Basis‑Kalender des Projekts definiert sind. |
| **Zeitzonen‑Abweichung** | Verwenden Sie `java.util.TimeZone`, um die Zeitzone des Kalenders bei Bedarf an Ihr System anzupassen. |

## Häufig gestellte Fragen
### F: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet umfassende Unterstützung für die Verarbeitung komplexer Projektstrukturen, einschließlich Aufgaben, Ressourcen und Kalendern.

### F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?
A: Absolut, Aspose.Tasks für Java unterstützt verschiedene Versionen von MS Project und stellt damit die Kompatibilität über unterschiedliche Umgebungen hinweg sicher.

### F: Kann ich Arbeitszeiten und Feiertage in Projektkalendern anpassen?
A: Ja, Sie können Arbeitszeiten und Feiertage ganz einfach an die Anforderungen Ihres Projekts anpassen, indem Sie die APIs von Aspose.Tasks für Java verwenden.

### F: Bietet Aspose.Tasks für Java Support und Dokumentation?
A: Ja, Aspose.Tasks für Java stellt umfangreiche Dokumentation sowie dedizierte Support‑Foren bereit, um Entwicklern bei der effektiven Nutzung der Funktionen zu helfen.

### F: Gibt es eine Testversion von Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java unter [hier](https://releases.aspose.com/) erhalten.

## Fazit
In diesem Leitfaden haben wir gezeigt, wie man **Arbeitstage bestimmt**, **Arbeitszeiten extrahiert** und **die Aufgabendauer** aus einem MS Project‑Kalender mithilfe von Aspose.Tasks für Java berechnet. Durch Befolgen der oben genannten Schritte können Sie die Terminplananalyse automatisieren, Kalender anpassen und Ihre Projektpläne genau und aktuell halten.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks für Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}