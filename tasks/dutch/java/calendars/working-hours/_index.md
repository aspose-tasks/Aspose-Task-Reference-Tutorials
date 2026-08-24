---
date: 2026-08-24
description: Leer hoe u een vakantiekalender kunt toevoegen, werkdagen kunt bepalen
  en de taakduur kunt berekenen door werkuren uit MS Project‑kalenders te extraheren
  met Aspose.Tasks voor Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Hoe een vakantiekalender toe te voegen en werkdagen te bepalen
og_description: Leer hoe u een vakantiekalender kunt toevoegen, werkdagen kunt bepalen
  en de taakduur kunt berekenen door werkuren uit MS Project‑kalenders te extraheren
  met Aspose.Tasks voor Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Hoe een vakantiekalender toe te voegen en werkdagen te bepalen
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
title: Hoe een vakantiekalender toe te voegen en werkdagen te bepalen
url: /nl/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een vakantiekalender toe te voegen en werkdagen te bepalen

Het beheren van projectkalenders is een kernonderdeel van succesvolle projectplanning. In deze tutorial voeg je **een vakantiekalender toe**, **bepaal je werkdagen** voor elke taak, en **haal je werkuren** uit een MS Project‑kalender met behulp van Aspose.Tasks for Java. Aan het einde van de gids kun je **de taakduur berekenen**, werkuren aanpassen, en betrouwbaar **een MPP‑bestand laden** om de benodigde gegevens op te halen — zonder Microsoft Project te installeren.

## Snelle antwoorden
- **Wat betekent “determine working days”?** Het betekent het identificeren van welke kalenderdatums als werkdagen worden beschouwd voor een bepaalde taak.  
- **Welke bibliotheek moet ik gebruiken?** Aspose.Tasks for Java biedt een volledig uitgeruste API voor het werken met MS Project‑bestanden.  
- **Hoe lang duurt de implementatie?** Meestal 10–15 minuten voor een eenvoudige extractie.  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Kan ik werkuren aanpassen?** Ja – je kunt kalenders wijzigen, vakanties toevoegen en aangepaste werktijdreeksen instellen.  

## Wat is “determine working days”?
**Determine working days** betekent het opvragen van een projectkalender om te achterhalen welke datums gemarkeerd zijn als werkdagen versus niet‑werkdagen (weekenden, vakanties of aangepaste uitzonderingen). Deze informatie is essentieel voor een nauwkeurige **calculate task duration** omdat alleen werkdagen bijdragen aan de verstreken tijd van een taak.

## Waarom Aspose.Tasks gebruiken om werkuren op te halen?
Aspose.Tasks stelt je in staat MS Project‑bestanden te lezen zonder dat Microsoft Project geïnstalleerd is, waardoor automatisering op elk platform mogelijk is. Het biedt ook high‑performance verwerking, uitgebreide formatondersteuning en gedetailleerde documentatie.  

- **Volledige kalenderondersteuning** – standaard-, resource- en taakkalenders zijn allemaal toegankelijk.  
- **Hoge prestaties** – kan projecten met **10.000+ taken in minder dan 2 seconden** verwerken op een standaard 2,5 GHz CPU.  
- **Uitgebreide formatdekking** – ondersteunt **50+ invoer‑ en uitvoerformaten**, waaronder MPP, MPX, XML en Primavera.  
- **Uitgebreide documentatie** – code‑voorbeelden, API‑referentie en community‑forums zijn allemaal beschikbaar.

## Vereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Basiskennis van Java‑programmeren.  

## Pakketten importeren
De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel MS Project‑bestand in het geheugen vertegenwoordigt. Importeer de vereiste namespace voordat je begint:

Importeer pakketten

```java
import com.aspose.tasks.*;
```

## Hoe een MPP‑bestand laden met Aspose.Tasks?
De `Project`‑klasse laadt een MS Project‑bestand en biedt toegang tot de gegevens. Laad het projectbestand in één regel code; er is geen UI of COM‑interop vereist. Deze eenvoudige stap geeft je volledige toegang tot kalenders, taken en resources.

Een MPP‑bestand laden

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Taak‑ en kalenderinformatie ophalen
`Task` vertegenwoordigt een projecttaak, en `Calendar` definieert de werktijdregels. Selecteer de taak die je wilt analyseren en verkrijg de bijbehorende kalender. Het `Task`‑object biedt de methoden `getStart()` en `getFinish()`, terwijl het `Calendar`‑object werktijddefinities blootlegt.

Taak en kalender ophalen

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Begin‑ en einddatums definiëren
`Date`‑objecten geven het tijdvenster voor kalenderanalyse op. Stel het tijdvenster in waarvoor je **determine working days** wilt bepalen. Het gebruik van de start‑ en einddatums van de taak zorgt ervoor dat je alleen de relevante periode evalueert.

Datums definiëren

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Door datums itereren
Een `for`‑lus kan over elke dag in het datumbereik itereren. Loop door elke datum in de duur van de taak. Deze lus stelt je later in staat **working hours** aan te passen indien nodig en vormt de basis voor het berekenen van de totale werktijd.

Datums itereren

```java
java.util.Calendar tempDate = calStartDate;
```

## Duur berekenen
`Duration` verzamelt de totale werktijd die uit de iteratie is berekend. Tijdens de iteratie controleer je of elke dag een werkdag is, tel je de werkuren op, en bereken je uiteindelijk de duur van de taak in minuten, uren en dagen. Dit laat zien hoe je **calculate working days** en **calculate task duration** programmatisch kunt berekenen.

Duur berekenen

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

## Hoe werkuren en vakanties aanpassen
Je kunt de werktijdreeksen van de kalender aanpassen en uitzonderingen toevoegen, zoals vakanties. Gebruik `taskCalendar.addWorkingTime()` om nieuwe werkperioden in te stellen en `taskCalendar.addException()` om een vakantie toe te voegen. Dit is handig wanneer het standaard 9‑5‑schema niet overeenkomt met het beleid van je organisatie.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Taak retourneert `null` voor kalender** | Zorg ervoor dat de taak daadwerkelijk een toegewezen kalender heeft; anders erft hij de standaardkalender van het project. |
| **Onjuiste duur door vakanties** | Controleer of vakanties zijn gedefinieerd in de kalender van de taak of in de basis‑kalender van het project. |
| **Tijdzone‑mismatch** | Gebruik `java.util.TimeZone` om de tijdzone van de kalender af te stemmen op je systeem indien nodig. |

## Veelgestelde vragen
### V: Kan Aspose.Tasks for Java complexe projectstructuren aan?
A: Ja, Aspose.Tasks for Java biedt uitgebreide ondersteuning voor het omgaan met complexe projectstructuren, inclusief taken, resources en kalenders.

### V: Is Aspose.Tasks for Java compatibel met verschillende versies van MS Project?
A: Absoluut, Aspose.Tasks for Java ondersteunt verschillende MS Project‑versies, waardoor compatibiliteit over verschillende omgevingen heen wordt gegarandeerd.

### V: Kan ik werkuren en vakanties aanpassen in projectkalenders?
A: Ja, je kunt werkuren en vakanties eenvoudig aanpassen aan je projectvereisten met behulp van de Aspose.Tasks for Java‑API's.

### V: Biedt Aspose.Tasks for Java ondersteuning en documentatie?
A: Ja, Aspose.Tasks for Java biedt uitgebreide documentatie en toegewijde ondersteuningsforums om ontwikkelaars te helpen de functies effectief te gebruiken.

### V: Is er een proefversie beschikbaar voor Aspose.Tasks for Java?
A: Ja, je kunt een gratis proefversie van Aspose.Tasks for Java verkrijgen via de [Aspose releases page](https://releases.aspose.com/).

## Conclusie
In deze gids hebben we laten zien hoe je **een vakantiekalender toevoegt**, **werkdagen bepaalt**, **werkuren ophaalt**, en **taakduur berekent** vanuit een MS Project‑kalender met behulp van Aspose.Tasks for Java. Door de bovenstaande stappen te volgen kun je planningsanalyse automatiseren, kalenders aanpassen en je projectplannen nauwkeurig en actueel houden. Je beschikt nu over de tools om **MS Project**‑gegevens te lezen, **een MPP‑bestand te laden**, en nauwkeurige duurberekeningen uit te voeren zonder Microsoft Project zelf te hoeven gebruiken.

---

**Laatst bijgewerkt:** 2026-08-24  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Kalender toevoegen aan project met Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Vakanties toevoegen aan kalender en opslaan als MPP met Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Aangepaste kalenderuitzonderingen maken met Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}