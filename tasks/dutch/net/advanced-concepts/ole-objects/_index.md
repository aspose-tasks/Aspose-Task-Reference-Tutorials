---
date: 2026-03-16
description: Leer hoe u OLE‑objecten kunt verwijderen met Aspose.Tasks voor .NET,
  en ontdek hoe u OLE kunt beheren en OLE efficiënt kunt opruimen in uw projecten.
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hoe OLE-objecten te verwijderen in Aspose.Tasks voor .NET
url: /nl/net/advanced-concepts/ole-objects/
weight: 22
---

Last Updated:** 2026-03-16" unchanged.

"**Tested With:** Aspose.Tasks 24.11 for .NET" unchanged.

"**Author:** Aspose" unchanged.

All good.

Make sure to keep markdown formatting exactly.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe OLE-objecten te verwijderen in Aspose.Tasks voor .NET

## Inleiding

Aspose.Tasks for .NET geeft u volledige controle over OLE (Object Linking and Embedding)-objecten die zich binnen Microsoft Project‑bestanden bevinden. In deze tutorial leert u **hoe OLE-objecten te verwijderen**, hoe **OLE**‑inhoud te **beheren**, en de exacte stappen om **OLE**‑gegevens te **wissen** wanneer ze niet meer nodig zijn. Aan het einde kunt u een projectbestand laden, de ingebedde OLE-objecten inspecteren, ze veilig verwijderen en het opgeschoonde project opslaan — allemaal met nette, leesbare C#‑code.

## Snelle antwoorden
- **Wat is de primaire manier om OLE-objecten te verwijderen?** Gebruik `project.OleObjects.Clear()` en sla vervolgens het project op.  
- **Heb ik een speciale licentie nodig?** Een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kan ik OLE‑inhoud inspecteren vóór het verwijderen?** Ja, loop door `project.OleObjects` om eigenschappen of inhoudsbytes te lezen.  
- **Is het veilig om OLE-objecten te wissen in grote projecten?** Absoluut – de bewerking is snel en heeft geen invloed op andere projectgegevens.

## Wat betekent “remove OLE objects” in de context van Aspose.Tasks?

Het verwijderen van OLE-objecten betekent het verwijderen van de ingebedde bestanden (afbeeldingen, Excel‑bladen, Word‑documenten, enz.) die opgeslagen zijn in een Microsoft Project‑bestand (.mpp). Dit is nuttig wanneer u de bestandsgrootte wilt verkleinen, verouderde verwijzingen wilt verwijderen of wilt voldoen aan gegevensbewaar‑beleid.

## Waarom OLE-objecten beheren met Aspose.Tasks?

- **Fijne controle** – Toegang tot de ID, naam en ruwe bytes van elk OLE‑object.  
- **Automatisering** – Programma’s kunnen tientallen projecten opschonen zonder ze te openen in Microsoft Project.  
- **Cross‑versie‑ondersteuning** – Werkt met Project‑bestanden van 2007‑2023.

## Voorwaarden

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

1. **Aspose.Tasks for .NET** geïnstalleerd. U kunt het downloaden van [here](https://releases.aspose.com/tasks/net/).  
2. Basiskennis van **C#** en het **.NET**‑ecosysteem.  
3. Een ontwikkelomgeving zoals **Visual Studio** (Community of hoger).  

## Namespaces importeren

Importeer eerst de namespaces die de Aspose.Tasks‑API blootleggen:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Hoe OLE-objecten te beheren – Stapsgewijze handleiding

Hieronder lopen we drie veelvoorkomende scenario's door:

1. **Inspectie van OLE-objecten** – lees hun eigenschappen en een fragment van de binaire inhoud.  
2. **Alle OLE-objecten wissen** – de kernoperatie “remove OLE objects”.  
3. **Visuele plaatsingsinformatie lezen** – nuttig wanneer u moet aanpassen hoe OLE-objecten verschijnen in Gantt of andere weergaven.

### Scenario 1: OLE-objecten inspecteren

#### Stap 1: Projectbestand laden  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Stap 2: Toegang tot OLE-objecten  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### Stap 3: Door OLE-objecten itereren  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### Stap 4: Een klein deel van de binaire inhoud ophalen (optioneel)  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### Scenario 2: Hoe OLE te wissen – alle ingebedde objecten verwijderen

#### Stap 1: Projectbestand laden  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Stap 2: OLE-objecten wissen  
```csharp
project.OleObjects.Clear();
```

#### Stap 3: Het opgeschoonde project opslaan  
```csharp
project.Save("ClearedProject.mpp");
```

> **Pro tip:** Na het wissen van OLE-objecten kunt u `project.Save` aanroepen met een andere bestandsnaam om het origineel onaangeroerd te laten.

### Scenario 3: Visuele objectplaatsingseigenschappen ophalen

#### Stap 1: Projectbestand laden  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Stap 2: Toegang tot het eerste OLE-object en de plaatsing ervan in de Gantt‑weergave  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### Stap 3: Plaatsingseigenschappen ophalen  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Veelvoorkomende valkuilen en probleemoplossing

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `project.OleObjects` is leeg | Het bron‑.mpp‑bestand bevat geen OLE‑objecten. | Controleer of het projectbestand daadwerkelijk OLE‑gegevens bevat (bijv. een bijgevoegd Excel‑blad). |
| `project.Save` geeft een uitzondering | Bestand is vergrendeld of u heeft geen schrijfrechten. | Sluit alle geopende exemplaren van het bestand en zorg dat de doelmap beschrijfbaar is. |
| Inhoudsbytes lijken corrupt | U leest de volledige byte‑array als tekst. | Gebruik `Get10Bytes` of schrijf de bytes naar een bestand om ze in een geschikte viewer te inspecteren. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks verschillende OLE‑objectformaten verwerken?**  
A: Ja, het ondersteunt afbeeldingen, Office‑documenten, PDF‑s en vele andere OLE‑formaten.

**Q: Is de API compatibel met oudere Microsoft Project‑versies?**  
A: Absoluut – Aspose.Tasks werkt met Project‑bestanden van 2007 tot en met de nieuwste 2023‑releases.

**Q: Hoe verwijder ik alleen specifieke OLE‑objecten in plaats van alles te wissen?**  
A: Zoek het gewenste `OleObject` op via zijn `Id` of `Name` en roep `project.OleObjects.Remove(oleObject)` aan vóór het opslaan.

**Q: Heeft het wissen van OLE‑objecten invloed op taakafhankelijkheden of planningen?**  
A: Nee. OLE‑objecten zijn onafhankelijke visuele elementen; het verwijderen ervan wijzigt geen taakrelaties.

**Q: Waar kan ik meer voorbeelden vinden over OLE‑manipulatie?**  
A: Bekijk de officiële Aspose.Tasks‑documentatie en de API‑referentie voor de klassen `OleObject` en `VisualObjectsPlacements`.

## Conclusie

We hebben alles behandeld wat u nodig heeft om **OLE-objecten te verwijderen** en OLE‑inhoud te beheren in Aspose.Tasks voor .NET. Door de stapsgewijze voorbeelden te volgen, kunt u OLE‑objecten inspecteren, wissen en de visuele plaatsing aanpassen, waardoor uw projectbestanden slank en gefocust blijven.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose