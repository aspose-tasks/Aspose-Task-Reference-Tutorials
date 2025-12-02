---
date: 2025-12-02
description: Erfahren Sie, wie Sie den Kalender festlegen, Wochentage in MS Project
  definieren und benutzerdefinierte Arbeitstage mit Aspose.Tasks für Java einstellen.
  Speichern Sie das Projekt als XML mit nur wenigen Codezeilen.
language: de
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man den Kalender einstellt und Wochentage in MS Project mit Aspose.Tasks
  definiert
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Kalender einstellt und Wochentage in MS Project mit Aspose.Tasks definiert

## Einleitung
In diesem Tutorial erfahren Sie **wie man Kalendereinstellungen** programmgesteuert vornimmt und Wochentage in einer Microsoft‑Project‑Datei mithilfe der Aspose.Tasks‑Bibliothek für Java definiert. Egal, ob Sie eine Standardarbeitswoche erstellen, Wochenendarbeitstage hinzufügen oder einen kurzen Freitag‑Zeitplan konfigurieren möchten – diese Anleitung führt Sie Schritt für Schritt von der Projekterstellung bis zum Speichern der Datei als XML.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java  
- **Kann ich Wochenendarbeitstage hinzufügen?** Ja – fügen Sie einfach Samstag und Sonntag als Arbeitstage hinzu.  
- **Wie speichere ich das Projekt?** Verwenden Sie `prj.save(..., SaveFileFormat.Xml)`.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher.

## Was bedeutet „Kalender einstellen“ im Kontext von MS Project?
Einen Kalender in MS Project einzustellen bedeutet, festzulegen, welche Tage Arbeitstage sind, die täglichen Arbeitszeiten und etwaige Ausnahmen wie Feiertage. Dieser Kalender steuert die Aufgabenplanung, Ressourcenzuweisung und die gesamten Projektzeitpläne.

## Warum Aspose.Tasks für die Kalendermanipulation verwenden?
- **Vollständige Kontrolle** – programmgesteuert Kalender erstellen, ändern oder löschen, ohne die Benutzeroberfläche zu öffnen.  
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **Unterstützt alle Dateiformate** – MPP, MPT und XML, sodass Sie *Projekt als XML speichern* können, um die Integration mit anderen Systemen zu erleichtern.  
- **Keine COM‑Abhängigkeiten** – im Gegensatz zur Microsoft Project Interop‑Bibliothek.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK) 8+** – herunterladen von der [Oracle‑Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks für Java** – das neueste JAR von der [Aspose.Tasks‑Download‑Seite](https://releases.aspose.com/tasks/java/) beziehen.  
3. Eine IDE oder ein Build‑Tool (Maven/Gradle), um das Aspose.Tasks‑JAR zum Klassenpfad Ihres Projekts hinzuzufügen.

## Pakete importieren
Zuerst importieren Sie die Klassen, die Sie benötigen. Diese Importe geben Ihnen Zugriff auf Projekt-, Kalender‑ und Arbeitszeit‑Objekte.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projektinstanz erstellen
Erzeugen Sie ein neues `Project`‑Objekt. Dieses Objekt repräsentiert die MS‑Project‑Datei, die Sie bearbeiten werden.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Schritt 2: Neuen Kalender definieren
Fügen Sie dem Projekt einen frischen Kalender hinzu. Ein klarer Name erleichtert die Arbeit, wenn Sie mehrere Kalender besitzen.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Schritt 3: Standardarbeitstage hinzufügen (Montag‑Donnerstag)
Verwenden Sie den integrierten Helfer `WeekDay.createDefaultWorkingDay`, um den Standard‑9‑Uhr‑‑17‑Uhr‑Zeitplan für die Kernarbeitswoche festzulegen.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Schritt 4: Wochenendarbeitstage hinzufügen
Falls Ihr Projekt an Wochenenden läuft, fügen Sie einfach Samstag und Sonntag als reguläre Arbeitstage hinzu. Dies demonstriert **Wochenendarbeitstage hinzufügen**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Schritt 5: Einen benutzerdefinierten kurzen Arbeitstag festlegen (Freitag)
Hier **setzen wir benutzerdefinierte Arbeitstage** für Freitag: eine Morgenschicht (9 Uhr‑12 Uhr) und eine Nachmittagsschicht (13 Uhr‑16 Uhr).

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
Abschließend persistieren Sie die Änderungen. Die Option `SaveFileFormat.Xml` ermöglicht es Ihnen, **Projekt als XML zu speichern**, was für die Integration mit anderen Tools nützlich ist.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Häufige Probleme & Lösungen
| Problem | Lösung |
|-------|----------|
| **Arbeitszeiten werden nicht angewendet** | Stellen Sie sicher, dass `setDayWorking(true)` für das benutzerdefinierte `WeekDay` aufgerufen wird. |
| **Datei beim Speichern nicht gefunden** | Prüfen Sie, ob `dataDir` auf einen existierenden Ordner verweist und Ihre Anwendung Schreibrechte hat. |
| **Kalender wird in Aufgaben nicht übernommen** | Weisen Sie den neu erstellten Kalender Ressourcen oder Aufgaben zu, z. B. mit `task.setCalendar(cal)`. |

## Häufig gestellte Fragen

**F: Kann ich benutzerdefinierte Nicht‑Arbeitstage mit Aspose.Tasks für Java definieren?**  
A: Ja. Setzen Sie die Eigenschaft `DayWorking` auf `false` für jedes `WeekDay`, das Sie als Nicht‑Arbeitstag behandeln möchten.

**F: Wie kann ich Feiertage oder unternehmensweite Ausnahmen hinzufügen?**  
A: Erzeugen Sie `CalendarException`‑Objekte, geben Sie die Ausnahmedaten an und fügen Sie sie zu `cal.getExceptions()` hinzu.

**F: Ist die Bibliothek mit älteren MS‑Project‑Versionen kompatibel?**  
A: Absolut. Aspose.Tasks unterstützt MPP, MPT und XML‑Formate über mehrere Project‑Versionen hinweg.

**F: Kann ich einen bestehenden Kalender in einem importierten Projekt ändern?**  
A: Laden Sie das Projekt mit `new Project("existing.mpp")`, holen Sie den gewünschten Kalender, nehmen Sie Änderungen vor und speichern Sie erneut.

**F: Handhabt Aspose.Tasks auch wiederkehrende Aufgaben?**  
A: Ja, Sie können wiederkehrende Aufgaben mit der Klasse `RecurringTask` erstellen und bearbeiten.

## Fazit
Sie wissen jetzt **wie man Kalendereinstellungen** vornimmt, **Wochentage in MS Project definiert**, Wochenendarbeitstage hinzufügt und einen kurzen Freitag‑Zeitplan erstellt – alles mit Aspose.Tasks für Java. Speichern Sie das Ergebnis als XML und integrieren Sie die Kalenderlogik in jede Java‑basierte Projektmanagement‑Lösung.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}