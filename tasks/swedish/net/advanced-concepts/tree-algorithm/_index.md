---
date: 2026-03-19
description: Lär dig hur du lägger till en resurs i projektet och beräknar uppgiftens
  varaktighet med Aspose.Tasks trädalgoritm, samt tilldelar resurser till uppgifter
  i .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Lägg till resurs till projekt med trädalgoritm i Aspose.Tasks
url: /sv/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till resurs i projekt med trädalgoritmen i Aspose.Tasks

## Introduktion

I den här handledningen kommer du att upptäcka **hur man lägger till resurs i projekt** genom att utnyttja den kraftfulla trädalgoritmen som levereras av Aspose.Tasks för .NET. Vi går igenom hur man skapar en uppgiftshierarki, beräknar uppgiftens varaktighet och tilldelar resurser till uppgifter — allt i ett tydligt, steg‑för‑steg‑sätt som du kan kopiera in i din egen lösning.

## Snabba svar
- **Vad gör trädalgoritmen?** Den traverserar en uppgiftshierarki för att effektivt samla arbetsvärden.  
- **Vilken primär operation täcker denna guide?** Att lägga till en resurs i ett projekt och uppdatera arbets totalsummor.  
- **Behöver jag en licens?** En tillfällig eller fullständig licens krävs för produktionsanvändning.  
- **Kan jag använda detta med .NET Core?** Ja, Aspose.Tasks stöder .NET Framework och .NET Core.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande projektfil.

## Vad betyder “add resource to project” i Aspose.Tasks?

Att lägga till en resurs i ett projekt innebär att skapa ett `Resource`‑objekt, definiera dess typ (t.ex. arbete), och länka det till en eller flera uppgifter via `ResourceAssignments`. Detta gör att schemaläggaren kan beräkna insats, kostnad och den totala projektvaraktigheten.

## Varför använda trädalgoritmen för beräkning av resursarbete?

Trädalgoritmen går igenom uppgiftsträdet en gång och samlar arbete från lövuppgifter upp till deras sammanfattningsuppgifter. Detta tillvägagångssätt är mycket mer effektivt än att iterera över varje uppgift individuellt, särskilt i stora projekt med djupa hierarkier. Det garanterar också att sammanfattningsarbetsvärden hålls i synk med sina underordnade.

## Förutsättningar

1. **Visual Studio** – någon nyligen version (2019, 2022 eller senare).  
2. **Aspose.Tasks for .NET** – ladda ner det från [här](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – du bör vara bekväm med klasser, objekt och enkel LINQ.

## Importera namnrymder

I ditt C#‑projekt importerar du de nödvändiga namnrymderna för att arbeta med Aspose.Tasks‑funktioner:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Nu ska vi bryta ner varje exempel i flera steg:

## Steg 1: Ladda projektfil

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Ladda projektfilen i minnet med hjälp av `Project`‑klassen.

## Steg 2: Definiera uppgiftshierarki

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definiera uppgiftshierarkin genom att lägga till föräldra‑ och barnuppgifter.

## Steg 3: Ställ in uppgiftsegenskaper (inklusive **calculate task duration**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Här **beräknar vi uppgiftens varaktighet** genom att konvertera arbetstimmar till ett `Duration`‑objekt och sedan härleda slutdatumet.

## Steg 4: Lägg till resurs (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Detta kodsnutt **lägger till en resurs i projektet** och **tilldelar resurser till uppgifter** så att schemaläggaren vet vem som är ansvarig för arbetet.

## Steg 5: Tillämpa trädalgoritmen

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Initiera klassen `WorkAccumulator` och tillämpa trädalgoritmen för att samla gemensamt arbete över hela hierarkin.

## Steg 6: Uppdatera uppgiftsarbete

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Uppdatera arbetsvärdena för uppgifterna baserat på den insamlade informationen.

## Vanliga problem & tips

- **Saknade kalendersinställningar:** Om slutdatumet ser felaktigt ut, se till att projektkalendern är korrekt konfigurerad innan du anropar `GetFinishDateByStartAndWork`.  
- **Resurstypmatchning:** Sätt alltid `Rsc.Type` till `ResourceType.Work` för insatsbaserade resurser; annars kan arbetsackumuleringen bli noll.  
- **Proffstips:** Efter att ha uppdaterat arbete, anropa `project.Save("UpdatedProject.mpp")` för att spara ändringarna.

## Slutsats

Genom att följa dessa steg vet du nu hur du **lägger till resurs i projekt**, **beräknar uppgiftens varaktighet** och **tilldelar resurser till uppgifter** med hjälp av Aspose.Tasks trädalgoritm. Denna metod förenklar hantering av hierarkier och håller sammanfattningsarbetsvärdena korrekta med minimal kod.

## Vanliga frågor

### Q1: Vad är Aspose.Tasks för .NET?

A1: Aspose.Tasks för .NET är ett kraftfullt API som låter utvecklare manipulera Microsoft Project‑filer programatiskt med C#.

### Q2: Kan jag ladda ner en gratis provversion av Aspose.Tasks för .NET?

A2: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks för .NET från [här](https://releases.aspose.com/).

### Q3: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?

A3: Du kan hitta dokumentationen för Aspose.Tasks för .NET [här](https://reference.aspose.com/tasks/net/).

### Q4: Hur kan jag få support för Aspose.Tasks för .NET?

A4: För support relaterad till Aspose.Tasks för .NET kan du besöka [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15).

### Q5: Finns det en tillfällig licens för teständamål?

A5: Ja, du kan skaffa en tillfällig licens för teständamål från [här](https://purchase.aspose.com/temporary-license/).

## Vanligt ställda frågor

**Q: Kan jag använda detta tillvägagångssätt med en befintlig stor projektfil?**  
A: Absolut. Trädalgoritmen fungerar på vilken `Project`‑instans som helst, oavsett storlek.

**Q: Uppdaterar algoritmen också kostnadsvärden?**  
A: Exemplet fokuserar på arbete, men du kan utöka det till kostnad genom att ackumulera `Tsk.Cost` på liknande sätt.

**Q: Vilka .NET‑versioner stöds?**  
A: Aspose.Tasks stöder .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ och .NET 6+.

**Q: Hur hanterar jag flera resurser per uppgift?**  
A: Lägg till varje resurs med `project.ResourceAssignments.Add(task, resource)`; ackumulatorn kommer automatiskt att summera deras arbete.

**Senast uppdaterad:** 2026-03-19  
**Testad med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}