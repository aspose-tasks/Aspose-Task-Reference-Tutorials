---
title: Pas de kolommen van de MS Project Resource View aan in Aspose.Tasks
linktitle: Kolommen voor bronweergave aanpassen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u de kolommen voor de resourceweergave van MS Project efficiënt kunt aanpassen met Aspose.Tasks voor .NET. Creëer op maat gemaakte weergaven voor beter projectbeheer.
type: docs
weight: 17
url: /nl/net/resource-risk-analysis/resource-view-columns/
---
## Invoering
Aspose.Tasks voor .NET is een krachtige API waarmee ontwikkelaars programmatisch met Microsoft Project-bestanden kunnen werken. Een veel voorkomende taak bij projectbeheer is het aanpassen van weergaven om specifieke informatie weer te geven. In deze zelfstudie onderzoeken we hoe u de kolommen voor de resourceweergave van MS Project kunt aanpassen met Aspose.Tasks voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Aspose.Tasks voor .NET-bibliotheek: u kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
2. Microsoft Project-bestand: Houd een voorbeeld van een MS Project-bestand bij de hand om te testen.
3. Ontwikkelomgeving: een ontwikkelomgeving die is opgezet met het .NET-framework.
## Naamruimten importeren
Laten we eerst de benodigde naamruimten in ons project importeren:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Stap 1: Laad het projectbestand
Laad het MS Project-bestand met de Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Stap 2: Haal bronnen op en definieer opties
Haal vervolgens de bron op waarvan u de weergavekolommen wilt aanpassen en definieer de opties voor het opslaan van de PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Stap 3: Definieer aangepaste kolommen
Definieer nu aangepaste kolommen voor de resourceweergave. U kunt verschillende velden opgeven en zelfs afgevaardigden gebruiken voor aangepaste berekeningen:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Stap 4: Herhaal de kolommen
Herhaal de gedefinieerde kolommen en geef hun eigenschappen weer:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Stap 5: Sla de aangepaste weergave op
Stel ten slotte de aangepaste weergave in en sla deze op als PDF-bestand:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Door deze stappen te volgen, kunt u de kolommen voor de resourceweergave van MS Project efficiënt aanpassen met Aspose.Tasks voor .NET.
## Conclusie
Het aanpassen van de kolommen in de resourceweergave van MS Project is essentieel voor het weergeven van relevante informatie die is afgestemd op de behoeften van uw project. Met Aspose.Tasks voor .NET wordt deze taak eenvoudig en efficiënt, waardoor u moeiteloos aangepaste weergaven kunt maken.
## Veelgestelde vragen
### Kan ik weergaven voor andere elementen dan bronnen aanpassen?
Ja, Aspose.Tasks maakt ook maatwerk mogelijk voor taken, opdrachten en andere projectelementen.
### Ondersteunt Aspose.Tasks het opslaan van weergaven in andere formaten dan PDF?
Ja, u kunt weergaven in verschillende formaten opslaan, zoals XLSX, HTML en afbeeldingen.
### Is het mogelijk om opmaak toe te passen op de aangepaste weergave?
Absoluut, Aspose.Tasks biedt uitgebreide opmaakopties om het uiterlijk van uw aangepaste weergaven te verbeteren.
### Kan ik de aangepaste weergave dynamisch bijwerken op basis van veranderende projectgegevens?
Ja, u kunt de aangepaste weergave bijwerken en opnieuw genereren wanneer de onderliggende projectgegevens veranderen.
### Ondersteunt Aspose.Tasks platformonafhankelijke ontwikkeling?
Aspose.Tasks voor .NET richt zich primair op .NET-platforms, maar er zijn ook versies beschikbaar voor Java en andere platforms.