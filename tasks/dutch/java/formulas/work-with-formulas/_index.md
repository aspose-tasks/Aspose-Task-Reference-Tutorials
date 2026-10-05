---
date: 2026-10-05
description: Leer hoe u een testproject maakt en dagen tussen datums berekent met
  Aspose.Tasks for Java, een aangepast veld toevoegt en MPP-bestanden efficiënt bewerkt.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Werken met formules in Aspose.Tasks
og_description: Maak een testproject en bereken dagen tussen datums met Aspose.Tasks
  for Java. Deze gids laat zien hoe u een aangepast veld toevoegt, taakdeadlines instelt
  en het project opslaat als een MPP-bestand.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Maak testproject en bereken dagen tussen datums
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Maak testproject en bereken dagen tussen datums
url: /nl/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak testproject en bereken dagen tussen datums

In deze tutorial **maak je een testproject** en **bereken je dagen tussen datums** door een aangepast veld toe te voegen, een uitgebreid attribuut te definiëren en een Microsoft Project‑formule toe te passen via de Aspose.Tasks‑bibliotheek voor Java. Of je nu planningen moet genereren, deadlines moet berekenen of rapportage moet automatiseren, Aspose.Tasks stelt je in staat Project‑gegevens programmatisch te manipuleren zonder een desktop‑installatie, ondersteunt meer dan 50 invoer‑ en uitvoerformaten en verwerkt bestanden van honderden pagina's in een geheugen‑efficiënte modus.

## Snelle antwoorden
- **Wat behandelt de tutorial?** Het laat zien hoe je een testproject maakt, een uitgebreid attribuut definieert, een taakdeadline instelt en een formule gebruikt om dagen tussen datums te berekenen.  
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java (latest version).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productiegebruik.  
- **Welke IDE kan ik gebruiken?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, VS Code) die JDK 8+ ondersteunt.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten om de code te kopiëren en uit te voeren.

## Wat is “dagen tussen datums berekenen” in Aspose.Tasks?
In Aspose.Tasks is een formule een tekenreeks die taakvelden kan refereren en berekeningen kan uitvoeren. `[Deadline] - [Finish]` is de formulesyntaxis die Aspose.Tasks gebruikt om het numerieke verschil in dagen tussen twee datumvelden te retourneren. Het resultaat wordt opgeslagen als een numerieke waarde die hele dagen vertegenwoordigt, die je kunt weergeven in een aangepast veld of gebruiken in verdere berekeningen.

## Waarom Aspose.Tasks gebruiken om dagen tussen datums te berekenen?
Aspose.Tasks biedt **volledige API-dekking** voor elke Project-, Taak- en Resource‑eigenschap, draait op Windows, Linux en macOS, en **vereist geen Microsoft Project of Office** om geïnstalleerd te zijn. De engine kan projecten met **meer dan 500 taken** in minder dan een seconde verwerken op typische serverhardware, waardoor het ideaal is voor CI‑pipelines, Docker‑containers en grootschalige batchverwerking.

## Hoe een deadline voor een taak instellen
java.util.Calendar is een Java‑klasse die een specifiek moment in de tijd vertegenwoordigt. Je stelt een deadline in door een `java.util.Calendar`‑waarde toe te wijzen aan het `Tsk.DEADLINE`‑veld van een taak. Na het aanmaken van de Calendar‑instantie stel je jaar, maand en dag in op de gewenste deadline, en roep je vervolgens `task.set(Tsk.DEADLINE, calendar);` aan. De deadline wordt opgeslagen in het projectbestand en kan worden gebruikt in formules zoals `[Deadline] - [Finish]`.

## Hoe een uitgebreid attribuut definiëren
Een uitgebreid attribuut is een aangepast veld dat het resultaat van je formule opslaat. Je maakt het één keer aan, geeft het een vriendelijke alias, en koppelt de `[Deadline] - [Finish]`‑expressie zodat elke taak automatisch het interval kan berekenen. Maak het aan door een `ExtendedAttribute` te instantieren, de Alias in te stellen, de formule toe te wijzen en het toe te voegen aan de collectie van het project.

## Vereisten
Before you start, make sure you have the following:

- **Java Development Kit (JDK) 8+** – download van de Oracle‑website of adopteer OpenJDK.  
- **Aspose.Tasks for Java** – verkrijg de nieuwste JAR van de [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) en voeg deze toe aan de classpath van je project of aan Maven/Gradle‑afhankelijkheden.

## Pakketten importeren
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Stapsgewijze handleiding

### Stap 1: Maak een testproject met een aangepast veld
We beginnen met **het maken van een testproject** en het toevoegen van een aangepast veld dat later ons formuleresultaat zal bevatten.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` is een hulpmethode die een minimale planning maakt en een uitgebreid attribuut registreert dat klaar is voor toewijzing van een formule.

### Stap 2: Definieer een uitgebreid attribuut (voeg aangepast veld toe)
Vervolgens **definiëren we een uitgebreid attribuut** – in wezen het aangepaste veld – en geven we het een vriendelijke alias. Hier voegen we de **logica voor aangepast veld** toe.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** maakt het veld leesbaar in Project.  
- **Formule** berekent het aantal dagen tussen de *Finish*-datum van een taak en de *Deadline* – de kern van *dagen tussen datums berekenen*.

### Stap 3: Deadline voor een taak instellen (deadline‑taak toevoegen & taakdeadline instellen)
Nu voegen we **deadline‑taak** gegevens toe door de *Deadline*-eigenschap op een specifieke taak in te stellen.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- De `Calendar`‑instantie definieert het exacte deadline‑moment.  
- `set(Tsk.DEADLINE, …)` **stelt de taakdeadline in** voor de gekozen taak.

### Stap 4: Sla het project op (Microsoft Project‑bestand manipuleren)
Tot slot **manipuleren we Microsoft Project** door de wijzigingen op te slaan in een MPP‑bestand.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Je kunt `SaveFile.mpp` openen in Microsoft Project om het aangepaste veld, het formuleresultaat en de deadline in de planning te zien.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oplossing |
|----------|-----------|
| **Formule wordt niet geëvalueerd** | Zorg ervoor dat de `Formula`‑string van het attribuut de juiste veldnamen gebruikt (bijv. `[Deadline]`, `[Finish]`). |
| **Taak niet gevonden** | Controleer of de taak‑ID (`1` in het voorbeeld) bestaat; gebruik `project.getRootTask().getChildren().size()` om te debuggen. |
| **Licentie‑exception** | Pas een geldige Aspose.Tasks‑licentie toe voordat je API‑methoden aanroept (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Veelgestelde vragen

**V: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks biedt API's voor .NET, Java en andere platforms, waardoor je Microsoft Project‑bestanden kunt manipuleren in de taal van jouw keuze.

**V: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Absoluut. Download een volledig functionele proefversie van de [Aspose.Tasks download page](https://releases.aspose.com/).

**V: Waar kan ik gedetailleerde documentatie voor Aspose.Tasks vinden?**  
A: De officiële documentatie staat op [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**V: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?**  
A: Bezoek het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) om vragen te stellen en ervaringen te delen met de community.

**V: Heb ik een tijdelijke licentie nodig voor evaluatie?**  
A: Een tijdelijke licentie is beschikbaar voor kortetermijntesten; je kunt er een aanvragen via de [temporary license request page](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-10-05  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe een MPP‑bestand maken – Maak & sla een leeg project op in MPP‑formaat met Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Stel project‑startdatum in MS Project met Aspose.Tasks voor Java](/tasks/java/project-properties/write-project-info/)
- [Hoe een uitgebreid attribuut maken in Java met Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}