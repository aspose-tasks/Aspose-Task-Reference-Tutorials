---
date: 2026-09-25
description: Leer hoe u een projectschema maakt in Java met Aspose.Tasks. Deze gids
  laat u zien hoe u summary tasks toevoegt, project hierarchy beheert en document
  directory efficiënt instelt.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Taken maken in Aspose.Tasks
og_description: Leer hoe u een projectschema maakt in Java met Aspose.Tasks. Volg
  stap‑voor‑stap instructies om summary tasks toe te voegen, hierarchy te beheren
  en document directory in te stellen.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Hoe een projectschema maken met Aspose.Tasks voor Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Hoe een projectschema maken met Aspose.Tasks voor Java
url: /nl/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een projectschema maken met Aspose.Tasks voor Java

## Inleiding
In deze tutorial leer je hoe je een **projectschema** maakt in een Java‑applicatie met Aspose.Tasks. Of je nu een eenvoudige takenlijst bouwt of een complex enterprise‑niveau planner, de onderstaande stappen leiden je door het toevoegen van samenvattende taken, het beheren van de projecthiërarchie en het instellen van de documentmap — allemaal met duidelijke, uitvoerbare code‑fragmenten. Aan het einde heb je een volledig gestructureerd schema klaar voor verdere manipulatie of export.

## Snelle antwoorden
- **Wat beheert Aspose.Tasks?** Het beheert taakhiërarchieën, resources, agenda’s en projectbestandsformaten (MS‑Project, Primavera, enz.).  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 en nieuwer worden volledig ondersteund.  
- **Kan ik aangepaste velden aan taken toevoegen?** Ja, je kunt taken uitbreiden met door de gebruiker gedefinieerde velden via de API.  
- **Is er ingebouwde ondersteuning voor Gantt‑diagrammen?** Aspose.Tasks kan exporteren naar PDF/HTML die Gantt‑visualisaties bevatten.

## Wat is een projectschema in Aspose.Tasks?
Een projectschema is de volledige set van taken, afhankelijkheden en tijdlijnen die definiëren hoe werk wordt uitgevoerd. Aspose.Tasks slaat deze informatie op in een `Project`‑object dat je kunt lezen, wijzigen en opslaan in verschillende formaten. Het omvat start‑ en einddatums, beperkingen en resource‑toewijzingen, waardoor uitgebreide planning en rapportage mogelijk zijn.

## Waarom Aspose.Tasks gebruiken voor Java projectbeheer?
Aspose.Tasks ondersteunt **meer dan 30 invoer‑ en uitvoerformaten** en kan projecten met **tot 10.000 taken** verwerken zonder het volledige bestand in het geheugen te laden, wat hoge prestaties levert voor grootschalige Java‑projectbeheerscenario’s.

## Vereisten
- **Java Development Kit (JDK)** – JDK 8 of later geïnstalleerd op je machine.  
- **Aspose.Tasks for Java library** – Download en installeer de bibliotheek vanaf [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Gebruik Eclipse, IntelliJ IDEA, of een andere Java‑vriendelijke IDE naar keuze.

## Importeer pakketten
`Project`, `Task` en gerelateerde klassen bevinden zich in de `com.aspose.tasks`‑namespace. Importeer ze bovenaan je Java‑bestand:

De `Project`‑klasse vertegenwoordigt een compleet projectschema en biedt methoden om taken en resources te manipuleren.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

De `Project`‑klasse is het toegangspunt voor alle bewerkingen op een projectbestand.

## Hoe een projectschema maken met Aspose.Tasks?

Laad een nieuw `Project`‑instance, stel de documentmap in en begin met het toevoegen van taken. Deze directe‑antwoord‑paragraaf legt de kernstroom uit: je maakt een `Project`, configureert zijn `RootFolder` (de documentmap), en voegt vervolgens een samenvattende taak toe gevolgd door subtaken. Alle wijzigingen blijven in het geheugen totdat je `save` aanroept om het schema naar een bestand te persisteren.

### Stap 1: stel de documentmap in
Definieer waar het resulterende projectbestand wordt weggeschreven. Het vroegtijdig instellen van de map zorgt ervoor dat alle daaropvolgende opslaan‑operaties een consistent pad gebruiken.

De `RootFolder`‑eigenschap geeft de basismap aan waar projectbestanden van worden gelezen of naartoe worden geschreven.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Stap 2: maak een nieuw project
Instantieer een nieuw `Project`‑object dat je schema zal bevatten. Optioneel kun je een reeds bestaand bestandspad doorgeven om een bestaand schema te laden voor bewerking.

De `Project`‑constructor maakt een leeg schema klaar voor het toevoegen van taken.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Stap 3: voeg een samenvattende taak toe
Een samenvattende taak groepeert gerelateerde subtaken en verschijnt als een inklapbare knoop in Gantt‑diagrammen. Gebruik de `Task`‑klasse en stel `IsSummary` in op `true`.

De `addTask`‑methode maakt een nieuwe taak onder een opgegeven ouder en retourneert het ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Stap 4: voeg een subtaak toe
Subtaken erven start‑/einddatums van hun bovenliggende samenvattende taak tenzij je deze overschrijft. Het toevoegen van een subtaak is zo simpel als opnieuw `addTask` aanroepen en de ouder‑ID opgeven.

Het aanroepen van `addTask` met een ouder‑ID voegt een subtaak toe onder die samenvattende taak.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Blijf zoveel taken en subtaken toevoegen als nodig is voor je project. Elke stap draagt bij aan het opbouwen van een gestructureerde projecthiërarchie die kan worden geëxporteerd naar MS‑Project, PDF of andere ondersteunde formaten.

## Veelvoorkomende problemen en oplossingen
- **Problem:** “Document directory not found.”  
  **Solution:** Controleer of het pad dat je toewijst aan `RootFolder` bestaat op het bestandssysteem en of je Java‑proces schrijfrechten heeft.
- **Problem:** Subtasks not appearing under the summary task.  
  **Solution:** Zorg ervoor dat je de juiste ouder‑taak‑ID doorgeeft bij het aanroepen van `addTask`. De API vereist de ouder‑ID als tweede argument.
- **Problem:** Large projects cause OutOfMemoryError.  
  **Solution:** Aspose.Tasks verwerkt taken in een streaming‑modus; vergroot de JVM‑heap‑grootte (`-Xmx2g`) of splits het schema in meerdere bestanden.

## Veelgestelde vragen
**Q: Is Aspose.Tasks suitable for small‑scale projects?**  
A: Absoluut. De bibliotheek schaalt van een enkele takenlijst tot enterprise‑niveau schema’s met duizenden taken.

**Q: Where can I find detailed documentation for Aspose.Tasks for Java?**  
A: Raadpleeg de documentatie [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q: How do I obtain a temporary license for Aspose.Tasks?**  
A: Bezoek de [temporary license request page](https://purchase.aspose.com/temporary-license/) voor een tijd‑beperkte licentie die werkt voor ontwikkeling en testen.

**Q: Can I customize task attributes using Aspose.Tasks?**  
A: Ja, je kunt taken uitbreiden met aangepaste velden, resources toewijzen en agenda’s programmatisch wijzigen.

**Q: Is there a support community for Aspose.Tasks users?**  
A: Absoluut! Word lid van de Aspose.Tasks‑community op [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2026-09-25  
**Getest met:** Aspose.Tasks 24.12 for Java  
**Auteur:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Gerelateerde tutorials

- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [Create Project Management Task Dependencies in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}