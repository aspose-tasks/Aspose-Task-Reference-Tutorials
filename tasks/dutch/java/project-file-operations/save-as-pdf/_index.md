---
title: Opslaan als PDF in Aspose.Tasks
linktitle: Opslaan als PDF in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u projectbestanden naar PDF converteert met Aspose.Tasks voor Java. Eenvoudige stappen voor efficiënte conversie.
weight: 17
url: /nl/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opslaan als PDF in Aspose.Tasks

## Invoering
In deze zelfstudie begeleiden we u bij het proces van het opslaan van een project als PDF met Aspose.Tasks voor Java. Met Aspose.Tasks kunt u uw projectbestanden efficiënt naar PDF-formaat converteren, waardoor compatibiliteit en eenvoudig delen verzekerd zijn. Laten we in de stappen duiken:
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek: Download en installeer de Aspose.Tasks-bibliotheek. Je kunt de downloadlink vinden[hier](https://releases.aspose.com/tasks/java/).
3. Een projectbestand: Zorg dat u een projectbestand (bijvoorbeeld HomeMovePlan.mpp) bij de hand heeft dat u naar PDF wilt converteren.

## Pakketten importeren
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Stap 1: Lees het invoerprojectbestand
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Zorg ervoor dat u vervangt`"Your Data Directory"` met het pad naar uw gegevensmap die het projectbestand bevat.
## Stap 2: Sla het project op als PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Dit codefragment slaat het project op als een PDF-bestand met de naam "Project5.pdf".
## Stap 3: Inhoud aanpassen aan celgrootte
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Hier stellen we opties in voor het opslaan van de PDF, inclusief passende inhoud, tijdschaal en presentatieformaat.
## Stap 4: Legenda's verbergen
```java
o.setLegendOnEachPage(false);
```
Met deze stap worden legenda's op elke pagina van de PDF verborgen.
## Stap 5: Sla het project op met toegepaste opties
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Ten slotte slaat deze code het project met toegepaste opties op in een PDF-bestand.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u Aspose.Tasks voor Java kunt gebruiken om een project als PDF op te slaan. Door deze eenvoudige stappen te volgen, kunt u uw projectbestanden efficiënt converteren, zodat u ze eenvoudig kunt delen en distribueren.
## Veelgestelde vragen
### Vraag: Is Aspose.Tasks compatibel met alle versies van Java?
A: Ja, Aspose.Tasks ondersteunt Java-versies vanaf JDK 6 en hoger.
### Vraag: Kan ik het uiterlijk van de PDF-uitvoer aanpassen?
EEN: Absoluut! Aspose.Tasks biedt verschillende opties om de PDF-uitvoer aan uw wensen aan te passen.
### Vraag: Ondersteunt Aspose.Tasks andere bestandsformaten voor conversie?
A: Ja, Aspose.Tasks ondersteunt een breed scala aan bestandsindelingen, waaronder MPP, XML, XLSX en meer.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks?
 A: Ja, u kunt een gratis proefversie van Aspose.Tasks krijgen van[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks?
 A: Voor ondersteuning en assistentie kunt u terecht bij de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
