---
title: Houd toezicht op overuren, resterende kosten en werk in Aspose.Tasks
linktitle: Houd toezicht op overuren, resterende kosten en werk in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u overuren en resterende kosten kunt monitoren en hoe u in Java-projecten kunt werken met Aspose.Tasks. Eenvoudige stappen voor effectief projectmanagement.
weight: 18
url: /nl/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Houd toezicht op overuren, resterende kosten en werk in Aspose.Tasks

## Invoering
In deze zelfstudie leren we hoe u Aspose.Tasks voor Java kunt gebruiken om overuren, resterende kosten en het werk in een project te controleren. Dit kan van onschatbare waarde zijn voor projectmanagers en teamleiders om ervoor te zorgen dat projecten op koers en binnen het budget blijven.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Java Development Kit (JDK): Aspose.Tasks voor Java vereist Java SE 6 of hoger.
2.  Aspose.Tasks voor Java-bibliotheek: download en installeer de bibliotheek van[hier](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Elke Java IDE zoals Eclipse, IntelliJ IDEA of NetBeans.

## Pakketten importeren
Begin met het importeren van de benodigde pakketten in uw Java-bestand:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Stap 1: Stel de gegevensdirectory in
Definieer de map waar uw projectbestand zich bevindt:
```java
String dataDir = "Your Data Directory";
```
 Vervangen`"Your Data Directory"` met het pad naar uw projectbestand.
## Stap 2: Laad het project
 Instantieer een`Project` object en laad het projectbestand:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Vervangen`"ResourceAssignmentOvertimes.mpp"` met de naam van uw projectbestand.
## Stap 3: Herhaal de resourcetoewijzingen
Loop door elke resourcetoewijzing in het project:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Stap 4: Druk de kosten en het werk van overuren af
Overwerkkosten en werk voor elke resourcetoewijzing ophalen en afdrukken:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Stap 5: Druk de resterende kosten en werkzaamheden af
Resterende kosten en werk voor elke resourcetoewijzing ophalen en afdrukken:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Stap 6: Druk de resterende overuren en werk af
Resterende overuren en werk voor elke resourcetoewijzing ophalen en afdrukken:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Conclusie
Het monitoren van overuren, resterende kosten en werk in een project is cruciaal voor succesvol projectmanagement. Met Aspose.Tasks voor Java heeft u eenvoudig toegang tot deze informatie en kunt u deze volgen, zodat uw projecten op schema en binnen het budget blijven.
## Veelgestelde vragen
### Kan ik Aspose.Tasks voor Java gebruiken met andere Java-bibliotheken?
Ja, Aspose.Tasks voor Java is compatibel met andere Java-bibliotheken en -frameworks.
### Ondersteunt Aspose.Tasks verschillende projectbestandsformaten?
Ja, Aspose.Tasks ondersteunt verschillende projectbestandsindelingen, waaronder MPP, XML en meer.
### Is er een proefversie beschikbaar?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Waar kan ik ondersteuning vinden als ik problemen tegenkom?
 U kunt het Aspose.Tasks-forum bezoeken[hier](https://forum.aspose.com/c/tasks/15) Voor ondersteuning.
### Hoe kan ik een licentie voor Aspose.Tasks kopen?
 U kunt een licentie kopen bij[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
