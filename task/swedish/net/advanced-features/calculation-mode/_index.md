---
title: Beräkningsläge i Aspose.Tasks
linktitle: Beräkningsläge i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar beräkningslägen effektivt i Aspose.Tasks för .NET för att effektivisera projektschemaläggning och uppgiftsberoende.
type: docs
weight: 29
url: /sv/net/advanced-features/calculation-mode/
---
## Introduktion

Aspose.Tasks för .NET är ett kraftfullt API som låter utvecklare arbeta med Microsoft Project-filer programmatiskt i sina .NET-applikationer. En avgörande aspekt av att arbeta med projektfiler är att hantera beräkningslägen, som dikterar hur uppgifter och projektscheman beräknas och uppdateras. I den här handledningen kommer vi att fördjupa oss i de olika beräkningslägen som stöds av Aspose.Tasks för .NET och visa hur man använder dem effektivt.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#-programmering: Bekanta dig med C#-programmeringskoncept.

## Importera namnområden

Innan vi börjar arbeta med Aspose.Tasks för .NET, låt oss importera de nödvändiga namnrymden:

```csharp
using Aspose.Tasks;
using System;


```

## Använder automatiskt beräkningsläge

### Steg 1: Skapa en ny projektinstans

 Initiera en ny`Project` objekt och ställ in dess`CalculationMode` egendom till`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Steg 2: Ställ in projektets startdatum och lägg till uppgifter

Definiera startdatumet för projektet och lägg till uppgifter till det.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Steg 3: Länka uppgifter

Upprätta beroenden mellan uppgifter.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Steg 4: Verifiera omräknade datum

Kontrollera om datumen har räknats om automatiskt.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Lägg till fler verifieringar efter behov
```

## Använder manuellt beräkningsläge

### Steg 1: Skapa en ny projektinstans

 Initiera en ny`Project` objekt och ställ in dess`CalculationMode` egendom till`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Steg 2: Ställ in projektets startdatum och lägg till uppgifter

Definiera startdatumet för projektet och lägg till uppgifter till det.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Steg 3: Verifiera uppgiftens egenskaper

Kontrollera om uppgiftsegenskaperna är korrekt inställda i manuellt läge.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Lägg till fler verifieringar efter behov
```

### Steg 4: Länka uppgifter och verifiera datum

Koppla samman uppgifter och kontrollera om deras datum inte räknas om.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Använder inget beräkningsläge

### Steg 1: Skapa en ny projektinstans

 Initiera en ny`Project` objekt och ställ in dess`CalculationMode` egendom till`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Steg 2: Lägg till en ny uppgift

Lägg till en ny uppgift till projektet.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Steg 3: Verifiera uppgiftens egenskaper

Kontrollera om uppgiftsegenskaperna inte beräknas automatiskt.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Lägg till fler verifieringar efter behov
```

## Slutsats

I den här handledningen har vi utforskat de beräkningslägen som är tillgängliga i Aspose.Tasks för .NET och lärt oss hur man tillämpar dem i praktiska scenarier. Oavsett om du behöver automatiskt, manuellt eller inget beräkningsläge ger Aspose.Tasks flexibiliteten för att passa ditt projekts krav.

## FAQ's

### F1: Kan jag ändra beräkningsläget dynamiskt under körning?

S1: Ja, du kan ändra beräkningsläget för ett projekt när som helst under körning genom att ändra`CalculationMode` fast egendom.

### F2: Stöder Aspose.Tasks andra filformat för projekthantering förutom Microsoft Project?

S2: Aspose.Tasks fokuserar främst på Microsoft Project-filformat, men det stöder även andra format som Primavera P6 XML, Primavera DB och Asta Powerproject XML.

### F3: Är Aspose.Tasks lämpligt för både småskaliga projekt och projekt på företagsnivå?

A3: Absolut! Aspose.Tasks är designat för att tillgodose behoven hos både småskaliga projekt och projekt på företagsnivå med dess omfattande funktioner och robusta API:er.

### F4: Kan jag integrera Aspose.Tasks med andra .NET-bibliotek och ramverk?

S4: Ja, du kan sömlöst integrera Aspose.Tasks med andra .NET-bibliotek och ramverk för att förbättra funktionaliteten i dina applikationer.

### F5: Finns det ett communityforum eller supportkanal tillgängligt för Aspose.Tasks-användare?

 A5: Ja, du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och diskussioner.