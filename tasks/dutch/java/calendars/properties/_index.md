---
date: 2026-02-07
description: Leer hoe je de projectkalender in Java instelt en de eigenschappen van
  de MS Project‑kalender beheert met Aspose.Tasks. Stapsgewijze handleiding om de
  werkuren van de kalender weer te geven en schema’s aan te passen.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een projectkalender in Java instellen met Aspose.Tasks
url: /nl/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Projectkalender Instellen in Java met Aspose.Tasks

## Inleiding
In deze tutorial ontdek je **hoe je projectkalender java** programmatically instelt met behulp van de Aspose.Tasks bibliotheek voor Java. Het beheren van kalendereigenschappen stelt je in staat **kalenderwerkuren weer te geven**, aangepaste werkdagen te definiëren en je projectschema af te stemmen op real‑world beperkingen. We lopen elke stap door — van het opzetten van de omgeving tot het itereren over kalenders en het lezen van hun eigenschappen — zodat je vol vertrouwen **ms project kalender** instellingen kunt beheren in je applicaties.

## Snelle Antwoorden
- **Wat betekent “set project calendar”?** Het betekent het creëren of bijwerken van de werktijden, basisagenda en dagtypes van een kalender binnen een MS Project‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (een recente versie).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik kalenderwerkuren weergeven?** Ja — door elke `WeekDay` te lezen kun je de uren voor elk dagtype outputten.  
- **Is dit compatibel met Maven/Gradle?** Absoluut — voeg de Aspose.Tasks JAR toe als dependency.

## Hoe Projectkalender Instellen in Java
Deze sectie behandelt direct het primaire zoekwoord. We behandelen de exacte stappen die je nodig hebt om **set project calendar java** waarden in te stellen, kalenderwerkdagen te wijzigen en werkuren in java‑stijl te berekenen.

## Wat is een Projectkalender?
Een projectkalender definieert de werkdagen en uren voor taken, resources en de algehele projecttijdlijn. In MS Project kunnen kalenders overerven van een basisagenda, en elk dagtype (bijv. **Standard**, **Non‑working**) kan zijn eigen werktijd hebben. Het programmatically beheren van deze instellingen maakt dynamische schema‑aanpassingen mogelijk zonder handmatige bewerking.

## Waarom MS Project Kalender Programmatically Beheren?
- **Automatisering:** Pas kalenders aan over vele projecten met één script.  
- **Consistentie:** Handhaaf organisatie‑brede werktijdbeleid.  
- **Integratie:** Synchroniseer kalenders met externe systemen (HR, ERP).  
- **Zichtbaarheid:** Snel **display calendar working hours** weergeven voor rapportage of debugging.  
- **Flexibiliteit:** Je kunt **modify calendar working days** of uitzonderingen toevoegen on the fly.

## Vereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

- **Java Development Kit (JDK) 8+** geïnstalleerd en `JAVA_HOME` geconfigureerd.  
- **Aspose.Tasks for Java** bibliotheek gedownload van de [download page](https://releases.aspose.com/tasks/java/). Voeg de JAR toe aan de classpath van je project of Maven/Gradle dependencies.  

## Import Pakketten
Eerst importeer je de core Aspose.Tasks klassen die we gedurende de tutorial zullen gebruiken:

```java
import com.aspose.tasks.*;
```

## Stap 1: Data Directory Instellen
Definieer de map die je projectbestanden bevat. Vervang de placeholder door het daadwerkelijke pad op je machine.

```java
String dataDir = "Your Data Directory";
```

## Stap 2: Tijdseenheden Definiëren
Werktijden worden uitgedrukt in milliseconden. Het definiëren van herbruikbare constanten maakt de code makkelijker leesbaar en helpt je **calculate working hours java** nauwkeurig.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Stap 3: Projectgegevens Laden
Maak een `Project` instantie aan door een bestaand MS Project XML‑bestand (`.xml` of `.mpp`) te laden. Dit geeft ons toegang tot alle kalenders die in het bestand zijn opgeslagen.

```java
Project project = new Project(dataDir + "project.xml");
```

## Doorloop Kalenders Java
Nu doorlopen we elke kalender, printen we de unieke identifier, naam, basisagenda en de werkuren voor elk dagtype. Dit demonstreert **how to set project calendar java** waarden en ook hoe **display calendar working hours** te tonen.

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

### Wat Deze Code Doet
- **Filtert kalenders zonder naam** (sommige interne kalenders kunnen een `null` naam hebben).  
- **Print UID en naam** – handig om later de kalender te identificeren.  
- **Toont de basisagenda** – ofwel “Self” (de kalender is zijn eigen basis) of de naam van de geërfde agenda.  
- **Doorloopt elke `WeekDay`** om de totale werkuren te berekenen en weer te geven (`workingTime` is in milliseconden, dus we delen door `OneHour`).  

## Veelvoorkomende Problemen en Oplossingen
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` op `cal.getBaseCalendar()` | Kalender is zelf een basisagenda (`isBaseCalendar()` retourneert `true`). | Gebruik de ternary‑check zoals getoond (`cal.isBaseCalendar() ? "Self" : ...`). |
| Geen output voor werkuren | Het projectbestand gebruikt een andere tijdseenheid (ticks). | Controleer het bestandsformaat; Aspose.Tasks normaliseert naar milliseconden, maar zorg ervoor dat je het juiste bestandstype laadt. |
| Kan `project.xml` niet vinden | Onjuist `dataDir` pad. | Gebruik een absoluut pad of `Paths.get(dataDir, "project.xml").toString()`. |

## Veelgestelde Vragen

**Q: Kan ik kalender‑eigenschappen programmatically wijzigen met Aspose.Tasks?**  
A: Ja, de API biedt volledige lees‑/schrijftoegang tot kalenders, waardoor je werktijden, uitzonderingen en basisagenda‑relaties kunt toevoegen, bewerken of verwijderen.

**Q: Zijn er beperkingen aan kalender‑aanpassing met Aspose.Tasks?**  
A: De bibliotheek spiegelt de mogelijkheden van Microsoft Project, dus je kunt vrijwel alle kalenderaspecten aanpassen. Alleen zeer oude Project‑bestandversies kunnen kleine compatibiliteitsproblemen hebben.

**Q: Kan ik kalenderbeheer integreren in bestaande Java‑projecten?**  
A: Absoluut. Voeg simpelweg de Aspose.Tasks JAR toe aan je build‑pad en gebruik dezelfde codepatronen als hier getoond.

**Q: Ondersteunt Aspose.Tasks andere projectmanagement‑functionaliteiten naast kalenderbeheer?**  
A: Ja, het omvat taken, resources, toewijzingen, outlines, baselines en meer — waardoor het een uitgebreide oplossing is voor Java‑gebaseerde projectautomatisering.

**Q: Is technische ondersteuning beschikbaar voor ontwikkelaars die Aspose.Tasks gebruiken?**  
A: Ja, Aspose biedt speciale forums, e‑mailondersteuning en uitgebreide documentatie voor alle gelicentieerde gebruikers.

---

**Laatst bijgewerkt:** 2026-02-07  
**Getest met:** Aspose.Tasks for Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}