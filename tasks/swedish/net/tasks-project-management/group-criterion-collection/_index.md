---
title: Hantera MS Project Group Criteria med Aspose.Tasks
linktitle: Hantera insamling av gruppkriterier i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar Group Criterion MS Project-insamling med Aspose.Tasks för .NET. Steg-för-steg-guide för utvecklare.
weight: 28
url: /sv/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera MS Project Group Criteria med Aspose.Tasks

## Introduktion
Aspose.Tasks för .NET är ett kraftfullt API som låter utvecklare arbeta med Microsoft Project-filer programmatiskt. I den här handledningen kommer vi att utforska hur man hanterar gruppkriteriesamlingen inom MS Project med Aspose.Tasks.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1.  Aspose.Tasks för .NET: Se till att du har Aspose.Tasks-biblioteket installerat i ditt .NET-projekt. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).

2. Microsoft Project File: Ha en Microsoft Project-fil (MPP) redo att arbeta med.

## Importera namnområden

Först måste du importera de nödvändiga namnrymden till din C#-kod. Detta steg är avgörande för att få tillgång till funktionerna som tillhandahålls av Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Steg 1: Ladda projektfilen

 Initiera a`Project` objekt genom att ladda MPP-filen. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Steg 2: Åtkomstgruppskriterier

Hämta gruppen från projektet och få tillgång till dess kriterier.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Steg 3: Iterera över gruppkriterier

Gå igenom varje kriterium i gruppen och visa dess egenskaper.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Steg 4: Rensa gruppkriterier

Rensa befintliga gruppkriterier om det inte är skrivskyddat.

```csharp
group.GroupCriteria.Clear();
```

## Steg 5: Lägg till nytt kriterium

Skapa ett nytt gruppkriterium och lägg till det i gruppen.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Steg 6: Kopiera kriterier till en annan grupp

Kopiera kriterierna från en grupp till en annan.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Slutsats

I den här handledningen har vi lärt oss hur man hanterar Group Criterion MS Project-samlingen med Aspose.Tasks för .NET. Genom att följa dessa steg kan du effektivt manipulera gruppkriterier i dina Microsoft Project-filer programmatiskt.

## FAQ's

### F1: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?

S: Ja, Aspose.Tasks stöder Microsoft Project-filer i olika versioner, inklusive 2003, 2007, 2010, 2013 och 2016.

### F2: Kan jag tillämpa flera kriterier på en enda grupp?

S: Absolut, du kan lägga till flera kriterier till en grupp genom att iterera igenom varje och lägga till dem i enlighet med dem.

### F3: Finns det en testversion tillgänglig för Aspose.Tasks?

 S: Ja, du kan få en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).

### F4: Var kan jag hitta dokumentation för Aspose.Tasks?

 S: Du kan hänvisa till dokumentationen[här](https://reference.aspose.com/tasks/net/).

### F5: Hur kan jag få support om jag stöter på några problem?

 S: Om du har några frågor eller stöter på några problem kan du söka support från Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
