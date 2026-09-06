---
date: 2026-08-29
description: Leer hoe je een taak toevoegt aan een project in Java, een takenlijst
  maakt en een baseline instelt zonder Microsoft Project met behulp van Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Een taak-baseline maken in Aspose.Tasks
og_description: Leer hoe je een taak toevoegt aan een project in Java en een baseline
  instelt met Aspose.Tasks. Deze gids toont stapsgewijze code zonder Microsoft Project
  nodig te hebben.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Hoe een taak toe te voegen aan een project in Java en een baseline in te
  stellen
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Hoe een taak toe te voegen aan een project in Java en een baseline in te stellen
url: /nl/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe taak toevoegen aan project in Java en een baseline instellen

## Introductie
In deze tutorial **voeg je een taak toe aan een project** programmatisch, genereer je een Microsoft Project‑taakbaseline, en sla je het bestand op — allemaal zonder Microsoft Project te openen. Aspose.Tasks for Java biedt je een pure‑Java API die op elk platform werkt, waardoor het perfect is voor geautomatiseerde build‑pijplijnen, rapportageservices, of elke server‑side oplossing die .mpp‑bestanden moet manipuleren.

## Snelle antwoorden
- **Wat doet Aspose.Tasks?** Het biedt een Java API voor het maken, lezen en bewerken van Microsoft Project‑bestanden zonder dat Microsoft Project vereist is.  
- **Heb ik Microsoft Project geïnstalleerd nodig?** Nee, de bibliotheek werkt volledig onafhankelijk.  
- **Welke Java‑versie is vereist?** JDK 8 of hoger.  
- **Kan ik een baseline instellen voor een enkele taak?** Ja – roep `setBaseline` aan op een lijst die alleen de taken bevat die je wilt.  
- **Is een licentie nodig voor productie?** Ja, een commerciële licentie verwijdert evaluatielimieten en ontgrendelt alle functies.

## Wat is een taakbaseline?
Een taakbaseline legt de oorspronkelijk geplande startdatum, einddatum en werkinspanning voor een taak vast op het moment dat het schema voor het eerst wordt opgeslagen. Deze momentopname dient als referentiepunt, waardoor projectmanagers de werkelijke voortgang en kosten kunnen vergelijken met het oorspronkelijke plan, en variaties kunnen berekenen voor prestatie‑analyse.

## Waarom Aspose.Tasks gebruiken om taak toe te voegen aan project in Java?
Je kunt taken maken, wijzigen en een baseline instellen zonder enige desktop‑installatie, wat volledig geautomatiseerde workflows mogelijk maakt. Aspose.Tasks ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan projecten met **honderden taken** verwerken terwijl het geheugenverbruik onder de 200 MB blijft, waardoor het ideaal is voor clouddiensten en CI/CD‑pijplijnen.

## Voorwaarden
1. **Java Development Kit (JDK)** – installeer JDK 8 of nieuwer.  
2. **Aspose.Tasks for Java** – download de bibliotheek via de [downloadlink](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Om te beginnen met Aspose.Tasks in je Java‑project, importeer je de benodigde pakketten:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Stap 1: een projectobject maken
De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een Microsoft Project‑bestand in het geheugen vertegenwoordigt. Een instantie ervan geeft je een leeg project dat je kunt vullen met taken, resources en agenda's.

```java
Project project = new Project();
```
Hier maken we een nieuw `Project`‑object aan – dit vertegenwoordigt het MS Project‑bestand dat onze takenlijst zal bevatten.

## Stap 2: een taak toevoegen aan het project
De `Task`‑klasse vertegenwoordigt een individueel werkitem in een projectschema. Elke `Task` kan zijn eigen duur, startdatum en resource‑toewijzingen hebben.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Met `getRootTask()` krijgen we toegang tot de root van de projecthiërarchie en **voegen we een taak toe aan Microsoft Project**. De string "Task" is de taaknaam; je kunt deze vervangen door elke gewenste beschrijving.

## Stap 3: baseline instellen voor opgegeven taken
`BaselineType` is een enumeratie die definieert welke baseline‑slot (Baseline, Baseline1 … Baseline10) je wilt schrijven. Door een lijst met taken door te geven kun je alleen de geselecteerde items een baseline geven.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Om **een baseline in te stellen zonder MS Project** te maken, maak je een lijst van de taken die je wilt baselinen (hier `myList`) en geef je deze door aan `setBaseline`. Vul `myList` met de taken die je hebt toegevoegd als je alleen een selectieve baseline nodig hebt.

## Stap 4: baseline instellen voor het volledige project
`setBaseline` schrijft de geselecteerde baseline‑waarden naar elke taak in het project.  
Als je de hele project in één keer wilt baselinen, roep je eenvoudig `setBaseline` aan met de gewenste `BaselineType`.

```java
project.setBaseline(BaselineType.Baseline);
```
Deze oproep schrijft de gekozen baseline‑waarden voor **elke taak** in het project, waardoor een volledige momentopname van het oorspronkelijke schema wordt gegarandeerd.

## Hoe taak toevoegen aan Microsoft Project met Aspose.Tasks
`add()` maakt een nieuwe sub‑taak onder de opgegeven bovenliggende taak en retourneert het nieuw aangemaakte `Task`‑object.  
Je voegt een taak toe door `add()` aan te roepen op een bovenliggend `Task`‑object (meestal de root‑taak). De methode retourneert een nieuw `Task`‑instance die je verder kunt configureren — duur, startdatum, resources of aangepaste velden — voordat je het projectbestand opslaat.

## Hoe baseline instellen zonder MS Project
Aspose.Tasks maakt het mogelijk om een baseline volledig via code te creëren. Kies een `BaselineType` (bijv. `BaselineType.Baseline`) en roep `setBaseline` aan. Je kunt dit herhalen met `Baseline1`‑`Baseline10` om meerdere revisie‑baselines bij te houden, allemaal zonder Microsoft Project te openen.

## Veelvoorkomende problemen en oplossingen
- **Baseline verschijnt niet:** Zorg ervoor dat je `project.save("output.mpp")` aanroept na het instellen van de baseline (de opslagnorm is hier weggelaten voor beknoptheid).  
- **Takenlijst lijkt leeg:** Controleer of je taken toevoegt aan de juiste bovenliggende (`getRootTask()` of een sub‑taak).  
- **Versiemismatch‑fouten:** Gebruik de nieuwste Aspose.Tasks JAR om compatibiliteit met nieuwere .mpp‑formaten te garanderen.

## Veelgestelde vragen

**V: Kan ik Aspose.Tasks voor Java gebruiken zonder Microsoft Project geïnstalleerd?**  
A: Ja, Aspose.Tasks werkt onafhankelijk en vereist geen Microsoft Project op de hostmachine.

**V: Is Aspose.Tasks voor Java compatibel met verschillende versies van Microsoft Project?**  
A: Absoluut. De bibliotheek ondersteunt projectbestanden van 2007 tot en met de nieuwste 2024‑releases.

**V: Kan ik projectresources manipuleren met Aspose.Tasks voor Java?**  
A: Ja, je kunt resources programmatisch toevoegen, bijwerken en verwijderen, net als taken.

**V: Ondersteunt Aspose.Tasks voor Java het instellen van taakafhankelijkheden?**  
A: Ja, je kunt voorganger‑opvolgerrelaties definiëren met behulp van de `TaskLink`‑klasse.

**V: Is technische ondersteuning beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt hulp krijgen via het [ondersteuningsforum](https://forum.aspose.com/c/tasks/15), waar Aspose‑medewerkers en de community reageren op vragen.

## Conclusie
Door deze stappen te volgen heb je geleerd hoe je **taak toevoegt aan project** in Java, een takenlijst maakt, en **een baseline instelt zonder MS Project** met Aspose.Tasks. Deze aanpak stroomlijnt projectautomatisering, verwijdert de noodzaak voor desktop‑installaties van Project, en geeft je volledige programmatische controle over elk aspect van je planning.

---

**Laatst bijgewerkt:** 2026-08-29  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe project maken aspose.tasks – Nieuwe taak‑attributen instellen](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Hoe baseline‑duur instellen in Aspose.Tasks voor Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Taken maken Aspose Java – Taakeigenschappen](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}