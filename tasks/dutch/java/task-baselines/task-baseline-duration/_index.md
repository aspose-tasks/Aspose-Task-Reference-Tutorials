---
date: 2026-08-29
description: Leer hoe u baseline duration kunt instellen en projectvoortgang kunt
  bijhouden met Aspose.Tasks for Java. Deze stapsgewijze gids helpt u task baselines
  efficiënt te beheren.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Hoe baseline duration in te stellen in Aspose.Tasks for Java
og_description: Leer hoe u baseline duration kunt instellen en projectvoortgang kunt
  bijhouden met Aspose.Tasks for Java. Volg deze gedetailleerde gids om task baselines
  efficiënt te beheren.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Hoe baseline duration in te stellen om projectvoortgang bij te houden
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Hoe baseline duration in te stellen om projectvoortgang bij te houden
url: /nl/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe baseline-duur instellen om projectvoortgang te volgen

## Inleiding
Het volgen van de projectvoortgang begint met een solide baseline. In deze tutorial ontdek je **hoe je baseline-duur instelt** voor taken in Microsoft Project‑bestanden met behulp van de Aspose.Tasks‑bibliotheek voor Java, en begrijp je waarom het vroegtijdig vaststellen van een baseline je helpt om schema‑afwijkingen, kostenvariaties en resource‑overallocatie gedurende de levensduur van het project te monitoren.

## Snelle antwoorden
- **Wat betekent “set baseline”?** Het registreert de oorspronkelijke start-, eind- en duur van een taak zodat je toekomstige wijzigingen kunt vergelijken.  
- **Welke Aspose.Tasks‑klasse maakt een project?** De `Project`‑klasse – je leert ook hoe je **een project‑instantie maakt** op de juiste manier.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis evaluatielicentie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik tussentijdse baselines ophalen?** Ja, Aspose.Tasks stelt je in staat om tussentijdse baselines en hun vaste kosten op te vragen.  
- **Welke Java‑versie is vereist?** Java 8 of hoger wordt aanbevolen.  
- **Hoe helpt dit mij de projectvoortgang te volgen?** Zodra de baseline is ingesteld, kun je direct de werkelijke data vergelijken met het oorspronkelijke plan met behulp van ingebouwde rapportage‑functies.

## Wat is een taak‑baseline en waarom deze instellen?
Een taak‑baseline legt de geplande planning (startdatum, einddatum en duur) vast op een specifiek moment. Door een baseline in te stellen creëer je een referentiepunt dat het gemakkelijk maakt om schema‑afwijkingen, kostenoverschrijdingen en resource‑overallocatie te herkennen naarmate het project zich ontwikkelt.

## Waarom Aspose.Tasks gebruiken voor baseline‑beheer?
Aspose.Tasks biedt **volledige .mpp‑compatibiliteit** – je kunt native Microsoft Project‑bestanden lezen en schrijven zonder dat Microsoft Office geïnstalleerd hoeft te zijn. De API geeft je programmatische toegang tot **meer dan 50 invoer‑ en uitvoerformaten**, ondersteunt **tussentijdse baselines 1‑10**, en kan **projecten van honderden pagina's** verwerken zonder het volledige bestand in het geheugen te laden, wat essentieel is voor high‑performance batchverwerking.

## Vereisten
1. **Java‑ontwikkelomgeving** – JDK 8+ geïnstalleerd en geconfigureerd.  
2. **Aspose.Tasks for Java** – download de bibliotheek van de [Aspose.Tasks for Java downloadpagina](https://releases.aspose.com/tasks/java/).  
3. **IDE of build‑tool** – Maven, Gradle, of elke IDE die je verkiest.

## Importeer pakketten
De volgende imports brengen de kern‑Aspose.Tasks‑klassen binnen die nodig zijn om met projecten, taken, baselines en tijd‑gebaseerde gegevens te werken.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Stap 1: een project‑instantie maken
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand in het geheugen en is het toegangspunt voor alle bewerkingen.

```java
Project project = new Project();
```

## Stap 2: een taak‑baseline maken
Een `TaskBaseline` slaat de geplande start, eind en duur op voor een specifieke taak.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Stap 3: taak‑baseline‑informatie weergeven
De `getBaselines()`‑methode retourneert de collectie baselines die aan een taak zijn gekoppeld.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Stap 4: tussentijdse baseline en vaste kosten controleren
`BaselineType` somt de primaire en tussentijdse baselines op (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Stap 5: tijdgebaseerde gegevens afdrukken
`TimephasedData` vertegenwoordigt een stuk planningsinformatie voor een specifiek tijdsinterval.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Door deze stappen te volgen, kun je **baseline‑duur instellen** voor elke taak en gedetailleerde baseline‑informatie ophalen met Aspose.Tasks for Java, waardoor je een betrouwbare manier krijgt om **projectvoortgang te volgen** gedurende de levenscyclus van het project.

## Veelvoorkomende problemen en oplossingen
- **Baseline verschijnt niet in MS Project:** Zorg ervoor dat je `project.setBaseline(BaselineType.Baseline)` **na** het toevoegen van de taak hebt aangeroepen.  
- **NullPointerException bij `getBaselines()`:** Controleer of de taak aan het project is toegevoegd voordat de baseline wordt ingesteld.  
- **Tijdseenheid mismatch:** Gebruik `TimeUnitType` om de duur correct te formatteren, vooral bij het werken met aangepaste kalenders.

## Veelgestelde vragen
### Wat is een taak‑baseline in MS Project?
Een taak‑baseline in MS Project is een momentopname van de aanvankelijke geplande planning voor een taak, inclusief de startdatum, einddatum en duur.

### Waarom is het beheren van taak‑baselines belangrijk?
Het beheren van taak‑baselines helpt bij het vergelijken van de geplande planning met de werkelijke voortgang van het project, waardoor betere tracking en besluitvorming mogelijk wordt.

### Kan ik een taak‑baseline wijzigen nadat deze is ingesteld?
Ja, je kunt taak‑baselines in MS Project wijzigen om wijzigingen in het projectplan weer te geven. Het is echter essentieel om eventuele afwijkingen van de oorspronkelijke baseline te documenteren.

### Ondersteunt Aspose.Tasks andere projectmanagementfunctionaliteiten?
Ja, Aspose.Tasks biedt een breed scala aan functies voor projectmanagement, waaronder taakplanning, resource‑allocatie en het genereren van Gantt‑diagrammen.

### Waar kan ik ondersteuning vinden voor Aspose.Tasks?
Je kunt ondersteuning voor Aspose.Tasks vinden op het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15), waar je vragen kunt stellen en met andere gebruikers kunt communiceren.

## Aanvullende veelgestelde vragen
**Q: Moet ik `setBaseline` voor elke taak afzonderlijk aanroepen?**  
A: Nee. Het aanroepen van `project.setBaseline(BaselineType.Baseline)` registreert de baseline voor alle taken in het project tegelijk.

**Q: Hoe kan ik een tussentijdse baseline voor een specifieke taak instellen?**  
A: Gebruik `project.setBaseline(BaselineType.Baseline1)` (of Baseline2‑Baseline10) na het bijwerken van de planning van de taak.

**Q: Is het mogelijk om de baseline‑gegevens naar CSV te exporteren?**  
A: Ja. Iterate over `task.getBaselines()` en schrijf de gewenste velden naar een CSV‑bestand met standaard Java‑I/O.

**Q: Kan ik een bestaand .mpp‑bestand lezen dat al baselines bevat?**  
A: Absoluut. Laad het bestand met `new Project("myproject.mpp")` en krijg vervolgens toegang tot de baselines van elke taak zoals hierboven getoond.

**Q: Ondersteunt Aspose.Tasks multi‑projectbestanden?**  
A: Aspose.Tasks werkt met single‑project .mpp‑bestanden. Voor multi‑projectscenario's combineer je de projecten programmatisch.

---

**Laatst bijgewerkt:** 2026-08-29  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak takenlijst Java – MS Project-baseline met Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Maak MPP-project Java – Taakvoortgang wijzigen met Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Projectmanagement-baseline – Taakplanning met Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}