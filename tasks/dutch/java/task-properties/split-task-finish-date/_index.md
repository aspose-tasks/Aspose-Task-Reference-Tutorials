---
title: Einddatum van taak splitsen in Aspose.Tasks
linktitle: Einddatum van taak splitsen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u de einddatums van taken moeiteloos kunt splitsen met Aspose.Tasks voor Java. Verbeter projectmanagement met nauwkeurige tijdlijnen.
weight: 28
url: /nl/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Einddatum van taak splitsen in Aspose.Tasks

## Invoering
Bij projectmanagement is het begrijpen van taaktijdlijnen cruciaal voor een succesvolle afronding van het project. Aspose.Tasks voor Java biedt krachtige functies om projecttaken efficiënt te manipuleren. In deze zelfstudie gaan we dieper in op het splitsen van de einddatums van taken met behulp van Aspose.Tasks, zodat u projecttijdlijnen effectief kunt beheren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
- Basiskennis van Java-programmeren.
-  Aspose.Tasks voor Java-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/java/).
- Er is een Java-ontwikkelomgeving opgezet.
## Pakketten importeren
Begin met het opnemen van de benodigde pakketten in uw Java-project:
```java
import com.aspose.tasks.*;
```
## Stap 1: Zoek een gesplitste taak
Zoek de taak die u binnen het project wilt splitsen:
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Project lezen
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Stap 2: Zoek de projectkalender
Haal de projectkalender op voor nauwkeurige datumberekeningen:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Stap 3: Bereken de einddatum van de taak met verschillende duur
Bereken nu de einddatum van de taak voor verschillende tijdsduren:
## Stap 3.1: Duur van 8 uur
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Herhaal de bovenstaande code voor verschillende tijdsduren en pas de uren dienovereenkomstig aan.
## Conclusie
Het beheersen van de kunst van het manipuleren van de einddatum van taken is van cruciaal belang voor effectief projectmanagement. Aspose.Tasks voor Java vereenvoudigt dit proces, waardoor u de tijdlijnen van uw projecten moeiteloos kunt stroomlijnen.
## Veelgestelde vragen
### V1: Hoe kan ik Aspose.Tasks voor Java downloaden?
 A1: U kunt het downloaden[hier](https://releases.aspose.com/tasks/java/).
### V2: Waar kan ik documentatie voor Aspose.Tasks vinden?
 A2: Raadpleeg de documentatie[hier](https://reference.aspose.com/tasks/java/).
### V3: Hoe krijg ik een tijdelijke licentie voor Aspose.Tasks?
 A3: Verkrijg een tijdelijke licentie[hier](https://purchase.aspose.com/temporary-license/).
### V4: Waar kan ik ondersteuning zoeken voor Aspose.Tasks?
 A4: Bezoek het ondersteuningsforum[hier](https://forum.aspose.com/c/tasks/15).
### V5: Kan ik Aspose.Tasks kopen?
 A5: Ja, u kunt het kopen[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
