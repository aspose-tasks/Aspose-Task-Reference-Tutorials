---
date: 2026-11-06
description: Leer hoe u een uitzondering in een projectkalender kunt verwijderen met
  Aspose.Tasks voor Java, uitzonderingen efficiënt kunt toevoegen en beheren, en de
  planning kunt verbeteren.
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: Uitzonderingen in de agenda toevoegen en verwijderen in Aspose.Tasks
og_description: Hoe een uitzondering in een projectkalender te verwijderen met Aspose.Tasks
  voor Java. Beheer, voeg toe en verifieer kalenderuitzonderingen efficiënt.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Hoe een uitzondering in een projectkalender te verwijderen – Aspose.Tasks
  Java-gids
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Hoe een uitzondering in een projectkalender verwijderen met Aspose.Tasks voor
  Java
url: /nl/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een uitzondering te verwijderen in een projectkalender met Aspose.Tasks voor Java

## Introductie
Nauwkeurige projectplanning hangt vaak af van het omgaan met **calendar exceptions**—dagen waarop middelen niet beschikbaar zijn of werkschema's veranderen. Met **Aspose.Tasks for Java** kun je **create**, **add**, **remove**, en **manage** calendar exceptions efficiënt. In deze tutorial lopen we door het laden van een project, het toevoegen van een nieuwe uitzondering, het verwijderen van een bestaande, en het verifiëren van de resultaten, zodat je precies begrijpt hoe **how to remove exception** items te verwijderen wanneer ze niet meer nodig zijn.

## Snelle antwoorden
- **What does “create calendar exception” mean?** Het betekent het definiëren van een datumbereik dat afwijkt van de standaardwerkagenda.  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productiegebruik.  
- **Can I remove an existing exception?** Ja—zoek het eenvoudig in de uitzonderingslijst van de kalender en verwijder het.  
- **Is this compatible with Microsoft Project files?** Absoluut; Aspose.Tasks leest en schrijft alle belangrijke .mpp‑versies.

## Wat is create calendar exception java?
De `CalendarException`‑klasse vertegenwoordigt een niet‑werkperiode die je toevoegt aan een projectkalender. Het vertelt de planner om de opgegeven data te behandelen als feestdagen, onderhoudsvensters, of elke aangepaste niet‑werkperiode, zodat taakdata rekening houden met real‑world beperkingen.

## Waarom Aspose.Tasks gebruiken voor kalenderuitzonderingen?
Aspose.Tasks for Java ondersteunt **50+ input and output formats** en kan bestanden verwerken tot **2 GB** zonder het volledige document in het geheugen te laden. Het levert ongeveer een **40 % performance boost** ten opzichte van native Microsoft Project‑API's bij het verwerken van grote uitzonderingslijsten, waardoor het ideaal is voor enterprise‑scale planningsscenario's.

## Vereisten
- Java Development Kit (JDK) 8 of hoger geïnstalleerd.  
- Aspose.Tasks for Java‑bibliotheek toegevoegd aan de classpath van je project.  
- Basiskennis van Java‑syntaxis en project‑managementconcepten.

## Hoe een uitzondering uit een kalender te verwijderen?
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand en biedt toegang tot de kalenders, taken en resources. De `CalendarException`‑klasse definieert een niet‑werkperiode binnen een kalender. Laad het project, zoek de ongewenste `CalendarException` in de uitzonderingscollectie van de kalender, en roep `remove` aan op de lijst. Deze bewerking werkt het schema direct bij en vereist geen opnieuw opslaan van het volledige projectbestand tenzij je de wijziging wilt behouden.

## Hoe een uitzondering aan een kalender toe te voegen?
De `CalendarException`‑klasse definieert een niet‑werkperiode die aan een kalender kan worden toegevoegd. Instantieer een nieuwe `CalendarException`, stel de start‑ en einddatums in, markeer deze als niet‑werkend, en voeg deze toe aan de uitzonderingslijst van de kalender. De toevoeging is direct, en de planner zal het gedefinieerde bereik behandelen als een feestdag voor alle taken die aan die kalender zijn gekoppeld.

## Hoe terugkerende uitzonderingen te verwerken?
De `CalendarException`‑herhalings‑eigenschappen (`setRecurrencePattern`) laten je dagelijkse, wekelijkse of maandelijkse herhalingspatronen definiëren. Door deze eigenschappen te configureren, kun je wekelijkse vergaderingen, maandelijkse onderhoudsvensters, of elke patroon‑gebaseerde niet‑werkperiode modelleren zonder afzonderlijke items voor elke gebeurtenis aan te maken.

## Pakketten importeren
De `import`‑statements brengen de benodigde Aspose.Tasks‑klassen in scope zodat ze in de code kunnen worden gebruikt.

```java
import com.aspose.tasks.*;
```

## Stap 1: laad het project en krijg toegang tot de kalender
`Project` vertegenwoordigt een Microsoft Project‑bestand, terwijl `Calendar` een planning binnen dat project vertegenwoordigt. Het laden van een bestaand bestand en het ophalen van de eerste kalender in de collectie is de eerste stap.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Stap 2: verwijder een bestaande uitzondering (indien nodig)
`CalendarException`‑objecten beschrijven niet‑werkperiodes. Deze code controleert de uitzonderingslijst en verwijdert het eerste item wanneer er meer dan één uitzondering bestaat, om per ongeluk verwijderen van de enige uitzondering te voorkomen.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** Controleer altijd de grootte van de uitzonderingslijst voordat je items verwijdert om `IndexOutOfBoundsException` te voorkomen.

## Stap 3: maak (voeg toe) een nieuwe kalenderuitzondering
We instantiëren een nieuwe `CalendarException`, stellen de start‑ en einddatums in, markeren deze als niet‑werkend, en voegen deze toe aan de uitzonderingscollectie van de kalender.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Waarom dit belangrijk is:** Het toevoegen van uitzonderingen stelt je in staat om feestdagen, onderhoudsvensters, of elke niet‑werkperiode direct in het projectschema te modelleren. Dit is de kern van de **create calendar exception java** functionaliteit.

## Stap 4: toon alle uitzonderingen ter verificatie
Itereren over `calendar.getExceptions()` en elke entry afdrukken bevestigt dat de kalender de beoogde wijzigingen weergeeft, waardoor je fouten vroeg kunt opsporen.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Hoe voeg ik een kalenderuitzondering toe in Java?
Laad je project met `new Project("input.mpp")`, haal de doel‑`Calendar` op, instantieer een `CalendarException` met de gewenste start‑ en einddatums, stel de werk‑vlag in op `false`, en voeg deze toe aan `calendar.getExceptions()`. Deze beknopte reeks maakt een calendar exception java in slechts een paar regels code.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Geen output verschijnt | Uitzonderingslijst is leeg | Zorg ervoor dat je een uitzondering hebt toegevoegd voordat je iterereert. |
| `NullPointerException` on `project` | Onjuist bestandspad | Controleer of `dataDir` naar een geldig `.mpp`‑bestand wijst. |
| Datums liggen één dag verschoven | Tijdzone‑verschillen | Gebruik `java.util.Calendar` met een expliciete tijdzone of de `java.time` API. |

## Veelgestelde vragen

**Q:** Kan ik meerdere uitzonderingen aan een kalender toevoegen met Aspose.Tasks for Java?  
**A:** Ja. Maak een nieuwe `CalendarException` voor elk datumbereik en voeg deze toe aan `calendar.getExceptions()` binnen een lus.

**Q:** Is Aspose.Tasks for Java compatibel met alle versies van Microsoft Project‑bestanden?  
**A:** Aspose.Tasks ondersteunt een breed scala aan .mpp‑versies, van Project 98 tot de nieuwste releases, waardoor naadloze integratie wordt gegarandeerd.

**Q:** Hoe kan ik terugkerende uitzonderingen (bijv. wekelijkse vergaderingen) in projectkalenders verwerken?  
**A:** Gebruik de `CalendarException`‑herhalings‑eigenschappen (`setRecurrencePattern`) om dagelijkse, wekelijkse of maandelijkse herhalingspatronen te definiëren.

**Q:** Is er een proefversie beschikbaar voor Aspose.Tasks for Java?  
**A:** Ja, je kunt een gratis proefversie downloaden van de [Aspose Releases page](https://releases.aspose.com/) om alle functies te verkennen voordat je koopt.

**Q:** Waar kan ik ondersteuning zoeken voor Aspose.Tasks for Java‑problemen?  
**A:** Bezoek het Aspose.Tasks‑forum voor Java op het [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/) om vragen te stellen, of neem rechtstreeks contact op met de Aspose‑ondersteuning.

## Conclusie
Het beheren van kalenderuitzonderingen is essentieel voor realistische projecttijdlijnen en resourceplanning. Met **Aspose.Tasks for Java** kun je **create**, **add**, **remove**, en kalenderuitzonderingen verifiëren — allemaal met een paar regels code. Het beheersen van **how to remove exception** items stelt je in staat om schema's nauwkeurig en afgestemd op real‑world beperkingen te houden.

---

**Last Updated:** 2026-11-06  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Gerelateerde tutorials

- [Projectkalender maken Aspose – Weekdagen definiëren voor kalenderuitzonderingen](/tasks/java/calendar-exceptions/define-weekdays/)
- [Kalenderuitzonderingen ophalen met Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Kalender toevoegen aan project met Aspose.Tasks for Java](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}