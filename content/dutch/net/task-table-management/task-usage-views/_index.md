---
title: Beheer van taakgebruiksweergaven in Aspose.Tasks voor .NET
linktitle: Taakgebruiksweergaven configureren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Verken Aspose.Tasks voor .NET en leer hoe u taakgebruiksweergaven configureert. Pas de tijdschaalinstellingen aan en verbeter de visuals van uw projectmanagement.
type: docs
weight: 24
url: /nl/net/task-table-management/task-usage-views/
---
## Invoering
Op het gebied van projectmanagement is het visualiseren van taakgebruik cruciaal voor effectieve planning en uitvoering. Aspose.Tasks voor .NET biedt een robuuste oplossing voor het weergeven van weergaven van taakgebruik, waardoor u tijdschaalinstellingen en presentatie-indelingen kunt aanpassen. In deze zelfstudie doorlopen we de stappen voor het configureren van taakgebruiksweergaven met Aspose.Tasks.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET: Zorg ervoor dat de Aspose.Tasks-bibliotheek in uw .NET-project is geïntegreerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
2. .NET-omgeving: zorg dat er een werkende .NET-omgeving op uw computer is geïnstalleerd.
## Naamruimten importeren
Importeer in uw .NET-project de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-functionaliteiten. Voeg de volgende regels toe aan uw code:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Stap 1: Stel het documentmappad in
 Voordat u met de Aspose.Tasks-functionaliteiten gaat werken, stelt u het pad naar uw documentenmap in. Vervangen`"Your Document Directory"` met het daadwerkelijke pad.
```csharp
String DataDir = "Your Document Directory";
```
## Stap 2: Laad het project
 Initialiseer de Aspose.Tasks`Project` object door uw projectbestand te laden (bijvoorbeeld TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Stap 3: Definieer SaveOptions
 Maak een`SaveOptions`object om de weergaveopties op te geven. Stel de tijdschaal in op 'Dagen' en het presentatieformaat op 'TaskUsage'.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Stap 4: Bespaar met dagentijdschaal
Sla het project op met de vooraf gedefinieerde tijdschaalinstellingen van 'Dagen'.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Stap 5: Bespaar met de tijdschaal van ThirdsOfMonths
Wijzig de tijdschaalinstellingen in 'ThirdsOfMonths' en sla het project op.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Stap 6: Bespaar met maanden tijdschaal
Stel de tijdschaal in op 'Maanden' en sla het project op met de bijgewerkte instellingen.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Conclusie
Het configureren van taakgebruiksweergaven met Aspose.Tasks voor .NET is een eenvoudig proces. Door de tijdschaalinstellingen aan te passen, kunt u de visualisatie van uw projecttaken afstemmen op uw specifieke behoeften.
 Ontdek gerust meer functies en functionaliteiten in de[documentatie](https://reference.aspose.com/tasks/net/).
## Veel Gestelde Vragen
### Kan ik de tijdschaal aanpassen buiten de vooraf gedefinieerde instellingen?
Ja, u kunt een aangepaste tijdschaal instellen door de intervallen en eenheden op te geven.
### Zijn er andere presentatieformaten beschikbaar?
Aspose.Tasks ondersteunt verschillende presentatieformaten, waaronder GanttChart, ResourceUsage en meer.
### Is Aspose.Tasks compatibel met verschillende projectbestandsformaten?
Ja, Aspose.Tasks ondersteunt populaire projectbestandsindelingen zoals MPP, XML en CSV.
### Kan ik verschillende tijdschaalinstellingen toepassen op specifieke taken?
Absoluut, u kunt de tijdschaalinstellingen voor individuele taken binnen uw project aanpassen.
### Hoe kan ik ondersteuning krijgen of hulp zoeken voor Aspose.Tasks?
 Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning en begeleiding.