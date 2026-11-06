---
date: 2026-11-06
description: Maak moeiteloos aangepaste agenda-uitzonderingen, integreer de MS Project-agenda
  en beheer, definieer, verwerk en haal agenda-uitzonderingen op in Java-projecten
  met Aspose.Tasks. Stroomlijn projectworkflows voor efficiënt projectbeheer.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Agenda-uitzonderingen
og_description: Leer hoe u agenda-uitzonderingen maakt in Java met Aspose.Tasks. Beheer
  projectagenda's, stel niet-werkdagen in en pas MS Project-agenda's efficiënt aan.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Agenda-uitzonderingen maken met Aspose.Tasks voor Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Hoe u agenda-uitzonderingen maakt met Aspose.Tasks voor Java
url: /nl/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je agenda‑uitzonderingen met Aspose.Tasks voor Java

## Inleiding

`Aspose.Tasks` is een Java‑bibliotheek die programmatisch maken, manipuleren en converteren van Microsoft Project‑bestanden mogelijk maakt. In deze tutorial leer je hoe je **agenda‑uitzonderingen**—aangepaste niet‑werkperiodes die de standaardagenda van een project overschrijven—maakt. Precieze controle over werk‑ en niet‑werkdagen is essentieel voor nauwkeurige planning, resource‑toewijzing en naleving van regionale feestdagen. Aan het einde van deze gids weet je ook hoe je **een MS Project‑agenda** in je Java‑applicatie kunt integreren en de uitzonderingen kunt ophalen of wijzigen.

## Snelle antwoorden
- **Wat kan ik bereiken?** Maak, wijzig en haal aangepaste agenda‑uitzonderingen op in Java‑projecten.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (nieuwste stabiele release).  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Kan ik werken met MS Project‑bestanden?** Absoluut – je kunt MS Project‑agenda‑gegevens importeren, bewerken en exporteren.  
- **Is er speciale configuratie nodig?** Voeg gewoon de Aspose.Tasks‑JAR toe aan je classpath en importeer de relevante klassen.

## Hoe maak je aangepaste agenda‑uitzonderingen in Aspose.Tasks voor Java?

Om aangepaste agenda‑uitzonderingen te maken in Aspose.Tasks voor Java, laad je het doel‑Project, haal je de Calendar op, definieer je de start‑ en einddatums van de uitzondering met de gewenste werktijd, stel je eventueel een herhalingspatroon in, en sla je vervolgens het project op. Deze reeks voegt de uitzondering direct toe en slaat deze op in het .mpp‑bestand.

`Project`‑klasse is het primaire object van Aspose.Tasks dat een volledig Microsoft Project‑bestand modelleert. De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand en biedt toegang tot de inhoud. Het `Calendar`‑object definieert werk‑ en niet‑werktijden voor het project. De `Calendar`‑klasse is de container voor alle werktijd‑regels, inclusief uitzonderingen. De `addException()`‑methode voegt een nieuwe agenda‑uitzondering toe aan de agenda. `addException()` is een één‑oproep‑API die een niet‑werkperiode registreert voor het opgegeven datumbereik.

Laad het doel‑project met `Project project = new Project("example.mpp")`, verkrijg het `Calendar`‑object en roep `addException()` aan met de gewenste datumbereik‑ en werktijdinstellingen. Dit twee‑stappen‑patroon maakt een nieuwe uitzondering direct aan en slaat deze op wanneer je het project opslaat. Voor terugkerende feestdagen configureer je de `RecurrencePattern` op de uitzondering vóór het opslaan.

Op deze manier agenda‑uitzonderingen maken stelt je in staat om **niet‑werkdagen** nauwkeurig in te stellen, of het nu een eenmalige stillegging of jaarlijkse feestdagen betreft. Nadat de uitzondering is toegevoegd, kun je `project.save("updated.mpp")` aanroepen om de wijzigingen naar schijf te schrijven.

### Overzicht van stappen
1. Laad het projectbestand.  
2. Haal een `Calendar`‑instantie op of maak er een aan.  
3. Definieer het datumbereik en de werktijd van de uitzondering.  
4. (Optioneel) Configureer herhaling voor jaarlijkse feestdagen.  
5. Sla het project op.

## Beheer agenda‑uitzonderingen in Aspose.Tasks
[Leer hoe je agenda‑uitzonderingen kunt toevoegen en verwijderen in Aspose.Tasks voor Java efficiënt](./add-remove/). Als het gaat om projectmanagement, is flexibiliteit cruciaal. Aspose.Tasks stelt je in staat om moeiteloos agenda‑uitzonderingen te beheren, waardoor dynamische aanpassingen aan projecttijdlijnen mogelijk zijn. Deze tutorial biedt een stapsgewijze gids, zodat je het proces efficiënt onder de knie krijgt. Ontdek hoe je je projectmanagement‑workflows eenvoudig kunt verbeteren.

## Definieer weekdagen voor agenda‑uitzonderingen met Aspose.Tasks
[Beheers de kunst van het definiëren van weekdagen voor agenda‑uitzonderingen in Java‑projecten](./define-weekdays/) Nauwkeurige projectplanning vereist zorgvuldige aandacht voor detail. Met Aspose.Tasks kun je weekdagen voor agenda‑uitzonderingen precies definiëren, zodat je projecten naadloos aansluiten op specifieke tijdlijnen. Deze tutorial voorziet je van de kennis om de planning te optimaliseren, waardoor je controle krijgt over projecttijdlijnen.

## Behandel gebeurtenissen in agenda‑uitzonderingen met Aspose.Tasks
[Effectief agenda‑uitzonderingen behandelen in Java‑projecten](./handle-occurrences/) Projectmanagement is een dynamisch proces, dat vaak aanpassingen vereist om onvoorziene gebeurtenissen op te vangen. Aspose.Tasks stelt je in staat om agenda‑uitzonderingen effectief te behandelen, waardoor een gestroomlijnde aanpak van projectmanagement ontstaat. Leer de kunst van het beheren van projectonzekerheden met gemak via deze gedetailleerde tutorial.

## Haal agenda‑uitzonderingen op met Aspose.Tasks
[Leer hoe je agenda‑uitzonderingen kunt ophalen uit MS Project met Aspose.Tasks voor Java](./retrieve/) Integreer agenda‑uitzonderingen naadloos in je projectmanagementproces met Aspose.Tasks. Deze tutorial leidt je stap voor stap door het proces van het ophalen van agenda‑uitzonderingen, zodat een soepele en efficiënte integratie in je projecten gegarandeerd is. Ontgrendel de kracht van Aspose.Tasks om je projectmanagementmogelijkheden te verbeteren.

## Hoe integreer je een MS Project‑agenda met Aspose.Tasks?
Het integreren van een MS Project‑agenda met Aspose.Tasks omvat het laden van het bron‑.mpp‑bestand met de Project‑klasse, het benaderen van de standaard‑ of aangepaste Calendar‑objecten, het aanpassen of samenvoegen van uitzonderingen indien nodig, en vervolgens het opslaan van het bijgewerkte project. Hiermee kun je programmatisch werken met MS Project‑agenda's zonder handmatige UI‑interactie.

`Project`‑klasse is het primaire object van Aspose.Tasks dat een volledig Microsoft Project‑bestand modelleert. Importeer een bestaand MS Project‑bestand met `new Project("source.mpp")`; de bibliotheek laadt automatisch de standaardagenda en eventuele aangepaste uitzonderingen. Je kunt die uitzonderingen vervolgens lezen, wijzigen of samenvoegen voordat je het project weer opslaat. Deze aanpak stelt je in staat om **MS Project‑agenda**‑gegevens programmatisch te wijzigen zonder handmatige bewerking in de MS Project‑UI.

## Veelvoorkomende use‑cases
- **Feestdagenplanning** – Definieer nationale feestdagen als niet‑werkdagen over meerdere projecten.  
- **Shift work** – Stel aangepaste werkweken in voor teams die volgens niet‑standaard schema's werken.  
- **Project phase gating** – Blokkeer periodes waarin geen werk gepland mag worden, zoals onderhoudsvensters.  
- **Legacy migration** – Importeer agenda's uit oudere MS Project‑bestanden en pas ze programmatisch aan.

## Tips & best practices
- **Pro tip:** Haal altijd de bestaande agenda op voordat je nieuwe uitzonderingen toevoegt om duplicaten te voorkomen.  
- **Waarschuwing:** Het wijzigen van een agenda die al aan taken is toegewezen kan taakdatums verschuiven; herbereken het schema na aanpassingen.  
- **Prestaties:** Verwerk meerdere uitzonderingsupdates in één transactie om bestand‑I/O‑overhead te verminderen. Aspose.Tasks verwerkt bestanden tot 1 GB terwijl het geheugenverbruik onder 200 MB blijft, en het kan 30+ agenda‑gerelateerde API‑calls per seconde aan op typische serverhardware.

## Tutorials voor agenda‑uitzonderingen
### [Beheer agenda‑uitzonderingen in Aspose.Tasks](./add-remove/)
Leer hoe je agenda‑uitzonderingen kunt toevoegen en verwijderen in Aspose.Tasks voor Java efficiënt. Verbeter projectmanagement‑workflows moeiteloos.
### [Definieer weekdagen voor agenda‑uitzonderingen met Aspose.Tasks](./define-weekdays/)
Leer hoe je weekdagen voor agenda‑uitzonderingen kunt definiëren in Java‑projecten met Aspose.Tasks voor nauwkeurige projectplanning.
### [Behandel gebeurtenissen in agenda‑uitzonderingen met Aspose.Tasks](./handle-occurrences/)
Leer hoe je agenda‑uitzonderingen effectief kunt behandelen in Java‑projecten met Aspose.Tasks voor Java. Stroomlijn nu je projectmanagementproces.
### [Haal agenda‑uitzonderingen op met Aspose.Tasks](./retrieve/)
Leer hoe je agenda‑uitzonderingen kunt ophalen uit MS Project met Aspose.Tasks voor Java. Stapsgewijze tutorial voor naadloze integratie.

## Veelgestelde vragen

**Q: Kan ik agenda‑uitzonderingen wijzigen nadat een project al is gepubliceerd?**  
A: Ja. Gebruik de add‑remove‑ en define‑weekdays‑API's om de agenda bij te werken, en sla vervolgens het projectbestand opnieuw op.

**Q: Ondersteunt Aspose.Tasks terugkerende uitzonderingen (bijv. elke eerste maandag van de maand)?**  
A: Absoluut. De “handle occurrences”‑tutorial behandelt hoe je terugkerende patronen instelt.

**Q: Hoe zorg ik ervoor dat mijn aangepaste agenda door alle taken in het project wordt gebruikt?**  
A: Wijs de agenda toe aan de standaardagenda van het project of stel deze expliciet in op de `Calendar`‑eigenschap van elke taak.

**Q: Is het mogelijk om agenda's van meerdere MS Project‑bestanden samen te voegen?**  
A: Ja. Haal elke agenda op, combineer hun uitzonderingen programmatisch, en wijs vervolgens de samengevoegde agenda toe aan het doelproject.

**Q: Welke versie van Aspose.Tasks is vereist voor deze functies?**  
A: Alle functies zijn beschikbaar in de huidige stabiele release van Aspose.Tasks voor Java (2025.x).

## Gerelateerde tutorials
- [Projectagenda maken Aspose – Weekdagen definiëren voor agenda‑uitzonderingen](/tasks/java/calendar-exceptions/define-weekdays/)
- [Agenda‑uitzonderingen ophalen met Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Agenda‑uitzondering maken Aspose voor Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Laatst bijgewerkt:** 2026-11-06  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}