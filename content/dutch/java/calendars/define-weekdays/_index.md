---
title: Definieer weekdagen in Agenda met Aspose.Tasks
linktitle: Definieer weekdagen in Agenda met Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u weekdagen kunt definiëren in MS Project Calendar met behulp van Aspose.Tasks voor Java. Pas werkdagen en tijden moeiteloos aan.
type: docs
weight: 12
url: /nl/java/calendars/define-weekdays/
---
## Invoering
In deze zelfstudie doorlopen we het proces van het definiëren van weekdagen in een MS Project-agenda met behulp van Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java-bibliotheek waarmee ontwikkelaars Microsoft Project-bestanden programmatisch kunnen manipuleren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd. Je kunt het downloaden van de[Oracle-website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) als je dat nog niet hebt gedaan.
2.  Aspose.Tasks voor Java-bibliotheek: Download en installeer de Aspose.Tasks voor Java-bibliotheek van de[downloadpagina](https://releases.aspose.com/tasks/java/). Volg de installatie-instructies in de documentatie.

## Pakketten importeren
Importeer om te beginnen de benodigde pakketten die nodig zijn voor het werken met Aspose.Tasks in uw Java-project:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Stap 1: Maak een projectinstantie
Instantieer een Project-object, dat het MS Project-bestand vertegenwoordigt waarmee u gaat werken:
```java
// Het pad naar de documentenmap.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Stap 2: Kalender definiëren
Maak een nieuw agenda-exemplaar en voeg het toe aan het project:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Stap 3: Werkdagen toevoegen
Definieer de werkdagen door maandag tot en met donderdag toe te voegen met standaardtijden:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Stap 4: Aangepaste werkdag instellen
Definieer zaterdag en zondag als werkdagen:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Stap 5: Stel een korte werkdag in
Stel vrijdag in als korte werkdag met aangepaste werktijden:
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
## Stap 6: Sla het project op
Sla het gewijzigde project op in een XML-bestand:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Conclusie
Gefeliciteerd! U hebt met succes weekdagen gedefinieerd in een MS Project-agenda met behulp van Aspose.Tasks voor Java. U kunt deze functionaliteit nu in uw Java-applicaties integreren om MS Project-bestanden programmatisch te manipuleren.
## Veelgestelde vragen
### V1: Kan ik aangepaste niet-werkdagen definiëren met Aspose.Tasks voor Java?
 A: Ja, u kunt aangepaste niet-werkdagen definiëren door de`DayWorking` eigendom aan`false` voor de desbetreffende weekdag.
### Vraag 2: Hoe kan ik feestdagen aan de kalender toevoegen?
 A: U kunt feestdagen toevoegen door exemplaren van te maken`CalendarExceptions`en het specificeren van de niet-werkdata.
### V3: Is Aspose.Tasks compatibel met verschillende versies van MS Project-bestanden?
A: Ja, Aspose.Tasks ondersteunt verschillende versies van MS Project-bestanden, waaronder MPP-, MPT- en XML-formaten.
### V4: Kan ik bestaande kalenders in een MS Project-bestand wijzigen?
A: Ja, u kunt een bestaand project met kalenders laden, wijzigingen aanbrengen en de wijzigingen vervolgens weer opslaan in het originele bestand.
### V5: Biedt Aspose.Tasks ondersteuning voor terugkerende taken?
A: Ja, met Aspose.Tasks kunt u met terugkerende taken werken, inclusief het definiëren van hun herhalingspatronen en duur.