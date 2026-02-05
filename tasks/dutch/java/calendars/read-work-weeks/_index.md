---
date: 2026-02-05
description: Leer hoe u werkweken in Java kunt lezen uit een Microsoft Project‑kalender
  met Aspose.Tasks. Volg de stapsgewijze handleiding met volledige code‑voorbeelden.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe werkweken in Java lezen vanuit MS Project‑kalender met Aspose.Tasks
url: /nl/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe werkweken Java te lezen vanuit MS Project‑kalender Aspose.Tasks

## Introductie
In deze tutorial leer je **hoe je werkweken Java kunt lezen** uit een Microsoft Project‑kalender met behulp van de Aspose.Tasks‑bibliotheek. Of je nu een rapportagetool bouwt, roosters synchroniseert of projectgegevens automatisch extraheert, programmatic toegang tot werkweekdefinities bespaart talloze handmatige uren. We lopen de benodigde setup door, laten je de exacte code zien om werkweekdetails op te halen, en leggen elke stap uit zodat je de oplossing kunt aanpassen aan je eigen projecten.

## Snelle antwoorden
- **Wat betekent “read workweeks java”?** Het verwijst naar het extraheren van werkweekdefinities uit een Project‑bestand met Java‑code.  
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java (gratis proefversie beschikbaar).  
- **Heb ik een licentie nodig voor ontwikkeling?** Een proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Welke bestandsformaten worden ondersteund?** Zowel *.mpp* als Project‑XML‑bestanden worden verwerkt.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten zodra de bibliotheek is ingesteld.

## Hoe werkweken Java te lezen vanuit een Microsoft Project‑kalender
Het lezen van werkweken in Java betekent dat je de Aspose.Tasks‑API gebruikt om de `WorkWeekCollection` van een kalenderobject binnen een Microsoft Project‑bestand te benaderen. Elke `WorkWeek` bevat de start/einddatums en de dagelijkse werktijddefinities die bepalen hoe resources worden ingepland.

## Waarom werkweken Java lezen vanuit een Microsoft Project‑kalender?
- **Automatisering:** Handmatig kopiëren‑en‑plakken van planningsgegevens elimineren.  
- **Integratie:** Werkweekinformatie invoeren in ERP-, HR- of aangepaste rapportagesystemen.  
- **Consistentie:** Zekerstellen dat alle downstream‑tools dezelfde kalenderregels respecteren die in het Project‑bestand zijn gedefinieerd.

## Voorvereisten
Voordat we in de code duiken, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of later geïnstalleerd.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de officiële site: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Een **voorbeeld Project‑bestand** (`ReadWorkWeeksInformation.mpp`) geplaatst in een bekende map.

## Pakketten importeren
Eerst importeren we de klassen die we nodig hebben om met kalenders en werkweken te werken:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Stap 1: Stel uw gegevensmap in
Definieer de map die het `.mpp`‑bestand bevat. Vervang de placeholder door het daadwerkelijke pad op uw machine:

```java
String dataDir = "Your Data Directory";
```

## Stap 2: Maak een Project‑instantie en krijg toegang tot de kalender
Instantieer een `Project`‑object, kies de gewenste kalender (op UID), en verkrijg de `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Als je de kalender‑UID niet zeker weet, kun je itereren over `project.getCalendars()` en de naam en UID van elke kalender afdrukken.

## Stap 3: Doorloop werkweken
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

**Wat je zult zien:** De console print het label van elke werkweek (bijv. “Standard”), het effectieve datumbereik, en je kunt de exacte werktijden per dag inzien.

## Veelvoorkomende problemen en oplossingen
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Verkeerde UID of kalender bestaat niet | Verifieer de UID met `project.getCalendars().size()` en lijst eerst de beschikbare kalenders op. |
| No output for work weeks | De geselecteerde kalender heeft geen aangepaste werkweken (gebruikt standaard) | Gebruik de standaardkalender (`project.getDefaultCalendar()`) of maak een werkweek programmatisch aan. |
| Date format looks odd | `System.out.println` gebruikt de standaard `java.util.Date`‑notatie | Pas een `SimpleDateFormat` toe om datums naar wens te formatteren. |

## Veelgestelde vragen

**Q: Kan ik de werkweekinformatie wijzigen met Aspose.Tasks for Java?**  
A: Ja. De API biedt methoden zoals `addWorkWeek()`, `removeWorkWeek()` en property‑setters om namen, datums en werktijden aan te passen.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut. Het ondersteunt MPP‑bestanden van Project 98 tot de nieuwste versies, evenals Project‑XML‑bestanden.

**Q: Kan ik Aspose.Tasks integreren met andere Java‑frameworks?**  
A: Ja. De bibliotheek is pure Java, dus je kunt hem gebruiken naast Spring, Jakarta EE of elk ander framework.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, je kunt een gratis 30‑daagse proefversie downloaden van de officiële site: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning vinden voor Aspose.Tasks?**  
A: Het Aspose‑communityforum is de beste plek: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusie
Je hebt nu geleerd **hoe je werkweken Java kunt lezen** met Aspose.Tasks. Door de bovenstaande stappen te volgen kun je programmatic werkweekdefinities uit elke MS Project‑kalender halen, die gegevens in je applicaties integreren en rooster‑gerelateerde workflows automatiseren. Voel je vrij om te experimenteren met het aanmaken of bijwerken van werkweken — Aspose.Tasks maakt het eenvoudig.

---

**Laatst bijgewerkt:** 2026-02-05  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}