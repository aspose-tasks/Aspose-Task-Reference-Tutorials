---
date: 2026-03-24
description: Lär dig hur du ställer in beräkning i Aspose.Tasks för .NET, med exempel
  för att beräkna sammanfattningsvärden, definiera beräkningsformel och konfigurera
  rullningssammanfattning.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man ställer in beräkningstyp i Aspose.Tasks
url: /sv/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in beräkningstyp i Aspose.Tasks

## Introduktion

Om du behöver **how to set calculation** regler för uppgifter och sammanfattningsrader i en Microsoft Project‑fil, visar den här handledningen exakt det med Aspose.Tasks för .NET. Vi går igenom ett komplett **calculation type example**, demonstrerar hur man **calculate summary values**, och förklarar hur man **define calculation formula** och **configure rollup summary** för utökade attribut. I slutet kommer du att kunna lägga till en uppgift i ett projekt, ställa in anpassad beräkningslogik och kontrollera roll‑up‑beteendet med förtroende.

## Snabba svar
- **Vad är huvudsyftet?** Att kontrollera hur uppgifts‑ och sammanfattningsvärden beräknas i en Project‑fil.  
- **Vilken API‑klass används?** `ExtendedAttributeDefinition` tillsammans med `CalculationType` och `SummaryRowsCalculationType`.  
- **Kan jag använda en formel?** Ja – sätt `CalculationType = CalculationType.Formula` och ange en formelsträng.  
- **Hur rullar jag upp sammanfattningsvärden?** Använd `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` och specificera en `RollupType` såsom `Average`.  
- **Behöver jag en licens?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning.

## Vad är beräkningstyp och hur man ställer in beräkning?

`CalculationType` talar om för Aspose.Tasks hur värdet för ett utökat attribut ska beräknas. Du kan välja ett statiskt värde, en formel, eller låta biblioteket rulla upp värden från underuppgifter. Att ställa in beräkning korrekt är avgörande när du vill att projektet ska återspegla anpassade affärsregler utan manuella uppdateringar.

## Varför använda beräkningstyp för att beräkna sammanfattningsvärden?

När ett projekt innehåller sammanfattningsuppgifter behöver du ofta att sammanfattningsraderna visar aggregerad data (t.ex. total kostnad, genomsnittlig varaktighet). Genom att konfigurera **calculate summary values** via `SummaryRowsCalculationType` och `RollupType` kan Aspose.Tasks automatiskt hålla dessa aggregeringar i synk när du ändrar enskilda uppgifter.

## Förutsättningar

Innan vi börjar, se till att du har:

1. Grundläggande kunskap om C# och .NET‑ramverket.  
2. Visual Studio (valfri nyare version) installerad på din maskin.  
3. Aspose.Tasks för .NET‑biblioteket installerat – du kan ladda ner det från [here](https://releases.aspose.com/tasks/net/).  
4. Tillgång till den officiella Aspose.Tasks för .NET‑dokumentationen för referens, tillgänglig [here](https://reference.aspose.com/tasks/net/).

## Importera namnrymder

Innan du dyker ner i exemplet, se till att importera de nödvändiga namnrymderna:

```csharp
using Aspose.Tasks;
using System;
```

## Steg 1: Skapa ett nytt projekt

Först skapar vi ett tomt `Project`‑objekt som kommer att hålla våra uppgifter och anpassade attribut.

```csharp
var project = new Project();
```

## Steg 2: Lägg till en uppgift i projektet

Nu **add task project** data genom att skapa en enkel uppgift, sätta dess startdatum och ge den en dags varaktighet.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Steg 3: Definiera beräkningstyp för ett utökat attribut (Formelexempel)

Här skapar vi en definition av ett utökat attribut vars värde beräknas från en formel. Detta demonstrerar ett **calculation type example** och visar hur man **define calculation formula**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Steg 4: Definiera beräkningstyp för sammanfattningsrader (Konfigurera rollup‑sammanfattning)

Nästa steg är att skapa en annan definition av ett utökat attribut som talar om för Aspose.Tasks att **configure rollup summary** med *Average* roll‑up‑typ. Detta är det typiska sättet att **calculate summary values** för kostnad, arbete eller anpassade fält.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Vanliga problem & felsökning

| Symtom | Trolig orsak | Lösning |
|---------|--------------|-----|
| Formeln returnerar `null` | Fel fältreferens i formeln | Verifiera fältnamnet inom hakparenteser (t.ex. `[Start]` inte `[stARt]`). |
| Sammanfattningsrader visar 0 | `SummaryRowsCalculationType` inte satt eller fel `RollupType` | Se till att `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` och välj en lämplig `RollupType`. |
| Projektet går inte att ladda efter att attribut lagts till | Mismatch mellan attributdefinition och uppgiftsanvändning | Lägg till attributdefinitionen **innan** du tilldelar den till någon uppgift. |

## Slutsats

I den här handledningen har vi gått igenom **how to set calculation**‑regler i Aspose.Tasks för .NET, från att skapa en enkel uppgift till att definiera både formel‑baserade och roll‑up‑baserade beräkningstyper. Genom att behärska dessa inställningar får du fin‑granulär kontroll över **calculate summary values**, vilket möjliggör rikare projektanalys utan manuellt kalkylarksarbete.

## Vanliga frågor

### Q1: Vad är beräkningstyp i Aspose.Tasks?

A1: Beräkningstyp i Aspose.Tasks bestämmer hur värden beräknas för uppgifter och sammanfattningsuppgifter inom ett projekt, med alternativ som Formula och Rollup.

### Q2: Hur ställer jag in beräkningstyp för ett utökat attribut?

A2: Du kan ställa in beräkningstyp för ett utökat attribut genom att definiera dess `CalculationType`‑egenskap på lämpligt sätt.

### Q3: Kan jag anpassa beräkningstyp för sammanfattningsrader i ett projekt?

A3: Ja, Aspose.Tasks låter dig specificera beräkningstyp för sammanfattningsrader, så att du kan skräddarsy värdeberäkningar efter dina krav.

### Q4: Finns det olika Rollup‑typer tillgängliga för beräkning av sammanfattningsuppgifter?

A4: Ja, Aspose.Tasks erbjuder olika Rollup‑typer såsom Average, Sum och Count för att beräkna värden för sammanfattningsuppgifter.

### Q5: Var kan jag hitta fler resurser om Aspose.Tasks för .NET?

A5: Du kan utforska dokumentationen och community‑supportforum som finns på [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) för omfattande vägledning och hjälp.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}