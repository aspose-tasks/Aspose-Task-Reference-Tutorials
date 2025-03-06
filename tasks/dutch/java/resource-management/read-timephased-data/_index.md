---
title: Lees tijdgebonden gegevens voor bronnen in Aspose.Tasks
linktitle: Lees tijdgebonden gegevens voor bronnen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u tijdgebonden gegevens uit MS Project-bronnen kunt extraheren met behulp van Aspose.Tasks voor Java. Stapsgewijze zelfstudie.
weight: 15
url: /nl/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees tijdgebonden gegevens voor bronnen in Aspose.Tasks

## Invoering
In deze zelfstudie begeleiden we u bij het lezen van tijdgebonden gegevens voor MS Project-bronnen met behulp van Aspose.Tasks voor Java. Deze bibliotheek biedt krachtige functionaliteiten voor het programmatisch beheren van Microsoft Project-bestanden.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd. Je kunt het downloaden van de[website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) en volg de installatie-instructies.
2.  Aspose.Tasks voor Java-bibliotheek: Download de Aspose.Tasks voor Java-bibliotheek van de[downloadpagina](https://releases.aspose.com/tasks/java/) en volg de installatie-instructies in de documentatie.

## Pakketten importeren
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Stap 1: Stel de gegevensdirectory in
Definieer eerst de map waar uw MS Project-bestand zich bevindt.
```java
String dataDir = "Your Data Directory";
```
## Stap 2: Lees het MS Project-sjabloonbestand
Geef de naam op van uw MS Project-sjabloonbestand.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Stap 3: Lees het invoerbestand als project
Lees het invoerbestand met Aspose.Tasks en laad het als een Project-object.
```java
Project project = new Project(dataDir + fileName);
```
## Stap 4: Bron op ID ophalen
Haal de gewenste bron uit het project op aan de hand van de unieke identificatie (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Stap 5: Druk tijdgebonden gegevens af voor resourcewerk
Druk de tijdgebonden gegevens voor resourcewerk af.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Stap 6: Tijdgebonden gegevens voor resourcekosten afdrukken
Druk de tijdgebonden gegevens voor de resourcekosten af.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u tijdgebonden gegevens voor MS Project-bronnen kunt lezen met behulp van Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u op efficiënte wijze waardevolle informatie programmatisch uit uw projectbestanden halen.
## Veelgestelde vragen
### Kan Aspose.Tasks andere typen projectbestanden verwerken dan Microsoft Project?
Ja, Aspose.Tasks ondersteunt verschillende bestandsformaten, waaronder MPP, XML en CSV.
### Is Aspose.Tasks compatibel met verschillende Java-ontwikkelomgevingen?
Ja, Aspose.Tasks is compatibel met alle belangrijke Java IDE's en frameworks.
### Kan ik projectgegevens manipuleren met Aspose.Tasks?
Absoluut, Aspose.Tasks biedt uitgebreide API's voor het maken, wijzigen en analyseren van projectgegevens.
### Is Aspose.Tasks geschikt voor projecten op ondernemingsniveau?
Ja, Aspose.Tasks wordt veel gebruikt in bedrijfsomgevingen vanwege de betrouwbaarheid en schaalbaarheid.
### Waar kan ik ondersteuning vinden als ik problemen ondervind tijdens het gebruik van Aspose.Tasks?
 U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor hulp van de gemeenschap en het ondersteuningsteam.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
