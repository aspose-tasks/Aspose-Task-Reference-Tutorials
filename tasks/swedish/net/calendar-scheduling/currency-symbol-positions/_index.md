---
date: 2026-07-19
description: Lär dig hur du kontrollerar Currency Symbol efter belopp i .NET-projekt
  enkelt med Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Currency Symbol-positioner i Aspose.Tasks
og_description: Lär dig hur du placerar Currency Symbol efter belopp med Aspose.Tasks
  för .NET. Följ steg‑för‑steg‑instruktioner och bästa praxis.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Currency Symbol efter belopp i Aspose.Tasks — Snabbguide
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Hur du placerar Currency Symbol efter belopp i Aspose.Tasks
url: /sv/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man placerar valutasymbol efter belopp i Aspose.Tasks

## Introduktion

När du genererar projektkostnadsrapporter kan placeringen av **currency symbol after amount** påverka läsbarheten och efterlevnaden av regionala standarder. Aspose.Tasks för .NET låter dig kontrollera denna formatering med bara några rader kod, vilket säkerställer att varje finansiell siffra visas exakt som dina intressenter förväntar sig. I den här handledningen går vi igenom de nödvändiga stegen, förklarar varför inställningen är viktig och visar hur du tillämpar den i ett verkligt .NET‑projekt.

## Snabba svar
- **Vad betyder “currency symbol after amount”?** Det visar symbolen (t.ex. $) efter det numeriska värdet, som `100 $`.
- **Vilken egenskap styr positionen?** `CurrencySymbolPosition` på `Project`‑objektet.
- **Behöver jag en licens?** En provversion fungerar för utveckling; en kommersiell licens krävs för produktion.
- **Stödda valutor?** Över 50 valutor är inbyggda och täcker de flesta globala marknader.
- **Kan jag ändra inställningen vid körning?** Ja, du kan uppdatera den när som helst innan du sparar projektfilen.

## Vad är inställningen “currency symbol after amount”?

Alternativet **currency symbol after amount** bestämmer om valutasymbolen visas före eller efter det numeriska värdet i alla monetära fält i ett projekt. Att justera denna inställning säkerställer att rapporter följer lokala redovisningskonventioner utan manuell efterbehandling. Det förbättrar också läsbarheten för intressenter som är vana vid detta format.

## Varför använda Aspose.Tasks för valutformatering?

Aspose.Tasks stöder **50+ currencies** och kan hantera projekt med **10,000+ tasks** utan att ladda hela filen i minnet, vilket ger snabb prestanda även på modest hårdvara. API‑et ger dig programmatisk kontroll och eliminerar behovet av manuella kalkylbladsredigeringar. Detta gör storskalig finansiell rapportering både effektiv och pålitlig.

## Förutsättningar

### 1. Installation av Aspose.Tasks för .NET
Se till att du har Aspose.Tasks‑biblioteket installerat. Du kan ladda ner det från [here](https://releases.aspose.com/tasks/net/).

### 2. Grundläggande kunskap om .NET‑programmering
En grundläggande förståelse för .NET‑programmering är nödvändig för att följa exemplen.

## Importera namnrymder

`Aspose.Tasks`‑namnrymden ger åtkomst till `Project`‑klassen och relaterade uppräkningar.

`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild projektfil i minnet. Efter att ha importerat namnrymden kan du börja arbeta med projektdata.

```csharp

```

Nu ska vi bryta ner exemplet i tydliga, handlingsbara steg.

## Hur man ställer in valutasymbol efter belopp?

`CurrencySymbolPosition` är en uppräkning som specificerar om valutasymbolen visas före eller efter det numeriska värdet.

Läs in ditt projekt, sätt `CurrencySymbolPosition` till `After` och spara sedan – det är allt du behöver för att visa symbolen efter beloppet. Detta direkta tillvägagångssätt fungerar för alla stödda valutor och kräver ingen extra formateringslogik. Du kan också verifiera inställningen genom att exportera en exempel‑kostnadsrapport för att säkerställa att symbolen visas korrekt.

### Steg 1: Läs in projektfilen
`Project`‑klassen läser in en befintlig MS‑Project‑fil eller skapar en ny i minnet.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Steg 2: Ställ in valutasymbolens position
`CurrencySymbolPosition` är en uppräkning som låter dig välja `Before` eller `After`. Att sätta den till `After` placerar symbolen efter det numeriska värdet.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Steg 3: Arbeta med projektet
Efter att du har konfigurerat symbolens position kan du fortsätta att lägga till uppgifter, resurser eller anpassade fält efter behov. Inställningen sparas när du sparar projektet.

```csharp
// Perform other operations with the project...
```

## Vanliga problem och lösningar
- **Symbolen visas fortfarande före beloppet:** Se till att du sätter egenskapen *före* anropet till `Save`. Att ändra den efter sparning kräver att filen sparas igen.
- **Ej stödd valuta:** Verifiera att valutakoden du använder finns i Aspose.Tasks stödlista (över 50 valutor).
- **Prestandaförsämring i stora projekt:** Använd `ProjectReader` för att strömma stora filer om du överskrider 10 000 uppgifter.

## Vanliga frågor

**Q: Kan jag ändra valutasymbolens position flera gånger inom samma projekt?**  
A: Ja, du kan justera `CurrencySymbolPosition` så många gånger som behövs; sätt bara egenskapen och spara projektet igen.

**Q: Stöder Aspose.Tasks valutor förutom US Dollar?**  
A: Absolut. Aspose.Tasks stöder mer än 50 internationella valutor, vilket gör att du kan arbeta med vilket regionalt format som helst.

**Q: Finns det en provversion av Aspose.Tasks för .NET?**  
A: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från [here](https://releases.aspose.com/).

**Q: Kan jag få hjälp om jag stöter på problem när jag använder Aspose.Tasks för .NET?**  
A: Självklart! Du kan söka support och hjälp i Aspose.Tasks‑communityforum [here](https://forum.aspose.com/c/tasks/15).

**Q: Hur kan jag köpa en licens för Aspose.Tasks för .NET?**  
A: Du kan köpa en licens för Aspose.Tasks för .NET från [here](https://purchase.aspose.com/buy).

## Slutsats

Att kontrollera **currency symbol after amount** är en viktig del av finansiell rapportering i projektledningsprogramvara. Med Aspose.Tasks för .NET kan du ställa in detta alternativ programatiskt, stödja över 50 valutor och hantera stora projekt effektivt. Tillämpa stegen ovan för att säkerställa att dina projektrapporter matchar formateringsförväntningarna för vilken region som helst.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Hantera kalenderkollektion i Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Samling av kalendersundantag i Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Hantera MS Project‑priser med Aspose.Tasks för .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}