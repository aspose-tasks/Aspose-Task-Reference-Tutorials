---
date: 2026-07-29
description: Leer hoe u niet-werkdagen kunt plannen door een projectkalender te maken
  met Aspose.Tasks voor Java, weekdaguitzonderingen te definiëren en vakantieroosters
  te beheren.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Niet-werkdagen plannen – Projectkalender maken met Aspose
og_description: Plan niet-werkdagen met Aspose.Tasks voor Java. Leer weekdagen te
  definiëren, kalenderuitzonderingen toe te voegen en vakantieroosters efficiënt te
  beheren.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Niet-werkdagen plannen – Projectkalender maken met Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Niet-werkdagen plannen – Projectkalender maken met Aspose
url: /nl/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Plan Niet‑Werkdagen – Maak Projectkalender Aspose

### Inleiding
Wanneer je **niet‑werkdagen moet plannen** voor een project, moet je vakanties, speciale diensten of tijdelijke sluitingen direct in het projectplan kunnen modelleren. Aspose.Tasks for Java geeft je volledige controle over kalendardefinities, zodat je uitzonderingen kunt toevoegen die de realiteit weerspiegelen. In deze tutorial lopen we stap voor stap door hoe je weekdagen definieert voor kalenderuitzonderingen, zodat je projecttijdlijnen nauwkeurig en betrouwbaar blijven. Aan het einde zie je ook hoe dit past in een bredere **niet‑werkdagen‑schema**‑strategie voor elk bedrijfsproject.

## Snelle Antwoorden
- **Wat betekent “plan niet‑werkdagen”?**  
  Het betekent dat je Aspose.Tasks gebruikt om een kalender te maken die specifieke data markeert als niet‑werkend, waardoor taakdata automatisch worden aangepast.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?**  
  Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke IDE's worden ondersteund?**  
  IntelliJ IDEA, Eclipse, NetBeans, of elke IDE die Java 8+ ondersteunt.  
- **Kan ik meerdere uitzonderingen aan dezelfde kalender toevoegen?**  
  Ja – je kunt zoveel `CalendarException`‑objecten toevoegen als nodig is.  
- **Naar welke bestandsformaten kan ik het project opslaan?**  
  XML, MPP en verschillende andere formaten die door Aspose.Tasks worden ondersteund.  

## Wat is een Projectkalender in Aspose.Tasks?
**Projectkalender** is het top‑level object van Aspose.Tasks dat werkdagen en -uren voor een project definieert. Het beïnvloedt direct de start‑/einddatums van taken, resource‑toewijzing en algemene planningsberekeningen. Door een kalender aan te passen, zorg je ervoor dat het schema rekening houdt met real‑world beperkingen zoals bedrijfsfeestdagen of weekend‑werkbeleid.

## Waarom weekdagen definiëren voor kalenderuitzonderingen?
Het definiëren van weekdag‑uitzonderingen zorgt ervoor dat de projectengine die dagen als niet‑werkend behandelt, waardoor taken niet automatisch op die dagen worden ingepland en de tijdlijn in lijn blijft met real‑world beperkingen zoals feestdagen, onderhoudsvensters of speciale ploegendiensten binnen de organisatie.

- **Nauwkeurige tijdlijnen:** Taken worden niet geplaatst op feestdagen of blackout‑periodes.  
- **Resourceplanning:** Resources worden alleen toegewezen op geldige werkdagen, waardoor overallocatie wordt voorkomen.  
- **Naleving:** Schema's volgen automatisch organisatorische beleidsregels of wettelijke feestdagenkalenders.  

## Niet‑werkdagen Schema met Kalenderuitzonderingen
Wanneer je een **niet‑werkdagen schema** onderhoudt, heb je meestal een masterlijst van feestdagen, onderhoudsvensters of andere blackout‑periodes. Het toevoegen van die data als `CalendarException`‑objecten garandeert dat elke berekening—of het nu kritieke‑padanalyse of resource‑leveling is—automatisch die beperkingen respecteert. Deze aanpak elimineert handmatige datum‑aanpassingen en vermindert het risico op schema‑afwijkingen.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of later.  
2. **Aspose.Tasks for Java** – download van de officiële [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Een IDE** – IntelliJ IDEA, Eclipse, NetBeans, of elke Java‑compatibele editor.  

## Hoe niet‑werkdagen in te plannen met kalenderuitzonderingen

Laad je project, maak een aangepaste kalender en voeg `CalendarException`‑objecten toe die de gewenste weekdagen als niet‑werkend markeren. Dit volledige proces kan in een handvol eenvoudige stappen worden voltooid, en de resulterende kalender beïnvloedt automatisch alle taak‑planningslogica.

### Stapsgewijze Gids

### Stap 1: Vereiste Pakketten Importeren
We hebben de kern‑klassen van Aspose.Tasks en Java’s `GregorianCalendar` nodig voor datum‑verwerking.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Stap 2: Definieer de Data Directory
Geef aan waar het gegenereerde projectbestand wordt opgeslagen.

```java
String dataDir = "Your Data Directory";
```

### Stap 3: Maak een Projectinstantie
`Project` is het hoofdobject dat alle projectdata bevat, inclusief taken, resources en kalenders.

```java
Project project = new Project();
```

### Stap 4: Definieer een Kalender
`Calendar` vertegenwoordigt een schema van werk‑ en niet‑werktijden binnen een project.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Stap 5: Definieer Weekdagen Uitzondering
`CalendarException` vertegenwoordigt een periode die als niet‑werkend wordt gemarkeerd in een kalender.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Stap 6: Sla het Project Op
Sla het project op, inclusief de aangepaste kalender en de uitzondering, naar een XML‑bestand.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Uitzonderingsdatums niet toegepast** | Zorg dat `setEnteredByOccurrences(false)` en correcte `FromDate/ToDate`‑waarden zijn ingesteld. |
| **Opgeslagen bestand is leeg** | Controleer of `dataDir` naar een schrijfbare map wijst en dat de bestandsnaam eindigt op `.xml`. |
| **Kalender wordt niet weerspiegeld in taakplanning** | Wijs de kalender toe aan taken of resources met `task.setCalendar(cal)` of `resource.setCalendar(cal)`. |

## Veelgestelde Vragen

**Q: Kan ik meerdere uitzonderingen definiëren voor verschillende weekdagen binnen dezelfde kalender?**  
A: Ja. Voeg extra `CalendarException`‑objecten toe aan `cal.getExceptions()` voor elke afzonderlijke periode of regel.

**Q: Is Aspose.Tasks for Java compatibel met verschillende Java‑IDE's?**  
A: Absoluut. De bibliotheek werkt met IntelliJ IDEA, Eclipse, NetBeans en elke IDE die standaard Java‑projecten ondersteunt.

**Q: Kan ik uitzonderingstypen aanpassen die anders zijn dan dagelijkse uitzonderingen?**  
A: Ja. Gebruik `CalendarExceptionType.Weekly`, `Monthly` of `Yearly` om aan je planningsbehoeften te voldoen.

**Q: Hoe kan ik uitzonderingen dynamisch afhandelen op basis van projectvereisten?**  
A: Bouw de uitzonderingobjecten programmatisch—bijv. lees feestdagen uit een database of configuratiebestand en maak `CalendarException`‑instanties in een lus.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, je kunt een gratis proefversie downloaden van de [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusie
Door deze stappen te volgen weet je nu hoe je **niet‑werkdagen kunt plannen** door een projectkalender te maken en weekdag‑uitzonderingen te definiëren die feestdagen of speciale niet‑werkperiodes nauwkeurig weergeven. Een juiste kalenderconfiguratie is essentieel voor realistische schema's, resource‑toewijzing en het algehele projectsucces. Verken verder door de aangepaste kalender aan taken of resources te koppelen en experimenteer met andere uitzonderingstypen om een uitgebreid **niet‑werkdagen‑schema** voor elk project op te bouwen.

---

**Last Updated:** 2026-07-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Gerelateerde Tutorials

- [Kalender toevoegen aan project met Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Kalenderuitzondering maken Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [Hoe Kalender en Weekdagen in MS Project instellen met Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}