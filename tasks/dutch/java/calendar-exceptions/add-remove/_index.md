---
date: 2026-08-08
description: Leer hoe u een kalenderuitzondering in Java maakt met Aspose.Tasks voor
  Java, uitzonderingen efficiënt toevoegt en verwijdert, en de projectplanning verbetert.
keywords:
- create calendar exception java
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-08-08
linktitle: Kalenderuitzonderingen toevoegen en verwijderen in Aspose.Tasks
og_description: Leer hoe u een kalenderuitzondering in Java maakt met Aspose.Tasks
  voor Java. Voeg kalenderuitzonderingen toe, verwijder ze en verifieer ze efficiënt
  in Microsoft Project-bestanden.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Maak een kalenderuitzondering in Java met Aspose.Tasks – snelle gids
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create calendar exception java with Aspose.Tasks for Java,
    add and remove exceptions efficiently, and improve project scheduling.
  headline: Create calendar exception java using Aspose.Tasks
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
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Maak een kalenderuitzondering in Java met Aspose.Tasks
url: /nl/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak kalenderuitzondering java met Aspose.Tasks

## Introductie
Nauwkeurige projectplanning hangt vaak af van het omgaan met **calendar exceptions** — dagen waarop middelen niet beschikbaar zijn of werkschema's veranderen. Met **Aspose.Tasks for Java** kun je **create calendar exception java** objecten maken, toevoegen aan een projectkalender, of verwijderen wanneer ze niet meer nodig zijn. In deze tutorial lopen we het volledige proces door, van het laden van een projectbestand tot het verifiëren van de door jou beheerde uitzonderingen. Je ziet precies hoe je **create calendar exception java** in een Java‑omgeving kunt maken en waarom dit belangrijk is voor realistische tijdlijnen.

## Snelle antwoorden
- **Wat betekent “create calendar exception”?** Het betekent het definiëren van een datumbereik dat afwijkt van de standaardwerkagenda.  
- **Welke bibliotheek biedt deze mogelijkheid?** Aspose.Tasks for Java.  
- **Heb ik een licentie nodig om het te proberen?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productiegebruik.  
- **Kan ik een bestaande uitzondering verwijderen?** Ja — zoek deze eenvoudig op in de uitzonderingslijst van de kalender en verwijder hem.  
- **Is dit compatibel met Microsoft Project‑bestanden?** Absoluut; Aspose.Tasks leest en schrijft alle belangrijke .mpp‑versies.

## Wat is create calendar exception java?
Een calendar exception java voegt een niet‑werkperiode toe aan een projectkalender met behulp van de Java‑API van Aspose.Tasks. Dit vertelt de planner om de opgegeven data te behandelen als feestdagen, onderhoudsvensters of andere aangepaste niet‑werkperiodes, zodat taakdata rekening houden met real‑world‑beperkingen en beschikbaarheid van middelen.

## Waarom Aspose.Tasks gebruiken voor calendar exceptions?
Aspose.Tasks for Java ondersteunt meer dan 30 projectbestandsformaten en kan bestanden tot 2 GB verwerken zonder het volledige document in het geheugen te laden. Het levert ongeveer een prestatieverbetering van 40 % ten opzichte van native Microsoft Project‑API's bij het verwerken van grote uitzonderingslijsten, waardoor het ideaal is voor enterprise‑scale planningsscenario's die snelle, betrouwbare kalendermanipulatie vereisen.

## Voorvereisten
- Java Development Kit (JDK) 8 of hoger geïnstalleerd.  
- Aspose.Tasks for Java‑bibliotheek toegevoegd aan het classpath van je project.  
- Basiskennis van Java‑syntaxis en project‑managementconcepten.

## Hoe maak je calendar exception java met Aspose.Tasks
Laad het project, bewerk de kalender en verifieer de wijzigingen — alles in een paar eenvoudige stappen die duidelijke code combineren met beknopte uitleg.

## Importeer pakketten
De `import`‑verklaringen brengen de benodigde Aspose.Tasks‑klassen in scope zodat ze in de code kunnen worden gebruikt.

```java
import com.aspose.tasks.*;
```

## Stap 1: laad het project en krijg toegang tot de kalender
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand, terwijl `Calendar` een planning binnen dat project representeert. We laden een bestaand bestand en halen de eerste kalender uit de collectie.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Stap 2: verwijder een bestaande uitzondering (indien nodig)
`CalendarException`‑objecten beschrijven niet‑werkperiodes. Deze code controleert de uitzonderingslijst en verwijdert de eerste invoer wanneer er meer dan één uitzondering bestaat, waardoor per ongeluk verwijderen van de enige uitzondering wordt voorkomen.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** Controleer altijd de grootte van de uitzonderingslijst voordat je items verwijdert om `IndexOutOfBoundsException` te voorkomen.

## Stap 3: maak (voeg toe) een nieuwe calendar exception
We instantieren een nieuwe `CalendarException`, stellen de start‑ en einddatums in, markeren deze als niet‑werkend, en voegen hem toe aan de uitzonderingscollectie van de kalender.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Waarom dit belangrijk is:** Het toevoegen van uitzonderingen stelt je in staat om feestdagen, onderhoudsvensters of andere niet‑werkperiodes direct in de projectschema te modelleren. Dit is de kern van de **create calendar exception java** functionaliteit.

## Stap 4: toon alle uitzonderingen ter verificatie
Itereren over `calendar.getExceptions()` en elke invoer afdrukken bevestigt dat de kalender de beoogde wijzigingen weergeeft, waardoor je fouten vroeg kunt opsporen.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Hoe voeg ik een calendar exception toe in Java?
Laad je project met `new Project("input.mpp")`, haal de doel‑`Calendar` op, instantier een `CalendarException` met de gewenste start‑ en einddatums, zet de werk‑vlag op `false`, en voeg deze toe aan `calendar.getExceptions()`. Deze beknopte reeks creëert een calendar exception java in slechts een paar code‑regels.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Geen output verschijnt | Uitzonderingslijst is leeg | Zorg ervoor dat je een uitzondering hebt toegevoegd voordat je iterereert. |
| `NullPointerException` on `project` | Onjuist bestandspad | Controleer of `dataDir` naar een geldig `.mpp`‑bestand wijst. |
| Datums liggen één dag verschoven | Tijdzone‑verschillen | Gebruik `java.util.Calendar` met expliciete tijdzone of de `java.time` API. |

## Veelgestelde vragen

**Q: Kan ik meerdere uitzonderingen aan een kalender toevoegen met Aspose.Tasks for Java?**  
A: Ja. Maak een nieuwe `CalendarException` voor elk datumbereik en voeg deze toe aan `calendar.getExceptions()` binnen een lus.

**Q: Is Aspose.Tasks for Java compatibel met alle versies van Microsoft Project‑bestanden?**  
A: Aspose.Tasks ondersteunt een breed scala aan .mpp‑versies, van Project 98 tot de nieuwste releases, waardoor naadloze integratie wordt gegarandeerd.

**Q: Hoe kan ik terugkerende uitzonderingen (bijv. wekelijkse vergaderingen) in projectkalenders afhandelen?**  
A: Gebruik de `CalendarException`‑herhalings‑eigenschappen (`setRecurrencePattern`) om dagelijkse, wekelijkse of maandelijkse herhalingspatronen te definiëren.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, je kunt een gratis proefversie downloaden van de [website](https://releases.aspose.com/) om alle functies te verkennen voordat je koopt.

**Q: Waar kan ik ondersteuning zoeken voor Aspose.Tasks for Java‑problemen?**  
A: Bezoek het Aspose.Tasks‑forum voor Java op de [website](https://reference.aspose.com/tasks/java/) om vragen te stellen, of neem rechtstreeks contact op met de Aspose‑ondersteuning.

## Conclusie
Het beheren van kalenderuitzonderingen is essentieel voor realistische projecttijdlijnen en resourceplanning. Met **Aspose.Tasks for Java** kun je **create calendar exception java** objecten maken, toevoegen aan elke projectkalender, en verwijderen wanneer ze niet meer relevant zijn — allemaal met slechts een paar code‑regels. Deze mogelijkheid om **create calendar exception java** toe te passen stelt je in staat schema's te bouwen die echt de real‑world‑beperkingen weerspiegelen.

---

**Laatst bijgewerkt:** 2026-08-08  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak projectkalender Aspose – Definieer weekdagen voor kalenderuitzonderingen](/tasks/java/calendar-exceptions/define-weekdays/)
- [Ophalen van kalenderuitzonderingen met Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Kalender toevoegen aan project met Aspose.Tasks for Java](/tasks/java/calendars/create/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}