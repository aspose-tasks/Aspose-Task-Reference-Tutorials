---
title: Beheer van de taakbasislijnduur in Aspose.Tasks
linktitle: Beheer van de taakbasislijnduur in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u taakbasislijnen efficiënt beheert in MS Project met behulp van Aspose.Tasks voor Java. Deze tutorial begeleidt u stap voor stap door het proces.
type: docs
weight: 12
url: /nl/java/task-baselines/task-baseline-duration/
---
## Invoering
Het beheren van taakbasislijnen in MS Project is cruciaal voor projectplanning en -tracking. In deze zelfstudie onderzoeken we hoe u de basislijnduur van taken effectief kunt beheren met Aspose.Tasks voor Java.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Java-ontwikkelomgeving: Zorg ervoor dat Java Development Kit (JDK) op uw systeem is geïnstalleerd.
2.  Aspose.Tasks-bibliotheek: Download en installeer de Aspose.Tasks voor Java-bibliotheek van[hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Importeer eerst de benodigde pakketten voor uw Java-project:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Stap 1: Maak een projectinstantie
Initialiseer een nieuw projectexemplaar met de volgende code:
```java
Project project = new Project();
```
## Stap 2: Maak een taakbasislijn
Maak een nieuwe taak en stel de basislijn in met behulp van de volgende code:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Stap 3: Taakbasislijninformatie weergeven
Ophalen en weergeven van taakbasislijninformatie, zoals duur, startdatum, einddatum en meer:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Stap 4: Controleer de tussentijdse basislijn en vaste kosten
Controleer of de baseline een tussentijdse baseline is en haal eventuele daaraan verbonden vaste kosten op:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Stap 5: Tijdgebonden gegevens afdrukken
Druk tijdgebonden gegevens af die verband houden met de taakbasislijn:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Door deze stappen te volgen, kunt u de basislijnduur van taken in MS Project effectief beheren met behulp van Aspose.Tasks voor Java.

## Conclusie
Het beheren van taakbasislijnen is essentieel voor projectmanagement, waardoor u afwijkingen van de geplande planning kunt volgen. Met Aspose.Tasks voor Java wordt dit proces gestroomlijnd en efficiënt, waardoor een betere projectcontrole en -levering mogelijk wordt.
## Veelgestelde vragen
### Wat is een taakbasislijn in MS Project?
Een taakbasislijn in MS Project is een momentopname van de aanvankelijk geplande planning voor een taak, inclusief de startdatum, einddatum en duur.
### Waarom is het beheren van taakbasislijnen belangrijk?
Het beheren van taakbasislijnen helpt bij het vergelijken van de geplande planning met de daadwerkelijke voortgang van het project, waardoor een betere tracking en besluitvorming mogelijk wordt.
### Kan ik een taakbasislijn wijzigen nadat deze is ingesteld?
Ja, u kunt taakbasislijnen in MS Project wijzigen om wijzigingen in het projectplan weer te geven. Het is echter essentieel om eventuele afwijkingen van de oorspronkelijke basislijn te documenteren.
### Ondersteunt Aspose.Tasks andere functionaliteiten voor projectbeheer?
Ja, Aspose.Tasks biedt een breed scala aan functies voor projectbeheer, waaronder taakplanning, toewijzing van middelen en het genereren van Gantt-diagrammen.
### Waar kan ik ondersteuning vinden voor Aspose.Tasks?
 Ondersteuning voor Aspose.Tasks vindt u op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15), waar u vragen kunt stellen en kunt communiceren met andere gebruikers.