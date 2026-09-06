---
date: 2026-08-24
description: Leer hoe je calendar exceptions java uit MS Project‑bestanden kunt ophalen
  en hoe je een mpp‑kalender kunt lezen met Aspose.Tasks voor Java. Deze tutorial
  biedt step‑by‑step code examples.
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: Hoe calendar exceptions java op te halen met Aspose.Tasks
og_description: Leer hoe je calendar exceptions java uit MS Project‑bestanden kunt
  ophalen en hoe je een mpp‑kalender kunt lezen met Aspose.Tasks voor Java. Deze step‑by‑step
  gids helpt je nauwkeurige kalenderafhandeling toe te voegen aan je Java‑apps.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Hoe calendar exceptions java op te halen met Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: Hoe calendar exceptions java op te halen met Aspose.Tasks
url: /nl/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe kalenderuitzonderingen ophalen in Java met Aspose.Tasks

## Introductie
In deze **asp tasks java tutorial** leer je hoe je kalenderuitzonderingen kunt ophalen uit een Microsoft Project‑bestand met behulp van de Aspose.Tasks‑bibliotheek voor Java. Kalenderuitzonderingen vertegenwoordigen niet‑werkperiodes zoals feestdagen of aangepaste werktijd‑regels, en ze programmatisch kunnen lezen is essentieel voor resource‑leveling, rapportage en aangepaste planningslogica. We lopen het volledige proces stap‑voor‑stap door, zodat je deze functionaliteit met vertrouwen kunt integreren in je eigen Java‑toepassingen.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Het ophalen van kalenderuitzonderingen uit een MPP‑bestand met Aspose.Tasks voor Java.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisopzet.  
- **Vereisten?** JDK, Aspose.Tasks voor Java en een IDE (IntelliJ IDEA of Eclipse).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Ondersteunde Project‑versies?** Alle belangrijke MS Project‑formaten (MPP, MPT, XML).

## Wat is asp tasks java tutorial?
De **asp tasks java tutorial** legt uit hoe je de Aspose.Tasks‑API kunt gebruiken binnen Java‑projecten. Het biedt concrete code‑fragmenten, best‑practice‑uitleg en praktijkvoorbeelden zodat ontwikkelaars Project‑bestanden kunnen manipuleren zonder Microsoft Project geïnstalleerd te hebben. Door een tutorial als deze te volgen, krijgen ontwikkelaars een duidelijk, praktisch inzicht in de structuur van de API, veelvoorkomende gebruikspatronen en hoe ze de functionaliteit kunnen integreren in grotere bedrijfsapplicaties.

## Waarom kalenderuitzonderingen ophalen?
Het ophalen van kalenderuitzonderingen stelt je in staat nauwkeurige projecttijdlijnen te genereren die rekening houden met feestdagen en aangepaste werkschema's, rapportagetools te bouwen die niet‑werkdagen benadrukken, en Project‑kalenders te synchroniseren met externe systemen zoals ERP‑ of HR‑platformen. Aspose.Tasks kan uitzonderingen lezen van **30+** kalendertypen en ondersteunt **3 belangrijke** MS Project‑bestandsformaten (MPP, MPT, XML) zonder het volledige bestand in het geheugen te laden, waardoor efficiënte verwerking van projecten met honderden pagina's mogelijk is.

## Vereisten
Voordat we beginnen, zorg ervoor dat je de volgende vereisten hebt:

1. **Java Development Kit (JDK)** – Zorg ervoor dat je JDK 8 of hoger geïnstalleerd hebt.  
2. **Aspose.Tasks for Java** – Download en installeer Aspose.Tasks for Java vanaf de **[Aspose.Tasks for Java downloadpagina](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – Je kunt elke IDE naar keuze gebruiken, zoals IntelliJ IDEA of Eclipse.

## Import pakketten
De import‑verklaringen brengen Aspose.Tasks‑klassen in je Java‑bronbestand, zodat je kunt werken met projecten, kalenders en uitzonderingen.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## Stap 1: stel je gegevensmap in
Definieer een map die het Project‑bestand bevat dat je wilt analyseren. Het gebruik van een absoluut pad of een pad relatief ten opzichte van de resources‑map van je project voorkomt `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **Pro tip:** Sla je Project‑bestanden op in een speciale resources‑map en verwijs ernaar met `Paths.get(...)` voor platform‑onafhankelijke paden.

## Stap 2: laad ms project‑bestand
De `Project`‑klasse vertegenwoordigt een MS Project‑bestand en biedt toegang tot de kalenders, taken, resources en andere projectgegevens. Laad het Project‑bestand in een `Project`‑object. Dit object vertegenwoordigt het volledige MS Project‑bestand in het geheugen en biedt toegang tot kalenders, taken, resources en meer.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Stap 3: haal kalenderuitzonderingen op
Itereer door elke kalender in het project en vervolgens door elke kalenderuitzondering binnen die kalender. Print de start‑ en einddatums van elke uitzondering.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Geen uitvoer afgedrukt** | Projectbestand bevat geen kalenderuitzonderingen. | Controleer of de kalender in MS Project gedefinieerde uitzonderingen heeft (bijv. feestdagen). |
| **`NullPointerException`** | `dataDir`‑pad is onjuist of bestand niet gevonden. | Controleer het map‑pad nogmaals en zorg dat `project.mpp` bestaat. |
| **Tijdzone‑mismatch** | Datums worden weergegeven in UTC. | Gebruik `calExc.getFromDate().toLocalDateTime()` om, indien nodig, naar lokale tijd te converteren. |

## Veelgestelde vragen
### Kan Aspose.Tasks verschillende versies van MS Project‑bestanden verwerken?
Ja, Aspose.Tasks ondersteunt **alle belangrijke** MS Project‑formaten, inclusief MPP, MPT en XML, voor versies van 2000 tot de nieuwste release.

### Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
Ja, je kunt een gratis proefversie van Aspose.Tasks downloaden via de **[Aspose gratis proefversie downloadpagina](https://releases.aspose.com/)**.

### Waar kan ik documentatie vinden voor Aspose.Tasks voor Java?
Je kunt de documentatie raadplegen op **[Aspose.Tasks Java API‑referentie](https://reference.aspose.com/tasks/java/)**.

### Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?
Je kunt ondersteuning krijgen via het community‑forum **[Aspose.Tasks community‑forum](https://forum.aspose.com/c/tasks/15)**.

### Is er een optie voor tijdelijke licenties voor Aspose.Tasks?
Ja, je kunt tijdelijke licenties verkrijgen via de **[pagina voor aankoop van tijdelijke licentie](https://purchase.aspose.com/temporary-license/)**.

**Aanvullende Q&A**

**V:** *Kan ik kalenderuitzonderingen wijzigen nadat ik ze heb opgehaald?*  
**A:** Absoluut. Gebruik `CalendarException.setFromDate()` en `setToDate()` om datums aan te passen, en sla vervolgens het project op met `project.save(...)`.

**V:** *Behoudt Aspose.Tasks aangepaste velden op kalenders?*  
**A:** Ja, alle aangepaste velden en uitgebreide attributen worden behouden bij het laden en opslaan van het project.

## Conclusie
In deze **asp tasks java tutorial** hebben we geleerd hoe we kalenderuitzonderingen kunnen ophalen uit MS Project met Aspose.Tasks voor Java. Door deze eenvoudige stappen te volgen, kun je deze functionaliteit naadloos integreren in je Java‑applicaties, waardoor rijkere planningsfuncties en nauwkeurigere projectanalyses mogelijk worden.

---

**Laatste update:** 2026-08-24  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## Gerelateerde tutorials

- [Maak aangepaste kalenderuitzonderingen met Aspose.Tasks voor Java](/tasks/java/calendar-exceptions/)
- [Hoe Aspose.Tasks te gebruiken om MS Project‑kalenderinformatie op te halen](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [Hoe werkweken in Java te lezen uit MS Project‑kalender met Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}