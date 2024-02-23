---
title: Configureer MS Project-weergaveopties in Aspose.Tasks
linktitle: Configureer projectweergaveopties in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u MS Project-weergaveopties programmatisch configureert met Aspose.Tasks voor .NET. Pas het uiterlijk van uw project moeiteloos aan.
type: docs
weight: 17
url: /nl/net/project-management-integration/project-display-options/
---
## Invoering
Microsoft Project biedt een overvloed aan weergaveopties om het uiterlijk van uw project aan te passen. Aspose.Tasks voor .NET biedt een robuust raamwerk om deze opties programmatisch te manipuleren. In deze zelfstudie onderzoeken we hoe u de weergaveopties van MS Project kunt configureren met Aspose.Tasks.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:
1.  Aspose.Tasks voor .NET: Download en installeer de bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
2. Microsoft Project-bestand: Zorg ervoor dat u een geldig MS Project-bestand (.mpp) bij de hand hebt om de weergaveopties toe te passen.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is vereist.

## Naamruimten importeren
Zorg er eerst voor dat u de benodigde naamruimten in uw C#-code importeert:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Stap 1: Laad het projectbestand
 Laad het MS Project-bestand met behulp van de`Project` klasse aangeboden door Aspose.Taken:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Stap 2: Configureer weergaveopties
Laten we nu verschillende weergaveopties configureren die beschikbaar zijn in MS Project:
### Schakel waarschuwingen voor taakplanning uit
Waarschuwingen voor planningsconflicten met handmatig geplande taken uitschakelen (beschikbaar voor Project 2010 en hoger):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Voeg ruimte vóór het label toe
Instellen dat er een spatie wordt toegevoegd vóór de getalswaarde en de tijdafkorting:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Configureer de labelweergave voor tijdseenheden
Pas aan hoe verschillende tijdseenheden worden weergegeven:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Projectsamenvattingstaak weergeven
Geef samenvattende informatie over het hele project op één rij weer:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Suggesties voor taakplanning inschakelen
Sta het weergeven van suggesties voor planningsconflicten met handmatig geplande taken toe:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Onderstreep hyperlinks
Instellen om hyperlinks binnen het project te onderstrepen:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Stap 3: Sla het project op
Sla ten slotte het project op met de toegepaste weergaveopties:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de weergaveopties van MS Project kunt configureren met Aspose.Tasks voor .NET. Met deze mogelijkheden kunt u het uiterlijk van uw projectbestanden efficiënt programmatisch aanpassen.
## Veelgestelde vragen
### Vraag: Kan ik deze weergaveopties alleen op specifieke taken toepassen?
A: Ja, u kunt selectief weergaveopties toepassen op individuele taken met behulp van de Aspose.Tasks API.
### Vraag: Hebben deze weergaveopties invloed op de onderliggende projectgegevens?
A: Nee, deze opties wijzigen alleen de visuele weergave van het project en veranderen de onderliggende gegevens niet.
### Vraag: Zijn deze weergaveopties compatibel met alle versies van Microsoft Project?
A: Nee, sommige opties kunnen specifiek zijn voor bepaalde versies van MS Project. Raadpleeg de documentatie voor compatibiliteitsdetails.
### Vraag: Kan ik de weergaveopties terugzetten naar de standaardinstellingen?
A: Ja, u kunt de weergaveopties terugzetten naar hun standaardwaarden met behulp van de Aspose.Tasks API.
### Vraag: Zijn er beperkingen bij het programmatisch aanpassen van weergaveopties?
A: Hoewel Aspose.Tasks uitgebreide aanpassingsmogelijkheden biedt, zijn bepaalde weergaveopties mogelijk niet programmatisch toegankelijk vanwege beperkingen in de MS Project-bestandsindeling.