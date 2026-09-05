---
date: 2026-08-08
description: Erfahren Sie, wie Sie den Kalender in MS Project einstellen, tägliche
  Arbeitszeiten festlegen und Wochenendarbeitstage mit Aspose.Tasks für Java hinzufügen.
  Speichern Sie das Projekt als XML in nur wenigen Codezeilen.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Wie man den Kalender in MS Project einstellt und Wochentage definiert
og_description: Kalender in MS Project einstellen, Wochentage definieren und Wochenendarbeitstage
  mit Aspose.Tasks für Java hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung
  und speichern Sie als XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Kalender in MS Project mit Aspose.Tasks – Java‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Wie man den Kalender in MS Project einstellt und Wochentage definiert
url: /de/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Kalender in MS Project festlegt und Wochentage definiert

In diesem Tutorial lernen Sie **how to set calendar ms project** programmgesteuert, definieren Wochentage und konfigurieren benutzerdefinierte Arbeitstage mit der Aspose.Tasks-Bibliothek für Java. Egal, ob Sie eine Terminplanungs-Engine bauen, in ERP‑Systeme integrieren oder einfach einen Projektplan erstellen müssen, ohne Microsoft Project zu öffnen – die nachfolgenden Schritte zeigen Ihnen, wie Sie einen Kalender erstellen, tägliche Arbeitsstunden festlegen und Wochenend‑Arbeitstage in wenigen Codezeilen hinzufügen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Tasks for Java.  
- **Kann ich Wochenend‑Arbeitstage hinzufügen?** Ja – markieren Sie einfach Samstag und Sonntag als Arbeitstage.  
- **Wie speichere ich das Projekt?** Rufen Sie `prj.save(..., SaveFileFormat.Xml)` auf.  
- **Wird eine Lizenz benötigt?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.

## Was ist set calendar ms project?
Das Festlegen des Kalenders in MS Project bestimmt, welche Tage als Arbeitstage gelten, die Anzahl der Arbeitsstunden pro Tag und besondere Ausnahmen wie Feiertage oder unternehmensweite Stilllegungen. Diese Informationen steuern die Aufgabenzuweisung, Ressourcenallokation und die gesamten Projektzeitpläne und stellen sicher, dass Berechnungen den tatsächlichen Arbeitsabläufen der Organisation entsprechen.

## Warum Aspose.Tasks für die Kalendermanipulation verwenden?
Aspose.Tasks bietet Ihnen programmatischen Zugriff auf Kalender, ohne die Microsoft Project‑Benutzeroberfläche zu starten. Es läuft auf jedem Betriebssystem, das Java unterstützt, unterstützt mehr als 50 Eingabe‑ und Ausgabeformate und kann mehrseitige Projekte verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was es ideal für serverseitige Automatisierung macht.

## Voraussetzungen
- **Java Development Kit (JDK) 8+** – herunterladen von der [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – das neueste JAR von der [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) beziehen.  
- Eine IDE oder ein Build‑Tool (Maven/Gradle), um das Aspose.Tasks‑JAR zu Ihrem Klassenpfad hinzuzufügen.

## Pakete importieren
Importieren Sie die Klassen, die Zugriff auf Projekte, Kalender und Arbeitszeit‑Objekte bieten.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projektinstanz erstellen
Instanziieren Sie ein `Project`‑Objekt, das die MS Project‑Datei repräsentiert, die Sie manipulieren werden.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Schritt 2: Neuen Kalender definieren
`Calendar` repräsentiert eine Menge von Arbeitszeiten, Ausnahmen und Feiertagen für ein Projekt.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Schritt 3: Standard‑Arbeitstage hinzufügen (Montag‑Donnerstag)
`WeekDay` definiert die Arbeitszeit für einen bestimmten Wochentag.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Schritt 4: Wochenend‑Arbeitstage hinzufügen
Wenn Ihr Projekt an Wochenenden läuft, fügen Sie Samstag und Sonntag als reguläre Arbeitstage hinzu. Dies demonstriert **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Schritt 5: Benutzerdefinierten kurzen Arbeitstag festlegen (Freitag)
Konfigurieren Sie Freitag mit einer Morgenschicht (9 Uhr‑12 Uhr) und einer Nachmittagsschicht (13 Uhr‑16 Uhr), um **set daily working hours** und einen benutzerdefinierten kurzen Arbeitstag zu veranschaulichen.

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

### Schritt 6: Projekt als XML speichern
`SaveFileFormat` enumeriert die unterstützten Dateiformate beim Speichern eines Projekts, wie XML oder MPP.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Häufige Probleme & Lösungen
| Problem | Lösung |
|-------|----------|
| **Arbeitszeiten nicht angewendet** | Stellen Sie sicher, dass `setDayWorking(true)` für jedes benutzerdefinierte `WeekDay` aufgerufen wird. |
| **Datei beim Speichern nicht gefunden** | Vergewissern Sie sich, dass `dataDir` auf einen vorhandenen Ordner zeigt und die Anwendung Schreibrechte hat. |
| **Kalender wird in Aufgaben nicht übernommen** | Weisen Sie den neu erstellten Kalender Ressourcen oder Aufgaben zu, indem Sie `task.setCalendar(cal)` verwenden. |

## Häufig gestellte Fragen

**F: Kann ich benutzerdefinierte Nicht‑Arbeitstage mit Aspose.Tasks für Java definieren?**  
A: Ja. Setzen Sie die Eigenschaft `DayWorking` auf `false` für jedes `WeekDay`, das Sie als Nicht‑Arbeitstag behandeln möchten.

**F: Wie kann ich Feiertage oder unternehmensweite Ausnahmen hinzufügen?**  
A: Erstellen Sie `CalendarException`‑Objekte, geben Sie die Ausnahmedaten an und fügen Sie sie zu `cal.getExceptions()` hinzu.

**F: Ist die Bibliothek mit älteren MS Project‑Versionen kompatibel?**  
A: Absolut. Aspose.Tasks unterstützt MPP-, MPT- und XML‑Formate über mehrere Project‑Versionen hinweg.

**F: Kann ich einen bestehenden Kalender in einem importierten Projekt ändern?**  
A: Laden Sie das Projekt mit `new Project("existing.mpp")`, holen Sie den gewünschten Kalender, nehmen Sie Änderungen vor und speichern Sie.

**F: Unterstützt Aspose.Tasks auch wiederkehrende Aufgaben?**  
A: Ja, Sie können wiederkehrende Aufgaben mit der Klasse `RecurringTask` erstellen und bearbeiten.

## Fazit
Sie wissen jetzt, **how to set calendar ms project**, Wochentage zu definieren, Wochenend‑Arbeitstage hinzuzufügen und einen kurzen Freitags‑Zeitplan zu konfigurieren – alles mit Aspose.Tasks für Java. Speichern Sie das Ergebnis als XML und integrieren Sie die Kalenderlogik in jede Java‑basierte Projektmanagement‑Lösung.

---

**Zuletzt aktualisiert:** 2026-08-08  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/calendars/create/)
- [Arbeits‑Tage & Arbeits‑Stunden bestimmen mit Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Feiertage zum Kalender hinzufügen und als MPP speichern mit Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}