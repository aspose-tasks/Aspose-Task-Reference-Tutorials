---
date: 2026-08-08
description: Leer hoe u de agenda van MS Project instelt, de dagelijkse werktijden
  instelt en weekendwerkdagen toevoegt met Aspose.Tasks voor Java. Sla het project
  op als XML in slechts een paar regels code.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Hoe de agenda van MS Project in te stellen en weekdagen te definiëren
og_description: Stel de agenda van MS Project in, definieer weekdagen en voeg weekendwerkdagen
  toe met Aspose.Tasks voor Java. Volg deze stapsgewijze tutorial en sla op als XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Agenda van MS Project instellen met Aspose.Tasks – Java‑gids
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
title: Hoe de agenda van MS Project in te stellen en weekdagen te definiëren
url: /nl/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een kalender in MS Project instellen en weekdagen definiëren

In deze tutorial leer je **hoe je een kalender in MS Project instelt** programmatically, weekdagen definiëren en aangepaste werkdagen configureren met behulp van de Aspose.Tasks bibliotheek voor Java. Of je nu een planningsengine bouwt, integreert met ERP‑systemen, of simpelweg een projectplan moet genereren zonder Microsoft Project te openen, de onderstaande stappen laten zien hoe je een kalender maakt, dagelijkse werkuren instelt en weekendwerkdagen toevoegt in een paar regels code.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java.  
- **Kan ik weekendwerkdagen toevoegen?** Ja – markeer gewoon zaterdag en zondag als werkdagen.  
- **Hoe sla ik het project op?** Roep `prj.save(..., SaveFileFormat.Xml)` aan.  
- **Is een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een licentie is vereist voor productiegebruik.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  

## Wat is het instellen van een kalender in MS Project?
Het instellen van de kalender in MS Project bepaalt welke dagen als werkdagen worden beschouwd, het aantal werkuren per dag, en eventuele speciale uitzonderingen zoals feestdagen of bedrijfssluitingen. Deze informatie stuurt taakplanning, resource‑toewijzing en de algehele projecttijdlijnen, zodat berekeningen de werkpatronen van de organisatie respecteren.

## Waarom Aspose.Tasks gebruiken voor kalendermanipulatie?
Aspose.Tasks geeft je programmatische controle over kalenders zonder de Microsoft Project UI te starten. Het draait op elk besturingssysteem dat Java ondersteunt, ondersteunt meer dan 50 invoer‑ en uitvoerformaten, en kan projecten van honderden pagina’s verwerken zonder het volledige bestand in het geheugen te laden, waardoor het ideaal is voor server‑side automatisering.

## Vereisten
- **Java Development Kit (JDK) 8+** – download van de [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – verkrijg de nieuwste JAR van de [Aspose.Tasks downloadpagina](https://releases.aspose.com/tasks/java/).  
- Een IDE of build‑tool (Maven/Gradle) om de Aspose.Tasks JAR aan je classpath toe te voegen.

## Pakketten importeren
Importeer de klassen die toegang geven tot projecten, kalenders en werktijd‑objecten.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Stapsgewijze handleiding

### Stap 1: maak een projectinstantie
Instantieer een `Project`‑object, dat het MS Project‑bestand vertegenwoordigt dat je gaat manipuleren.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Stap 2: definieer een nieuwe kalender
`Calendar` vertegenwoordigt een set werktijden, uitzonderingen en feestdagen voor een project.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Stap 3: voeg standaardwerkdagen toe (maandag‑donderdag)
`WeekDay` definieert de werktijd voor een specifieke dag van de week.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Stap 4: voeg weekendwerkdagen toe
Als je project in het weekend loopt, voeg dan zaterdag en zondag toe als reguliere werkdagen. Dit demonstreert **weekendwerkdagen toevoegen**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Stap 5: stel een aangepaste korte werkdag in (vrijdag)
Configureer vrijdag met een ochtendshift (9 uur‑12 uur) en een middagshift (13 uur‑16 uur) om **dagelijkse werkuren instellen** en een aangepaste korte werkdag te illustreren.

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

### Stap 6: sla het project op als XML
`SaveFileFormat` somt de ondersteunde bestandsformaten op bij het opslaan van een project, zoals XML of MPP.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen & oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Werk tijden niet toegepast** | Zorg ervoor dat `setDayWorking(true)` wordt aangeroepen voor elke aangepaste `WeekDay`. |
| **Bestand niet gevonden bij opslaan** | Controleer of `dataDir` naar een bestaande map wijst en dat de applicatie schrijfrechten heeft. |
| **Kalender niet weergegeven in taken** | Wijs de nieuw gemaakte kalender toe aan resources of taken met `task.setCalendar(cal)`. |

## Veelgestelde vragen

**V: Kan ik aangepaste niet‑werkdagen definiëren met Aspose.Tasks voor Java?**  
A: Ja. Stel de `DayWorking`‑eigenschap in op `false` voor elke `WeekDay` die je als niet‑werkdag wilt behandelen.

**V: Hoe kan ik feestdagen of bedrijf‑brede uitzonderingen toevoegen?**  
A: Maak `CalendarException`‑objecten aan, specificeer de uitzonderingsdatums en voeg ze toe aan `cal.getExceptions()`.

**V: Is de bibliotheek compatibel met oudere MS Project‑versies?**  
A: Absoluut. Aspose.Tasks ondersteunt MPP-, MPT- en XML‑formaten voor meerdere Project‑versies.

**V: Kan ik een bestaande kalender in een geïmporteerd project wijzigen?**  
A: Laad het project met `new Project("existing.mpp")`, haal de gewenste kalender op, breng wijzigingen aan en sla op.

**V: Ondersteunt Aspose.Tasks ook terugkerende taken?**  
A: Ja, je kunt terugkerende taken maken en bewerken met de `RecurringTask`‑klasse.

## Conclusie
Je weet nu **hoe je een kalender in MS Project instelt**, weekdagen definiëren, weekendwerkdagen toevoegen en een korte vrijdagplanning configureren — allemaal met Aspose.Tasks voor Java. Sla het resultaat op als XML en integreer de kalenderlogica in elke Java‑gebaseerde project‑managementoplossing.

---

**Laatst bijgewerkt:** 2026-08-08  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Kalender toevoegen aan project met Aspose.Tasks voor Java](/tasks/java/calendars/create/)
- [Werkdagen & werktijden bepalen met Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Feestdagen toevoegen aan kalender en opslaan als MPP met Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}