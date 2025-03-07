---
title: Lees- en schrijfsnelheidsschaal voor resourcetoewijzingen in Aspose.Tasks
linktitle: Lees- en schrijfsnelheidsschaal voor resourcetoewijzingen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u de snelheidsschaal van resourcetoewijzingen effectief kunt beheren in Aspose.Tasks voor Java met deze uitgebreide zelfstudie.
weight: 20
url: /nl/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees- en schrijfsnelheidsschaal voor resourcetoewijzingen in Aspose.Tasks

## Invoering
In deze zelfstudie gaan we dieper in op het beheren van de snelheidsschaal van resourcetoewijzingen met behulp van Aspose.Tasks voor Java, een robuuste bibliotheek voor het programmatisch werken met Microsoft Project-bestanden. Door deze stappen te volgen, kunt u de tariefschaalinstellingen voor resourcetoewijzingen in uw Java-toepassingen effectief manipuleren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Java-ontwikkelomgeving: Zorg ervoor dat Java Development Kit (JDK) op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek: Download en installeer de Aspose.Tasks voor Java-bibliotheek van[hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Eerst moet u de benodigde pakketten importeren om met de Aspose.Tasks-functionaliteiten te kunnen werken. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Stap 1: Stel uw project in
Begin met het opzetten van uw Java-project en neem de Aspose.Tasks-bibliotheek op in uw afhankelijkheden.
## Stap 2: Laad het projectbestand
Laad het projectbestand waarmee u wilt werken in uw Java-toepassing.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Stap 3: Voeg een taak toe
Voeg een nieuwe taak toe aan uw project.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Stap 4: Definieer bronnen
Definieer materiële en niet-materiële hulpbronnen en specificeer hun typen.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Stap 5: Wijs bronnen toe aan een taak
Wijs de eerder gedefinieerde resources toe aan de taak, samen met hun tariefschaaltypen.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Stap 6: Sla het project op
Sla het project op met de gewijzigde resourcetoewijzingen.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Stap 7: Resourcetoewijzingen ophalen
Laad het opgeslagen project opnieuw en haal resourcetoewijzingen op om de tariefschaalinstellingen te verifiëren.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Conclusie
Het beheren van de snelheidsschaal voor resourcetoewijzingen in Aspose.Tasks voor Java is cruciaal voor effectief projectbeheer. Door deze stapsgewijze handleiding te volgen, kunt u naadloos de tariefschaalinstellingen voor resourcetoewijzingen in uw Java-applicaties manipuleren.
## Veelgestelde vragen
### V1: Kan ik Aspose.Tasks voor Java gebruiken met elke Java IDE?
A: Ja, Aspose.Tasks voor Java is compatibel met alle belangrijke Java-IDE's, inclusief IntelliJ IDEA, Eclipse en NetBeans.
### V2: Ondersteunt Aspose.Tasks naast MPP ook andere bestandsformaten?
A: Ja, Aspose.Tasks ondersteunt verschillende bestandsformaten, waaronder MPP, XML en HTML.
### Vraag 3: Is Aspose.Tasks geschikt voor projectmanagement op ondernemingsniveau?
A: Absoluut, Aspose.Tasks biedt uitgebreide functies voor het beheren van projecten van elke schaal, waardoor het geschikt is voor projectbeheer op ondernemingsniveau.
### V4: Kan ik resourcetoewijzingen verder aanpassen dan de tariefschaal?
A: Ja, Aspose.Tasks biedt uitgebreide mogelijkheden voor het aanpassen van resourcetoewijzingen, inclusief aanpassingen van kosten, werk en duur.
### V5: Is er een communityforum voor Aspose.Tasks-ondersteuning?
 A: Ja, u kunt ondersteuning vinden en communiceren met andere gebruikers op het Aspose.Tasks-forum[hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
