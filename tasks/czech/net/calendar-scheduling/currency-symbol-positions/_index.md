---
date: 2026-07-19
description: Zjistěte, jak snadno řídit symbol měny za částkou v .NET projektech pomocí
  Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Pozice symbolu měny v Aspose.Tasks
og_description: Zjistěte, jak umístit symbol měny za částku pomocí Aspose.Tasks pro
  .NET. Postupujte podle krok‑za‑krokem návodu a osvědčených postupů.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Symbol měny za částkou v Aspose.Tasks — Rychlý průvodce
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
title: Jak umístit symbol měny za částku v Aspose.Tasks
url: /cs/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak umístit symbol měny za částku v Aspose.Tasks

## Úvod

Když generujete zprávy o nákladech projektu, umístění **currency symbol after amount** může ovlivnit čitelnost a soulad s regionálními standardy. Aspose.Tasks pro .NET vám umožní ovládat toto formátování pomocí několika řádků kódu, což zajišťuje, že každá finanční hodnota se zobrazí přesně tak, jak očekávají vaši zainteresovaní. V tomto tutoriálu projdeme požadované kroky, vysvětlíme, proč je nastavení důležité, a ukážeme, jak jej použít v reálném .NET projektu.

## Rychlé odpovědi
- **Co znamená “currency symbol after amount”?** Zobrazuje symbol (např. $) za číselnou hodnotou, jako `100 $`.
- **Která vlastnost řídí pozici?** `CurrencySymbolPosition` na objektu `Project`.
- **Potřebuji licenci?** Zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Podporované měny?** Více než 50 měn je vestavěno, pokrývá většinu světových trhů.
- **Mohu nastavení změnit za běhu?** Ano, můžete jej aktualizovat kdykoli před uložením souboru projektu.

## Co je nastavení “currency symbol after amount”?
**currency symbol after amount** určuje, zda se znak měny zobrazí před nebo za číselnou hodnotou ve všech finančních polích projektu. Úprava tohoto nastavení zajišťuje, že zprávy odpovídají místním účetním konvencím bez ručního post‑zpracování. Také zlepšuje čitelnost pro zainteresované, kteří jsou na tento formát zvyklí.

## Proč použít Aspose.Tasks pro formátování měny?
Aspose.Tasks podporuje **více než 50 měn** a dokáže zpracovat projekty s **více než 10 000 úkoly** bez načítání celého souboru do paměti, což poskytuje vysoký výkon i na skromném hardware. API vám poskytuje programatickou kontrolu, čímž odstraňuje potřebu ručních úprav tabulek. To činí rozsáhlé finanční reportování jak efektivní, tak spolehlivé.

## Požadavky

### 1. Instalace Aspose.Tasks pro .NET
Ujistěte se, že máte nainstalovanou knihovnu Aspose.Tasks. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/net/).

### 2. Základní znalosti programování v .NET
Základní pochopení programování v .NET je nezbytné pro sledování příkladů.

## Importování jmenných prostorů

Jmenný prostor `Aspose.Tasks` poskytuje přístup ke třídě `Project` a souvisejícím výčtům.

Třída `Project` je hlavní objekt Aspose.Tasks, který představuje jeden soubor projektu v paměti. Po importování jmenného prostoru můžete začít pracovat s daty projektu.

```csharp

```

Nyní rozdělíme příklad na jasné, akční kroky.

## Jak nastavit symbol měny za částkou?

`CurrencySymbolPosition` je výčet, který určuje, zda se symbol měny zobrazí před nebo za číselnou hodnotou.

Načtěte svůj projekt, nastavte `CurrencySymbolPosition` na `After` a poté uložte – to je vše, co potřebujete k zobrazení symbolu za částkou. Tento přímý přístup funguje pro jakoukoli podporovanou měnu a nevyžaduje další logiku formátování. Nastavení můžete také ověřit exportem ukázkové zprávy o nákladech, abyste se ujistili, že se symbol zobrazuje správně.

### Krok 1: Načtení souboru projektu
Třída `Project` načte existující soubor MS‑Project nebo vytvoří nový v paměti.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Krok 2: Nastavení pozice symbolu měny
`CurrencySymbolPosition` je výčet, který vám umožňuje vybrat `Before` nebo `After`. Nastavením na `After` se symbol umístí za číselnou hodnotu.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Krok 3: Práce s projektem
Po nastavení pozice symbolu můžete pokračovat v přidávání úkolů, zdrojů nebo vlastních polí podle potřeby. Nastavení se uloží při uložení projektu.

```csharp
// Perform other operations with the project...
```

## Časté problémy a řešení
- **Symbol se stále zobrazuje před částkou:** Ujistěte se, že nastavíte vlastnost *před* voláním `Save`. Změna po uložení vyžaduje opětovné uložení souboru.
- **Není podporovaná měna:** Ověřte, že kód měny, který používáte, je uveden v seznamu podporovaných měn Aspose.Tasks (více než 50 měn).
- **Zpomalení výkonu u velkých projektů:** Použijte `ProjectReader` pro streamování velkých souborů, pokud překročíte 10 000 úkolů.

## Často kladené otázky

**Q: Mohu měnit pozici symbolu měny vícekrát v rámci jednoho projektu?**  
A: Ano, můžete upravit `CurrencySymbolPosition` tolikrát, kolik potřebujete; stačí nastavit vlastnost a projekt znovu uložit.

**Q: Podporuje Aspose.Tasks měny jiné než americký dolar?**  
A: Rozhodně. Aspose.Tasks podporuje více než 50 mezinárodních měn, což vám umožní pracovat s jakýmkoli regionálním formátem.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro .NET?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET [zde](https://releases.aspose.com/).

**Q: Můžu požádat o pomoc, pokud narazím na problémy při používání Aspose.Tasks pro .NET?**  
A: Samozřejmě! Podporu a pomoc můžete získat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Jak mohu zakoupit licenci pro Aspose.Tasks pro .NET?**  
A: Licenci pro Aspose.Tasks pro .NET můžete zakoupit [zde](https://purchase.aspose.com/buy).

## Závěr

Řízení **currency symbol after amount** je důležitou součástí finančního reportování v softwaru pro řízení projektů. S Aspose.Tasks pro .NET můžete tuto možnost nastavit programově, podporovat více než 50 měn a efektivně zpracovávat velké projekty. Použijte výše uvedené kroky, aby vaše projektové zprávy odpovídaly formátovacím očekáváním libovolného regionu.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Související tutoriály

- [Správa kolekce kalendářů v Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Kolekce výjimek kalendáře v Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Zpracování sazeb MS Project s Aspose.Tasks pro .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}