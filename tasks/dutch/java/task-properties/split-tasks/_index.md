---
title: Taken splitsen in Aspose.Tasks
linktitle: Taken splitsen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Beheers taakbeheer in Java met Aspose.Tasks! Leer hoe u taken efficiënt kunt splitsen voor geoptimaliseerde projecttijdlijnen. Download nu!
weight: 29
url: /nl/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Taken splitsen in Aspose.Tasks

## Invoering
Worstelt u met taakbeheer in uw Java-project? Aspose.Tasks voor Java biedt een krachtige oplossing voor het efficiënt splitsen van taken, waardoor de mogelijkheden voor projectbeheer worden verbeterd. In deze zelfstudie begeleiden we u door het proces van het splitsen van taken met Aspose.Tasks voor Java, zodat u uw projecttijdlijnen en resourcetoewijzingen kunt optimaliseren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw computer geïnstalleerd.
-  Aspose.Tasks voor de Java-bibliotheek gedownload en toegevoegd aan uw project. Je kunt het downloaden van de[Aspose.Tasks voor Java-documentatie](https://reference.aspose.com/tasks/java/).
## Pakketten importeren
Begin met het importeren van de benodigde pakketten in uw Java-project:
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
Begin met het maken van een nieuw project met behulp van de Aspose.Tasks-bibliotheek:
```java
// Maak een nieuw project
Project splitTaskProject = new Project();
```
## Stap 2: Projectkalender instellen
Stel de kalenderinstellingen van het project in om de tijdlijn vast te stellen:
```java
// Koop een standaardkalender
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Stel de kalenderinstellingen van het project in
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (ga verder met het voorbeeld)
```
## Stap 3: Voeg een roottaak toe
Voeg een hoofdtaak toe aan uw project:
```java
// Root-taak
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Stap 4: Voeg een nieuwe taak toe aan Split
Voeg een nieuwe taak toe aan uw project die u wilt splitsen:
```java
// Voeg een nieuwe taak toe
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Stap 5: Maak een resourcetoewijzing
Maak een nieuwe resourcetoewijzing voor de taak:
```java
// Maak een nieuwe resourcetoewijzing
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Stap 6: Genereer tijdgebonden gegevens
Tijdgebonden gegevens voor resourcetoewijzing genereren:
```java
// Genereer tijdgebonden gegevens over resourcetoewijzing
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Stap 7: Splits de taak
Splits de taak op in meerdere delen:
```java
// Verdeel de taak in 3 delen
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (ga verder met het voorbeeld)
```
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u taken kunt splitsen met Aspose.Tasks voor Java. Deze krachtige bibliotheek vereenvoudigt het taakbeheer in Java-projecten en biedt efficiënte oplossingen voor het optimaliseren van projecttijdlijnen en toewijzing van middelen.
## Veel Gestelde Vragen
### Kan ik taken met verschillende duur splitsen?
Ja, u kunt de duur van taken aanpassen aan uw projectvereisten.
### Is Aspose.Tasks voor Java compatibel met alle Java-versies?
Aspose.Tasks voor Java is ontworpen om naadloos samen te werken met verschillende Java-versies, waardoor compatibiliteit wordt gegarandeerd.
### Kan ik Aspose.Tasks voor Java gratis gebruiken?
Aspose.Tasks voor Java biedt een gratis proefperiode, zodat u de functies ervan kunt verkennen voordat u een aankoop doet.
### Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 Bezoek de[Aspose.Tasks voor Java-ondersteuningsforum](https://forum.aspose.com/c/tasks/15) om hulp te krijgen en verbinding te maken met de gemeenschap.
### Heb ik een tijdelijke licentie nodig voor Aspose.Tasks voor Java?
 Een tijdelijke licentie kunt u verkrijgen bij[deze link](https://purchase.aspose.com/temporary-license/) voor test- en evaluatiedoeleinden.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
