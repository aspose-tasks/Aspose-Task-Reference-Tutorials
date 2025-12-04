---
date: 2025-12-04
description: Leer hoe u de projectkalender instelt en de kalender‑eigenschappen van
  MS Project beheert in Java met Aspose.Tasks. Stapsgewijze handleiding om de werkuren
  van de kalender weer te geven en schema’s aan te passen.
language: nl
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe stel je een projectkalender in met Aspose.Tasks voor Java
url: /java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een projectkalender instellen met Aspose.Tasks voor Java

## Inleiding
In deze tutorial ontdek je **hoe je een projectkalender** programmatically kunt instellen met de Aspose.Tasks‑bibliotheek voor Java. Het beheren van kalender‑eigenschappen stelt je in staat **kalenderwerkuren weer te geven**, aangepaste werkdagen te definiëren en je projectschema af te stemmen op real‑world beperkingen. We lopen elke stap door — van het opzetten van de omgeving tot het itereren over kalenders en het lezen van hun eigenschappen — zodat je vol vertrouwen MS Project‑kalenders in je applicaties kunt beheren.

## Snelle antwoorden
- **Wat betekent “projectkalender instellen”?** Het betekent het aanmaken of bijwerken van de werktijden, basis‑kalender en dagtypes van een kalender binnen een MS Project‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (elke recente versie).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik kalenderwerkuren weergeven?** Ja — door elke `WeekDay` te lezen kun je de uren voor elk dagtype outputten.  
- **Is dit compatibel met Maven/Gradle?** Absoluut — voeg de Aspose.Tasks‑JAR toe als dependency.

## Wat is een projectkalender?
Een projectkalender definieert de werkdagen en -uren voor taken, resources en de algehele projecttijdlijn. In MS Project kunnen kalenders erven van een basis‑kalender, en elk dagtype (bijv. **Standard**, **Non‑working**) kan eigen werktijd hebben. Het programmatically beheren van deze instellingen maakt dynamische schema‑aanpassingen mogelijk zonder handmatige bewerking.

## Waarom MS Project‑kalender programmatically beheren?
- **Automatisering:** Pas kalenders aan in veel projecten met één script.  
- **Consistentie:** Handhaaf organisatie‑brede werktijd‑beleid.  
- **Integratie:** Synchroniseer kalenders met externe systemen (HR, ERP).  
- **Zichtbaarheid:** Snel **kalenderwerkuren weergeven** voor rapportage of debugging.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

- **Java Development Kit (JDK) 8+** geïnstalleerd en `JAVA_HOME` geconfigureerd.  
- **Aspose.Tasks voor Java** bibliotheek gedownload van de [download page](https://releases.aspose.com/tasks/java/). Voeg de JAR toe aan de classpath van je project of als Maven/Gradle‑dependency.  

## Importpakketten
Importeer eerst de core Aspose.Tasks‑klassen die we door de hele tutorial heen gebruiken:

```java
import com.aspose.tasks.*;
```

## Stap 1: De gegevensmap instellen
Definieer de map die je projectbestanden bevat. Vervang de placeholder door het daadwerkelijke pad op jouw machine.

```java
String dataDir = "Your Data Directory";
```

## Stap 2: Tijdseenheden definiëren
Werktijden worden uitgedrukt in milliseconden. Het definiëren van herbruikbare constanten maakt de code leesbaarder.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Stap 3: Projectgegevens laden
Maak een `Project`‑instantie door een bestaand MS Project‑XML‑bestand (`.xml` of `.mpp`) te laden. Hiermee krijg je toegang tot alle kalenders die in het bestand zijn opgeslagen.

```java
Project project = new Project(dataDir + "project.xml");
```

## Stap 4: Door kalenders itereren en werktijden weergeven
Nu lopen we door elke kalender, printen we de unieke identifier, naam, basis‑kalender en de werktijden voor elk dagtype. Dit demonstreert **hoe je een projectkalender** instelt en ook **hoe je kalenderwerkuren weergeeft**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Wat deze code doet
- **Filtert kalenders zonder naam** (sommige interne kalenders kunnen een `null` naam hebben).  
- **Print UID en naam** — handig om later de kalender te identificeren.  
- **Toont de basis‑kalender** — of “Self” (de kalender is zijn eigen basis) of de naam van de geërfde kalender.  
- **Itereert over elke `WeekDay`** om de totale werktijd te berekenen en uit te voeren (`workingTime` staat in milliseconden, dus delen we door `OneHour`).  

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `NullPointerException` op `cal.getBaseCalendar()` | Kalender is zelf een basis‑kalender (`isBaseCalendar()` retourneert `true`). | Gebruik de ternary‑check zoals getoond (`cal.isBaseCalendar() ? "Self" : ...`). |
| Geen output voor werktijden | Het projectbestand gebruikt een andere tijdseenheid (ticks). | Controleer het bestandsformaat; Aspose.Tasks normaliseert naar milliseconden, maar zorg dat je het juiste bestandstype laadt. |
| `project.xml` niet gevonden | Onjuist `dataDir`‑pad. | Gebruik een absoluut pad of `Paths.get(dataDir, "project.xml").toString()`. |

## Veelgestelde vragen

**V: Kan ik kalender‑eigenschappen programmatically wijzigen met Aspose.Tasks?**  
A: Ja, de API biedt volledige lees‑/schrijftoegang tot kalenders, zodat je werktijden, uitzonderingen en basis‑kalenderrelaties kunt toevoegen, bewerken of verwijderen.

**V: Zijn er beperkingen aan kalender‑aanpassing met Aspose.Tasks?**  
A: De bibliotheek spiegelt de mogelijkheden van Microsoft Project, dus je kunt vrijwel alle kalender‑aspecten aanpassen. Alleen zeer oude Project‑versies kunnen kleine compatibiliteitsproblemen hebben.

**V: Kan ik kalenderbeheer integreren in bestaande Java‑projecten?**  
A: Absoluut. Voeg simpelweg de Aspose.Tasks‑JAR toe aan je build‑path en gebruik dezelfde code‑patronen als hier getoond.

**V: Ondersteunt Aspose.Tasks andere project‑managementfunctionaliteiten naast kalenderbeheer?**  
A: Ja, het dekt taken, resources, toewijzingen, outlines, baselines en meer — een complete oplossing voor Java‑gebaseerde projectautomatisering.

**V: Is er technische ondersteuning beschikbaar voor ontwikkelaars die Aspose.Tasks gebruiken?**  
A: Ja, Aspose biedt speciale forums, e‑mailondersteuning en uitgebreide documentatie voor alle gelicentieerde gebruikers.

## Conclusie
Door deze gids te volgen weet je nu **hoe je een projectkalender** instelt, **kalenderwerkuren weergeeft**, en deze mogelijkheden in elke Java‑applicatie integreert met Aspose.Tasks. Dit stelt je in staat om schema‑aanpassingen te automatiseren, consistente werktijd‑beleid af te dwingen en rijkere project‑managementoplossingen te bouwen.

---

**Laatst bijgewerkt:** 2025-12-04  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}