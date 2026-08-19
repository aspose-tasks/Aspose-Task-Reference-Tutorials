---
date: 2026-02-26
description: Leer hoe u taken kunt splitsen met Aspose.Tasks voor Java – de definitieve
  gids over hoe u taken splitst, de projectkalender instelt en een resource‑toewijzing
  maakt.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe taken splitsen in Aspose.Tasks
url: /nl/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe taken splitsen in Aspose.Tasks

## Introductie
Als je op zoek bent naar **hoe taken te splitsen** in een Java‑gebaseerd project, ben je hier aan het juiste adres. Aspose.Tasks for Java biedt een nette, programmeerbare manier om een langdurige taak op te delen in kleinere, beheersbare delen, wat helpt bij resource‑leveling, nauwkeurige rapportage en strakkere projecttijdbestekken. In deze tutorial lopen we het volledige proces door — van het instellen van de projectkalender tot het maken van een resource‑toewijzing en uiteindelijk het splitsen van de taak in meerdere segmenten.

## Snelle antwoorden
- **Wat is taak‑splitsen?** Het verdelen van één taak in meerdere kleinere intervallen terwijl de totale duur behouden blijft.  
- **Waarom taken splitsen in Java?** Het maakt precieze resource‑toewijzing en betere voortgangsmonitoring mogelijk.  
- **Welke bibliotheek helpt?** Aspose.Tasks for Java biedt ingebouwde methoden voor splitsen en tijd‑fasering.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** De bibliotheek werkt met Java 8 en nieuwer.

## Vereisten
Voordat je aan de tutorial begint, zorg dat je de volgende zaken gereed hebt:
- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Tasks for Java‑bibliotheek gedownload en toegevoegd aan je project. Je kunt deze downloaden via de [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Pakketten importeren
Begin met het importeren van de benodigde pakketten in je Java‑project:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Stap 1: Maak een nieuw project
Start met het aanmaken van een nieuw project met behulp van de Aspose.Tasks‑bibliotheek:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Stap 2: Stel projectkalender in
Het instellen van de **projectkalender** definieert werkdagen, feestdagen en de algehele tijdlijn voor je planning. Deze stap is essentieel voor nauwkeurige tijd‑gephaseerde berekeningen.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Stap 3: Voeg een hoofdtaak toe
Elk project heeft een hoofdcontainer nodig. Het toevoegen van een hoofdtaak geeft je een plek om alle volgende taken aan te koppelen.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Stap 4: Voeg een nieuwe taak toe om te splitsen
Maak de taak die je wilt splitsen. Hier stellen we als voorbeeld een duur van drie dagen in.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Stap 5: Maak een resource‑toewijzing
Een **resource‑toewijzing** koppelt een resource (of een placeholder) aan de taak. Dit is vereist voordat tijd‑gephaseerde gegevens worden gegenereerd.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Stap 6: Genereer tijdgephaseerde gegevens
Tijd‑gephaseerde gegevens geven weer hoe werk over de duur van de taak wordt verdeeld. Het genereren hiervan maakt de taak klaar voor splitsen.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Stap 7: Splits de taak
Nu **splitsen we de taak in delen**. In dit voorbeeld verdelen we de drie‑daagse taak in drie één‑daagse segmenten.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Waarom taken splitsen?
Taken splitsen geeft je fijnmazigere controle over:
- **Resource leveling:** Wijs verschillende resources toe aan elk segment.  
- **Progress tracking:** Werk de status bij per segment.  
- **Reporting:** Genereer meer gedetailleerde Gantt‑diagrammen en rapporten.

## Veelvoorkomende problemen en oplossingen
- **Ontbrekende kalendergegevens:** Zorg ervoor dat je `timephasedDataFromTaskDuration` aanroept vóór het splitsen.  
- **Segmenten met nul‑duur:** Controleer of elk gesplitst interval een niet‑nul duur heeft; anders negeert de bibliotheek het.  
- **Licentie‑exceptions:** Werken zonder een geldige licentie kan een watermerk aan geëxporteerde bestanden toevoegen.

## Veelgestelde vragen
### Kan ik taken splitsen met verschillende duur?
Ja, je kunt de duur van elk deel aanpassen aan de eisen van je project.

### Is Aspose.Tasks for Java compatibel met alle Java‑versies?
Aspose.Tasks for Java is ontworpen om naadloos te werken met Java 8 en nieuwer, waardoor brede compatibiliteit wordt gegarandeerd.

### Kan ik Aspose.Tasks for Java gratis gebruiken?
Aspose.Tasks for Java biedt een gratis proefversie, zodat je de functionaliteit kunt verkennen voordat je een aankoop doet.

### Hoe kan ik ondersteuning krijgen voor Aspose.Tasks for Java?
Bezoek het [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) voor hulp en om in contact te komen met de community.

### Heb ik een tijdelijke licentie nodig voor Aspose.Tasks for Java?
Je kunt een tijdelijke licentie verkrijgen via [deze link](https://purchase.aspose.com/temporary-license/) voor test‑ en evaluatiedoeleinden.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}