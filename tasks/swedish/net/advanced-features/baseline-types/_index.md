---
date: 2026-04-30
description: Lär dig hur du sätter en baslinje och manipulerar projektbaslinjer effektivt
  med Aspose.Tasks för .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Olika typer av baslinjer i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man sätter baslinje i Aspose.Tasks – Olika baslinjetyper
url: /sv/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Olika typer av baslinjer i Aspose.Tasks

## Introduktion

Inom projektledning kan **how to set baseline** korrekt göra skillnaden mellan ett projekt som håller sig på rätt spår och ett som spårar ur kontroll. Aspose.Tasks för .NET ger dig ett full‑featured API för att skapa, uppdatera och jämföra baslinjer, så att du kan **track project progress** mot den ursprungliga planen. I den här handledningen kommer du att lära dig hur du sätter en baslinje, arbetar med flera baslinjetyper och använder data för att analysera **baseline vs actual schedule** för ditt projekt.

## Snabba svar
- **What is a baseline?** En ögonblicksbild av schema, kostnad och arbetsdata som tas vid en specifik tidpunkt i ett projekt.  
- **How many baselines can Aspose.Tasks store?** Upp till 11 olika baslinjer per projekt.  
- **Why set a baseline?** För att jämföra faktisk prestation med den ursprungliga planen och identifiera avvikelser.  
- **Do I need a license to try this?** En gratis provversion finns tillgänglig; en licens krävs för produktionsanvändning.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “how to set baseline” i Aspose.Tasks?
Att sätta en baslinje innebär att anropa `SetBaseline`-metoden på ett `Project`-objekt. API:et låter dig välja mellan flera `BaselineType`-värden (Baseline, Baseline1 … Baseline10) så att du kan behålla historiska ögonblicksbilder när projektet utvecklas.

## Varför hantera projektbaslinjer?
- **Measure variance:** Se snabbt om uppgifter ligger före eller efter schemat.  
- **Cost control:** Jämför baslinjekostnad med faktiska utgifter.  
- **Stakeholder reporting:** Exportera baslinjedata till PDF, XLSX eller andra format för tydlig kommunikation.  
- **Scenario planning:** Spara flera baslinjer för att utvärdera “what‑if”-scheman.

## Förutsättningar

### 1. Bekantskap med C# och .NET Framework
En grundläggande förståelse för C#-klasser, metoder och objektorienterade koncept krävs.

### 2. Installation av Aspose.Tasks för .NET
Se till att biblioteket är tillagt i ditt projekt. Du kan ladda ner det från [Aspose.Tasks website](https://releases.aspose.com/tasks/net/) eller installera det via NuGet.

### 3. Integrerad utvecklingsmiljö (IDE)
Visual Studio (eller någon kompatibel IDE) rekommenderas för att skriva, kompilera och felsöka C#-kod.

## Importera namnrymder

Innan vi börjar arbeta med Aspose.Tasks i vårt C#-projekt måste vi importera de nödvändiga namnrymderna för att komma åt de erforderliga klasserna och metoderna. Följ dessa steg:

```csharp

```

Nu när vi har ställt in våra förutsättningar och importerat de nödvändiga namnrymderna, låt oss dyka in i att sätta olika typer av baslinjer med Aspose.Tasks för .NET. Vi kommer att dela upp varje exempel i flera steg för tydlighet och lättförståelighet.

## Så sätter du en baslinje i Aspose.Tasks

### Steg 1: Ladda projektfilen
Först måste vi ladda projektfilen som vi avser att sätta baslinjen på. Detta steg innebär att initiera ett `Project`-objekt och ladda projektfilen. Så här kan du göra det:

```csharp
var project = new Project("Project2.mpp");
```

### Steg 2: Sätt baslinje
När projektet är laddat kan vi gå vidare och sätta baslinjen. Baslinjer ger en ögonblicksbild av projektets ursprungliga schema, vilket fungerar som en referenspunkt för jämförelse när projektet fortskrider. Använd `SetBaseline`-metoden för att sätta baslinjen. Till exempel, för att sätta baslinjen för hela projektet, använd `BaselineType.Baseline`-enumerationen:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Steg 3: Arbeta med projektbaslinjer
Efter att ha satt baslinjen kan du arbeta med olika projektbaslinjefält för att analysera och spåra projektets framsteg exakt. Detta steg innebär att komma åt baslinjedata såsom startdatum, slutdatum, varaktigheter och kostnader. Här kan du utnyttja det omfattande funktionsutbudet som Aspose.Tasks tillhandahåller för att manipulera baslinjedata enligt dina krav.

## Vanliga problem och lösningar
- **Baseline not applied:** Se till att projektfilen sparas efter att `SetBaseline` har anropats. Använd `project.Save("output.mpp");` om du behöver behålla ändringarna.  
- **Multiple baselines conflict:** När du sätter mer än en baslinje, ange rätt `BaselineType` (t.ex. `Baseline1`, `Baseline2`).  
- **Version mismatch:** Verifiera att Aspose.Tasks DLL-versionen matchar den målade .NET-runtime.

## Vanliga frågor

**Q: Kan jag sätta flera baslinjer för ett enda projekt med Aspose.Tasks för .NET?**  
A: Ja, Aspose.Tasks låter dig sätta upp till 11 baslinjer för ett projekt, vilket ger omfattande spårningsmöjligheter.

**Q: Är Aspose.Tasks kompatibel med olika projektfilformat?**  
A: Absolut! Aspose.Tasks stöder olika projektfilformat såsom MPP, XML och MPX, vilket säkerställer kompatibilitet över olika plattformar.

**Q: Hur kan jag visualisera baslinjedata i mitt projekt?**  
A: Du kan använda Aspose.Tasks för att exportera projektdata till populära filformat som PDF eller XLSX, vilket möjliggör enkel visualisering och delning av baslinjeinformation.

**Q: Erbjuder Aspose.Tasks stöd för integration med projektledningsverktyg?**  
A: Aspose.Tasks tillhandahåller omfattande dokumentation och supportforum för att hjälpa utvecklare att sömlöst integrera dess funktioner med populära projektledningsverktyg och plattformar.

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: Ja, du kan utforska Aspose.Tasks genom en gratis provversion som finns på webbplatsen, så att du kan uppleva dess funktioner direkt.

**Last Updated:** 2026-04-30  
**Tested With:** Aspose.Tasks for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}