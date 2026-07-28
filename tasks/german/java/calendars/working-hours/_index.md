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

## Einführung
Das Verwalten von Projektkalendern ist ein zentraler Bestandteil einer erfolgreichen Projektplanung. In diesem Tutorial **bestimmen Sie Arbeitstage** für jede Aufgabe und **extrahieren Arbeitszeiten** aus einem MSProject-Kalender mithilfe von Aspose.Tasks für Java. Am Ende der Anleitung können Sie **die Aufgabendauer berechnen**, Arbeitszeiten anpassen und zuverlässig **eine MPP-Datei laden**, um die benötigten Daten abzurufen. Außerdem sehen Sie, wie Sie **MSProject-Dateien lesen** können, ohne MicrosoftProject installiert zu haben, sodass Automatisierung auf jeder Plattform möglich ist.

## Schnelle Antworten
- **Was bedeutet „Arbeitstage bestimmen“?**Es bedeutet, die Kalendertage zu ermitteln, die für eine gegebene Aufgabe als Arbeitstage gelten.
- **Welche Bibliothek sollte ich verwenden?**Aspose.Tasks für Java bietet eine voll ausgestattete API zum Arbeiten mit MSProject‑Dateien.
- **Wie lange dauert die Implementierung?**In der Regel 10–15 Minuten für eine einfache Extraktion.
- **Benötige ich eine Lizenz?**Eine kostenlose Testversion ist verfügbar; Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.
- **Kann ich Arbeitszeiten anpassen?**Ja – Sie können Kalender ändern, Feiertage hinzufügen und benutzerdefinierte Arbeitszeitbereiche festlegen.

## Was ist „Arbeitstage festlegen“?
Wenn eine Aufgabe geplant wird, definiert der Projektkalender, welche Tage Arbeitstage und welche Tage Nicht‑Arbeitstage (Wochenenden, Feiertage) sind. Das Bestimmen von Arbeitstagen bedeutet, diesen Kalender abzufragen, um genau zu wissen, wann Arbeit stattfinden kann – das ist entscheidend für präzise **Berechnungen der Aufgabendauer**-Berechnungen.

## Warum Aspose.Tasks verwenden, um Arbeitsstunden abzurufen?
- **Kein MicrosoftProject erforderlich** – Sie können MSProject‑Dateien direkt aus Java‑Code lesen.
- **Vollständige Kalenderunterstützung** – beinhaltet Standard‑, Ressourcen‑ und Aufgaben‑Kalender.
- **Hohe Leistung** – große Projekte werden schnell verarbeitet.
- **Umfangreiche Dokumentation** – Beispiele und API-Referenz sind leicht verfügbar.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version8 oder höher.
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von [hier](https://releases.aspose.com/tasks/java/) herunter.
3. Grundkenntnisse in Java‑Programmierung.

## Pakete importieren
Zuerst importieren Sie den Kern-Namespace von Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Wie lade ich eine MPP-Datei mit Aspose.Tasks?
Das Laden der Projektdatei ist der erste Schritt für jede Kalenderanalyse. Die API ermöglicht es Ihnen, **eine MPP‑Datei** in einer einzigen Code‑Zeile zu **laden**, ohne die MS Project‑Benutzeroberfläche zu benötigen.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Aufgaben- und Kalenderinformationen abrufen
Wählen Sie die Aufgabe aus, die Sie analysieren möchten, und holen Sie den zugehörigen Kalender. Hier **holen wir die Arbeitszeiten** für die Aufgabe:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Start- und Enddatum definieren
Richten Sie das Zeitfenster ein, für das Sie **Arbeitstage bestimmen** möchten. Die Verwendung der Start‑ und Enddaten der Aufgabe stellt sicher, dass Sie nur den relevanten Zeitraum auswerten.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Datumsangaben durchlaufen
Durchlaufen Sie jedes Datum in der Aufgabendauer. Diese Schleife hilft Ihnen später, **Arbeitszeiten anzupassen**, falls nötig:

```java
java.util.Calendar tempDate = calStartDate;
```

## Dauer berechnen
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

## So passen Sie Arbeitszeiten und Feiertage an
Aspose.Tasks ermöglicht es Ihnen, die Arbeitszeitbereiche des Kalenders zu ändern und Ausnahmen wie Feiertage hinzuzufügen. Sie können „taskCalendar.addWorkingTime()“ oder „taskCalendar.addException()“ aufrufen, um den Zeitplan an die Richtlinien Ihrer Organisation anzupassen. Das ist nützlich, wenn der Standard-9-bis-5-Plan nicht der Realität entspricht.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Aufgabe gibt „null“ für Kalender zurück** | Stellen Sie sicher, dass der Aufgabe tatsächlich ein Kalender zugewiesen ist; Ansonsten erbt sie den Standard-Kalender des Projekts. |
| **Falsche Dauer aufgrund von Feiertagen** | Prüfen Sie, ob Feiertage im Kalender der Aufgabe oder im Basiskalender des Projekts definiert sind. |
| **Zeitzonenkonflikt** | Verwenden Sie `java.util.TimeZone`, um die Zeitzone des Kalenders bei Bedarf an Ihr System anzupassen.

## Häufig gestellte Fragen
### F: Kann Aspose.Tasks für Java komplexe Projektstrukturen verwalten?

A: Ja, Aspose.Tasks für Java bietet umfassende Unterstützung für die Verwaltung komplexer Projektstrukturen, einschließlich Aufgaben, Ressourcen und Kalender.

### F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?

A: Absolut, Aspose.Tasks für Java unterstützt verschiedene Versionen von MS Project und gewährleistet so Kompatibilität in unterschiedlichen Umgebungen.

### F: Kann ich Arbeitszeiten und Feiertage in Projektkalendern anpassen?

A: Ja, Sie können Arbeitszeiten und Feiertage mithilfe der Aspose.Tasks für Java APIs ganz einfach an Ihre Projektanforderungen anpassen.

### F: Bietet Aspose.Tasks für Java Support und Dokumentation?

A: Ja, Aspose.Tasks für Java bietet umfangreiche Dokumentation und spezielle Supportforen, um Entwickler bei der effektiven Nutzung der Funktionen zu unterstützen.

### F: Gibt es eine Testversion von Aspose.Tasks für Java?

A: Ja, Sie können hier eine kostenlose Testversion von Aspose.Tasks für Java herunterladen: [https://releases.aspose.com/].

## Fazit
In dieser Anleitung haben wir gezeigt, wie Sie mit Aspose.Tasks für Java **Arbeitstage ermitteln**, **Arbeitsstunden abrufen** und **die Aufgabendauer berechnen** können. Mit den oben beschriebenen Schritten können Sie die Terminplananalyse automatisieren, Kalender anpassen und Ihre Projektpläne stets aktuell halten. Sie verfügen nun über die nötigen Werkzeuge, um **MS Project-Daten** zu lesen, **MPP-Dateien zu laden** und präzise Dauerberechnungen durchzuführen – ganz ohne Microsoft Project selbst.

---

**Letzte Aktualisierung:** 05.02.2026
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung aktuellste Version)
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}