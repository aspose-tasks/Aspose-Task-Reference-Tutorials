---
title: MS-projectbestanden opslaan in verschillende formaten in Aspose.Tasks
linktitle: Bestanden in verschillende formaten opslaan in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u MS Project-bestanden in verschillende formaten kunt opslaan met Aspose.Tasks voor .NET. Eenvoudige stappen voor efficiënt projectbeheer.
weight: 17
url: /nl/net/rate-recurring-tasks/save-file-formats/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS-projectbestanden opslaan in verschillende formaten in Aspose.Tasks

## Invoering
In deze zelfstudie onderzoeken we hoe u Microsoft Project-bestanden in verschillende indelingen kunt opslaan met Aspose.Tasks voor .NET. Aspose.Tasks is een krachtige API waarmee ontwikkelaars projectbestanden programmatisch kunnen manipuleren en beheren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET van[hier](https://releases.aspose.com/tasks/net/).
2. Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op, zoals Visual Studio.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is een voordeel.

## Naamruimten importeren
Zorg ervoor dat u de benodigde naamruimten importeert aan het begin van uw C#-bestand:
```csharp

using Aspose.Tasks.Saving;
```
## Stap 1: Maak een projectobject
Maak eerst een Project-object en laad uw Microsoft Project-bestand.
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Stap 2: Project opslaan in CSV-formaat
Laten we nu het project opslaan in CSV-formaat. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Stap 3: Ontdek andere formaten
 Aspose.Tasks ondersteunt verschillende formaten voor het opslaan van projectbestanden, zoals XML, PDF, XLSX en meer. U kunt deze formaten verkennen door simpelweg de`SaveFileFormat` parameter in de`Save` methode.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Door deze stappen te volgen, kunt u eenvoudig Microsoft Project-bestanden in verschillende formaten opslaan met Aspose.Tasks voor .NET.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u MS Project-bestanden in verschillende formaten kunt opslaan met Aspose.Tasks voor .NET. Aspose.Tasks vereenvoudigt het proces van het programmatisch manipuleren van projectbestanden en biedt ontwikkelaars flexibiliteit en efficiëntie.
## Veelgestelde vragen
### Vraag: Is Aspose.Tasks compatibel met alle versies van Microsoft Project?
A: Aspose.Tasks ondersteunt de formaten Microsoft Project 2003 XML, Microsoft Project 2007 MPP en Microsoft Project 2010 MPP.
### Vraag: Kan ik Aspose.Tasks uitproberen voordat ik een aankoop doe?
 A: Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?
A: U kunt ondersteuning krijgen van het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Zijn er tijdelijke licenties beschikbaar voor Aspose.Tasks?
 A: Ja, er zijn tijdelijke licenties beschikbaar voor evaluatiedoeleinden. Je kunt er een verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Wat zijn de prijzen voor Aspose.Tasks?
 A: Prijsinformatie is te vinden op de aankooppagina van Aspose.Tasks[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
