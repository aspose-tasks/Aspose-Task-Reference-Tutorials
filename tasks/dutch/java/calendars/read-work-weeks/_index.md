---
date: 2026-08-13
description: Leer hoe u werkweken uit een MS Project‑agenda kunt lezen met Aspose.Tasks
  voor Java. Volg de stapsgewijze handleiding met code‑voorbeelden en tips voor probleemoplossing.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Werkweken lezen uit agenda met Aspose.Tasks
og_description: Hoe werkweken uit een MS Project‑agenda te lezen met Aspose.Tasks
  voor Java. Volg de beknopte tutorial met installatiestappen, codefragmenten en tips
  voor probleemoplossing.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Hoe werkweken uit een MS‑agenda lezen met Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Hoe werkweken uit een MS‑agenda lezen met Aspose.Tasks
url: /nl/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe werkweken lezen uit MS‑agenda met Aspose.Tasks

## Introductie
In deze tutorial **leert u hoe u werkweken** kunt lezen uit een Microsoft Project‑agenda met behulp van de Aspose.Tasks‑bibliotheek voor Java. Of u nu een rapportagedashboard bouwt, roosters synchroniseert met een ERP‑systeem, of gegevensautomatisering voor analyses uitvoert, programmatische toegang tot werkweekdefinities bespaart talloze handmatige uren. Aspose.Tasks ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan projectbestanden van honderden pagina's verwerken zonder het volledige bestand in het geheugen te laden, waardoor u zowel flexibiliteit als prestaties krijgt.

## Snelle antwoorden
- **Wat betekent “werkweken lezen”?** Het verwijst naar het extraheren van werkweekdefinities (datums en dagelijkse werktijdregels) uit een Project‑bestand via Java‑code.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (gratis proefversie beschikbaar).  
- **Heb ik een licentie nodig voor ontwikkeling?** Een proefversie werkt voor testen; een commerciële licentie is vereist voor productie‑implementaties.  
- **Welke bestandsformaten worden ondersteund?** Zowel *.mpp* als Project‑XML‑bestanden worden verwerkt, plus meer dan 50 andere formaten voor import/export.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten zodra de bibliotheek is ingesteld.

## Wat is een werkweek in MS Project?
Een werkweek definieert de agendarules die bepalen wanneer resources beschikbaar zijn gedurende een specifieke periode. Het omvat een startdatum, een einddatum en dagelijkse werktijd‑intervallen (bijv. 9 uur‑–17 uur). In MS Project kan elke agenda meerdere werkweken bevatten, zodat u vakanties, ploegendiensten of seizoensroosters kunt modelleren.

## Hoe leest Aspose.Tasks werkweken uit een agenda?
Aspose.Tasks biedt toegang tot de `WorkWeekCollection` van een `Calendar`‑object. Door een `Project`‑instantie te maken, de gewenste agenda te selecteren (op UID of naam) en over de `WorkWeekCollection` te itereren, kunt u elk werkweek‑label, de effectieve datumbereik en de gedetailleerde dagelijkse werktijd‑slots ophalen. De API handelt alle datum‑tijdconversies af en respecteert automatisch de tijdzone‑instellingen van het project.

## Waarom werkweken lezen in Java uit een Microsoft Project‑agenda?
Werkweken programmatisch lezen elimineert handmatig kopiëren‑plakken, zorgt ervoor dat downstream‑systemen (ERP, HR, rapportage) exact dezelfde planningsregels gebruiken, en garandeert consistentie over meerdere projecten. Automatisering vermindert bovendien menselijke fouten en versnelt integratie‑pipelines, vooral wanneer u ’s nachts tientallen projectbestanden moet verwerken.

## Vereisten
Voordat we in de code duiken, zorg dat u het volgende heeft:

1. **Java Development Kit (JDK)** – versie 8 of later geïnstalleerd.  
2. **Aspose.Tasks voor Java** – download de nieuwste JAR van de officiële site: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Een **voorbeeld‑Project‑bestand** (`ReadWorkWeeksInformation.mpp`) geplaatst in een bekende map op uw computer.

## Pakketten importeren
Eerst importeren we de klassen die we nodig hebben om met agenda’s en werkweken te werken:

`Project` vertegenwoordigt een Microsoft Project‑bestand, `Calendar` levert de agenda’s, `WorkWeek` definieert een werkweek, en `WeekDay` staat voor een dag.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Stap 1: stel uw gegevensmap in
Definieer de map die het `.mpp`‑bestand bevat. Vervang de placeholder door het daadwerkelijke pad op uw machine:

```java
String dataDir = "Your Data Directory";
```

## Stap 2: maak een Project‑instantie en krijg toegang tot de agenda
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand en biedt toegang tot de datastructuren, inclusief agenda’s, taken en resources.  
Instantieer een `Project`‑object, kies de agenda die u wilt (op UID), en verkrijg de `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Als u niet zeker bent van de agenda‑UID, iterate dan door `project.getCalendars()` en print eerst de naam en UID van elke agenda.

## Stap 3: doorloop werkweken
De `WorkWeek`‑klasse omvat een werkweekdefinitie, met start/einddatums en dagelijkse werktijdinstellingen.  
Loop door elke `WorkWeek` om de naam, start/einddatums en de dagelijkse werktijden weer te geven:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Wat u zult zien:** De console print elk werkweek‑label (bijv. “Standaard”), het effectieve datumbereik, en u kunt de exacte werktijden per dag inzien.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `NullPointerException` bij toegang tot `calendar` | Verkeerde UID of agenda bestaat niet | Controleer de UID met `project.getCalendars().size()` en lijst eerst de beschikbare agenda’s op. |
| Geen output voor werkweken | De geselecteerde agenda heeft geen aangepaste werkweken (gebruikt standaard) | Gebruik de standaardagenda (`project.getDefaultCalendar()`) of maak een werkweek programmatisch aan. |
| Datumnotatie ziet er vreemd uit | `System.out.println` gebruikt de standaard `java.util.Date`‑notatie | Pas een `SimpleDateFormat` toe om datums naar wens te formatteren. |

## Veelgestelde vragen
**Q: Kan ik de werkweekinformatie wijzigen met Aspose.Tasks voor Java?**  
A: Ja. De API biedt `addWorkWeek()`, `removeWorkWeek()` en property‑setters om namen, datums en werktijden aan te passen.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut. Het ondersteunt MPP‑bestanden van Project 98 tot de nieuwste releases, evenals Project‑XML‑bestanden.

**Q: Kan ik Aspose.Tasks integreren met andere Java‑frameworks?**  
A: Ja. De bibliotheek is pure Java, dus u kunt het naast Spring, Jakarta EE of elk ander framework gebruiken.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, u kunt een gratis 30‑daagse proefversie downloaden van de officiële site: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning vinden voor Aspose.Tasks?**  
A: Het Aspose‑communityforum is de beste plek: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2026-08-13  
**Getest met:** Aspose.Tasks for Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Agenda toevoegen aan project met Aspose.Tasks voor Java](/tasks/java/calendars/create/)
- [Agenda‑uitzonderingen ophalen met Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Hoe agenda instellen en weekdagen definiëren in MS Project met Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}