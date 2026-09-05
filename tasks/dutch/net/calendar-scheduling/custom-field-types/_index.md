---
date: 2026-07-19
description: Leer hoe u aangepaste veldtypen toevoegt in Aspose.Tasks voor .NET met
  stapsgewijze code, vereisten en veelgestelde vragen.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aangepaste veldtypen in Aspose.Tasks
og_description: Leer hoe u aangepaste veldtypen toevoegt in Aspose.Tasks voor .NET.
  Volg deze stapsgewijze gids om uitgebreide attributen efficiënt te maken, definiëren
  en gebruiken.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Hoe u aangepaste veldtypen toevoegt in Aspose.Tasks voor .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Hoe u aangepaste veldtypen toevoegt in Aspose.Tasks voor .NET
url: /nl/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe aangepaste veldtypen toe te voegen in Aspose.Tasks

## Introductie

In deze tutorial ontdek je **hoe je een aangepast veld toevoegt** typen aan een Microsoft Project‑bestand met Aspose.Tasks voor .NET. Aangepaste velden laten je extra informatie opslaan—zoals risicoscores, afdelingscodes of aangepaste notities—direct op taken, resources of het project zelf. We lopen het volledige proces door, van het opzetten van de omgeving tot het definiëren, toevoegen en verifiëren van een aangepast tekstveld.

## Snelle antwoorden
- **Wat is een aangepast veld?** Een door de gebruiker gedefinieerde kolom die tekst, getallen, datums of vlaggen kan bevatten op taken/resources.  
- **Welke klasse definieert een aangepast veld?** `ExtendedAttributeDefinition`.  
- **Kan ik een aangepast veld toevoegen aan een bestaand project?** Ja—laad het project, maak de definitie, en voeg deze toe aan de collectie.  
- **Heb ik een licentie nodig voor Aspose.Tasks?** Een licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “hoe je een aangepast veld toevoegt” in Aspose.Tasks?
**Hoe je een aangepast veld toevoegt** verwijst naar het proces van het maken van een `ExtendedAttributeDefinition` en het koppelen ervan aan de `ExtendedAttributes`‑collectie van een project. Dit stelt je in staat extra metadata op te slaan die niet deel uitmaken van het standaard Project‑schema. Het kan worden gebruikt voor taken, resources of het project zelf, waardoor je informatie kunt vastleggen zoals risiconiveaus, afdelingscodes of aangepaste notities die niet beschikbaar zijn in de standaardvelden.

## Waarom aangepaste velden gebruiken in projectmanagement?
Aspose.Tasks ondersteunt **meer dan 50 ingebouwde uitgebreide attribuuttypen** en stelt je in staat **een onbeperkt aantal aangepaste velden** te definiëren zonder de bestandsgrootte aanzienlijk te beïnvloeden. Met aangepaste velden kun je:  
Deze velden verschijnen als extra kolommen in Microsoft Project en kunnen worden gebruikt in formules, rapporten en filters. Ze worden opgeslagen in het projectbestand en reizen mee, waardoor downstream‑tools de aangepaste gegevens behouden.

## Voorvereisten

### 1. Visual Studio geïnstalleerd
Zorg ervoor dat Visual Studio (2019 of later) op je machine is geïnstalleerd. Je kunt het downloaden van de Microsoft‑website.

### 2. Aspose.Tasks voor .NET
Voeg het Aspose.Tasks NuGet‑pakket toe aan je project. Download de nieuwste versie van [hier](https://releases.aspose.com/tasks/net/).

### 3. Basis C#‑kennis
Je moet vertrouwd zijn met C#‑syntaxis, klassen en .NET‑projectstructuur.

## Namespaces importeren

De `Project`, `ExtendedAttributeDefinition` en gerelateerde enums bevinden zich in de `Aspose.Tasks`‑namespace. Importeer deze bovenaan je bestand:

De `Aspose.Tasks`‑namespace biedt alle kern‑types voor het verwerken van Microsoft Project‑bestanden.

```csharp

```

## Hoe een aangepast veld toevoegen aan een project?

Laad het bestaande project, maak een definitie voor een aangepast veld, en voeg deze toe aan de collectie van uitgebreide attributen van het project—alles in drie beknopte stappen. Dit patroon werkt voor taken, resources en het project zelf, en zorgt ervoor dat het aangepaste veld wordt bewaard wanneer je het bestand opslaat.

### Stap 1: Projectobject maken
`Project` is het top‑level object van Aspose.Tasks dat een enkel Project‑bestand in het geheugen vertegenwoordigt. Het instantieren laadt het bestand en geeft je toegang tot taken, resources en uitgebreide attributen.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Stap 2: Aangepast veld definiëren
`ExtendedAttributeDefinition` beschrijft een nieuwe kolom. In dit voorbeeld maken we een **Text**‑type aangepast veld voor taken en geven we het de alias “MyText”. De enum‑waarde `ExtendedAttributeTask.Text1` vertelt Aspose.Tasks waar de waarde moet worden opgeslagen.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Stap 3: Aangepaste velddefinitie toevoegen aan project
De `ExtendedAttributes`‑collectie van het project bevat alle definities van aangepaste velden. Het toevoegen van de definitie maakt deze beschikbaar voor elke taak in het project.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Veelvoorkomende problemen en oplossingen
- **Veld verschijnt niet in de MS Project UI** – Zorg ervoor dat je de `Alias`‑eigenschap instelt; MS Project toont de alias als kolomkop.  
- **Opslaan veroorzaakt een uitzondering** – Controleer of het projectbestand niet alleen‑lezen is en dat je een geldige licentie hebt.  
- **Aangepaste veldwaarden gaan verloren na herladen** – Zorg ervoor dat je `project.Save("output.mpp")` aanroept nadat je waarden aan taken hebt toegewezen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere .NET‑frameworks?**  
A: Ja, Aspose.Tasks werkt met .NET Framework, .NET Core en .NET 5/6/7.

**Q: Is Aspose.Tasks geschikt voor enterprise‑level toepassingen?**  
A: Absoluut. Het ondersteunt het verwerken van projecten met **tot 10.000 taken** en kan draaien in multi‑threaded serveromgevingen.

**Q: Ondersteunt Aspose.Tasks meerdere projectbestandsformaten?**  
A: Ja—Aspose.Tasks leest en schrijft MPP, XML, HTML en CSV‑formaten, en dekt **alle belangrijke Microsoft Project‑versies**.

**Q: Kan ik resource‑data manipuleren met Aspose.Tasks?**  
A: Ja, je kunt resources toevoegen, bijwerken en verwijderen, evenals aangepaste velden aan hen toewijzen.

**Q: Is er een community‑forum voor Aspose.Tasks‑gebruikers?**  
A: Ja, je kunt het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) bezoeken om met andere gebruikers te communiceren en ondersteuning van het Aspose‑team te krijgen.

---

**Laatst bijgewerkt:** 2026-07-19  
**Getest met:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Beheers uitgebreide attribuutdefinities MS Project in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipuleer MS Project uitgebreide attributen met Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper MS Project integratie in Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}