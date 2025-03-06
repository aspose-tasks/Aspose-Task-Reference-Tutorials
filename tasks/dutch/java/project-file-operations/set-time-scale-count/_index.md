---
title: Beheersing van de MS Project-tijdschaaltelling in Aspose.Tasks
linktitle: Stel het aantal tijdschalen in Aspose.Tasks in
second_title: Aspose.Tasks Java-API
description: Leer hoe u het aantal tijdschalen in MS Project effectief kunt beheren met behulp van Aspose.Tasks voor Java. Optimaliseer moeiteloos projectvisualisatie en -beheer.
weight: 22
url: /nl/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheersing van de MS Project-tijdschaaltelling in Aspose.Tasks

## Invoering
Het beheren van de tijdschaaltelling in MS Project kan de visualisatie en het beheer van projecten aanzienlijk beïnvloeden. Met Aspose.Tasks voor Java, een krachtige API voor het programmatisch afhandelen van projectmanagementtaken, kunt u de tijdschaaltelling efficiënt manipuleren om projectweergaven af te stemmen op uw specifieke behoeften.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:
1. Java-ontwikkelomgeving: Zorg ervoor dat Java Development Kit (JDK) op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek: Download en installeer de Aspose.Tasks voor Java-bibliotheek. Je kunt het krijgen van[hier](https://releases.aspose.com/tasks/java/).
3. Basiskennis van Java-programmeren: Bekendheid met de Java-programmeertaal zal nuttig zijn.

## Pakketten importeren
Importeer de benodigde pakketten in uw Java-project:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Stap 1: Stel de gegevensmap in
Definieer het pad naar de gegevensmap waar uw projectbestanden worden opgeslagen:
```java
String dataDir = "Your Data Directory";
```
 Vervangen`"Your Data Directory"` met het pad naar uw gegevensmap.
## Stap 2: Projectinstantie maken
 Instantieer een nieuwe`Project` voorwerp:
```java
Project project = new Project();
```
Hierdoor wordt een nieuw projectobject gemaakt.
## Stap 3: Configureer de Gantt-diagramweergave
 Maak een`GanttChartView` object om de Gantt-diagramweergave te configureren:
```java
GanttChartView view = new GanttChartView();
```
## Stap 4: Stel de tijdschaaltelling in voor het onderste niveau
Stel de zichtbaarheid van het aantal en de vinkjes in voor de onderste tijdschaallaag:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Dit specificeert het aantal intervallen en of er ticks moeten worden weergegeven voor het onderste niveau.
## Stap 5: Stel de tijdschaaltelling in voor het middelste niveau
Configureer op dezelfde manier de middelste tijdschaallaag:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Stap 6: Voeg weergave toe aan project
Voeg de geconfigureerde weergave toe aan het project:
```java
project.getViews().add(view);
```
Hiermee wordt de aangepaste weergave aan het project toegevoegd.
## Stap 7: Voeg testgegevens toe aan het project
Voeg enkele testgegevens toe aan het project voor demonstratie:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Hierdoor worden twee taken met een opgegeven duur gemaakt.
## Stap 8: Project opslaan als PDF
Sla het project op als PDF-bestand:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Hierdoor wordt het project met de toegepaste configuraties opgeslagen in een PDF-bestand.

## Conclusie
Door het effectief beheren van de tijdschaaltelling in MS Project met behulp van Aspose.Tasks voor Java kunt u projectweergaven aanpassen voor betere visualisatie en beheer.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks voor Java grootschalige projectbestanden verwerken?
A: Ja, Aspose.Tasks voor Java kan grootschalige projectbestanden efficiënt verwerken.
### Vraag: Is Aspose.Tasks voor Java compatibel met verschillende Java-IDE's?
A: Ja, Aspose.Tasks voor Java werkt naadloos samen met populaire Java Integrated Development Environments (IDE's) zoals Eclipse en IntelliJ IDEA.
### Vraag: Kan ik het uiterlijk van Gantt-diagrammen aanpassen met Aspose.Tasks voor Java?
A: Absoluut, Aspose.Tasks voor Java biedt uitgebreide mogelijkheden om het uiterlijk van Gantt-diagrammen aan te passen aan uw vereisten.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt een gratis proefversie krijgen van[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 A: U kunt ondersteuning en hulp vinden op het Aspose.Tasks-forum[hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
