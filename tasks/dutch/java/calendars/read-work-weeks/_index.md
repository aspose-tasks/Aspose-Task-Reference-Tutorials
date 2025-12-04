---
date: 2025-12-03
description: Leer hoe u werkweken in Java kunt lezen uit een Microsoft Project‑kalender
  met Aspose.Tasks. Volg de stapsgewijze handleiding met volledige codevoorbeelden.
language: nl
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Werkweken lezen in Java vanuit MS Project‑kalender Aspose.Tasks
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Werkweken lezen in Java vanuit MS Project Kalender Aspose.Tasks

## Introductie
In deze tutorial **lees je werkweken in Java** uit een Microsoft Project‑kalender met behulp van de Aspose.Tasks‑bibliotheek. Of je nu een rapportagetool bouwt, planningen synchroniseert, of projectdata‑extractie automatiseert, programmatisch toegang krijgen tot werkweek‑definities bespaart ontelbare handmatige uren. We lopen de benodigde configuratie door, laten je de exacte code zien om werkweek‑details op te halen, en leggen elke stap uit zodat je de oplossing kunt aanpassen aan je eigen projecten.

## Snelle antwoorden
- **Wat betekent “read work weeks java”?** Het verwijst naar het extraheren van werkweek‑definities uit een Project‑bestand met Java‑code.  
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java (gratis proefversie beschikbaar).  
- **Heb ik een licentie nodig voor ontwikkeling?** Een proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Welke bestandsformaten worden ondersteund?** Zowel *.mpp* als Project‑XML‑bestanden worden verwerkt.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten zodra de bibliotheek is ingesteld.

## Wat is “read work weeks java”?
Werkweken lezen in Java betekent dat je de Aspose.Tasks‑API gebruikt om de `WorkWeekCollection` van een kalenderobject binnen een Microsoft Project‑bestand te benaderen. Elke `WorkWeek` bevat de start‑/einddatums en de dagelijkse werktijd‑definities die bepalen hoe resources worden ingepland.

## Waarom werkweken lezen in Java vanuit een Microsoft Project‑kalender?
- **Automatisering:** Handmatig kopiëren‑plakken van planningsdata elimineren.  
- **Integratie:** Werkweek‑informatie invoeren in ERP-, HR- of aangepaste rapportagesystemen.  
- **Consistentie:** Zorgen dat alle downstream‑tools dezelfde kalenderregels uit het Project‑bestand respecteren.

## Voorwaarden
Voordat we in de code duiken, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of later geïnstalleerd.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de officiële site: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Een **voorbeeld Project‑bestand** (`ReadWorkWeeksInformation.mpp`) geplaatst in een bekende map.

## Pakketten importeren
First, import the classes we’ll need to interact with calendars and work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Stap 1: Stel je gegevensmap in
Define the folder that contains the `.mpp` file. Replace the placeholder with the actual path on your machine:

```java
String dataDir = "Your Data Directory";
```

## Stap 2: Maak een Project‑instantie en krijg toegang tot de kalender
Instantiate a `Project` object, pick the calendar you want (by UID), and obtain its `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Als je de kalender‑UID niet zeker weet, kun je itereren over `project.getCalendars()` en de naam en UID van elke kalender afdrukken.

## Stap 3: Doorloop werkweken
Loop through each `WorkWeek` to display its name, start/end dates, and the daily working times:

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

**Wat je zult zien:** De console drukt het label van elke werkweek (bijv. “Standard”), het toepassingsdatumbereik, en je kunt de exacte werktijden per dag bekijken.

## Veelvoorkomende problemen en oplossingen
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Verkeerde UID of kalender bestaat niet | Controleer de UID met `project.getCalendars().size()` en lijst eerst de beschikbare kalenders. |
| No output for work weeks | De geselecteerde kalender heeft geen aangepaste werkweken (gebruikt standaard). | Gebruik de standaardkalender (`project.getDefaultCalendar()`) of maak een werkweek programmatisch aan. |
| Date format looks odd | `System.out.println` gebruikt het standaard `java.util.Date`‑formaat. | Pas een `SimpleDateFormat` toe om datums naar wens te formatteren. |

## Veelgestelde vragen

**V: Kan ik de werkweek‑informatie wijzigen met Aspose.Tasks for Java?**  
A: Ja. De API biedt methoden zoals `addWorkWeek()`, `removeWorkWeek()` en property‑setters om namen, datums en werktijden te wijzigen.

**V: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut. Het ondersteunt MPP‑bestanden van Project 98 tot de nieuwste versies, evenals Project‑XML‑bestanden.

**V: Kan ik Aspose.Tasks integreren met andere Java‑frameworks?**  
A: Ja. De bibliotheek is pure Java, dus je kunt het gebruiken naast Spring, Jakarta EE of elk ander framework.

**V: Is er een proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, je kunt een gratis 30‑daagse proefversie downloaden van de officiële site: [Aspose.Tasks trial](https://releases.aspose.com/).

**V: Waar kan ik ondersteuning vinden voor Aspose.Tasks?**  
A: Het Aspose‑communityforum is de beste plek: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusie
Je hebt nu **werkweken lezen in Java** onder de knie met Aspose.Tasks. Door de bovenstaande stappen te volgen kun je programmatisch werkweek‑definities uit elke MS Project‑kalender halen, die data integreren in je applicaties, en planningsgerelateerde workflows automatiseren. Voel je vrij om te experimenteren met het maken of bijwerken van werkweken — Aspose.Tasks maakt dit eenvoudig.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}