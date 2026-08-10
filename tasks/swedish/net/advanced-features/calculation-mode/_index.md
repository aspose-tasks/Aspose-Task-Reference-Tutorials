---
date: 2026-03-24
description: Lär dig hur du ställer in beräkningsläge i Aspose.Tasks för .NET, inklusive
  automatiskt, manuellt och inget läge för att hantera uppgiftsberoenden.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hur man ställer in beräkningsläge i Aspose.Tasks för .NET
url: /sv/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in beräkningsläge i Aspose.Tasks för .NET

## Introduktion

Aspose.Tasks for .NET är ett kraftfullt API som låter dig arbeta med Microsoft Project‑filer programatiskt. En av de viktigaste inställningarna du kommer att stöta på är **calculation mode**, som styr hur uppgiftsdatum och projektscheman uppdateras. I den här handledningen kommer du att lära dig **how to set calculation** mode, utforska **automatic calculation mode**, **manual calculation mode** och **none calculation mode**, och se hur dessa alternativ påverkar **manage task dependencies**, **create project start date** och **link tasks finish‑start**‑relationer.

## Snabba svar
- **Vad är calculation mode?** Det bestämmer om uppgiftsdatum beräknas om automatiskt, manuellt eller inte alls.  
- **Varför använda manual calculation mode?** För att få full kontroll över när schemat uppdateras, användbart vid massuppdateringar.  
- **Vilket läge är standard?** Automatic calculation mode, som uppdaterar datum omedelbart efter ändringar.  
- **Kan jag ändra läget vid körning?** Ja—sätt helt enkelt `CalculationMode`‑egenskapen på `Project`‑objektet.  
- **Behöver jag en licens?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning.

## Vad är “how to set calculation” i Aspose.Tasks?

Att ställa in beräkningsläget är så enkelt som att tilldela ett enum‑värde till `Project.CalculationMode`‑egenskapen. Enumet erbjuder tre alternativ: `Automatic`, `Manual` och `None`. Att välja rätt läge beror på ditt arbetsflöde—om du vill ha omedelbara uppdateringar, batch‑behandling eller full kontroll.

## Förutsättningar

1. **Visual Studio** – någon nyare version (2019, 2022 eller senare).  
2. **Aspose.Tasks for .NET** – ladda ner och installera biblioteket från [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – du bör vara bekväm med att skapa konsolapplikationer och använda NuGet‑paket.

## Importera namnrymder

Innan vi börjar arbeta med Aspose.Tasks för .NET, låt oss importera de nödvändiga namnrymderna:

```csharp
using Aspose.Tasks;
using System;
```

## Hur man ställer in beräkningsläge

Nedan hittar du steg‑för‑steg‑exempel för varje beräkningsläge. Kodblocken är oförändrade från den ursprungliga handledningen; de omgivande förklaringarna har utökats för tydlighet.

### Använda Automatic Calculation Mode

Automatic‑läget beräknar om datum omedelbart när du ändrar uppgifter eller länkar.

#### Steg 1: Skapa en ny Project‑instans

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Steg 2: Ställ in projektets startdatum och lägg till uppgifter

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Steg 3: Länka uppgifter (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Steg 4: Verifiera omräknade datum

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Använda Manual Calculation Mode

Manual‑läget inaktiverar automatiska uppdateringar, vilket ger dig möjlighet att batch‑processa ändringar innan du tvingar en omräkning.

#### Steg 1: Skapa en ny Project‑instans

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Steg 2: Ställ in projektets startdatum och lägg till uppgifter

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Steg 3: Verifiera uppgiftsegenskaper

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Steg 4: Länka uppgifter och verifiera datum (ingen automatisk omräkning)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Använda None Calculation Mode

None‑läget stänger av alla interna beräkningar. Använd det när du bara behöver läsa eller exportera data utan några schemaläggningsändringar.

#### Steg 1: Skapa en ny Project‑instans

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Steg 2: Lägg till en ny uppgift

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Steg 3: Verifiera uppgiftsegenskaper (inga automatiska ID:n)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| Datum uppdateras inte efter att ha länkat uppgifter | Projektet är i **Manual** eller **None**‑läge | Ställ in `project.CalculationMode = CalculationMode.Automatic` eller anropa `project.Calculate()` manuellt |
| Uppgifts‑ID:n förblir 0 | Användning av **None**‑läge förhindrar ID‑generering | Byt till **Automatic** eller **Manual**‑läge, och beräkna sedan om |
| Länkning misslyckas med `ArgumentException` | Startdatumet för föregångaren är senare än efterträdaren när **Manual**‑läge används utan omräkning | Säkerställ korrekta startdatum eller beräkna om efter att ha lagt till länkar |

## Vanliga frågor

**Q1: Kan jag ändra beräkningsläget dynamiskt under körning?**  
A1: Ja, du kan ändra `CalculationMode`‑egenskapen när som helst i din kod och sedan anropa `project.Calculate()` om du behöver en omedelbar uppdatering.

**Q2: Stöder Aspose.Tasks andra projektledningsfilformat förutom Microsoft Project?**  
A2: Aspose.Tasks fokuserar främst på Microsoft Project‑format, men stöder även Primavera P6 XML, Primavera DB och Asta Powerproject XML.

**Q3: Är Aspose.Tasks lämpligt för både småskaliga och företagsnivåprojekt?**  
A3: Absolut. API:et skalar från enkla uppgiftslistor till komplexa, flerfasiga företagsplaner.

**Q4: Kan jag integrera Aspose.Tasks med andra .NET‑bibliotek och ramverk?**  
A4: Ja, du kan kombinera Aspose.Tasks med ASP.NET, WPF, Xamarin eller någon annan .NET‑teknik för att bygga kraftfulla projektledningslösningar.

**Q5: Finns det ett community‑forum eller supportkanal för Aspose.Tasks‑användare?**  
A5: Ja, du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för community‑support och diskussioner.

**Senast uppdaterad:** 2026-03-24  
**Testad med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}