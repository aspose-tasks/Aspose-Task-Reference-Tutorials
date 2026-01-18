---
date: 2026-01-18
description: Leer hoe je een takenlijst in Java maakt en een taak toevoegt aan Microsoft
  Project, een baseline instelt zonder MS Project met behulp van Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Taaklijst maken in Java – MS Project-baseline met Aspose.Tasks
url: /nl/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Taaklijst Java – MS Project Baseline met Aspose.Tasks

## Introductie
In deze tutorial **maak je een taaklijst in Java** door een Microsoft Project‑taakbaseline te genereren met Aspose.Tasks voor Java. Aspose.Tasks stelt je in staat om met Project‑bestanden te werken zonder Microsoft Project geïnstalleerd te hebben, zodat je **taken kunt toevoegen aan Microsoft Project**, resources kunt manipuleren en zelfs **een baseline kunt instellen zonder MS Project**—alles vanuit pure Java‑code.

## Snelle Antwoorden
- **Wat doet Aspose.Tasks?** Het biedt een Java‑API voor het maken, lezen en bewerken van Microsoft Project‑bestanden zonder MS Project.  
- **Heb ik Microsoft Project geïnstalleerd nodig?** Nee, Aspose.Tasks werkt onafhankelijk.  
- **Welke Java‑versie is vereist?** JDK 8 of hoger.  
- **Kan ik een baseline voor één taak instellen?** Ja, gebruik `setBaseline` met een takenlijst.  
- **Is een licentie nodig voor productie?** Ja, een commerciële licentie verwijdert de evaluatie‑beperkingen.

## Wat is een Taakbaseline?
Een taakbaseline legt de oorspronkelijk geplande start‑, eind‑ en werkwaarden voor een taak vast. Het dient als referentiepunt om de werkelijke voortgang te vergelijken met het oorspronkelijke plan.

## Waarom Aspose.Tasks gebruiken om een taaklijst in Java te maken?
- **Geen afhankelijkheid van MS Project** – ideaal voor automatisering aan de server‑kant.  
- **Volledige controle** over taken, resources en kalenders via Java‑code.  
- **Cross‑versie compatibiliteit** met Project‑bestanden van 2007‑2024.

## Voorvereisten
1. **Java Development Kit (JDK)** – installeer JDK 8 of nieuwer.  
2. **Aspose.Tasks voor Java** – download de bibliotheek via de [download link](https://releases.aspose.com/tasks/java/).  

## Pakketten Importeren
Om met Aspose.Tasks in je Java‑project te werken, importeer je de benodigde pakketten:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Stap 1: Een Project‑object maken
```java
Project project = new Project();
```
Hier instantieren we een nieuw `Project`‑object – dit vertegenwoordigt het MS Project‑bestand dat onze taaklijst zal bevatten.

## Stap 2: Een Taak toevoegen aan het Project
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Met `getRootTask()` benaderen we de root van de project‑hiërarchie en **voegen we een taak toe aan Microsoft Project**. De string `"Task"` is de taaknaam; je kunt deze vervangen door elke gewenste beschrijving.

## Stap 3: Baseline instellen voor opgegeven Taken
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Om **een baseline in te stellen zonder MS Project**, maak je een lijst van de taken die je wilt baselinen (hier `myList`) en geef je deze door aan `setBaseline`. Vul `myList` met de taken die je hebt toegevoegd als je alleen een selectieve baseline nodig hebt.

## Stap 4: Baseline instellen voor het gehele Project
```java
project.setBaseline(BaselineType.Baseline);
```
Als je de hele project in één keer wilt baselinen, roep je simpelweg `setBaseline` aan met het gewenste `BaselineType`.

## Hoe een taak toevoegen aan Microsoft Project met Aspose.Tasks
Naast de enkele taak die hierboven wordt getoond, kun je meerdere taken, sub‑taken en resources toewijzen. Elke aanroep van `add()` retourneert een `Task`‑object dat je verder kunt configureren (duur, startdatum, enzovoort).

## Hoe een baseline instellen zonder MS Project
Aspose.Tasks maakt het mogelijk om baselines volledig via code te creëren. Je kunt verschillende baseline‑types (Baseline, Baseline1‑Baseline10) instellen door de `BaselineType`‑enum te wijzigen, waardoor je meerdere revisie‑baselines kunt bijhouden zonder ooit MS Project te openen.

## Veelvoorkomende Problemen en Oplossingen
- **Baseline verschijnt niet:** Zorg ervoor dat je `project.save("output.mpp")` aanroept na het instellen van de baseline (opslaan‑stap hier weggelaten voor beknoptheid).  
- **Takenlijst lijkt leeg:** Controleer of je taken toevoegt aan de juiste ouder (`getRootTask()` of een sub‑taak).  
- **Versiemismatch‑fouten:** Gebruik de nieuwste Aspose.Tasks‑JAR om compatibiliteit met nieuwere .mpp‑formaten te garanderen.

## Veelgestelde Vragen

**Q: Kan ik Aspose.Tasks voor Java gebruiken zonder Microsoft Project geïnstalleerd?**  
A: Ja, Aspose.Tasks werkt onafhankelijk en vereist geen Microsoft Project op de hostmachine.

**Q: Is Aspose.Tasks voor Java compatibel met verschillende versies van Microsoft Project?**  
A: Absoluut. De bibliotheek ondersteunt Project‑bestanden van 2007 tot en met de nieuwste 2024‑releases.

**Q: Kan ik project‑resources manipuleren met Aspose.Tasks voor Java?**  
A: Ja, je kunt resources programmatisch toevoegen, bijwerken en verwijderen, net als taken.

**Q: Ondersteunt Aspose.Tasks voor Java het instellen van taak‑afhankelijkheden?**  
A: Ja, je kunt predecessor‑successor relaties definiëren met de `TaskLink`‑klasse.

**Q: Is technische ondersteuning beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt hulp krijgen via het [support forum](https://forum.aspose.com/c/tasks/15), waar Aspose‑medewerkers en de community vragen beantwoorden.

## Conclusie
Door deze stappen te volgen, heb je geleerd hoe je **een taaklijst in Java maakt**, **taken toevoegt aan Microsoft Project**, en **een baseline instelt zonder MS Project** met behulp van Aspose.Tasks. Deze aanpak stroomlijnt projectautomatisering, elimineert de noodzaak voor desktop‑installaties van Project en geeft je volledige programmatische controle over je projectdata.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-18  
**Getest met:** Aspose.Tasks voor Java 24.12  
**Auteur:** Aspose  

---