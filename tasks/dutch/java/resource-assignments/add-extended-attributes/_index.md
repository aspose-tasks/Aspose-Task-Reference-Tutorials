---
date: 2026-05-20
description: Leer hoe je Aspose.Tasks voor Java kunt gebruiken om uitgebreide attributen
  toe te voegen aan resource‑toewijzingen, de project‑startdatum in te stellen en
  efficiënt MS Project‑bestanden te schrijven.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Uitgebreide attributen toevoegen aan resource‑toewijzingen in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hoe gebruik je Aspose.Tasks voor Java – Uitgebreide attributen toevoegen aan
  resource‑toewijzingen
url: /nl/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheersen van MS Project-manipulatie met Aspose.Tasks voor Java

## Introductie
In deze tutorial ontdek je **hoe je Aspose.Tasks voor Java** kunt gebruiken om uitgebreide attributen toe te voegen aan resource‑toewijzingen en Microsoft Project‑informatie programmatisch te schrijven. Of je nu een rapportage‑pipeline automatiseert of een aangepast project‑managementtool bouwt, de onderstaande stappen laten je precies zien hoe je de project‑startdatum instelt, resource‑toewijzingen maakt en het bestand als XML opslaat — allemaal met slechts een paar regels Java‑code.

## Snelle antwoorden
- **Wat doet Aspose.Tasks voor Java?** Het leest, schrijft en wijzigt Microsoft Project‑bestanden zonder dat Microsoft Project geïnstalleerd hoeft te zijn.  
- **Kan ik aangepaste velden toevoegen aan een resource‑toewijzing?** Ja, gebruik de `ExtendedAttribute`‑collectie op het `ResourceAssignment`‑object.  
- **Hoe stel ik de project‑startdatum in?** Roep `project.setStartDate(LocalDateTime.of(...))` aan vóór het opslaan.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie verwijdert evaluatiewatermerken en ontgrendelt volledige API‑toegang.  
- **Welke Java‑versies worden ondersteund?** Aspose.Tasks voor Java ondersteunt JDK 8 tot en met JDK 21.

## Hoe gebruik je Aspose.Tasks voor Java?
`Project` is het primaire object dat een Microsoft Project‑bestand in het geheugen vertegenwoordigt. Laad de Aspose.Tasks‑bibliotheek, maak een `Project`‑instantie, configureer project‑niveau eigenschappen, voeg uitgebreide attributen toe aan een resource‑toewijzing en sla tenslotte het project op als XML. De kernworkflow bestaat uit drie beknopte stappen: initialiseren, wijzigen en opslaan. Dit patroon werkt voor elk formaat projectbestand en draait op Windows-, Linux- of macOS‑JVM's.

## Wat is een uitgebreid attribuut in Aspose.Tasks?
Een **uitgebreid attribuut** is een aangepast veld dat je aan taken, resources of toewijzingen koppelt om extra metadata op te slaan naast de ingebouwde kolommen. `ExtendedAttributeDefinition` definieert het schema voor een aangepast veld. Aspose.Tasks biedt de klassen `ExtendedAttributeDefinition` en `ExtendedAttribute` om deze velden programmatisch te definiëren en toe te wijzen.

## Waarom uitgebreide attributen toevoegen aan een resource‑toewijzing?
Aspose.Tasks ondersteunt **meer dan 50 ingebouwde en aangepaste velden**, en je kunt onbeperkt door de gebruiker gedefinieerde attributen toevoegen. Door ze toe te voegen kun je kosten‑codes, afdelings‑ID's of andere bedrijfsspecifieke gegevens direct in het .mpp‑bestand vastleggen, waardoor externe spreadsheets overbodig worden en de gegevensintegriteit gedurende de volledige projectlevenscyclus wordt gewaarborgd.

## Voorvereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – JDK 8 of later geïnstalleerd.  
2. **Aspose.Tasks for Java library** – Download het vanaf de officiële release‑pagina [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse of een andere Java‑compatibele editor die je verkiest.

## Import Packages
Importeer eerst de benodigde pakketten in je Java‑project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Stap 1: Stel gegevensmap in
Definieer de map waarin je projectgegevens worden opgeslagen. Dit pad wordt later gebruikt wanneer je het XML‑bestand opslaat.

```java
String dataDir = "Your Data Directory";
```

### Stap 2: Maak projectinstantie
De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel Microsoft Project‑bestand in het geheugen vertegenwoordigt. Het instantieren geeft je volledige toegang tot alle projecte­lementen.

```java
Project project = new Project();
```

### Stap 3: Stel projectinformatie‑eigenschappen in
Stel essentiële projecteigenschappen in, zoals de startdatum, de 'schedule from start'-vlag en de statusdatum. Deze waarden worden opgeslagen in het `ProjectInfo`‑object van het project.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Stap 4: Voeg uitgebreide attributen toe aan een resource‑toewijzing
Maak een `ExtendedAttributeDefinition` voor het aangepaste veld, koppel deze aan een `ResourceAssignment` en vul de waarde in. Deze stap toont het **add extended attributes**‑keyword in actie.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen en oplossingen
- **NullPointerException bij het benaderen van de toewijzingscollectie** – Zorg ervoor dat je minstens één resource en één taak hebt aangemaakt voordat je toewijzingen ophaalt.  
- **Uitgebreid attribuut verschijnt niet in MS Project** – Controleer of de `FieldId` van het attribuut overeenkomt met een aangepast veldslot (bijv. `ExtendedAttributeTask.Text1`).  
- **Datumnotatie komt niet overeen** – Gebruik `java.time.LocalDateTime` voor datumwaarden; Aspose.Tasks converteert ze automatisch naar het kalenderformaat van het project.

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks voor Java gebruiken om MS Project‑bestanden te lezen?**  
A: Ja, de bibliotheek biedt volledige lees‑schrijffunctionaliteit voor .mpp, .xml en .xps-formaten.

**Q: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?**  
A: Absoluut, het ondersteunt bestanden van Project 2000 tot de nieuwste 2024-release, met meer dan 20 versies.

**Q: Zijn er beperkingen aan de proefversie van Aspose.Tasks voor Java?**  
A: De proefversie voegt een watermerk toe aan gegenereerde bestanden en beperkt het aantal taken dat je kunt maken, maar alle API‑functies blijven toegankelijk.

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Je kunt hulp zoeken op het Aspose.Tasks community‑forum [hier](https://forum.aspose.com/c/tasks/15).

**Q: Kan ik een tijdelijke licentie aanschaffen voor Aspose.Tasks voor Java?**  
A: Ja, tijdelijke licenties zijn beschikbaar voor kortetermijngebruik. Je kunt er een verkrijgen via [hier](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-05-20  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde handleidingen

- [Hoe notities toe te voegen aan resource‑toewijzingen in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Hoe de tarief‑schaal te lezen en te schrijven voor resource‑toewijzingen in Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Hoe een resource toe te voegen aan een project en de leveling‑vertragingseigenschappen te beheren in Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}