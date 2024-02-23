---
title: Configureer de tijdschaallagen van Gantt-diagrammen in Aspose.Tasks
linktitle: Configureer tijdschaallagen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Verken Aspose.Tasks voor .NET om tijdschaallagen in uw Gantt-diagramweergave te configureren voor nauwkeurige visualisatie van de projecttijdlijn. #Aspose.Tasks #MS-project
type: docs
weight: 16
url: /nl/net/text-view-configuration/timescale-tiers/
---
## Invoering
In het dynamische landschap van projectmanagement is effectieve visualisatie cruciaal voor het begrijpen van tijdlijnen en deadlines. Aspose.Tasks voor .NET biedt een krachtige toolset en in deze zelfstudie onderzoeken we hoe u tijdschaallagen kunt configureren voor optimale weergave in de Gantt-diagramweergave. Volg deze stapsgewijze instructies om uw projectvisualisatie te verbeteren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:
- Basiskennis van C# en .NET.
- Aspose.Tasks voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
- Een ontwikkelomgeving die is opgezet voor de ontwikkeling van .NET-applicaties.
## Naamruimten importeren
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Laten we nu elke stap van het gegeven voorbeeld opsplitsen.
## Stap 1: Project initialiseren en taakkoppelingen toevoegen
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Hier maken we een project en brengen we taakkoppelingen tot stand tussen 'Taak 1' en 'Taak 2'.
## Stap 2: Configureer de Gantt-diagramweergave
```csharp
var view = (GanttChartView)project.DefaultView;
```
Toegang tot de Gantt-diagramweergave voor aanpassing.
## Stap 3: Stem het middelste tijdschaalniveau af
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Pas de middelste tijdschaallaag aan om weken met specifieke labels en uitlijning weer te geven.
## Stap 4: Voeg het hoogste tijdschaalniveau toe
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Voeg een hoogste tijdschaallaag toe om maanden weer te geven.
## Stap 5: Pas datums op het middenniveau aan
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personaliseer de maandlabels voor een betere visualisatie.
## Stap 6: Stel de projecttijdschaal in
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Definieer de projecttijdschaal om de algehele tijdlijn te beheren.
## Stap 7: Sla het project op met een aangepaste tijdschaal
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Sla het project op met de gedefinieerde tijdschaalinstellingen.
## Conclusie
Concluderend: het configureren van tijdschaallagen in Aspose.Tasks voor .NET zorgt voor een meer op maat gemaakte en visueel aantrekkelijke weergave van projecttijdlijnen. Met deze stappen kunt u een Gantt-diagramweergave maken die precies voldoet aan uw projectbeheerbehoeften.
## Veelgestelde vragen
### Kan ik Aspose.Tasks gebruiken met andere .NET-bibliotheken?
Ja, Aspose.Tasks integreert naadloos met andere .NET-bibliotheken en biedt flexibiliteit in uw ontwikkelingsstack.
### Is er een tijdelijke licentie beschikbaar voor testdoeleinden?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/) voor evaluatie.
### Zijn er aanvullende aanpassingsopties voor de Gantt-diagramweergave?
Absoluut, Aspose.Tasks biedt uitgebreide aanpassingsmogelijkheden voor de Gantt-diagramweergave om aan diverse projectvereisten te voldoen.
### Kan ik tijdschalen in verschillende formaten weergeven?
Natuurlijk kunt u verschillende formaten en stijlen voor weergave op tijdschaal verkennen, zodat deze het beste passen bij de context van uw project.
### Is er een communityforum voor Aspose.Tasks-ondersteuning?
 Ja, bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning en discussies.