---
title: Sla MS-projectbestanden op als sjablonen met Aspose.Tasks
linktitle: Sjabloonopties opslaan voor Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Microsoft Project-bestanden opslaat als sjablonen met Aspose.Tasks voor .NET. Pas sjablooninstellingen aan voor gestroomlijnd projectbeheer.
weight: 18
url: /nl/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sla MS-projectbestanden op als sjablonen met Aspose.Tasks

## Invoering
In deze zelfstudie doorlopen we het proces van het opslaan van een sjabloon met Aspose.Tasks voor .NET. Sjablonen zijn handig voor het standaardiseren van projectstructuren en instellingen voor toekomstig gebruik. We laten zien hoe u een project als sjabloon kunt opslaan en gaandeweg de eigenschappen ervan kunt afstemmen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Tasks voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
2. Kennis van C#-programmering: Basiskennis van C#-programmering is vereist om de meegeleverde codefragmenten te begrijpen en te implementeren.
3. Microsoft Project-bestand: Zorg ervoor dat u een Microsoft Project-bestand (MPP-formaat) bij de hand heeft dat u als sjabloon wilt opslaan.

## Naamruimten importeren
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Stap 1: Project laden
Eerst moeten we het Microsoft Project-bestand (.mpp) laden dat we als sjabloon willen opslaan.
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Stap 2: Ontvang projectbestandsinformatie
Haal informatie op over het geladen projectbestand, zoals het formaat ervan.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Stap 3: Configureer de opties voor het opslaan van sjabloon
Creëer opties voor het opslaan van sjablonen en configureer de eigenschappen ervan volgens uw vereisten. Met deze opties kunt u aanpassen welke gegevens uit de sjabloon moeten worden verwijderd.
```csharp
var options = new SaveTemplateOptions
{
	// Verwijder alle vaste kosten uit het projectsjabloon
	RemoveFixedCosts = true,
	// Verwijder alle werkelijke waarden uit de projectsjabloon
	RemoveActualValues = true,
	// Verwijder resourcetarieven uit de projectsjabloon
	RemoveResourceRates = true,
	// Verwijder alle basislijnwaarden uit de projectsjabloon
	RemoveBaselineValues = true
};
```
## Stap 4: Project opslaan als sjabloon
Sla het project op als sjabloon met de opgegeven opties.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Stap 5: Krijg sjabloonbestandsinformatie
Haal informatie op over het opgeslagen sjabloonbestand, zoals de indeling ervan.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Gefeliciteerd! U hebt met succes een sjabloon opgeslagen met Aspose.Tasks voor .NET, waarbij u de eigenschappen indien nodig hebt aangepast.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u een Microsoft Project-bestand als sjabloon kunt opslaan met Aspose.Tasks voor .NET. Sjablonen zijn waardevol voor het standaardiseren van projectstructuren en -instellingen, waardoor toekomstige projectcreaties worden gestroomlijnd.
## Veelgestelde vragen
### Vraag: Kan ik aanpassen welke gegevens uit de sjabloon moeten worden verwijderd?
A: Ja, u kunt de opties voor het opslaan van sjabloon configureren om specifieke gegevens te verwijderen, zoals vaste kosten, werkelijke waarden, resourcetarieven en basislijnwaarden.
### Vraag: Is Aspose.Tasks voor .NET compatibel met alle versies van Microsoft Project?
A: Aspose.Tasks voor .NET biedt uitgebreide compatibiliteit met verschillende versies van Microsoft Project, waardoor naadloze integratie en functionaliteit wordt gegarandeerd.
### Vraag: Kan ik sjablonen toepassen op bestaande projecten?
A: Ja, u kunt sjablonen toepassen op bestaande projecten door het sjabloonbestand te laden en indien nodig samen te voegen met uw huidige project.
### Vraag: Ondersteunt Aspose.Tasks voor .NET platformonafhankelijke ontwikkeling?
A: Aspose.Tasks voor .NET is voornamelijk ontworpen voor .NET-framework-applicaties die op Windows-platforms draaien.
### Vraag: Is er technische ondersteuning beschikbaar voor Aspose.Tasks voor .NET?
 A: Ja, u kunt technische hulp en begeleiding zoeken bij de Aspose.Tasks-gemeenschap[forums](https://forum.aspose.com/c/tasks/15)of neem rechtstreeks contact op met hun ondersteuningsteam.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
