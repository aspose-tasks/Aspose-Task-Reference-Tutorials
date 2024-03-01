---
title: Stylingbalk in Aspose.Tasks
linktitle: Stylingbalk in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u balken kunt opmaken in Aspose.Tasks voor .NET om de projectvisualisatie te verbeteren.
type: docs
weight: 19
url: /nl/net/advanced-features/styling-bar/
---
## Invoering

Het stylen van balken in Aspose.Tasks is een essentieel aspect bij het maken van visueel aantrekkelijke projectplannen. Met de flexibiliteit die de Aspose.Tasks API biedt, kunnen ontwikkelaars verschillende aspecten van balken aanpassen, zoals kleur, vorm en tekststijl, om de projectvisualisatie te verbeteren. In deze zelfstudie onderzoeken we hoe u balken kunt opmaken met Aspose.Tasks voor .NET, waarbij we elk voorbeeld opsplitsen in beheersbare stappen.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1.  Aspose.Tasks voor .NET-bibliotheek: Download en installeer de Aspose.Tasks voor .NET-bibliotheek vanaf de[downloadpagina](https://releases.aspose.com/tasks/net/).
2. Ontwikkelomgeving: Zet een ontwikkelomgeving op met ondersteuning voor .NET Framework.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is een voordeel.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren om toegang te krijgen tot de Aspose.Tasks-klassen en -methoden:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Stap 1: Laad het project

Laad om te beginnen het projectbestand met behulp van de Aspose.Tasks API:

```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Stap 2: Configureer de opslagopties

Definieer de opslagopties en specificeer de staafstijlen die moeten worden toegepast:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Stap 3: Definieer de staafstijl

Maak een nieuwe staafstijl en pas de eigenschappen ervan aan:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Stel het type staafitem in
style.BarColor = Color.Green; // Stel de kleur van de balk in
style.BarShape = BarShape.HalfHeight; // Staafvorm instellen
style.StartShape = Shape.LeftBracket; // Vorm instellen aan het begin van de balk
style.StartShapeColor = Color.Aqua; // Stel de kleur van de startvorm in
style.EndShape = Shape.RightBracket; // Vorm aan het einde van de balk instellen
style.EndShapeColor = Color.Aquamarine; // Stel de kleur van de eindvorm in
style.TextStyle = new TextStyle(); // Tekststijl instellen
style.TextStyle.BackgroundColor = Color.Black; // Achtergrondkleur voor tekst instellen
```

## Stap 4: Pas de tekstconverter aan

Pas desgewenst de tekstconversie aan om de tekstweergave te wijzigen:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Stap 5: Voeg staafstijl toe aan Opties

Voeg de geconfigureerde balkstijl toe aan de opslagopties:

```csharp
options.BarStyles.Add(style);
```

## Stap 6: Sla het project op

Sla ten slotte het project op met de toegepaste staafstijlen:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Conclusie

Het aanpassen van staafstijlen in Aspose.Tasks voor .NET biedt ontwikkelaars de mogelijkheid om visueel aantrekkelijke projectplannen te maken. Door de stappen in deze zelfstudie te volgen, kunt u staven efficiënt opmaken om aan specifieke projectvisualisatievereisten te voldoen.

## Veelgestelde vragen

### V1: Kan ik meerdere staafstijlen op één project toepassen?

A1: Ja, u kunt meerdere staafstijlen definiëren en toepassen op verschillende soorten taken binnen hetzelfde project.
   
### Vraag 2: Is het mogelijk om de staafstijlen tijdens runtime dynamisch te wijzigen?

A2: Ja, u kunt staafstijlen dynamisch wijzigen op basis van bepaalde voorwaarden of gebruikersvoorkeuren binnen uw toepassing.
   
### V3: Ondersteunt Aspose.Tasks het exporteren van projecten met opgemaakte balken naar verschillende bestandsformaten?

A3: Ja, Aspose.Tasks ondersteunt het exporteren van projecten met opgemaakte balken naar verschillende formaten zoals PDF, XLSX en HTML.
   
### V4: Zijn er vooraf gedefinieerde staafstijlen beschikbaar in Aspose.Tasks?

A4: Hoewel Aspose.Tasks standaardbalkstijlen biedt, kunnen ontwikkelaars ook aangepaste staafstijlen maken die zijn afgestemd op hun projectvereisten.
   
### V5: Kan ik bestaande staafstijlen binnen een project ophalen en wijzigen met behulp van de API?

A5: Ja, u kunt bestaande staafstijlen programmatisch ophalen en wijzigen met Aspose.Tasks voor .NET API.