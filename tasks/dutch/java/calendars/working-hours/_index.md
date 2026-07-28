---
date: 2026-02-05
description: Leer hoe u werkdagen kunt bepalen en de taakduur kunt berekenen door
  werkuren uit MS Project‑calendars te extraheren met Aspose.Tasks voor Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Bepaal werkdagen en werktijden met Aspose.Tasks
url: /nl/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bepaal Werkdagen & Werkuren met Aspose.Tasks

## Introductie
Het beheren van projectkalenders is een essentieel onderdeel van succesvolle projectplanning. In deze tutorial zult u **werkdagen bepalen** voor elke taak en **werkuren extraheren** uit een MS Project‑kalender met Aspose.Tasks voor Java. Aan het einde van de gids kunt u **taakduur berekenen**, werkuren aanpassen en betrouwbaar **een MPP‑bestand laden** om de benodigde gegevens op te halen. U ziet ook hoe u **MS Project**‑bestanden kunt **lezen** zonder Microsoft Project geïnstalleerd te hebben, waardoor automatisering op elk platform mogelijk is.

## Snelle Antwoorden
- **Wat betekent “werkdagen bepalen”?** Het betekent het identificeren van welke kalenderdatums als werkdagen worden beschouwd voor een gegeven taak.  
- **Welke bibliotheek moet ik gebruiken?** Aspose.Tasks voor Java biedt een volledig uitgeruste API voor het werken met MS Project‑bestanden.  
- **Hoe lang duurt de implementatie?** Meestal 10–15 minuten voor een eenvoudige extractie.  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Kan ik werkuren aanpassen?** Ja – u kunt kalenders wijzigen, feestdagen toevoegen en aangepaste werktijdreeksen instellen.  

## Wat is “werkdagen bepalen”?
Wanneer een taak wordt ingepland, definieert de projectkalender welke dagen werkdagen zijn en welke niet‑werkdagen (weekenden, feestdagen). Werkdagen bepalen betekent dat u die kalender bevraagt om precies te weten wanneer er gewerkt kan worden, wat essentieel is voor nauwkeurige **taakduur berekenen** berekeningen.

## Waarom Aspose.Tasks gebruiken om werkuren op te halen?
- **Geen Microsoft Project vereist** – u kunt MS Project‑bestanden direct vanuit Java‑code lezen.  
- **Volledige kalenderondersteuning** – omvat standaard-, resource‑ en taakkalenders.  
- **Hoge prestaties** – verwerk grote projecten snel.  
- **Uitgebreide documentatie** – voorbeelden en API‑referentie zijn direct beschikbaar.  

## Vereisten
1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van [hier](https://releases.aspose.com/tasks/java/).  
3. Basiskennis van Java‑programmeren.  

## Importeer Pakketten
Eerst importeert u de core Aspose.Tasks‑namespace:

```java
import com.aspose.tasks.*;
```

## Hoe een MPP‑bestand laden met Aspose.Tasks?
Het laden van het projectbestand is de eerste stap naar elke kalenderanalyse. De API stelt u in staat om **een MPP‑bestand te laden** in één regel code, zonder de MS Project‑UI nodig te hebben.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Taak‑ en Kalenderinformatie Ophalen
Kies de taak die u wilt analyseren en haal de bijbehorende kalender op. Hier **halen we de werkuren** voor de taak op:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Start‑ en Einddatums Definiëren
Stel het tijdvenster in waarvoor u **werkdagen wilt bepalen**. Het gebruik van de start‑ en einddatums van de taak zorgt ervoor dat u alleen de relevante periode evalueert.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Door Datums Itereren
Loop door elke datum in de duur van de taak. Deze lus helpt ons later **werkuren aan te passen** indien nodig:

```java
java.util.Calendar tempDate = calStartDate;
```

## Duur Berekenen
Tijdens de iteratie controleren we of elke dag een werkdag is, tellen we de werkuren op en berekenen we uiteindelijk de duur van de taak in minuten, uren en dagen. Deze stap laat zien hoe u **werkdagen kunt berekenen** en **taakduur kunt berekenen** programmatisch.

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

## Hoe werkuren en feestdagen aanpassen
Aspose.Tasks stelt u in staat om de werktijdreeksen van de kalender aan te passen en uitzonderingen zoals feestdagen toe te voegen. U kunt `taskCalendar.addWorkingTime()` of `taskCalendar.addException()` aanroepen om het schema af te stemmen op het beleid van uw organisatie. Dit is nuttig wanneer het standaard 9‑5‑schema niet overeenkomt met de realiteit.

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Oplossing |
|-------|----------|
| **Taak retourneert `null` voor kalender** | Zorg ervoor dat de taak daadwerkelijk een kalender toegewezen heeft; anders erft hij de standaardkalender van het project. |
| **Onjuiste duur door feestdagen** | Controleer of feestdagen zijn gedefinieerd in de kalender van de taak of in de basis‑kalender van het project. |
| **Tijdzone‑mismatch** | Gebruik `java.util.TimeZone` om de tijdzone van de kalender af te stemmen op uw systeem indien nodig. |

## Veelgestelde Vragen
### Q: Kan Aspose.Tasks voor Java complexe projectstructuren verwerken?
A: Ja, Aspose.Tasks voor Java biedt uitgebreide ondersteuning voor het verwerken van complexe projectstructuren, inclusief taken, resources en kalenders.

### Q: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?
A: Absoluut, Aspose.Tasks voor Java ondersteunt verschillende versies van MS Project, waardoor compatibiliteit over verschillende omgevingen heen wordt gegarandeerd.

### Q: Kan ik werkuren en feestdagen aanpassen in projectkalenders?
A: Ja, u kunt eenvoudig werkuren en feestdagen aanpassen aan uw projectvereisten met behulp van de Aspose.Tasks voor Java‑API's.

### Q: Biedt Aspose.Tasks voor Java ondersteuning en documentatie?
A: Ja, Aspose.Tasks voor Java biedt uitgebreide documentatie en speciale ondersteuningsforums om ontwikkelaars te helpen de functies effectief te gebruiken.

### Q: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
A: Ja, u kunt een gratis proefversie van Aspose.Tasks voor Java krijgen via [hier](https://releases.aspose.com/).

## Conclusie
In deze gids hebben we laten zien hoe u **werkdagen kunt bepalen**, **werkuren kunt ophalen**, en **taakduur kunt berekenen** uit een MS Project‑kalender met Aspose.Tasks voor Java. Door de bovenstaande stappen te volgen kunt u schema‑analyse automatiseren, kalenders aanpassen en uw projectplannen nauwkeurig en actueel houden. U heeft nu de tools om **MS Project**‑gegevens te **lezen**, een **MPP‑bestand te laden**, en precieze duur‑berekeningen uit te voeren zonder dat Microsoft Project nodig is.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}