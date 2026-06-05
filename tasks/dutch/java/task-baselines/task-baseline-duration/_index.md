---
date: 2026-01-23
description: Leer hoe u de baseline‑duur instelt en een projectinstantie maakt met
  Aspose.Tasks voor Java. Deze stapsgewijze gids helpt u taakbaselines efficiënt te
  beheren.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Hoe de baseline‑duur instellen in Aspose.Tasks voor Java
url: /nl/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe stel je de baseline-duur in Aspose.Tasks voor Java

## Introductie
Het instellen van een baseline is een fundamentele stap om de voortgang van een project te volgen ten opzichte van het oorspronkelijke plan. In deze tutorial leer je **hoe je een baseline**-duur voor taken in Microsoft Project in te stellen met behulp van de Aspose.Tasks-bibliotheek voor Java, en zie je waarom het vroegtijdig vaststellen van een baseline je later tijd en hoofdpijn kan besparen.

## Snelle antwoorden
- **Wat betekent “set baseline”?** Het registreert de oorspronkelijke start, eind en duur van een taak zodat je toekomstige wijzigingen kunt vergelijken.  
- **Welke Aspose.Tasks‑klasse maakt een project?** De `Project`‑klasse – je leert ook hoe je **projectinstantie maakt** correct.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis evaluatielicentie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik tussentijdse baselines ophalen?** Ja, Aspose.Tasks stelt je in staat om tussentijdse baselines en hun vaste kosten op te vragen.  
- **Welke Java‑versie is vereist?** Java 8 of later wordt aanbevolen.

## Wat is een taak‑baseline en waarom deze instellen?
Een taak‑baseline legt de geplande planning (startdatum, einddatum en duur) vast op een specifiek moment. Door een baseline in te stellen creëer je een referentiepunt dat het gemakkelijk maakt om schema‑afwijkingen, kostenoverschrijdingen en resource‑overallocatie te ontdekken terwijl het project zich ontwikkelt.

## Waarom Aspose.Tasks gebruiken voor baseline‑beheer?
- **Volledige .mpp‑compatibiliteit** – lees en schrijf native Microsoft Project‑bestanden zonder Office geïnstalleerd.  
- **Rijke API** – krijg programmatisch toegang tot baseline‑gegevens, tussentijdse baselines en tijd‑gebaseerde informatie.  
- **Cross‑platform** – werkt op Windows, Linux en macOS met elke standaard JDK.

## Voorvereisten
1. **Java‑ontwikkelomgeving** – JDK 8+ geïnstalleerd en geconfigureerd.  
2. **Aspose.Tasks voor Java** – download de bibliotheek van [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE of build‑tool** – Maven, Gradle, of elke IDE die je verkiest.

## Import pakketten
Eerst importeer je de benodigde klassen in je Java‑project:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Stap 1: Maak een project‑instance
Het maken van een project‑instance is de basis voor elke verdere manipulatie. Deze stap laat zien hoe je **projectinstantie maakt** met Aspose.Tasks:

```java
Project project = new Project();
```

## Stap 2: Maak een taak‑baseline
Voeg een nieuwe taak toe aan de root van het project en stel de baseline in. Dit legt de oorspronkelijke planning voor de taak vast:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Stap 3: Toon taak‑baseline‑informatie
Haalt de baseline op die je zojuist hebt gemaakt en print de belangrijkste eigenschappen. Dit helpt je te verifiëren dat de baseline correct is ingesteld:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Stap 4: Controleer tussentijdse baseline en vaste kosten
Als je werkt met tussentijdse baselines, kun je opvragen of de huidige baseline tussentijds is en eventuele bijbehorende vaste kosten:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Stap 5: Print tijd‑gebaseerde gegevens
Tijd‑gebaseerde gegevens tonen hoe de baseline over de tijd is verdeeld. Loop door de collectie om elk item te inspecteren:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Door deze stappen te volgen, kun je **hoe je een baseline instelt** duur voor elke taak en gedetailleerde baseline‑informatie ophalen met Aspose.Tasks voor Java.

## Veelvoorkomende problemen en oplossingen
- **Baseline verschijnt niet in MS Project:** Zorg ervoor dat je `project.setBaseline(BaselineType.Baseline)` **na** het toevoegen van de taak hebt aangeroepen.  
- **NullPointerException bij `getBaselines()`:** Controleer of de taak aan het project is toegevoegd voordat je de baseline instelt.  
- **Tijdseenheid mismatch:** Gebruik `TimeUnitType` om de duur correct te formatteren, vooral bij het werken met aangepaste kalenders.

## Veelgestelde vragen
### Wat is een taak‑baseline in MS Project?
Een taak‑baseline in MS Project is een momentopname van de aanvankelijke geplande planning voor een taak, inclusief de startdatum, einddatum en duur.

### Waarom is het beheren van taak‑baselines belangrijk?
Het beheren van taak‑baselines helpt bij het vergelijken van de geplande planning met de werkelijke voortgang van het project, waardoor beter volgen en beslissen mogelijk wordt.

### Kan ik een taak‑baseline wijzigen nadat deze is ingesteld?
Ja, je kunt taak‑baselines in MS Project wijzigen om veranderingen in het projectplan weer te geven. Het is echter essentieel om eventuele afwijkingen van de oorspronkelijke baseline te documenteren.

### Ondersteunt Aspose.Tasks andere projectmanagementfunctionaliteiten?
Ja, Aspose.Tasks biedt een breed scala aan functies voor projectmanagement, waaronder taakplanning, resource‑allocatie en het genereren van Gantt‑diagrammen.

### Waar kan ik ondersteuning vinden voor Aspose.Tasks?
Je kunt ondersteuning voor Aspose.Tasks vinden op het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15), waar je vragen kunt stellen en met andere gebruikers kunt communiceren.

## Aanvullende veelgestelde vragen
**Q:** Moet ik `setBaseline` voor elke taak afzonderlijk aanroepen?  
**A:** Nee. Het aanroepen van `project.setBaseline(BaselineType.Baseline)` registreert de baseline voor alle taken in het project tegelijk.

**Q:** Hoe kan ik een tussentijdse baseline instellen voor een specifieke taak?  
**A:** Gebruik `project.setBaseline(BaselineType.Baseline1)` (of Baseline2‑Baseline10) na het bijwerken van de planning van de taak.

**Q:** Is het mogelijk om de baseline‑gegevens te exporteren naar CSV?  
**A:** Ja. Loop over `task.getBaselines()` en schrijf de gewenste velden naar een CSV‑bestand met standaard Java‑I/O.

**Q:** Kan ik een bestaand .mpp‑bestand lezen dat al baselines bevat?  
**A:** Absoluut. Laad het bestand met `new Project("myproject.mpp")` en krijg vervolgens toegang tot de baselines van elke taak zoals hierboven getoond.

**Q:** Ondersteunt Aspose.Tasks multi‑projectbestanden?  
**A:** Aspose.Tasks werkt met .mpp‑bestanden voor één project. Voor multi‑projectscenario's combineer je de projecten programmatisch.

---

**Laatst bijgewerkt:** 2026-01-23  
**Getest met:** Aspose.Tasks voor Java 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}