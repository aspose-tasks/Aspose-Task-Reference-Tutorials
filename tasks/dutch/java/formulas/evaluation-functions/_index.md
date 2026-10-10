---
date: 2026-10-10
description: Leer hoe u een uitgebreid attribuut kunt toevoegen in Aspose.Tasks, evaluatiefuncties
  kunt gebruiken en projectrapporten kunt genereren met deze Java-projectmanagementbibliotheek.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Ondersteun evaluatiefuncties in Aspose.Tasks-formules
og_description: Leer hoe u een uitgebreid attribuut kunt toevoegen in Aspose.Tasks,
  evaluatiefuncties kunt gebruiken en projectrapporten kunt genereren met deze Java-projectmanagementbibliotheek.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Hoe een uitgebreid attribuut toe te voegen in Aspose.Tasks-formules
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Hoe een uitgebreid attribuut toe te voegen in Aspose.Tasks-formules
url: /nl/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een uitgebreid attribuut toe te voegen in Aspose.Tasks-formules

## Inleiding
Aspose.Tasks for Java is een **Java projectmanagementbibliotheek** die je in staat stelt projectrapporten te genereren door een `Project`‑object in Java te maken en Microsoft Project‑functies direct in je code te evalueren. Door deze formules in te sluiten, kun je geavanceerde berekeningen uitvoeren, aangepaste rapporten genereren en projectanalyse automatiseren zonder je ontwikkelomgeving te verlaten. In deze tutorial lopen we door het maken van een projectobject, het toevoegen van een uitgebreid attribuut, en het gebruiken van evaluatiefuncties om **add custom field task** gegevens toe te voegen.

## Snelle antwoorden
- **Wat betekent “create project object java”?** Het maakt een in‑memory `Project`‑instantie die je programmatisch kunt manipuleren.  
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java (download van de officiële site).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige Aspose.Tasks‑licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Kan ik aangepaste velden gebruiken?** Ja – je kunt **add extended attribute** aan taken toevoegen en ze behandelen als aangepaste velden.  
- **Is dit compatibel met alle Project‑bestandformaten?** Aspose.Tasks ondersteunt 3 hoofdformaten (MPP, MPT, XML) en meer dan 50 extra invoer-/uitvoerformaten.

## Voorvereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

1. **Java Development Environment** – JDK 8+ en een IDE zoals IntelliJ IDEA of Eclipse.  
2. **Aspose.Tasks for Java Library** – Download en voeg de bibliotheek toe vanaf de [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Importeer pakketten
Voeg de Aspose.Tasks‑namespace toe aan je Java‑klasse zodat je kunt werken met projecten, taken en uitgebreide attributen:

```java
import com.aspose.tasks.*;
```

## Genereer projectrapport – create project object java
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand in het geheugen en biedt toegang tot taken, resources en aangepaste gegevens. Het instantieren van deze klasse geeft je een container voor alle projectelementen die je zult definiëren.

```java
Project project = new Project();
```

De bovenstaande regel **creates project object java** die leeg begint en klaar is voor aanpassing.

## Hoe een uitgebreid attribuut toe te voegen
De `ExtendedAttributeDefinition`‑klasse definieert een aangepast veld dat aan taken kan worden gekoppeld. Om een uitgebreid attribuut toe te voegen, maak je een instantie van deze klasse met type `Number`, ken je er een alias toe, bijvoorbeeld “Sine”, voeg je het toe aan de `ExtendedAttributes`‑collectie van het project, en koppel je het vervolgens aan elke taak die het aangepaste veld nodig heeft.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Hier **add extended attribute** van type `Number` met de naam “Sine” en koppelen we het aan taken.

## Voeg het uitgebreide attribuut toe aan het project
```java
project.getExtendedAttributes().add(attr);
```

## Maak een nieuwe taak
`Task` vertegenwoordigt een werkitem in het project en kan aangepaste velden bevatten.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Voeg custom field task toe aan het project
Koppel het eerder gedefinieerde uitgebreide attribuut aan de nieuw aangemaakte taak, waardoor de taak een aangepast “Sine”‑veld krijgt dat je kunt gebruiken in formules of berekeningen.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nu bevat de taak een aangepast “Sine”‑veld dat je kunt gebruiken in formules of berekeningen. Dit is ook hoe je **add custom field task** gegevens programmatically toevoegt.

## Waarom evaluatiefuncties gebruiken?
Evaluatiefuncties stellen je in staat native Microsoft Project‑formules (bijv. `Sin([Start])`) direct in Aspose.Tasks in te sluiten, waardoor berekeningen on‑the‑fly mogelijk zijn zonder externe verwerking. Dit houdt alle projectlogica op één plek, vermindert data‑synchronisatiefouten en versnelt de rapportgeneratie. Aspose.Tasks ondersteunt de evaluatie van meer dan 100 MS Project‑functies, waardoor een uitgebreide rekenmachine in Java beschikbaar is.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Formula returns `NaN`** | Controleer of het type van het aangepaste veld overeenkomt met het verwachte numerieke type. |
| **Extended attribute not visible** | Zorg ervoor dat de attribuutdefinitie aan het project wordt toegevoegd **voordat** taken worden aangemaakt. |
| **License exception** | Installeer een tijdelijke of volledige **Aspose.Tasks license**; de proefmodus kan bepaalde functies beperken. |
| **Missing temporary license** | Verkrijg een **temporary Aspose license** van de Aspose‑website. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks for Java complexe MS Project‑formules verwerken?**  
A: Ja, Aspose.Tasks for Java ondersteunt de evaluatie van een breed scala aan MS Project‑functies, waardoor complexe berekeningen binnen Java‑applicaties mogelijk zijn.

**Q: Is Aspose.Tasks for Java compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Ja, Aspose.Tasks for Java ondersteunt verschillende versies van Microsoft Project‑bestanden, inclusief MPP, MPT en XML‑formaten.

**Q: Kan ik Aspose.Tasks for Java uitproberen voordat ik koop?**  
A: Ja, je kunt een gratis proefversie van Aspose.Tasks for Java downloaden van de website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks for Java?**  
A: Je kunt ondersteuning krijgen via het Aspose.Tasks community‑forum [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Is er een tijdelijke licentie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, je kunt een tijdelijke licentie voor testdoeleinden verkrijgen via de Aspose‑website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Conclusie
Door deze stappen te volgen heb je geleerd hoe je **create project object**, **add extended attribute**, en evaluatiefuncties kunt benutten om **generate project report** automatisch te genereren. Je kunt nu deze basis uitbreiden om uitgebreidere projectanalyses, aangepaste dashboards of geautomatiseerde planningshulpmiddelen te bouwen — allemaal aangedreven door Aspose.Tasks for Java.

---

**Laatst bijgewerkt:** 2026-10-10  
**Getest met:** Aspose.Tasks for Java 24.10  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Aangepaste kolommen en uitgebreide attributen in Java projectmanagement](/tasks/java/project-management/extended-attributes/)
- [Lees uitgebreide taakattributen met Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [Hoe Aspose.Tasks for Java te gebruiken – Uitgebreide attributen toevoegen aan resource‑toewijzingen](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}