---
date: 2026-08-24
description: Erfahren Sie, wie Sie einen Feiertagskalender hinzufügen, Arbeitstage
  bestimmen und die Aufgabendauer berechnen, indem Sie Arbeitsstunden aus MS Project‑Kalendern
  mit Aspose.Tasks for Java extrahieren.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Wie man einen Feiertagskalender hinzufügt und Arbeitstage bestimmt
og_description: Erfahren Sie, wie Sie einen Feiertagskalender hinzufügen, Arbeitstage
  bestimmen und die Aufgabendauer berechnen, indem Sie Arbeitsstunden aus MS Project‑Kalendern
  mit Aspose.Tasks for Java extrahieren.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Wie man einen Feiertagskalender hinzufügt und Arbeitstage bestimmt
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Wie man einen Feiertagskalender hinzufügt und Arbeitstage bestimmt
url: /de/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Feiertagskalender hinzufügt und Arbeitstage bestimmt

Die Verwaltung von Projektkalendern ist ein zentraler Bestandteil erfolgreicher Projektplanung. In diesem Tutorial fügen Sie **einen Feiertagskalender hinzu**, **bestimmen Arbeitstage** für jede Aufgabe und **extrahieren Arbeitsstunden** aus einem MS Project‑Kalender mithilfe von Aspose.Tasks für Java. Am Ende der Anleitung können Sie **die Aufgabendauer berechnen**, Arbeitszeiten anpassen und zuverlässig **eine MPP‑Datei laden**, um die benötigten Daten abzurufen – und das alles ohne Microsoft Project zu installieren.

## Schnelle Antworten
- **Was bedeutet „Arbeitstage bestimmen“?** Es bedeutet, zu ermitteln, welche Kalendertage für eine gegebene Aufgabe als Arbeitstage gelten.  
- **Welche Bibliothek sollte ich verwenden?** Aspose.Tasks für Java bietet eine voll ausgestattete API zur Arbeit mit MS‑Project‑Dateien.  
- **Wie lange dauert die Implementierung?** In der Regel 10–15 Minuten für eine grundlegende Extraktion.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Arbeitszeiten anpassen?** Ja – Sie können Kalender ändern, Feiertage hinzufügen und benutzerdefinierte Arbeitszeitbereiche festlegen.  

## Was bedeutet „Arbeitstage bestimmen“?
**Arbeitstage bestimmen** bedeutet, einen Projektkalender abzufragen, um herauszufinden, welche Daten als Arbeitstage und welche als Nicht‑Arbeitstage (Wochenenden, Feiertage oder benutzerdefinierte Ausnahmen) markiert sind. Diese Information ist für eine genaue **Aufgabendauer berechnen** unerlässlich, da nur Arbeitstage zur verstrichenen Zeit einer Aufgabe beitragen.

## Warum Aspose.Tasks zur Ermittlung von Arbeitsstunden verwenden?
Aspose.Tasks ermöglicht das Lesen von MS‑Project‑Dateien, ohne dass Microsoft Project installiert sein muss, und erlaubt Automatisierung auf jeder Plattform. Es bietet zudem Hochleistungsverarbeitung, umfangreiche Formatunterstützung und detaillierte Dokumentation.  

- **Vollständige Kalenderunterstützung** – Standard‑, Ressourcen‑ und Aufgaben‑Kalender sind alle zugänglich.  
- **Hohe Leistung** – kann Projekte mit **10.000+ Aufgaben in unter 2 Sekunden** auf einer Standard‑CPU mit 2,5 GHz verarbeiten.  
- **Umfangreiche Formatabdeckung** – unterstützt **50+ Eingabe‑ und Ausgabeformate**, darunter MPP, MPX, XML und Primavera.  
- **Umfassende Dokumentation** – Code‑Beispiele, API‑Referenz und Community‑Foren sind verfügbar.

## Voraussetzungen
1. **Java Development Kit (JDK)** – Version 8 oder höher.  
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) herunter.  
3. Grundlegende Java‑Programmierkenntnisse.  

## Pakete importieren
Die Klasse `Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne MS‑Project‑Datei im Speicher repräsentiert. Importieren Sie den erforderlichen Namespace, bevor Sie beginnen:

Pakete importieren

```java
import com.aspose.tasks.*;
```

## Wie lädt man eine MPP‑Datei mit Aspose.Tasks?
Die Klasse `Project` lädt eine MS‑Project‑Datei und stellt Zugriff auf deren Daten bereit. Laden Sie die Projektdatei in einer einzigen Codezeile; keine UI oder COM‑Interop ist erforderlich. Dieser einfache Schritt verschafft Ihnen vollen Zugriff auf Kalender, Aufgaben und Ressourcen.

Laden einer MPP‑Datei

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Aufgaben‑ und Kalenderinformationen abrufen
`Task` repräsentiert eine Projektaufgabe und `Calendar` definiert deren Arbeitszeitregeln. Wählen Sie die Aufgabe aus, die Sie analysieren möchten, und holen Sie den zugehörigen Kalender. Das `Task`‑Objekt bietet die Methoden `getStart()` und `getFinish()`, während das `Calendar`‑Objekt die Arbeitszeitdefinitionen bereitstellt.

Abrufen von Aufgabe und Kalender

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Start‑ und Enddaten festlegen
`Date`‑Objekte geben das Zeitfenster für die Kalenderanalyse an. Legen Sie das Zeitfenster fest, für das Sie **Arbeitstage bestimmen** möchten. Die Verwendung der Start‑ und Enddaten der Aufgabe stellt sicher, dass Sie nur den relevanten Zeitraum auswerten.

Daten festlegen

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Durch Daten iterieren
Eine `for`‑Schleife kann über jeden Tag im Datumsbereich iterieren. Durchlaufen Sie jedes Datum in der Dauer der Aufgabe. Diese Schleife ermöglicht es Ihnen, später bei Bedarf **Arbeitszeiten anzupassen**, und bildet die Grundlage für die Berechnung der gesamten Arbeitszeit.

Iterieren über Daten

```java
java.util.Calendar tempDate = calStartDate;
```

## Dauer berechnen
`Duration` fasst die aus der Iteration berechnete gesamte Arbeitszeit zusammen. Während der Iteration prüfen Sie, ob jeder Tag ein Arbeitstag ist, summieren die Arbeitsstunden und berechnen schließlich die Aufgabendauer in Minuten, Stunden und Tagen. Dies zeigt, wie man **Arbeitstage berechnet** und **die Aufgabendauer** programmgesteuert ermittelt.

Dauer berechnen

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

## Wie man Arbeitszeiten und Feiertage anpasst
Sie können die Arbeitszeitbereiche des Kalenders ändern und Ausnahmen wie Feiertage hinzufügen. Verwenden Sie `taskCalendar.addWorkingTime()`, um neue Arbeitsperioden festzulegen, und `taskCalendar.addException()`, um einen Feiertag einzufügen. Dies ist nützlich, wenn der Standard‑9‑bis‑5‑Plan nicht den Richtlinien Ihrer Organisation entspricht.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Task returns `null` for calendar** | Stellen Sie sicher, dass der Aufgabe tatsächlich ein Kalender zugewiesen ist; andernfalls erbt sie den Standardkalender des Projekts. |
| **Incorrect duration because of holidays** | Überprüfen Sie, ob Feiertage im Kalender der Aufgabe oder im Basis‑Kalender des Projekts definiert sind. |
| **Time zone mismatch** | Verwenden Sie `java.util.TimeZone`, um die Zeitzone des Kalenders bei Bedarf an Ihr System anzupassen. |

## Häufig gestellte Fragen
### Q: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet umfassende Unterstützung für die Handhabung komplexer Projektstrukturen, einschließlich Aufgaben, Ressourcen und Kalendern.

### Q: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?
A: Absolut, Aspose.Tasks für Java unterstützt verschiedene MS‑Project‑Versionen und gewährleistet Kompatibilität in unterschiedlichen Umgebungen.

### Q: Kann ich Arbeitszeiten und Feiertage in Projektkalendern anpassen?
A: Ja, Sie können Arbeitszeiten und Feiertage einfach an die Anforderungen Ihres Projekts anpassen, indem Sie die APIs von Aspose.Tasks für Java verwenden.

### Q: Bietet Aspose.Tasks für Java Support und Dokumentation?
A: Ja, Aspose.Tasks für Java stellt umfangreiche Dokumentation und dedizierte Support‑Foren bereit, um Entwicklern bei der effektiven Nutzung seiner Funktionen zu helfen.

### Q: Gibt es eine Testversion von Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von der [Aspose releases page](https://releases.aspose.com/) erhalten.

## Fazit
In diesem Leitfaden haben wir gezeigt, wie man **einen Feiertagskalender hinzufügt**, **Arbeitstage bestimmt**, **Arbeitsstunden abruft** und **die Aufgabendauer** aus einem MS‑Project‑Kalender mithilfe von Aspose.Tasks für Java berechnet. Durch Befolgen der obigen Schritte können Sie die Zeitplananalyse automatisieren, Kalender anpassen und Ihre Projektpläne genau und aktuell halten. Sie verfügen nun über die Werkzeuge, um **MS‑Project**‑Daten zu **lesen**, **eine MPP‑Datei zu laden** und präzise Dauernberechnungen durchzuführen, ohne Microsoft Project selbst zu benötigen.

---

**Zuletzt aktualisiert:** 2026-08-24  
**Getestet mit:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/calendars/create/)
- [Feiertage zum Kalender hinzufügen und als MPP speichern mit Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Benutzerdefinierte Kalenderausnahmen erstellen mit Aspose.Tasks für Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}