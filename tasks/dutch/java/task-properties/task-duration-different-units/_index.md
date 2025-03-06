---
title: Taakduur in verschillende eenheden met Aspose.Tasks
linktitle: Taakduur in verschillende eenheden met Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Ontdek het beheer van de taakduur in Java-projecten met Aspose.Tasks. Bereken en converteer de duur nauwkeurig in minuten, dagen, uren, weken en maanden.
weight: 32
url: /nl/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Taakduur in verschillende eenheden met Aspose.Tasks

## Invoering
Op het gebied van projectmanagement is het begrijpen en beheren van de taakduur een cruciaal aspect. Aspose.Tasks voor Java biedt een krachtige toolset om dit efficiënt aan te pakken. In deze zelfstudie begeleiden we u bij het ophalen van taakduur in verschillende eenheden met behulp van Aspose.Tasks.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:
- Java Development Kit (JDK) geïnstalleerd
-  Aspose.Tasks voor Java-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/java/)
- Een basiskennis van Java-programmeren
## Pakketten importeren
Neem in uw Java-project de bibliotheek Aspose.Tasks op. Voeg de volgende importinstructie toe aan het begin van uw code:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Stap 1: Stel uw project in
Begin met het maken van een nieuw Java-project in de Integrated Development Environment (IDE) van uw voorkeur. Zorg ervoor dat u de bibliotheek Aspose.Tasks opneemt in de afhankelijkheden van uw project.
## Stap 2: Lees de projectsjabloon
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lees het MS Project-sjabloonbestand
String fileName = dataDir + "project.xml";
// Lees het invoerbestand als Project
Project project = new Project(fileName);
```
 Zorg ervoor dat u deze vervangt`"Your Document Directory"` met het daadwerkelijke pad naar uw projectbestanden.
## Stap 3: Haal een taak op
```java
// Ontvang een taak om de duur ervan in verschillende formaten te berekenen
Task task = project.getRootTask().getChildren().getById(1);
```
 Hier verkrijgen we een taak uit het project. Aanpassen`getById(1)` op basis van de taak-ID van uw project.
## Stap 4: Duur in minuten
```java
// Haal de duur op in minuten
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Met deze stap wordt de taakduur in minuten berekend.
## Stap 5: Duur in dagen
```java
// Haal de duur op in dagen
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Met deze stap wordt de taakduur in dagen berekend.
## Stap 6: Duur in uren
```java
// Haal de duur op in uren
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Met deze stap wordt de taakduur in uren berekend.
## Stap 7: Duur in weken
```java
// Haal de duur op in weken
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Met deze stap wordt de taakduur in weken berekend.
## Stap 8: Duur in maanden
```java
// Haal de duur op in maanden
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Met deze stap wordt de taakduur in maanden berekend.
## Conclusie
Het beheren van de taakduur is eenvoudig gemaakt met Aspose.Tasks voor Java. Deze tutorial heeft u stap voor stap door het proces geleid en duidelijkheid gegeven over verschillende tijdseenheden.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.Tasks voor Java gebruiken met elke Java IDE?
Ja, Aspose.Tasks voor Java is compatibel met elke Java Integrated Development Environment (IDE).
### Vraag: Hoe kan ik de ID van een taak verkrijgen in een Microsoft Project-bestand?
U kunt het projectbestand inspecteren of de Aspose.Tasks API gebruiken om taak-ID's programmatisch op te halen.
### Vraag: Is Aspose.Tasks geschikt voor het uitvoeren van grootschalige projecten?
Absoluut. Aspose.Tasks is ontworpen om projecten van verschillende omvang efficiënt af te handelen.
### Vraag: Waar kan ik verdere documentatie vinden?
 Bezoek de[documentatie](https://reference.aspose.com/tasks/java/)voor uitgebreide bronnen.
### Vraag: Kan ik Aspose.Tasks voor Java uitproberen voordat ik het aanschaf?
 Ja, u kunt een verkennen[gratis proefperiode](https://releases.aspose.com/) om zijn capaciteiten te evalueren.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
