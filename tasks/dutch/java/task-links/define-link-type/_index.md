---
date: 2026-08-29
description: Leer hoe u linktypen kunt instellen en taakafhankelijkheden kunt beheren
  met Aspose.Tasks for Java in een stapsgewijze tutorial.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Hoe linktypen instellen in Aspose.Tasks for Java
og_description: Leer hoe u linktypen kunt instellen en taakafhankelijkheden kunt beheren
  met Aspose.Tasks for Java. Stapsgewijze gids voor ontwikkelaars.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Hoe linktypen in te stellen in Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Hoe linktypen instellen in Aspose.Tasks for Java
url: /nl/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe koppeltypen in te stellen in Aspose.Tasks voor Java

## Introductie
Als je je afvraagt **hoe je een koppeling** tussen taken moet instellen terwijl je *taakafhankelijkheden beheert* in een project, ben je hier op de juiste plek. In deze tutorial lopen we door het maken van een nieuw project, het toevoegen van taken, en het definiëren van het koppeltype (Start‑naar‑Start, Finish‑naar‑Start, enz.) met Aspose.Tasks voor Java. Aan het einde voel je je zeker in het aanpassen van taakrelaties om te voldoen aan real‑world planningsbehoeften en zie je hoe de API grote plannen met tot 10.000 taken aankan.

## Snelle antwoorden
- **Welke klasse vertegenwoordigt een afhankelijkheid?** `TaskLink` is het kernobject dat een koppeling tussen twee taken modelleert.  
- **Welke enum definieert het relatietype?** `TaskLinkType` (bijv. `StartToStart`, `FinishToStart`).  
- **Kan ik bestaande koppeltypen lezen?** Ja – iterate `Project.getTaskLinks()` and call `getLinkType()`.  
- **Heb ik een licentie nodig voor deze code?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Is dit compatibel met Java 8+?** Absoluut – Aspose.Tasks ondersteunt Java 8 tot en met Java 21, covering 13 major releases.

## Wat is een taakkoppeling?
Een **taakkoppeling** modelleert een afhankelijkheid tussen twee taken in een projectplanning.  
Je kunt een `TaskLink` maken, wijzigen of verwijderen om voorganger‑opvolgerrelaties weer te geven, waardoor de planner automatisch start‑ en einddatums kan berekenen.

## Waarom Aspose.Tasks koppeltypen gebruiken?
Aspose.Tasks ondersteunt **meer dan 30 invoer‑ en uitvoerformaten** en kan projecten verwerken die **tot 10.000 taken** bevatten zonder het volledige bestand in het geheugen te laden. Deze gekwantificeerde capaciteit zorgt voor snelle prestaties, zelfs voor ondernemings‑grote plannen, en de bibliotheek behoudt alle Microsoft Project‑functies zoals aangepaste velden en resource‑toewijzingen.

## Vereisten
- **Java‑ontwikkelomgeving** – JDK 8 of nieuwer geïnstalleerd en geconfigureerd.  
- **Aspose.Tasks‑bibliotheek** – Download de nieuwste JAR van de [download link](https://releases.aspose.com/tasks/java/).  
- **Documentmap** – Maak een map op je computer waarin je de voorbeeldprojectbestanden opslaat.

## Pakketten importeren
We beginnen met het importeren van de essentiële Aspose.Tasks‑klassen. Dit bereidt de IDE voor om de API‑aanroepen die we later gebruiken te herkennen.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Hoe koppeltypen in te stellen in Aspose.Tasks voor Java?
Laad een nieuwe `Project`‑instantie, voeg twee taken toe, en maak vervolgens een `TaskLink` met het gewenste `TaskLinkType`. Dit twee‑stappenpatroon stelt je in staat om elk van de vier standaard afhankelijkheidstypen in één oproep te definiëren. `Project` vertegenwoordigt het volledige projectbestand en de planning. `Task` is een individueel werkitem binnen het project. `TaskLink` verbindt een voorganger‑taak met een opvolger‑taak. `TaskLinkType` is een enumeratie die de relatie specificeert (Start‑naar‑Start, Finish‑naar‑Start, enz.).

### Stap 1: een koppeltype instellen
`TaskLink` vertegenwoordigt een afhankelijkheid tussen twee taken, terwijl `TaskLinkType` de mogelijke relatietypen opsomt, zoals `StartToStart`. In deze stap maken we een nieuw project, voegen twee taken toe, en koppelen ze met de **Start‑naar‑Start** relatie.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** Je kunt `StartToStart` vervangen door `FinishToStart`, `StartToFinish` of `FinishToFinish` afhankelijk van de afhankelijkheid die je moet **taakafhankelijkheden beheren**.

### Stap 2: een koppeltype ophalen
`Project.getTaskLinks()` retourneert een collectie van alle `TaskLink`‑objecten in de planning. Door deze collectie te itereren kun je voor elke koppeling de `TaskLinkType` lezen en verifiëren dat de juiste relatie is opgeslagen.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

De console zal waarden weergeven zoals `StartToStart`, `FinishToStart`, enz., waarmee wordt bevestigd dat het koppeltype dat je eerder hebt ingesteld correct is.

## Veelvoorkomende problemen & oplossingen
- **NullPointerException bij het toevoegen van koppelingen** – Zorg ervoor dat zowel de voorganger‑ als opvolger‑taken aan het project zijn toegevoegd voordat je een `TaskLink` maakt.  
- **Onjuist koppeltype na opslaan** – Roep altijd `project.save("output.mpp")` (of een ander ondersteund formaat) aan na het instellen van het koppeltype om wijzigingen op te slaan.  
- **Licentie niet gevonden** – Plaats je Aspose.Tasks‑licentiebestand in de classpath van het project en laad het met `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Veelgestelde vragen

**V: Is Aspose.Tasks compatibel met verschillende Java‑omgevingen?**  
A: Ja, Aspose.Tasks integreert met standaard Java SE, Java EE en Android‑ontwikkelkits zonder extra afhankelijkheden.

**V: Kan ik koppeltypen aanpassen op basis van mijn projectvereisten?**  
A: Absoluut. De `TaskLinkType`‑enum biedt vier standaardtypen, en je kunt ze combineren met vertragingstijden om complexe planningen te modelleren.

**V: Waar kan ik gedetailleerde documentatie vinden voor Aspose.Tasks voor Java?**  
A: Raadpleeg de [Aspose.Tasks for Java documentatie](https://reference.aspose.com/tasks/java/) voor uitgebreide begeleiding, API‑referentie en code‑voorbeelden.

**V: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?**  
A: Bezoek de [tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor testdoeleinden te verkrijgen.

**V: Waar kan ik ondersteuning krijgen voor vragen over Aspose.Tasks?**  
A: Word lid van de Aspose.Tasks‑community op het [ondersteuningsforum](https://forum.aspose.com/c/tasks/15) voor hulp en discussies.

**V: Kan ik een koppeltype wijzigen nadat het project is opgeslagen?**  
A: Ja. Laad het project, haal de `TaskLink` op, roep `setLinkType()` aan met de nieuwe enum‑waarde, en sla het project opnieuw op.

**V: Ondersteunt Aspose.Tasks het lezen van Microsoft Project (MPP)‑bestanden?**  
A: Ja. Gebruik `new Project("file.mpp")` om MPP‑bestanden te laden en met hun taakkoppelingen te werken, net als het XML‑voorbeeld hierboven.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Gerelateerde tutorials

- [Maak cross‑project taakkoppeling in Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Stel project startdatum in en beheer boven‑ en onderliggende taken in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Laad MPP‑bestand Java – Beheer projecteigenschappen met Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}