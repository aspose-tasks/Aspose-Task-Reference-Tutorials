---
title: Beräkningstyp i Aspose.Tasks
linktitle: Beräkningstyp i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du anpassar värdeberäkningar i .NET-projekt med Calculation Type i Aspose.Tasks-biblioteket.
type: docs
weight: 30
url: /sv/net/advanced-features/calculation-type/
---
## Introduktion

I den här handledningen kommer vi att utforska funktionen Beräkningstyp i Aspose.Tasks för .NET. Aspose.Tasks är ett kraftfullt bibliotek som gör det möjligt för .NET-utvecklare att arbeta med Microsoft Project-filer utan att Microsoft Project behöver installeras på sina system. Beräkningstyp låter oss definiera hur värden beräknas för uppgifter och sammanfattningsuppgifter inom ett projekt.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

1. Grundläggande kunskaper i C# och .NET framework.
2. Visual Studio installerat på ditt system.
3.  Aspose.Tasks för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
4.  Tillgång till Aspose.Tasks för .NET-dokumentation för referens, tillgänglig[här](https://reference.aspose.com/tasks/net/).

## Importera namnområden

Innan du dyker in i exemplet, se till att importera de nödvändiga namnrymden:

```csharp
using Aspose.Tasks;
using System;


```

## Steg 1: Skapa ett nytt projekt

Låt oss först skapa ett nytt projektobjekt:

```csharp
var project = new Project();
```

## Steg 2: Lägg till en uppgift

Låt oss nu lägga till en uppgift till vårt projekt:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Steg 3: Definiera beräkningstyp för ett utökat attribut

Vi skapar en utökad attributdefinition med beräkningstyp inställd på formel:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Steg 4: Definiera beräkningstyp för sammanfattningsrader

Därefter skapar vi en annan utökad attributdefinition där värden för sammanfattningsuppgifter beräknas med hjälp av den genomsnittliga sammanställningstypen:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Slutsats

I den här handledningen har vi utforskat hur man arbetar med beräkningstyp i Aspose.Tasks för .NET. Genom att definiera beräkningstyper för utökade attribut kan vi anpassa hur värden beräknas för uppgifter och sammanfattningsuppgifter inom ett projekt, vilket ger större flexibilitet och kontroll.

## FAQ's

### F1: Vad är beräkningstyp i Aspose.Tasks?

A1: Beräkningstyp i Aspose.Tasks bestämmer hur värden beräknas för uppgifter och sammanfattningsuppgifter inom ett projekt, och erbjuder alternativ som Formula och Rollup.

### F2: Hur ställer jag in beräkningstyp för ett utökat attribut?

S2: Du kan ställa in beräkningstyp för ett utökat attribut genom att definiera dess CalculationType-egenskap i enlighet med detta.

### F3: Kan jag anpassa beräkningstyp för sammanfattningsrader i ett projekt?

S3: Ja, Aspose.Tasks låter dig ange beräkningstyp för sammanfattningsrader, vilket gör att du kan skräddarsy värdeberäkningar baserat på dina krav.

### F4: Finns det olika samlade typer tillgängliga för sammanfattande uppgiftsberäkningar?

S4: Ja, Aspose.Tasks tillhandahåller olika sammanställningstyper som medelvärde, summa och antal för att beräkna värden för sammanfattningsuppgifter.

### F5: Var kan jag hitta fler resurser på Aspose.Tasks för .NET?

 S5: Du kan utforska dokumentationen och forumen för communitysupport som finns på[Aspose.Tasks för .NET](https://reference.aspose.com/tasks/net/) för omfattande vägledning och hjälp.