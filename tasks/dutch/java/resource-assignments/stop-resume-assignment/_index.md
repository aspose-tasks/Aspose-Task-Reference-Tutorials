---
title: Stop en hervat resourcetoewijzingen in Aspose.Tasks
linktitle: Stop en hervat resourcetoewijzingen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u resourcetoewijzingen effectief kunt beheren in Aspose.Tasks voor Java met deze stapsgewijze zelfstudie.
weight: 23
url: /nl/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stop en hervat resourcetoewijzingen in Aspose.Tasks

## Invoering
In deze zelfstudie leren we hoe u resourcetoewijzingen kunt stoppen en hervatten met Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java API waarmee ontwikkelaars met Microsoft Project-bestanden kunnen werken zonder dat Microsoft Project op hun systemen hoeft te zijn geïnstalleerd. We zullen het proces opsplitsen in beheersbare stappen, zodat het gemakkelijk te volgen is.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Tasks voor Java-bibliotheek gedownload. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
- Basiskennis van Java-programmeren.
## Pakketten importeren
Laten we eerst de benodigde pakketten in ons Java-project importeren:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Stap 1: Laad het projectbestand
```java
// Het pad naar de documentenmap.
String dataDir = "Your Data Directory";
// Laad het projectbestand
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 In deze stap laden we het projectbestand in een`Project` object met behulp van het bestandspad.
## Stap 2: Herhaal de resourcetoewijzingen
```java
// Definieer de minimumdatum
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Herhaal de resourcetoewijzingen
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Hier definiëren we een minimumdatum en beginnen we met het doorlopen van elke resourcetoewijzing in het project.
## Stap 3: Controleer de stop- en hervattingsdatums
```java
    // Controleer de stopdatum
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Controleer de CV-datum
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
In deze stap controleren we of de stop- en hervattingsdatums van elke resourcetoewijzing vóór de minimumdatum liggen. Als dat zo is, drukken we "NA" af, anders drukken we de respectieve data af.
## Conclusie
In deze zelfstudie hebben we geleerd hoe u resourcetoewijzingen in Aspose.Tasks voor Java kunt stoppen en hervatten. Door de aangegeven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw Java-projecten implementeren.

## Veelgestelde vragen
### Kan ik Aspose.Tasks gebruiken zonder dat Microsoft Project is geïnstalleerd?
Ja, met Aspose.Tasks kunt u met Microsoft Project-bestanden werken zonder dat Microsoft Project op uw systeem hoeft te zijn geïnstalleerd.
### Waar kan ik meer documentatie vinden?
 U kunt gedetailleerde documentatie vinden[hier](https://reference.aspose.com/tasks/java/).
### Is er een gratis proefversie beschikbaar?
 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen als ik problemen tegenkom?
 kunt steun krijgen van de gemeenschap[hier](https://forum.aspose.com/c/tasks/15).
### Kan ik een tijdelijke licentie kopen?
 Ja, u kunt een tijdelijke licentie aanschaffen[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
