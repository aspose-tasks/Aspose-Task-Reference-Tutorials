---
title: Beheer de duur van taken in Aspose.Tasks
linktitle: Beheer de duur van taken in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Ontdek Aspose.Tasks voor Java en leer moeiteloos de duur van taken beheren. Volg onze stapsgewijze handleiding voor een effectieve projectplanning en -uitvoering.
type: docs
weight: 20
url: /nl/java/task-properties/manage-durations/
---
## Invoering
Aspose.Tasks voor Java biedt een robuuste oplossing voor het efficiënt beheren van projecttaken en -duur. In deze zelfstudie onderzoeken we hoe u de duur van taken kunt beheren met Aspose.Tasks, waarbij we u bij elke stap begeleiden. Of u nu een doorgewinterde ontwikkelaar of een beginner bent, deze gids helpt u de essentie te begrijpen van het werken met taakduur in uw projecten.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Java Development Kit (JDK): Zorg ervoor dat Java op uw computer is geïnstalleerd. Je kunt het downloaden[hier](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks-bibliotheek: Download de Aspose.Tasks-bibliotheek en neem deze op in uw project. Je kunt de bibliotheek vinden[hier](https://releases.aspose.com/tasks/java/).
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten om met Aspose.Tasks te werken:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Stap 1: Stel uw project in
```java
// Maak een nieuw project
Project project = new Project();
```
## Stap 2: Voeg een nieuwe taak toe
```java
// Voeg een nieuwe taak toe aan het project
Task task = project.getRootTask().getChildren().add("Task");
```
## Stap 3: Taakduur ophalen en converteren
```java
// Taakduur in dagen ophalen (standaard tijdseenheid)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Converteer duur naar uren tijdseenheid
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Stap 4: Update de taakduur naar 1 week
```java
// Verleng de taakduur naar 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Stap 5: Verkort de taakduur
```java
// Verkort de taakduur
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Door deze stappen te volgen, hebt u met succes de duur van taken in uw Aspose.Tasks voor Java-project beheerd.
## Conclusie
In deze zelfstudie hebben we de basisbeginselen besproken van het beheren van de taakduur met Aspose.Tasks voor Java. Nu kunt u deze technieken vol vertrouwen in uw projecten integreren voor een effectief beheer van de taakduur.
## Veelgestelde vragen
### Is Aspose.Tasks compatibel met alle Java-versies?
Aspose.Tasks is compatibel met Java 6 en latere versies.
### Kan ik Aspose.Tasks gebruiken voor commerciële projecten?
 Ja, u kunt Aspose.Tasks gebruiken voor zowel persoonlijke als commerciële projecten. Bezoek[hier](https://purchase.aspose.com/buy) voor licentiegegevens.
### Waar kan ik aanvullende ondersteuning en hulpmiddelen vinden?
 Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning en discussies.
### Hoe kan ik een tijdelijke licentie verkrijgen voor testdoeleinden?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/) voor testen en evalueren.
### Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
 Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/) om Aspose.Tasks te verkennen voordat u een aankoop doet.