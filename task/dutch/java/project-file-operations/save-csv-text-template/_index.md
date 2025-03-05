---
title: Opslaan als CSV, tekst en sjabloon in Aspose.Tasks
linktitle: Opslaan als CSV, tekst en sjabloon in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u Microsoft Project-bestanden in CSV-, tekst- en sjabloonindelingen kunt opslaan met Aspose.Tasks voor Java.
type: docs
weight: 16
url: /nl/java/project-file-operations/save-csv-text-template/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u projectbestanden in verschillende indelingen, zoals CSV, tekst en sjabloon, kunt opslaan met Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java-bibliotheek waarmee ontwikkelaars met Microsoft Project-bestanden kunnen werken zonder dat Microsoft Project hoeft te worden geïnstalleerd.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2.  Aspose.Tasks voor de Java-bibliotheek gedownload en geconfigureerd in uw Java-project. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
3. Basiskennis van de programmeertaal Java.

## Pakketten importeren
Eerst moet u de benodigde pakketten in uw Java-bestand importeren:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Project opslaan als CSV
Laten we de stappen voor het opslaan van een project als CSV opsplitsen:
### Stap 1: Laad het project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Stap 2: Opslaan als CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Project opslaan als tekst
Zo kunt u een project als tekst opslaan:
### Stap 1: Laad het project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Stap 2: Opslaan als tekst
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Project opslaan als sjabloon
Het opslaan van een project als sjabloon omvat de volgende stappen:
### Stap 1: Laad het project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Stap 2: Stel sjabloonopties in
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Stap 3: Opslaan als sjabloon
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u Microsoft Project-bestanden kunt opslaan als CSV, tekst en sjabloon met Aspose.Tasks voor Java. Met deze eenvoudige stappen kunt u uw projectbestanden in verschillende formaten efficiënt beheren, waardoor uw productiviteit als Java-ontwikkelaar toeneemt.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks voor Java complexe projectbestanden verwerken?
EEN: Absoluut! Aspose.Tasks voor Java kan met gemak projecten van verschillende complexiteit aan, en biedt uitgebreide ondersteuning voor Microsoft Project-bestandsformaten.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt een gratis proefversie van Aspose.Tasks voor Java krijgen van[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning vinden voor Aspose.Tasks voor Java?
 A: U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor hulp of vragen over Aspose.Tasks voor Java.
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks voor Java?
 A: Ja, u kunt een tijdelijke licentie kopen bij[hier](https://purchase.aspose.com/temporary-license/), zodat u het volledige potentieel van de bibliotheek kunt evalueren.
### Vraag: Is Aspose.Tasks voor Java compatibel met verschillende besturingssystemen?
A: Ja, Aspose.Tasks voor Java is compatibel met verschillende besturingssystemen, waaronder Windows, macOS en Linux.