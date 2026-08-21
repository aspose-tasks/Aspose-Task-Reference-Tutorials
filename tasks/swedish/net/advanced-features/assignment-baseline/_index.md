---
date: 2026-03-19
description: Lär dig hur du ställer in projektbaslinje och hanterar uppdragsbaslinjer
  effektivt med Aspose.Tasks för .NET, vilket säkerställer exakt spårning av projektets
  framsteg.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ange projektbaslinje – Hantera uppdragsbaslinje i Aspose.Tasks
url: /sv/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in projektbaslinje – Hantera tilldelningsbaslinje i Aspose.Tasks

## Introduktion

När du arbetar med projektledningsuppgifter är **att ställa in en projektbaslinje** avgörande för att mäta faktisk framsteg mot den ursprungliga planen. Aspose.Tasks för .NET låter dig inte bara **ställa in projektbaslinje** utan ger dig också full kontroll över tilldelningsbaslinjer, vilket möjliggör exakt prestationsspårning. I den här handledningen går vi igenom hela processen — att läsa in ett projekt, ställa in en baslinje, läsa tilldelningsbaslinjedata och jämföra baslinjer — så att du kan övervaka dina projekt med självförtroende.

## Snabba svar
- **Vad betyder “set project baseline”?** Det registrerar den ursprungliga tidsplanen och kostnadsdata för senare jämförelse med faktisk prestation.  
- **Vilken API‑metod ställer in en baslinje?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Kräver tilldelningsbaslinjer ett separat anrop?** Nej, de lagras automatiskt när du ställer in en projektbaslinje.  
- **Vilka format stöds?** MPP, XML, MPX och fler via Aspose.Tasks.  
- **Krävs en licens för produktion?** Ja, en kommersiell licens behövs för icke‑testanvändning.

## Förutsättningar

Innan vi börjar, se till att du har:

- Grundläggande kunskap i C#‑programmering.  
- Visual Studio (någon nyare version).  
- Aspose.Tasks för .NET‑biblioteket tillagt i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/tasks/net/).  
- Tillgång till en projektfil i MPP‑format (t.ex. `AssignmentBaseline2007.mpp`).

## Importera namnrymder

Lägg till de nödvändiga namnrymderna högst upp i din C#‑fil så att kompilatorn vet var den ska hitta Aspose.Tasks‑klasserna.

```csharp
using Aspose.Tasks;
using System;
```

## Steg 1: Läs in projekt och ställ in projektbaslinje

Först läser du in den befintliga MPP‑filen och anropar sedan `SetBaseline` för att **ställa in projektbaslinje** för hela projektet.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Steg 2: Läs tilldelningsbaslinjeinformation

Efter att baslinjen har ställts in innehåller varje resurs‑tilldelning sina egna baslinjeposter. Loopen nedan extraherar och skriver ut dessa detaljer, inklusive start-/slutdatum, kostnad, arbete och eventuell tidsfasad data.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Steg 3: Jämför tilldelningsbaslinjer

Du kan jämföra baslinjer för olika tilldelningar med de inbyggda likhets‑ och jämförelseoperatorerna. Detta är praktiskt när du behöver upptäcka schemaförskjutningar eller kostnadsöverskridanden mellan uppgifter.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Baslinjedata visas tom** | Projektfilen öppnades i skrivskyddat läge eller baslinjen sattes aldrig. | Anropa `project.SetBaseline(BaselineType.Baseline)` innan du läser tilldelningsbaslinjer. |
| **`NullReferenceException` on `TimephasedData`** | Inte alla baslinjer innehåller tidsfasade poster. | Kontrollera alltid `baseline.TimephasedData != null` (som visas i koden). |
| **Felaktig UID‑hämtning** | UID‑värden skiljer sig mellan filversioner. | Använd `ResourceAssignments.GetByUid` med rätt UID eller iterera för att hitta den tilldelning du behöver. |

## Vanliga frågor

**Q: Kan Aspose.Tasks hantera flera baslinjer för en enskild tilldelning?**  
A: Ja, Aspose.Tasks stöder flera baslinjer för varje tilldelning, vilket möjliggör omfattande spårning av projektets framsteg över tid.

**Q: Är Aspose.Tasks kompatibel med olika projektfilformat förutom MPP?**  
A: Ja, Aspose.Tasks stödjer ett brett spektrum av projektfilformat, inklusive XML, MPX och MPP, vilket säkerställer kompatibilitet med olika projektledningsverktyg.

**Q: Kan jag modifiera baslinjeinformation programatiskt med Aspose.Tasks?**  
A: Absolut, Aspose.Tasks tillhandahåller omfattande API:er för att dynamiskt ändra baslinjeinformation enligt projektkrav, vilket ger flexibilitet och kontroll över projektledningsprocesser.

**Q: Erbjuder Aspose.Tasks dokumentation och supportresurser för utvecklare?**  
A: Ja, utvecklare kan få tillgång till omfattande dokumentation, handledningar och forum på Aspose.Tasks‑webbplatsen, vilket underlättar smidig integration och felsökning.

**Q: Finns en provversion tillgänglig för Aspose.Tasks för .NET?**  
A: Ja, utvecklare kan få en gratis provversion av Aspose.Tasks för .NET från [här](https://releases.aspose.com/), vilket låter dem utvärdera dess funktioner och möjligheter innan de fattar ett köpbeslut.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-03-19  
**Testat med:** Aspose.Tasks 24.12 för .NET  
**Författare:** Aspose