---
date: 2026-04-06
description: Lär dig hur du tar bort alla baslinjer och hanterar baslinjesamlingar
  i Aspose.Tasks för .NET med steg‑för‑steg kodexempel.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Ta bort alla baslinjer med Aspose.Tasks Baseline Collection
second_title: Aspose.Tasks .NET API
title: Ta bort alla baslinjer med Aspose.Tasks Baseline Collection
url: /sv/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ta bort alla baslinjer med Aspose.Tasks Baseline Collection

## Introduktion

Aspose.Tasks for .NET låter dig manipulera Microsoft Project‑filer direkt från dina .NET‑applikationer. En av de mest kraftfulla funktionerna är möjligheten att **ta bort alla baslinjer** för en resurs, vilket är viktigt när du behöver återställa ett projekts spårningsdata eller starta en ny baslinjeperiod. I den här handledningen går vi igenom hela processen – från att läsa in en projektfil till att ta bort varje baslinje som är kopplad till en specifik resurs – med tydliga, konversativa förklaringar och färdig‑att‑köra C#‑kod.

## Snabba svar
- **Vad gör “delete all baselines”?** Det tar bort varje lagrad baslinjepost för en vald resurs och rensar historisk kostnads‑ och arbetsdata.  
- **Varför skulle jag behöva detta?** För att återställa spårning efter en stor projektförändring eller när de ursprungliga baslinjerna inte längre är relevanta.  
- **Vilket bibliotek tillhandahåller denna funktion?** Aspose.Tasks för .NET.  
- **Behöver jag en licens?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.  
- **Är koden kompatibel med .NET 6+?** Ja, API:et fungerar med .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6.

## Vad är en baslinje och varför ta bort alla baslinjer?

En baslinje fångar den ursprungliga planen för kostnad, arbete och schema vid en specifik tidpunkt. Under ett projekts livslängd kan du skapa flera baslinjer (Baseline 1, Baseline 2, osv.) för att jämföra faktiskt framsteg mot olika planeringsögonblick. I vissa scenarier – såsom en omdefiniering av projektet eller en nystart – blir det förvirrande att behålla de historiska baslinjerna. Att ta bort alla baslinjer ger dig en ren start, så att du kan sätta nya baslinjer som speglar den aktuella verkligheten.

## Förutsättningar

Innan vi dyker ner i koden, se till att du har:

1. **Visual Studio** – någon recent version (Community, Professional eller Enterprise).  
2. **Aspose.Tasks for .NET** – ladda ner den från [download link](https://releases.aspose.com/tasks/net/).  
3. **Grundläggande C#‑kunskaper** – du bör vara bekväm med variabler, loopar och konsolutmatning.  
4. **En Microsoft Project‑fil** (`.mpp`) – en exempelfil med namnet *WorkWithBaselineCollection.mpp* kommer att användas i exemplen.

## Importera namnrymder

Först importerar vi de nödvändiga namnrymderna så att kompilatorn vet var klasserna vi ska använda finns.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Steg 1: Ladda projektfilen

Vi börjar med att läsa in en befintlig Project‑fil. Anpassa `DataDir` så att den pekar på mappen som innehåller din `.mpp`‑fil.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Steg 2: Hämta målresursen

För demonstration hämtar vi resursen med UID = 1. I ett verkligt scenario skulle du lokalisera resursen efter namn eller någon annan identifierare.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Steg 3: Visa befintlig baslinjeinformation

Innan du tar bort något är det bra att se vilka baslinjer som för närvarande är kopplade till resursen. Detta ger dig förtroende för att du tar bort rätt data.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Steg 4: Iterera genom alla baslinjer

Här loopar vi igenom varje baslinje och skriver ut nyckeltal som kostnad, arbete och earned value (BCWP/BCWS). Detta steg är valfritt men användbart för loggning eller revisionsändamål.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Ta bort alla baslinjer

Nu utför vi huvudåtgärden: **ta bort alla baslinjer** för den valda resursen. Vi kopierar först samlingen till en lista för att undvika att modifiera samlingen medan vi itererar, och tar sedan bort varje baslinje en efter en.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Efter att detta block har körts kommer `resource.Baselines.Count` att vara `0`, vilket bekräftar att alla baslinjeposter har rensats.

## Vanliga problem och tips

- **NullReferenceException** – Se till att projektfilen faktiskt innehåller den resurs du riktar in dig på; annars kommer `GetByUid` att returnera `null`.  
- **Licensiering** – Utan en giltig Aspose.Tasks‑licens kommer du att se ett vattenmärke i utskriften och begränsad funktionalitet.  
- **Prestanda** – För mycket stora projekt, överväg att iterera med `Parallel.ForEach` för att snabba upp borttagningsprocessen, men kom ihåg att den underliggande samlingen inte är trådsäker.

## Vanliga frågor

**Q: Kan Aspose.Tasks hantera stora projektfiler?**  
A: Ja, Aspose.Tasks är optimerat för prestanda och kan effektivt bearbeta multi‑gigabyte `.mpp`‑filer.

**Q: Är biblioteket kompatibelt med alla Microsoft Project‑versioner?**  
A: Aspose.Tasks stöder Project 2000 till Project 2024, vilket täcker både äldre `.mpp`‑format och de nyare XML‑baserade filerna.

**Q: Kan jag anpassa baslinjer innan jag tar bort dem?**  
A: Absolut. Du kan läsa eller ändra någon baslinjeegenskap (kostnad, arbete, datum) innan du bestämmer dig för att ta bort den.

**Q: Fungerar Aspose.Tasks på molnplattformar?**  
A: Ja, API:et körs i alla .NET‑kompatibla miljöer, inklusive Azure App Service, AWS Lambda (via .NET Core) och Docker‑behållare.

**Q: Var kan jag be communityn om hjälp?**  
A: Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för att komma i kontakt med andra utvecklare och Aspose‑personal.

## Slutsats

I den här guiden demonstrerade vi hur man **raderar alla baslinjer** från en resurs med Aspose.Tasks för .NET. Genom att följa den steg‑för‑steg‑koden kan du återställa baslinjedata, hålla ditt projekts spårning ren och förbereda ditt schema för en ny planeringscykel. Känn dig fri att experimentera med att skapa nya baslinjer efter borttagningen för att se hur biblioteket uppdaterar projektfilen.

---

**Senast uppdaterad:** 2026-04-06  
**Testad med:** Aspose.Tasks 24.12 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}