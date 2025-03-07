---
title: Percentage voltooide berekeningen voor taken in Aspose.Tasks
linktitle: Percentage voltooide berekeningen voor taken in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Verken Aspose.Tasks voor Java en stroomlijn het bijhouden van de projectvoortgang. Bereken moeiteloos taakpercentages voor efficiënt projectmanagement.
weight: 25
url: /nl/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Percentage voltooide berekeningen voor taken in Aspose.Tasks

## Invoering
Welkom bij onze uitgebreide handleiding over het beheersen van taakpercentageberekeningen met Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java-bibliotheek die is ontworpen voor het werken met Microsoft Project-bestanden en die een robuuste reeks functies voor projectbeheer biedt. In deze zelfstudie concentreren we ons op Percentage Complete-berekeningen, waardoor u de kennis krijgt om de projectvoortgang effectief te monitoren en analyseren.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java-ontwikkelomgeving: Zorg ervoor dat Java op uw systeem is geïnstalleerd.
-  Aspose.Tasks-bibliotheek: Download de Aspose.Tasks-bibliotheek voor Java van[deze link](https://releases.aspose.com/tasks/java/).
## Pakketten importeren
Laten we beginnen met het importeren van de benodigde pakketten voor uw Aspose.Tasks voor Java-project. Neem het volgende codefragment op in uw project:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Laten we nu elke stap opsplitsen met gedetailleerde uitleg.
## Stap 1: Pakketten importeren
In de eerste stap importeren we de benodigde pakketten om ons Aspose.Tasks-project op te zetten.
## Stap 2: Documentmap instellen
 Definieer het pad naar uw documentmap met behulp van de`dataDir`variabel. Zorg ervoor dat uw Microsoft Project-bestand, zoals 'Software Development.mpp', zich in deze map bevindt.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
```
## Stap 3: Het project laden
 Initialiseer een nieuwe`Project` object en laad uw Microsoft Project-bestand in de projectinstantie.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Stap 4: Taakverzameling ophalen
 Haal de hoofdtaak van het project op en haal de onderliggende taken ervan op als een verzameling met behulp van`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Stap 5: Afdrukpercentage voltooid
Loop door elke taak in de verzameling en druk het Percentage Voltooid, Percentage Werk voltooid en Fysiek Percentage Voltooid af.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Herhaal deze stappen voor elke taak in uw project om inzicht te krijgen in de voortgang van elke taak.
## Conclusie
Gefeliciteerd! U heeft de taakpercentageberekeningen met succes onder de knie met Aspose.Tasks voor Java. Deze krachtige bibliotheek stelt ontwikkelaars in staat de projectvoortgang efficiënt te beheren en analyseren.
## Veelgestelde vragen
### Vraag: Waar kan ik de Aspose.Tasks-documentatie vinden?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/tasks/java/).
### Vraag: Hoe kan ik de Aspose.Tasks-bibliotheek voor Java downloaden?
 Je kunt het downloaden[hier](https://releases.aspose.com/tasks/java/).
### Vraag: Is er een gratis proefversie beschikbaar?
Ja, u krijgt toegang tot een gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks?
 Bezoek het ondersteuningsforum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Hoe verkrijg ik een tijdelijke licentie?
 U kunt een tijdelijke licentie aanschaffen[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
