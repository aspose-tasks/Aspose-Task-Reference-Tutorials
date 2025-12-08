---
date: 2025-12-05
description: Leer hoe u werkdagen kunt bepalen en de taakduur kunt berekenen door
  werkuren uit MS Project‑kalenders te extraheren met Aspose.Tasks voor Java.
language: nl
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Bepaal werkdagen en werktijden met Aspose.Tasks
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bepaal Werkdagen & Werkuren met Aspose.Tasks

## Inleiding
Het beheren van projectkalenders is een essentieel onderdeel van succesvolle projectplanning. In deze tutorial **bepaal je werkdagen** voor elke taak en **haal je werkuren** uit een MS Project‑kalender met behulp van Aspose.Tasks voor Java. Aan het einde van de gids kun je **de taakduur berekenen**, werkuren aanpassen en betrouwbaar een **MPP‑bestand laden** om de benodigde gegevens op te halen.

## Snelle Antwoorden
- **Wat betekent “bepaal werkdagen”?** Het betekent identificeren welke kalenderdatums als werkdagen voor een bepaalde taak worden beschouwd.  
- **Welke bibliotheek moet ik gebruiken?** Aspose.Tasks voor Java biedt een volledig uitgeruste API voor het werken met MS Project‑bestanden.  
- **Hoe lang duurt de implementatie?** Meestal 10–15 minuten voor een basis‑extractie.  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Kan ik werkuren aanpassen?** Ja – je kunt kalenders wijzigen, feestdagen toevoegen en aangepaste werktijd‑bereiken instellen.

## Wat is “bepaal werkdagen”?
Wanneer een taak wordt ingepland, definieert de projectkalender welke dagen werkdagen zijn en welke dagen geen werk (weekenden, feestdagen). Werkdagen bepalen betekent die kalender raadplegen om precies te weten wanneer er gewerkt kan worden, wat essentieel is voor nauwkeurige **berekeningen van taakduur**.

## Waarom Aspose.Tasks gebruiken om werkuren op te halen?
- **Geen Microsoft Project nodig** – werk met .MPP‑bestanden op elk platform.  
- **Volledige kalenderondersteuning** – omvat standaard-, resource‑ en taakkalenders.  
- **oge prestaties** – verwerk grote projecten snel.  
- **Uitgebreide documentatie** – voorbeelden en API‑referentie zijn direct beschikbaar.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks voor Java** – download de nieuwste JAR van [hier](https://releases.aspose.com/tasks/java/).  
3. Basiskennis van Java‑programmeren.  

## Pakketten Importeren
Importeer eerst de core Aspose.Tasks‑namespace:

```java
import com.aspose.tasks.*;
```

## Stap 1: Het MPP‑bestand laden
Laad je projectbestand (de **load mpp file**‑stap) zodat je met de kalenders kunt werken:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Stap 2: Taak‑ en Kalenderinformatie Ophalen
Selecteer de taak die je wilt analyseren en haal de bijbehorende kalender op. Dit is waar we **werkuren voor de taak ophalen**:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Stap 3: Begin‑ en Einddatums Definiëren
Stel het tijdvenster in waarvoor je **werkdagen wilt bepalen**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Stap 4: Door Datums Itereren
Loop door elke datum in de duur van de taak. Deze lus helpt ons later **werkuren aan te passen** indien nodig:

```java
java.util.Calendar tempDate = calStartDate;
```

## Stap 5: Duur Berekenen
Tijdens de iteratie controleren we of elke dag een werkdag is, tellen we de werkuren op en berekenen we uiteindelijk de duur van de taak in minuten, uren en dagen:

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

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Taak geeft `null` terug voor kalender** | Zorg ervoor dat de taak daadwerkelijk een kalender heeft toegewezen; anders erft hij de standaardkalender van het project. |
| **Onjuiste duur door feestdagen** | Controleer of feestdagen zijn gedefinieerd in de kalender van de taak of in de basis­kalender van het project. |
| **Tijdzone‑mismatch** | Gebruik `java.util.TimeZone` om de tijdzone van de kalender af te stemmen op je systeem indien nodig. |

## Veelgestelde Vragen
### Q: Kan Aspose.Tasks voor Java complexe projectstructuren aan?
A: Ja, Aspose.Tasks voor Java biedt uitgebreide ondersteuning voor het verwerken van complexe projectstructuren, inclusief taken, resources en kalenders.

### Q: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?
A: Absoluut, Aspose.Tasks voor Java ondersteunt diverse versies van MS Project, waardoor compatibiliteit over verschillende omgevingen heen gegarandeerd is.

### Q: Kan ik werkuren en feestdagen in projectkalenders aanpassen?
A: Ja, je kunt eenvoudig werkuren en feestdagen aanpassen volgens de eisen van je project met behulp van de Aspose.Tasks voor Java‑API’s.

### Q: Biedt Aspose.Tasks voor Java ondersteuning en documentatie?
A: Ja, Aspose.Tasks voor Java levert uitgebreide documentatie en toegewijde ondersteuningsforums om ontwikkelaars te helpen de functionaliteit effectief te benutten.

### Q: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
A: Ja, je kunt een gratis proefversie van Aspose.Tasks voor Java verkrijgen via [hier](https://releases.aspose.com/).

## Conclusie
In deze gids hebben we laten zien hoe je **werkdagen kunt bepalen**, **werkuren kunt ophalen** en **taakduur kunt berekenen** uit een MS Project‑kalender met Aspose.Tasks voor Java. Door de bovenstaande stappen te volgen kun je planningsanalyse automatiseren, kalenders aanpassen en je projectplannen nauwkeurig en actueel houden.

---

**Laatst bijgewerkt:** 2025-12-05  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}