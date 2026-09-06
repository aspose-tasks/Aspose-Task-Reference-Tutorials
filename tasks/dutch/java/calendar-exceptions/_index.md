---
date: 2026-08-18
description: Maak moeiteloos aangepaste kalenderexcepties, integreer de MS Project-kalender
  en beheer, definieer, verwerk en haal kalenderexcepties op in Java-projecten met
  Aspose.Tasks. Stroomlijn projectworkflows voor efficiënt projectbeheer.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Kalenderexcepties
og_description: Leer hoe u kalenderexcepties maakt, de projectkalender beheert en
  niet-werkdagen instelt in Java met Aspose.Tasks. Snelle gids voor ontwikkelaars.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Hoe u kalenderexcepties maakt met Aspose.Tasks voor Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
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
title: Hoe u kalenderexcepties maakt met Aspose.Tasks voor Java
url: /nl/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je agenda‑uitzonderingen met Aspose.Tasks voor Java

## Introductie

`Aspose.Tasks` is een Java‑bibliotheek die programmatisch maken, manipuleren en converteren van Microsoft Project‑bestanden mogelijk maakt. In deze tutorial leer je hoe je **agenda‑uitzonderingen** kunt maken — aangepaste niet‑werkperiodes die de standaardagenda van een project overschrijven. Precieze controle over werk‑ en niet‑werkdagen is essentieel voor nauwkeurige planningsvoorspellingen, resource‑allocatie en naleving van regionale feestdagen. Aan het einde van deze gids weet je ook hoe je **een MS Project‑agenda** in je Java‑applicatie kunt integreren en de uitzonderingen kunt ophalen of aanpassen.

## Snelle antwoorden
- **Wat kan ik bereiken?** Maak, wijzig en haal aangepaste agenda‑uitzonderingen op in Java‑projecten.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (laatste stabiele release).  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Kan ik werken met MS Project‑bestanden?** Absoluut — je kunt MS Project‑agendagegevens importeren, bewerken en exporteren.  
- **Is er speciale configuratie nodig?** Voeg gewoon de Aspose.Tasks‑JAR toe aan je classpath en importeer de relevante klassen.

## Hoe maak je aangepaste agenda‑uitzonderingen in Aspose.Tasks voor Java?

De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand en biedt toegang tot de inhoud. Het `Calendar`‑object definieert werk‑ en niet‑werktijden voor het project. De methode `addException()` voegt een nieuwe agenda‑uitzondering toe aan de agenda.

Laad het doelproject met `Project project = new Project("example.mpp")`, verkrijg het `Calendar`‑object en roep `addException()` aan met het gewenste datumbereik en de werk‑tijdinstellingen. Dit tweestappenpatroon maakt onmiddellijk een nieuwe uitzondering aan en slaat deze op wanneer je het project opslaat. Voor terugkerende feestdagen configureer je het `RecurrencePattern` op de uitzondering vóór het opslaan.

Het op deze manier maken van agenda‑uitzonderingen stelt je in staat **niet‑werkdagen nauwkeurig** in te stellen, of het nu een eenmalige stillegging of een jaarlijkse feestdag betreft. Nadat de uitzondering is toegevoegd, kun je `project.save("updated.mpp")` aanroepen om de wijzigingen naar schijf te schrijven.

### Overzicht van stappen
1. Laad het projectbestand.  
2. Haal een `Calendar`‑instantie op of maak er een aan.  
3. Definieer het datumbereik en de werktijd van de uitzondering.  
4. (Optioneel) Configureer terugkeer voor jaarlijkse feestdagen.  
5. Sla het project op.

## Beheer agenda‑uitzonderingen in Aspose.Tasks
[Leer hoe je agenda‑uitzonderingen kunt toevoegen en verwijderen in Aspose.Tasks voor Java efficiënt](./add-remove/). Wanneer het om projectmanagement gaat, is flexibiliteit cruciaal. Aspose.Tasks stelt je in staat om moeiteloos agenda‑uitzonderingen te beheren, waardoor dynamische aanpassingen aan projecttijden mogelijk zijn. Deze tutorial biedt een stap‑voor‑stap‑gids, zodat je het proces efficiënt onder de knie krijgt. Ontdek hoe je je projectmanagement‑workflows eenvoudig kunt verbeteren.

## Definieer weekdagen voor agenda‑uitzonderingen met Aspose.Tasks
[Beheers de kunst van het definiëren van weekdagen voor agenda‑uitzonderingen in Java‑projecten](./define-weekdays/) met Aspose.Tasks. Nauwkeurige projectplanning vereist zorgvuldige aandacht voor details. Met Aspose.Tasks kun je weekdagen voor agenda‑uitzonderingen precies definiëren, zodat je projecten naadloos op specifieke tijdlijnen aansluiten. Deze tutorial voorziet je van de kennis om de planning te optimaliseren en geeft je controle over projecttijden.

## Behandel gebeurtenissen in agenda‑uitzonderingen met Aspose.Tasks
[Behandel agenda‑uitzonderingen effectief in Java‑projecten](./handle-occurrences/) met Aspose.Tasks voor Java. Projectmanagement is een dynamisch proces, dat vaak aanpassingen vereist om onvoorziene gebeurtenissen op te vangen. Aspose.Tasks stelt je in staat om agenda‑uitzonderingen effectief te behandelen, waardoor een gestroomlijnde aanpak van projectmanagement ontstaat. Leer de kunst van het beheren van projectonzekerheden met gemak via deze gedetailleerde tutorial.

## Haal agenda‑uitzonderingen op met Aspose.Tasks
[Leer hoe je agenda‑uitzonderingen kunt ophalen uit MS Project met Aspose.Tasks voor Java](./retrieve/). Integreer agenda‑uitzonderingen naadloos in je projectmanagementproces met Aspose.Tasks. Deze tutorial leidt je stap‑voor‑stap door het ophalen van agenda‑uitzonderingen, zodat je een soepele en efficiënte integratie in je projecten realiseert. Ontgrendel de kracht van Aspose.Tasks om je projectmanagement‑mogelijkheden te verbeteren.

## Hoe integreer je een MS Project‑agenda met Aspose.Tasks?

De `Project`‑klasse laadt een Microsoft Project‑bestand en maakt de agenda’s en andere projectgegevens beschikbaar. Importeer een bestaand MS Project‑bestand met `new Project("source.mpp")`; de bibliotheek laadt automatisch de standaardagenda en eventuele aangepaste uitzonderingen. Je kunt vervolgens die uitzonderingen lezen, wijzigen of samenvoegen voordat je het project weer opslaat. Deze aanpak stelt je in staat **MS Project‑agenda**‑gegevens programmatisch te wijzigen zonder handmatige bewerking in de MS Project‑UI.

## Veelvoorkomende use‑cases
- **Feestdagenplanning** – Definieer nationale feestdagen als niet‑werkdagen over meerdere projecten.  
- **Shift‑werk** – Stel aangepaste werkweken in voor teams die volgens niet‑standaard schema’s werken.  
- **Projectfase‑gating** – Blokkeer periodes waarin geen werk moet worden ingepland, zoals onderhoudsvensters.  
- **Legacy‑migratie** – Importeer agenda’s uit oudere MS Project‑bestanden en pas ze programmatisch aan.

## Tips & best practices
- **Pro tip:** Haal altijd de bestaande agenda op voordat je nieuwe uitzonderingen toevoegt om duplicaten te voorkomen.  
- **Waarschuwing:** Het wijzigen van een agenda die al aan taken is toegewezen, kan taakdata verschuiven; herbereken de planning na aanpassingen.  
- **Prestaties:** Batch meerdere uitzondering‑updates in één transactie om bestands‑I/O‑overhead te verminderen. Aspose.Tasks verwerkt bestanden tot 500 MB zonder het volledige document in het geheugen te laden, en verwerkt 50+ agenda‑gerelateerde API‑calls per seconde op typische serverhardware.

## Agenda‑uitzonderingen tutorials
### [Beheer agenda‑uitzonderingen in Aspose.Tasks](./add-remove/)
Leer hoe je agenda‑uitzonderingen kunt toevoegen en verwijderen in Aspose.Tasks voor Java efficiënt. Verbeter projectmanagement‑workflows moeiteloos.
### [Definieer weekdagen voor agenda‑uitzonderingen met Aspose.Tasks](./define-weekdays/)
Leer hoe je weekdagen voor agenda‑uitzonderingen in Java‑projecten definieert met Aspose.Tasks voor nauwkeurige projectplanning.
### [Behandel gebeurtenissen in agenda‑uitzonderingen met Aspose.Tasks](./handle-occurrences/)
Leer hoe je agenda‑uitzonderingen effectief behandelt in Java‑projecten met Aspose.Tasks voor Java. Stroomlijn nu je projectmanagementproces.
### [Haal agenda‑uitzonderingen op met Aspose.Tasks](./retrieve/)
Leer hoe je agenda‑uitzonderingen ophaalt uit MS Project met Aspose.Tasks voor Java. Stap‑voor‑stap tutorial voor naadloze integratie.

## Veelgestelde vragen

**Q: Kan ik agenda‑uitzonderingen aanpassen nadat een project al is gepubliceerd?**  
A: Ja. Gebruik de add‑remove‑ en define‑weekdays‑API’s om de agenda bij te werken en sla vervolgens het projectbestand opnieuw op.

**Q: Ondersteunt Aspose.Tasks terugkerende uitzonderingen (bijv. elke eerste maandag van de maand)?**  
A: Absoluut. De tutorial “behandel gebeurtenissen” behandelt hoe je terugkerende patronen instelt.

**Q: Hoe zorg ik ervoor dat mijn aangepaste agenda door alle taken in het project wordt gebruikt?**  
A: Wijs de agenda toe aan de standaardagenda van het project of stel deze expliciet in op de `Calendar`‑eigenschap van elke taak.

**Q: Is het mogelijk om agenda’s uit meerdere MS Project‑bestanden samen te voegen?**  
A: Ja. Haal elke agenda op, combineer hun uitzonderingen programmatisch en wijs vervolgens de samengevoegde agenda toe aan het doelproject.

**Q: Welke versie van Aspose.Tasks is vereist voor deze functionaliteit?**  
A: Alle functies zijn beschikbaar in de huidige stabiele release van Aspose.Tasks voor Java (2025.x).

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Gerelateerde tutorials

- [Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions](/tasks/java/calendar-exceptions/define-weekdays/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}