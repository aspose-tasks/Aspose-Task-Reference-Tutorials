---
date: 2026-04-13
description: Lär dig hur du skapar en samlare för underuppgifter med Aspose.Tasks
  för .NET. Förbättra projektstyrningen i dina .NET-applikationer.
keywords:
- create child tasks collector
- Aspose.Tasks child tasks
- .NET project management
- collect child tasks
- Aspose.Tasks API
linktitle: Skapa samlare för underuppgifter i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man skapar en samlare för underuppgifter i Aspose.Tasks
url: /sv/net/calendar-scheduling/child-tasks-collector/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Child Tasks Collector i Aspose.Tasks

## Introduktion

Om du behöver **create child tasks collector** för en Microsoft Project‑fil, gör Aspose.Tasks för .NET det enkelt. I den här handledningen går vi igenom de exakta stegen som krävs för att samla alla underuppgifter under en förälder, så att du kan bearbeta, analysera eller exportera dem med förtroende. I slutet av guiden har du ett återanvändbart kodsnutt som passar naturligt in i alla .NET‑baserade projekt‑hanteringslösningar.

## Snabba svar
- **Vad gör ChildTasksCollector?** Den traverserar en uppgiftshierarki och samlar alla underordnade uppgifter i en samling.  
- **Vilket bibliotek tillhandahåller denna funktion?** Aspose.Tasks for .NET.  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter när biblioteket är installerat.

## Vad är en Child Tasks Collector?

En **child tasks collector** är ett verktygsobjekt som går igenom uppgiftsträdet i en Project‑fil, med start från en specificerad rotuppgift, och samlar varje underuppgift (sub‑task) den stöter på. Detta är särskilt användbart när du vill utföra massoperationer — såsom att uppdatera fält, exportera data eller generera rapporter — utan att manuellt iterera över varje nivå i hierarkin.

## Varför skapa en child tasks collector?

- **Förenkla rekursion:** Samlaren hanterar djup‑först‑traverseringen internt, så du undviker att skriva egna rekursiva loopar.  
- **Öka produktiviteten:** Hämta alla underordnade uppgifter i en enda samling, vilket gör massredigeringar eller analyser enkla.  
- **Behåll ren kod:** Håller din affärslogik separerad från den lågnivå‑navigering som krävs för projektstrukturen.

## Förutsättningar

1. **Grundläggande förståelse för C#** – du bör vara bekväm med att skriva och köra enkla konsolapplikationer.  
2. **Aspose.Tasks for .NET installerat** – ladda ner det från [download link](https://releases.aspose.com/tasks/net/).  
3. **En utvecklingsmiljö** – Visual Studio, Rider eller någon IDE som stödjer C#.  
4. **Tillgång till den officiella dokumentationen** – ha [Aspose.Tasks for .NET documentation](https://reference.aspose.com/tasks/net/) nära till hands för referens.

Nu när grunderna är lagda, låt oss dyka ner i koden.

## Importera namnrymder

Först, importera de nödvändiga namnrymderna så att kompilatorn vet var den kan hitta klasserna vi ska använda.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## Steg‑för‑steg‑guide

### Steg 1: Initiera Project‑objektet

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

Denna rad laddar en befintlig Microsoft Project‑fil (`ParentChildTasks.mpp`) från `DataDir`‑mappen in i ett `Project`‑objekt, vilket ger oss programmatisk åtkomst till dess uppgifter.

### Steg 2: Skapa ChildTasksCollector‑instansen

```csharp
var collector = new ChildTasksCollector();
```

Här **create child tasks collector** – en instans av `ChildTasksCollector` som kommer att lagra varje underuppgift den upptäcker.

### Steg 3: Applicera samlaren på rotuppgiften

```csharp
TaskUtils.Apply(project.RootTask, collector, 0);
```

Vi instruerar Aspose.Tasks att börja samla in från projektets rotuppgift. `Apply`‑metoden traverserar hierarkin rekursivt och fyller `collector.Tasks` med alla underordnade uppgifter.

### Steg 4: Iterera genom de insamlade uppgifterna

```csharp
foreach (var task in collector.Tasks)
{
    Console.WriteLine(task.Get(Tsk.Name));
}
```

Till sist loopar vi över de insamlade uppgifterna och skriver ut varje uppgifts namn till konsolen. I ett verkligt scenario kan du ersätta `Console.WriteLine` med någon anpassad bearbetning du behöver (t.ex. export till CSV, uppdatera fält, osv.).

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Inga uppgifter returneras** | Samlaren applicerades på fel uppgift (t.ex. ett löv). | Applicera `TaskUtils.Apply` på `project.RootTask` eller den specifika förälder du vill starta från. |
| **NullReferenceException** | `DataDir` eller filsökvägen är felaktig. | Verifiera att `DataDir` pekar på mappen som innehåller `ParentChildTasks.mpp`. |
| **License not set** | Aspose.Tasks ger en licensvarning i provläge. | Läs in din licens med `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` innan du skapar `Project`‑objektet. |

## Vanliga frågor

**Q: Är Aspose.Tasks for .NET kompatibel med alla versioner av .NET?**  
A: Ja, Aspose.Tasks for .NET fungerar med .NET Framework 4.5+, .NET Core 3.1+ och .NET 5/6+.

**Q: Kan jag använda Aspose.Tasks for .NET för att skapa nya projektfiler?**  
A: Absolut! Biblioteket låter dig skapa, läsa och manipulera projektfiler programmässigt.

**Q: Stöder Aspose.Tasks for .NET flera plattformar?**  
A: Även om det är designat för .NET, kan du köra det på vilken plattform som helst som stödjer .NET‑runtime, inklusive Windows, Linux och macOS.

**Q: Finns teknisk support för Aspose.Tasks for .NET?**  
A: Ja, du kan få hjälp via [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Kan jag prova Aspose.Tasks for .NET innan jag köper?**  
A: Självklart! En gratis provversion finns på [release page](https://releases.aspose.com/).

---

**Senast uppdaterad:** 2026-04-13  
**Testad med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}