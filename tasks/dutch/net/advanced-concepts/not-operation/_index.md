---
title: Werken met NOT-bewerking in Aspose.Tasks
linktitle: Werken met NOT-bewerking in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u de NOT-bewerking in Aspose.Tasks voor .NET gebruikt om taken effectief te filteren. Verbeter nu uw projectmanagementmogelijkheden.
weight: 20
url: /nl/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Werken met NOT-bewerking in Aspose.Tasks

## Invoering

In deze zelfstudie onderzoeken we hoe u de NOT-bewerking in Aspose.Tasks voor .NET kunt gebruiken. Met de NOT-bewerking kunnen we een filtervoorwaarde omkeren, waardoor we elementen kunnen selecteren die niet aan een bepaald criterium voldoen.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1. Visual Studio: U hebt een werkende installatie van Visual Studio nodig om de codevoorbeelden te kunnen volgen.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van de[website](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: Bekendheid met de programmeertaal C# zal nuttig zijn bij het begrijpen van de codevoorbeelden.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten voor onze code importeren:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Project en taken instellen

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 We beginnen met het laden van een projectbestand met de naam "Project2.mpp" met behulp van de`Project` klasse aangeboden door Aspose.Tasks. Zorg ervoor dat het projectbestand in de opgegeven map bestaat.

## Stap 2: Verzamel projecttaken

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Hier creëren we een`ChildTasksCollector` object om alle taken binnen het project te verzamelen. Wij gebruiken dan`TaskUtils.Apply` methode om de takenhiërarchie van het project te doorlopen en alle onderliggende taken te verzamelen.

## Stap 3: Definieer de filtervoorwaarde

```csharp
var filter = new NullCondition();
```

 We definiëren een filtervoorwaarde met behulp van een aangepaste klasse met de naam`NullCondition`. Met deze voorwaarde worden taken geselecteerd die een nulwaarde hebben.

## Stap 4: Pas NOT-bewerking toe

```csharp
var condition = new Not<Task>(filter);
```

 We passen de NOT-bewerking toe op de filtervoorwaarde met behulp van de`Not<T>`klasse aangeboden door Aspose.Tasks. Hierdoor wordt de filtervoorwaarde omgekeerd en worden taken geselecteerd die geen nulwaarde hebben.

## Stap 5: Taken filteren

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 We filteren de verzamelde taken op basis van de toegepaste voorwaarde met behulp van een custom`Filter` methode. Deze methode gebruikt een optelbare verzameling taken en een filtervoorwaarde als invoerparameters, en retourneert een lijst met taken die aan de voorwaarde voldoen.

## Stap 6: Verwerk gefilterde taken

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Werken met andere eigenschappen...
}
```

Ten slotte doorlopen we de gefilterde taken en voeren we de gewenste bewerkingen uit. In dit voorbeeld printen we eenvoudigweg de namen van de taken naar de console.

## Conclusie

In deze tutorial hebben we geleerd hoe we met de NOT-bewerking in Aspose.Tasks voor .NET kunnen werken. Door de filtervoorwaarden om te keren, kunnen we selectief elementen kiezen die niet aan gespecificeerde criteria voldoen, waardoor onze flexibiliteit bij het manipuleren van taken binnen projecten wordt vergroot.

## Veelgestelde vragen

### V1: Kan ik Aspose.Tasks gebruiken met andere .NET-frameworks?

A: Ja, Aspose.Tasks ondersteunt verschillende .NET-frameworks, waaronder .NET Core, .NET Standard en .NET Framework.

### V2: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?

 A: Ja, u kunt een gratis proefversie downloaden van de[website](https://releases.aspose.com/).

### V3: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?

 A: U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor eventuele ondersteuningsvragen of technische assistentie.

### V4: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks?

 A: Ja, u kunt een tijdelijke licentie kopen bij de[aankooppagina](https://purchase.aspose.com/temporary-license/).

### V5: Waar kan ik uitgebreide documentatie voor Aspose.Tasks vinden?

 A: U kunt toegang krijgen tot de volledige documentatie op de[Aspose.Tasks-documentatiepagina](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
