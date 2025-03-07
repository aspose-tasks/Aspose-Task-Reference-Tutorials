---
title: Beheer MS Project Outline-waarden met Aspose.Tasks
linktitle: Verzameling van overzichtswaarden in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u overzichtswaarden in Microsoft Project-bestanden beheert met Aspose.Tasks voor .NET. Stapsgewijze zelfstudie met codevoorbeelden.
weight: 17
url: /nl/net/outline-code-page-settings/outline-value-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheer MS Project Outline-waarden met Aspose.Tasks

## Invoering
Aspose.Tasks voor .NET biedt een uitgebreide reeks functies voor interactie met Microsoft Project-bestanden. Eén zo'n functie is de mogelijkheid om overzichtswaarden binnen een project te beheren. In deze zelfstudie onderzoeken we hoe u overzichtswaarden kunt verzamelen en manipuleren met Aspose.Tasks voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Aspose.Tasks voor .NET: U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/tasks/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een geschikte IDE hebt geïnstalleerd, zoals Visual Studio.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is een voordeel.
## Naamruimten importeren
Importeer in uw C#-codebestand de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-klassen en -methoden:
```csharp
using Aspose.Tasks;
using System;

```
Laten we het gegeven voorbeeld in meerdere stappen opsplitsen:
## Stap 1: Laad een projectbestand
 Initialiseer eerst a`Project` object door een bestaand Microsoft Project-bestand te laden:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Stap 2: Bestaande overzichtswaarden wissen
Wis vervolgens alle bestaande overzichtswaarden uit het project:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Stap 3: Definieer nieuwe overzichtscode
Definieer nu een nieuwe overzichtscode met een beschrijving en waarde:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Stap 4: Overzichtswaarde bijwerken
Update de waarde van de overzichtscode:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Stap 5: Herhaal de overzichtswaarden
Herhaal de overzichtswaarden en druk de details ervan af:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Stap 6: Manipuleer overzichtswaarden
Voer indien nodig bewerkingen uit zoals het verwijderen, invoegen en kopiëren van overzichtswaarden:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Conclusie
In deze zelfstudie hebben we geleerd hoe we met overzichtswaarden in Microsoft Project-bestanden kunnen werken met behulp van Aspose.Tasks voor .NET. Door de aangegeven stappen te volgen, kunt u de hoofdlijnen binnen uw projecten efficiënt beheren, waardoor u meer controle en flexibiliteit krijgt.
## Veelgestelde vragen
### Vraag: Kan ik meerdere overzichtscodes tegelijkertijd manipuleren?
A: Ja, u kunt binnen een project meerdere overzichtscodes definiëren en manipuleren met behulp van Aspose.Tasks.
### Vraag: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project-bestanden?
A: Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project-bestanden, inclusief MPP- en XML-formaten.
### Vraag: Hoe kan ik omgaan met fouten tijdens het werken met overzichtswaarden?
A: U kunt mechanismen voor foutafhandeling implementeren, zoals try-catch-blokken, om uitzonderingen netjes te beheren.
### Vraag: Kan ik de weergave van overzichtswaarden in mijn project aanpassen?
A: Ja, Aspose.Tasks biedt uitgebreide API's om het uiterlijk en het gedrag van overzichtswaarden aan te passen aan uw vereisten.
### Vraag: Waar kan ik aanvullende bronnen en ondersteuning vinden voor Aspose.Tasks?
 A: U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning en verken de[documentatie](https://reference.aspose.com/tasks/net/) voor gedetailleerde informatie over API's en functies.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
