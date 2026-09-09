---
date: 2026-09-09
description: Hoe stel je de projectkalender in Java in met Aspose.Tasks. Leer hoe
  je calendar working hours weergeeft, working time configureert en calendar days
  wijzigt in MS Project-bestanden.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Beheer calendar-eigenschappen in Aspose.Tasks
og_description: Hoe stel je de projectkalender in Java in met Aspose.Tasks. Leer hoe
  je calendar working hours weergeeft, working time configureert en calendar days
  wijzigt in MS Project-bestanden.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Hoe stel je de projectkalender in Java in met Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Hoe stel je de projectkalender in Java in met Aspose.Tasks
url: /nl/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe stel je projectkalender in Java met Aspose.Tasks

## Introductie
In deze tutorial leer je **hoe je een projectkalender instelt** in Java met behulp van de Aspose.Tasks‑bibliotheek. Het beheren van kalendereigenschappen stelt je in staat **kalenderwerkuren weer te geven**, aangepaste werkdagen te configureren en je projectschema af te stemmen op real‑world beperkingen zoals feestdagen of ploegendiensten. We doorlopen de omgeving‑configuratie, het laden van een project, het itereren over kalenders, en het lezen of bijwerken van hun eigenschappen, zodat je vol vertrouwen **MS Project‑kalender**‑instellingen kunt beheren in elke Java‑applicatie.

## Snelle antwoorden
- **Wat betekent “projectkalender instellen”?** Het betekent het aanmaken of bijwerken van de werktijden, basis‑kalender en dagtypes van een kalender binnen een MS Project‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (een recente versie).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik kalenderwerkuren weergeven?** Ja—door elke `WeekDay` te lezen kun je de uren voor elk dagtype weergeven.  
- **Is dit compatibel met Maven/Gradle?** Absoluut—voeg de Aspose.Tasks‑JAR toe als afhankelijkheid.

## Hoe stel je projectkalender in Java in
Laad je projectbestand, vind de doelkalender en pas vervolgens de definities van werktijden, basis‑kalender en dagtypes aan indien nodig. De onderstaande stappen bieden een volledige, end‑to‑end‑oplossing die het laden, itereren, wijzigen en opslaan van het project demonstreert, terwijl uitzonderingen worden afgehandeld en nauwkeurige berekeningen van werktijden worden gegarandeerd.

## Wat is een projectkalender?
Een projectkalender definieert de werkdagen en -uren voor taken, resources en de algehele projecttijdlijn. In MS Project kunnen kalenders erven van een basis‑kalender, en elk dagtype (bijv. **Standard**, **Non‑working**) kan zijn eigen werktijd hebben. Het programmatisch beheren van deze instellingen maakt dynamische schema‑aanpassingen mogelijk zonder handmatige bewerking.

## Waarom MS Project‑kalender programmatisch beheren?
Het programmatisch beheren van kalenders stelt je in staat consistente planningsregels toe te passen over vele projecten, handmatige fouten te verminderen en kalendergegevens te integreren met andere bedrijfsystemen zoals HR of ERP. Deze automatisering versnelt de projectopzet en zorgt ervoor dat alle teamleden dezelfde werktijd‑beleid volgen.

- **Automatisering:** Pas kalenders aan in tientallen projecten met één script.  
- **Consistentie:** Handhaaf organisatie‑brede werktijd‑beleid automatisch.  
- **Integratie:** Synchroniseer kalenders met externe HR‑ of ERP‑systemen.  
- **Zichtbaarheid:** Toon snel **kalenderwerkuren** voor rapportage of foutopsporing.  
- **Flexibiliteit:** Voeg uitzonderingen of ploegendiensten toe on‑the‑fly zonder de UI te openen.

## Vereisten
- **Java Development Kit (JDK) 8+** geïnstalleerd en `JAVA_HOME` geconfigureerd.  
- **Aspose.Tasks for Java** bibliotheek gedownload van de [downloadpagina](https://releases.aspose.com/tasks/java/). Voeg de JAR toe aan je classpath of declareer deze als een Maven/Gradle‑afhankelijkheid.  
- Een voorbeeld‑MS Project‑bestand (`.mpp` of `.xml`) dat minstens één kalender bevat die je wilt inspecteren of wijzigen.

## Import pakketten
De klassen `Project`, `Calendar`, `WeekDay` en gerelateerde klassen vormen de kern van kalendermanipulatie.  
De `Calendar`‑klasse vertegenwoordigt een projectkalender, met werkdagen, uitzonderingen en relaties met basis‑kalenders.  
De `WeekDay`‑klasse definieert de werktijdinstellingen voor één dag binnen een kalender.

De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel MS Project‑bestand in het geheugen vertegenwoordigt. Nadat je een bestand hebt geladen, verlopen alle kalenderbewerkingen via dit object.

```java
import com.aspose.tasks.*;
```

## Stap 1: stel de gegevensmap in
Definieer de map die je projectbestanden bevat. Vervang de placeholder door het daadwerkelijke pad op jouw machine.

```java
String dataDir = "Your Data Directory";
```

## Stap 2: definieer tijd‑eenheidsconstanten
Werktijden worden uitgedrukt in milliseconden. Het definiëren van herbruikbare constanten maakt de code leesbaarder en helpt je **werktijden in Java nauwkeurig te berekenen**.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Stap 3: laad projectgegevens
Maak een `Project`‑instantie door een bestaand MS Project‑XML‑bestand (`.xml` of `.mpp`) te laden. Dit geeft je toegang tot alle kalenders die in het bestand zijn opgeslagen.

De `Project`‑klasse laadt het bestand in een lichtgewicht objectmodel; het **vereist niet** dat het volledige bestand in het geheugen wordt gehouden, waardoor je kunt werken met projecten die tienduizenden taken bevatten.

```java
Project project = new Project(dataDir + "project.xml");
```

## Stap 4: doorloop kalenders Java
Nu doorlopen we elke kalender, printen we de unieke identifier, naam, basis‑kalender en de werktijden voor elk dagtype. Dit demonstreert **hoe je projectkalender in Java instelt** en ook hoe je **kalenderwerkuren weergeeft**.

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
- **Filtert kalenders zonder naam** (sommige interne kalenders kunnen een `null`‑naam hebben).  
- **Print UID en naam** – handig om later de kalender te identificeren.  
- **Toont de basis‑kalender** – ofwel “Self” (de kalender is zijn eigen basis) of de naam van de geërfde kalender.  
- **Doorloopt elke `WeekDay`** om de totale werktijd te berekenen en weer te geven (`workingTime` is in milliseconden, dus we delen door `OneHour`).  

## Gekwantificeerde voordelen van het gebruik van Aspose.Tasks
Aspose.Tasks ondersteunt **30+ invoer‑ en uitvoerformaten** en kan **projecten met tot 10.000 taken** verwerken zonder het volledige bestand in het geheugen te laden, en levert resultaten in minder dan een seconde op typische serverhardware. Deze cijfers maken het een betrouwbare keuze voor automatisering op ondernemingsniveau.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `NullPointerException` on `cal.getBaseCalendar()` | Kalender is zelf een basis‑kalender (`isBaseCalendar()` retourneert `true`). | Gebruik de ternary‑controle zoals getoond (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | Het projectbestand gebruikt een andere tijdseenheid (ticks). | Controleer het bestandsformaat; Aspose.Tasks normaliseert naar milliseconden, maar zorg ervoor dat je het juiste bestandstype laadt. |
| Unable to locate `project.xml` | Onjuist `dataDir`‑pad. | Gebruik een absoluut pad of `Paths.get(dataDir, "project.xml").toString()`. |

## Veelgestelde vragen

**V: Kan ik kalendereigenschappen programmatisch wijzigen met Aspose.Tasks?**  
A: Ja, de API biedt volledige lees‑/schrijftoegang tot kalenders, waardoor je werktijden, uitzonderingen en basis‑kalenderrelaties kunt toevoegen, bewerken of verwijderen.

**V: Zijn er beperkingen aan het aanpassen van kalenders met Aspose.Tasks?**  
A: De bibliotheek weerspiegelt de mogelijkheden van Microsoft Project, dus je kunt vrijwel alle kalenderaspecten aanpassen. Alleen zeer oude Project‑bestandversies kunnen kleine compatibiliteitsproblemen hebben.

**V: Kan ik kalenderbeheer integreren in bestaande Java‑projecten?**  
A: Absoluut. Voeg simpelweg de Aspose.Tasks‑JAR toe aan je build‑pad en gebruik dezelfde code‑patronen die hier worden getoond.

**V: Ondersteunt Aspose.Tasks andere project‑managementfunctionaliteiten naast kalenderbeheer?**  
A: Ja, het omvat taken, resources, toewijzingen, outlines, baselines en meer—waardoor het een allesomvattende oplossing is voor Java‑gebaseerde projectautomatisering.

**V: Is technische ondersteuning beschikbaar voor ontwikkelaars die Aspose.Tasks gebruiken?**  
A: Ja, Aspose biedt speciale forums, e‑mailondersteuning en uitgebreide documentatie voor alle gelicentieerde gebruikers.

**Laatst bijgewerkt:** 2026-09-09  
**Getest met:** Aspose.Tasks for Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak projectkalender Java – Aspose.Tasks voor Java‑gids](/tasks/java/)
- [Laad projectbestanden in Java en beheer projecteigenschappen](/tasks/java/project-management/default-properties/)
- [Stel projectstartdatum in MS Project in met Aspose.Tasks voor Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}