---
title: Lees MS Project van Primavera met Aspose.Tasks voor Java
linktitle: Lees Project van Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u MS Project-bestanden van Primavera XML naadloos kunt lezen met Aspose.Tasks voor Java. Verbeter de efficiëntie van uw projectbeheer.
type: docs
weight: 20
url: /nl/java/project-management/read-primavera/
---
## Invoering
Bij projectmanagement is interoperabiliteit tussen verschillende softwareplatforms cruciaal voor een naadloze workflow. Aspose.Tasks voor Java biedt robuuste functionaliteit om Microsoft Project-bestanden van Primavera XML te lezen. Deze tutorial leidt u door het proces van het lezen van MS Project-bestanden van Primavera met behulp van Aspose.Tasks voor Java, zodat u de Primavera-specifieke eigenschappen van taken efficiënt kunt onderzoeken.
## Vereisten
Voordat u doorgaat, moet u ervoor zorgen dat de volgende vereisten zijn geïnstalleerd en ingesteld:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java: Download en installeer Aspose.Tasks voor Java van[hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Stap 1: Stel de gegevensdirectory in
```java
String dataDir = "Your Data Directory";
```
 Zorg ervoor dat u deze vervangt`"Your Data Directory"` met het daadwerkelijke pad naar uw gegevensmap.
## Stap 2: Project uit Primavera XML lezen
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Zorg ervoor dat u deze vervangt`"PrimaveraProject.xml"` met de werkelijke naam van uw Primavera XML-bestand.
## Stap 3: Herhaal de taken en haal Primavera-specifieke eigenschappen op
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Deze code doorloopt elke taak in het project en drukt relevante Primavera-specifieke eigenschappen af.

## Conclusie
In deze zelfstudie leerde u hoe u MS Project-bestanden van Primavera XML kunt lezen met Aspose.Tasks voor Java. Deze functionaliteit maakt een naadloze integratie en analyse van projectgegevens op verschillende platforms mogelijk, waardoor de algehele efficiëntie van het projectbeheer wordt verbeterd.
## Veelgestelde vragen
### Vraag: Kan ik de Primavera-specifieke eigenschappen van taken wijzigen met Aspose.Tasks voor Java?
A: Ja, Aspose.Tasks voor Java biedt API's om Primavera-specifieke eigenschappen van taken indien nodig te wijzigen.
### Vraag: Ondersteunt Aspose.Tasks voor Java het lezen van andere projectbestandsformaten?
A: Ja, Aspose.Tasks voor Java ondersteunt het lezen van verschillende projectbestandsformaten, waaronder MPP, XML en Primavera XML.
### Vraag: Is Aspose.Tasks voor Java geschikt voor projectbeheertoepassingen op bedrijfsniveau?
A: Absoluut, Aspose.Tasks voor Java biedt robuuste functies en schaalbaarheid, waardoor het geschikt is voor projectbeheertoepassingen op bedrijfsniveau.
### Vraag: Kan ik broninformatie uit Primavera-projecten extraheren met Aspose.Tasks voor Java?
A: Ja, met Aspose.Tasks voor Java kunt u broninformatie en taakdetails uit Primavera-projecten extraheren.
### Vraag: Waar kan ik aanvullende ondersteuning of documentatie vinden voor Aspose.Tasks voor Java?
 A: U kunt uitgebreide documentatie en toegang tot forums voor ondersteuning vinden op de[Aspose.Tasks voor Java-documentatie](https://reference.aspose.com/tasks/java/) bladzijde.