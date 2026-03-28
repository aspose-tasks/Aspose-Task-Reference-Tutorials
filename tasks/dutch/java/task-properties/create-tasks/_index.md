---
date: 2026-01-25
description: Leer hoe u taken maakt in Aspose.Tasks voor Java. Beheer projecten, maak
  samenvattingstaken, stel de documentmap in en meer met deze stapsgewijze handleiding.
linktitle: Create Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe taken aanmaken in Aspose.Tasks
url: /nl/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe taken maken in Aspose.Tasks

## Introductie
 je taken maakt** in Aspose.Tasks voor Java, van het instellen van de documentdirectory tot het toevoegen van samenvattende taken en subtaken. Of je nu een laten draaien.

## Sn volledige licKan ik samenvattende taken maken?** Ja – gebruik de `add`‑methode op de kinderen‑collectie van de root‑taak.  
- **Waar worden bestanden opgeslagen?** In de map die je instelt met de *set document directory* stap.

## Wat betekent “hoe taken maken” in Aspose.Tasks?
Taken maken betekent dat je programmatisch `Task`‑objecten toevoegt aan een `Project`‑instantie, hun hiërarchie definieert (samenvattende taken, subtaken) en de structuur opslaat in een MPP‑bestand. Dit maakt geautomatiseerde projectgeneratie, bulk‑updates en integratie met andere systemen mogelijk.

## Waarom Aspose.Tasks voor Java gebruiken?
- **Volle controle** over projectgegevens zonder dat Microsoft Project geïnstalleerd hoeft te zijn.  
- **Cross‑platform** compatibiliteit – werkt op Windows, Linux en macOS.  
- **Rijke API** voor taak‑attributen, resources, kalenders en meer.  
- **Schaalbaar** – geschikt voor kleine hulpprogramma's of enterprise‑niveau planningsengines.

## Vereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

- **Java Development Kit (JDK)** geïnstalleerd op je machine.  
- **Aspose.Tasks for Java** bibliotheek gedownload van [hier](https://releases.aspose.com/tasks/java/).  
- Een IDE zoals **Eclipse** of **IntelliJ IDEA** voor het schrijven en uitvoeren van Java‑code.

## Pakketten importeren
Voeg de vereiste Aspose.Tasks‑klassen toe aan de bovenkant van je Java‑bronbestand:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Stap 1: Stel de documentdirectory in
Definieer de map waarin je projectbestanden worden gelezen of geschreven.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

*Deze stap voldoet aan de **set document directory**‑vereiste en geeft de API een duidelijke locatie voor het MPP‑bestand.*

## Stap 2: Maak een nieuw project
Instantieer een `Project`‑object, eventueel door een bestaand MPP‑bestand te laden of te beginnen met een lege sjabloon.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

## Stap 3: Voeg een samenvattende taak toe
Een samenvattende taak groepeert gerelateerde subtaken. Hier **maken we een samenvattende taak** “Summary1”.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

## Stap 4: Voeg een subtaak toe
Voeg nu een kindtaak toe onder de samenvattende taak om de hiërarchie op te bouwen.

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

Blijf extra taken en subtaken toevoegen indien nodig om de structuur van je project weer te geven. Elke aanroep van `add` breidt de hiërarchie uit, waardoor je complexe planningen programmatisch kunt modelleren.

## Veelvoorkomende problemen & tips
- **Padfouten:** Zorg ervoor dat `dataDir` eindigt met de juiste scheidingsteken (`/` of `\\`).  
- **Licentie‑uitzonderingen:** Als je licentiefouten ziet, controleer dan of een geldig licentiebestand is geladen voordat je de `Project` maakt.  
- **Wijzigingen opslaan:** Na het aanpassen van het project, roep `project.save(dataDir + "updated_project.mpp");` aan om je wijzigingen te bewaren.

## Veelgestelde vragen

### Is Aspose.Tasks geschikt voor kleinschalige projecten?
Absoluut! De API schaalt van eenvoudige takenlijsten tot enorme enterprise‑schema's.

### Waar kan ik gedetailleerde documentatie vinden voor Aspose.Tasks voor Java?
Zie de documentatie [hier](https://reference.aspose.com/tasks/java/).

### Hoe krijg ik een tijdelijke licentie voor Aspose.Tasks?
Bezoek [deze link](https://purchase.aspose.com/temporary-license/) voor een proeflicentie die werkt voor evaluatie.

### Kan ik taak‑attributen aanpassen met Aspose.Tasks?
Ja, je kunt startdatums, duur, resources, aangepaste velden en vele andere eigenschappen instellen op elk `Task`‑object.

### Is er een ondersteuningscommunity voor Aspose.Tasks‑gebruikers?
Absoluut! Word lid van de Aspose.Tasks‑community op [het ondersteuningsforum](https://forum.aspose.com/c/tasks/15).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

**Laatst bijgewerkt:** 2026-01-25  
**Getest met:** Aspose.Tasks for Java (latest release)  
**Auteur:** Aspose  

---