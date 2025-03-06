---
title: Aangepaste toewijzingsweergavekolom in Aspose.Tasks
linktitle: Aangepaste toewijzingsweergavekolom in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u aangepaste kolommen voor toewijzingsweergaven kunt toevoegen in Aspose.Tasks voor .NET om de mogelijkheden voor projectbeheer te verbeteren.
weight: 16
url: /nl/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aangepaste toewijzingsweergavekolom in Aspose.Tasks

## Invoering

In deze zelfstudie onderzoeken we hoe u aangepaste kolommen voor toewijzingsweergaven kunt toevoegen met Aspose.Tasks voor .NET. Aangepaste kolommen bieden flexibiliteit en stellen u in staat aanvullende informatie weer te geven die relevant is voor uw projectbeheerbehoeften.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1. Basiskennis van de programmeertaal C#.
2.  Aspose.Tasks voor .NET-bibliotheek geïnstalleerd. Zo niet, dan kunt u deze downloaden[hier](https://releases.aspose.com/tasks/net/).
3. Een geïntegreerde ontwikkelomgeving (IDE) zoals Visual Studio.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren om toegang te krijgen tot de klassen en methoden die nodig zijn voor het maken van aangepaste kolommen in de toewijzingsweergave:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Stap 1: Laad het project

 Laad om te beginnen uw projectbestand met behulp van de`Project` klas:

```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Stap 2: Maak spreadsheet-opslagopties aan

 Maak vervolgens een exemplaar van`Spreadsheet2003SaveOptions` waarmee we de kolommen van de toewijzingsweergave kunnen aanpassen:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Stap 3: Definieer aangepaste kolom

 Definieer nu uw aangepaste kolom door een exemplaar van te maken`AssignmentViewColumn`. Deze klasse vereist de kolomnaam, breedte en een delegatiefunctie om toewijzingsgegevens om te zetten in kolomtekst:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Stap 4: Voeg aangepaste kolom toe aan Opties

Voeg de aangepaste kolom toe aan de verzameling kolommen met toewijzingsweergaven van de opslagopties:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Stap 5: Herhaal de opdrachten

Doorloop elke resourcetoewijzing in het project en geef de aangepaste kolomtekst weer:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Stap 6: Sla het project op met aangepaste kolommen

Sla ten slotte het project op met de aangepaste kolommen voor de toewijzingsweergave:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u aangepaste kolommen voor de toewijzingsweergave kunt toevoegen met Aspose.Tasks voor .NET. Aangepaste kolommen bieden flexibiliteit bij het weergeven van aanvullende informatie die is afgestemd op uw projectvereisten, waardoor de mogelijkheden voor projectbeheer worden verbeterd.

## Veelgestelde vragen

### V1: Kan ik meerdere aangepaste kolommen toevoegen aan de toewijzingsweergave?

 A1: Ja, u kunt meerdere aangepaste kolommen toevoegen door extra exemplaren van te maken`AssignmentViewColumn` en deze toevoegen aan de`Columns` verzameling.

### Vraag 2: Zijn er vooraf gedefinieerde converters beschikbaar voor algemene toewijzingsvelden?

A2: Ja, Aspose.Tasks biedt vooraf gedefinieerde converters voor algemene toewijzingsvelden, waardoor het eenvoudiger wordt om gegevens voor aangepaste kolommen te extraheren.

### V3: Kan ik het uiterlijk van aangepaste kolommen aanpassen, zoals het opmaken van tekst of het toepassen van stijlen?

A3: Ja, u kunt het uiterlijk van aangepaste kolommen aanpassen door eigenschappen zoals breedte, lettertype en uitlijning te wijzigen.

### V4: Is het mogelijk om standaardkolommen uit de toewijzingsweergave te verwijderen?

 A4: Ja, u kunt standaardkolommen verwijderen door ze uit te sluiten van de`Columns` verzameling of het instellen van de breedte op nul.

### V5: Ondersteunt Aspose.Tasks het exporteren van projecten naar andere formaten dan spreadsheets met aangepaste kolommen?

A5: Ja, Aspose.Tasks ondersteunt het exporteren van projecten naar verschillende formaten zoals PDF, HTML en XML, waardoor veelzijdige projectrapportageopties mogelijk zijn.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
