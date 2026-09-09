---
date: 2026-09-09
description: Leer hoe u cross‑projecttaken kunt identificeren met Aspose.Tasks voor
  Java. Ontdek naadloze integratie, efficiënt beheer en praktijkvoorbeelden.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identificeer cross‑projecttaken in Aspose.Tasks
og_description: Identificeer cross‑projecttaken in Aspose.Tasks voor Java. Leer hoe
  u de documentmap instelt, taak‑ID's ophaalt en gekoppelde projecten efficiënt beheert.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identificeer cross‑projecttaken in Aspose.Tasks – Java‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identificeer cross‑projecttaken in Aspose.Tasks
url: /nl/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identificeer cross‑projecttaken in Aspose.Tasks

## Inleiding
In deze tutorial leer je **hoe je cross‑projecttaken kunt identificeren** met Aspose.Tasks voor Java. Of je nu een portfolio van onderling afhankelijke planningen beheert of externe afhankelijkheden moet auditen, de onderstaande stappen laten zien hoe je taken kunt vinden die naar andere projectbestanden verwijzen, hun identifiers kunt ophalen en er programmatically mee kunt werken.

## Snelle antwoorden
- **Wat betekent “identify cross project tasks”?** Het betekent het lokaliseren van taken die verwijzen naar of afhankelijk zijn van taken in een ander projectbestand.  
- **Welke methode print de taak‑ID?** Gebruik `externalTask.get(Tsk.ID)` om de taak‑ID te printen.  
- **Hoe stel ik de documentdirectory in?** Wijs het mappad toe aan een `String`‑variabele (bijv. `dataDir`).  
- **Welke eigenschap haalt een taak op via UID?** Roep `getChildren().getByUid(yourUid)` aan.  
- **Heb ik een licentie nodig voor productiegebruik?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor commerciële implementaties.

## Wat is “identify cross project tasks”?
Het identificeren van cross‑projecttaken stelt je in staat relaties tussen taken die over meerdere Microsoft Project‑bestanden verspreid zijn, te volgen. Door taken te vinden die naar externe planningen verwijzen of daarvan afhankelijk zijn, kun je begrijpen hoe werkitems over projectgrenzen heen interageren, dubbele inspanningen voorkomen en nauwkeurige tijdlijnen behouden. Deze mogelijkheid is essentieel voor grootschalige portfolio’s waarin taken worden gedeeld of afhankelijk zijn van externe planningen.

## Waarom Aspose.Tasks voor Java gebruiken?
Aspose.Tasks voor Java ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** (inclusief MPP, MPX, XML en CSV) en kan projecten verwerken met **tot 10.000 taken** zonder het volledige bestand in het geheugen te laden. De bibliotheek werkt op elk JVM‑compatibel platform, vereist geen Microsoft Project‑installatie en biedt volledige API‑toegang tot ID’s, UID’s, externe ID’s en koppeling‑metadata.

## Vereisten
Before you begin, make sure you have:

- Een werkende Java‑ontwikkelomgeving (JDK 8 of hoger).  
- Aspose.Tasks voor Java geïnstalleerd. Je kunt het **[hier](https://releases.aspose.com/tasks/java/)** downloaden.  
- Een geldig Aspose.Tasks‑licentiebestand als je van plan bent de code in productie uit te voeren.

## Importeer pakketten
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand, `Task` vertegenwoordigt een individuele taak, en `Tsk` levert taakveld‑constanten.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Stap 1: stel documentdirectory in
De `dataDir`‑string bevat het pad naar de map met je `.mpp`‑bestanden.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Stap 2: laad extern project
`Project externalProject` laadt het opgegeven externe projectbestand voor inspectie.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Stap 3: haal externe taak op via uid
`externalProject.getChildren().getByUid(uid)` haalt een taak op uit de taakcollectie van het externe project met behulp van zijn unieke identifier.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Stap 4: print taak‑ID (primaire use‑case)
`externalTask.get(Tsk.ID)` retourneert de interne ID die door Aspose.Tasks aan de opgegeven taak is toegewezen.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Stap 5: print originele (externe) taak‑ID
`externalTask.get(Tsk.ExternalID)` haalt de originele ID van de taak op zoals gedefinieerd in het bronprojectbestand.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Herhaal de bovenstaande stappen voor alle extra taken die je over projecten heen wilt volgen.

## Veelvoorkomende problemen & tips
- **Padfouten** – Zorg ervoor dat `dataDir` eindigt met de juiste bestandsseparator (`/` of `\\`).  
- **UID niet gevonden** – Controleer of de UID bestaat in het externe project; gebruik `externalProject.getRootTask().getChildren().size()` om beschikbare UID’s te tonen.  
- **Licentie‑uitzonderingen** – Een ontbrekende of ongeldige licentie zal een licentie‑exception veroorzaken tijdens runtime.  
- **Grote projecten** – Voor projecten groter dan 5.000 taken, overweeg het gebruik van `ProjectReader` met de `LoadOptions`‑vlag om gegevens te streamen en het geheugenverbruik te verminderen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks ondersteunt meerdere talen, waaronder Java, .NET en meer.

**Q: Waar kan ik gedetailleerde documentatie vinden voor Aspose.Tasks voor Java?**  
A: Raadpleeg de documentatie **[hier](https://reference.aspose.com/tasks/java/)**.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een gratis proefversie krijgen **[hier](https://releases.aspose.com/)**.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?**  
A: Verkrijg een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)**.

**Q: Hulp nodig of specifieke vragen?**  
A: Bezoek het Aspose.Tasks‑ondersteuningsforum **[hier](https://forum.aspose.com/c/tasks/15)**.

---

**Laatst bijgewerkt:** 2026-09-09  
**Getest met:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak projectmanagementtaak‑afhankelijkheden in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Stel projectstartdatum in en beheer hoofd‑ en sub‑taken in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Maak MPP‑project Java – wijzig taakvoortgang met Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}