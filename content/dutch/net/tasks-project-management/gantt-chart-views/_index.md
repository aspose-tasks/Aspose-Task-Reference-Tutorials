---
title: Gantt-diagramweergaven beheersen in Aspose.Tasks
linktitle: Gantt-diagramweergaven in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Gantt-diagramweergaven in Microsoft Project-bestanden kunt aanpassen met Aspose.Tasks voor .NET. Stap-voor-stap handleiding voor efficiënt projectmanagement.
type: docs
weight: 22
url: /nl/net/tasks-project-management/gantt-chart-views/
---
## Invoering
Gantt-diagrammen zijn krachtige hulpmiddelen die in projectmanagement worden gebruikt om taken, tijdlijnen en afhankelijkheden te visualiseren. Aspose.Tasks voor .NET biedt robuuste mogelijkheden voor het werken met Gantt-diagramweergaven in Microsoft Project-bestanden. In deze zelfstudie onderzoeken we hoe u Aspose.Tasks kunt gebruiken om Gantt-diagramweergaven te manipuleren, hun uiterlijk aan te passen en ze op te slaan als PDF-bestanden.
## Vereisten
Voordat u doorgaat, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Installatie van Aspose.Tasks voor .NET
 Zorg ervoor dat u Aspose.Tasks voor .NET hebt geïnstalleerd. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/tasks/net/)en volg de installatie-instructies in de documentatie[hier](https://reference.aspose.com/tasks/net/).
### 2. Microsoft Project-bestand
Bereid een Microsoft Project-bestand voor (`Project2.mpp`) die u gaat gebruiken om met Gantt-diagramweergaven te werken.
### 3. Basiskennis van C# en .NET Framework
In deze tutorial wordt ervan uitgegaan dat je basiskennis hebt van de programmeertaal C# en het .NET-framework.
## Naamruimten importeren
Voordat u met Gantt-diagramweergaven in Aspose.Tasks gaat werken, moet u de benodigde naamruimten in uw C#-code importeren. Hier ziet u hoe u het kunt doen:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Laten we de meegeleverde voorbeeldcode opsplitsen in meerdere stappen en elke stap in detail uitleggen:
## Stap 1: Laad het projectbestand
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Deze stap omvat het laden van het Microsoft Project-bestand (`Project2.mpp` ) naar een exemplaar van de`Project` klas.
## Stap 2: Stel de statusdatum in
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Hier stellen we de statusdatum van het project in op de startdatum.
## Stap 3: Open de Gantt-diagramweergave
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
We hebben vanuit het project toegang tot de Gantt-diagramweergave. Aspose.Tasks biedt toegang tot weergaven zoals Gantt-diagram, netwerkdiagram en taakgebruik.
## Stap 4: Gantt-diagramweergave aanpassen
Laten we nu verschillende aspecten van de Gantt-diagramweergave aanpassen:
### Staafafronding instellen
```csharp
view.BarRounding = false;
```
Hiermee wordt ingesteld of de staven op het Gantt-diagram worden afgerond naar de dichtstbijzijnde dag.
### Stel de staafgrootte in
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Dit bepaalt de hoogte van de Gantt-balken in het diagram.
### Samenvouwbalken verbergen
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Specificeert of de samenvouwbalken verborgen zullen zijn bij het uitvouwen van overzichtstaken.
### Kleur voor niet-werktijd instellen
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Definieert de kleur voor niet-werktijd in het Gantt-diagram.
### Oprolbare Gantt-staven
```csharp
view.RollUpGanttBars = true;
```
Geef op of staven in het Gantt-diagram moeten worden opgerold.
### Staafsplitsingen weergeven
```csharp
view.ShowBarSplits = true;
```
Bepaalt of taaksplitsingen in het Gantt-diagram moeten worden weergegeven.
### tekeningen tonen
```csharp
view.ShowDrawings = true;
```
Specificeert of tekeningen op het Gantt-diagram moeten worden weergegeven.
### Tijdschaalgroottepercentage
```csharp
view.TimescaleSizePercentage = 10;
```
Stelt een percentage in om de afstand tussen eenheden op de tijdschaallaag aan te passen.
## Stap 5: Bewaar de Gantt-diagramweergave als PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Ten slotte slaan we de aangepaste Gantt-diagramweergave op als PDF-bestand.
## Conclusie
In deze zelfstudie hebben we geleerd hoe u met Gantt-diagramweergaven kunt werken in Aspose.Tasks voor .NET. Door de gegeven stappen te volgen, kunt u Gantt-diagrammen efficiënt manipuleren en aanpassen aan uw projectvereisten.
## Veelgestelde vragen
### Vraag: Kan ik het uiterlijk van de Gantt-diagrambalken verder aanpassen?
A: Ja, Aspose.Tasks biedt uitgebreide opties om het uiterlijk van Gantt-diagrambalken aan te passen, inclusief kleuren, vormen en formaten.
### Vraag: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project-bestanden?
A: Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project-bestanden, waaronder MPP-, MPT- en XML-formaten.
### Vraag: Kan ik Gantt-diagramweergaven exporteren naar andere formaten dan PDF?
A: Absoluut, Aspose.Tasks ondersteunt het exporteren van Gantt-diagramweergaven naar meerdere formaten, waaronder PNG, JPEG en XPS.
### Vraag: Biedt Aspose.Tasks ondersteuning voor complexe algoritmen voor projectplanning?
A: Ja, Aspose.Tasks biedt geavanceerde planningsalgoritmen om complexe projectplanningen effectief af te handelen.
### Vraag: Is er een communityforum waar ik hulp kan zoeken of mijn ervaringen met Aspose.Tasks kan delen?
 A: Ja, u kunt de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) om met andere gebruikers in contact te komen, vragen te stellen en oplossingen voor uw vragen te vinden.