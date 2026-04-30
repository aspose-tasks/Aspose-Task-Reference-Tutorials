---
date: 2026-04-30
description: Naučte se, jak nastavit základní linii a efektivně manipulovat s projektovými
  základními liniemi pomocí Aspose.Tasks pro .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Různé typy základních plánů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak nastavit základní linii v Aspose.Tasks – Různé typy základních linií
url: /cs/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Různé typy baseline v Aspose.Tasks

## Úvod

V projektovém řízení může **jak nastavit baseline** správně rozhodnout o rozdílu mezi projektem, který zůstává na správné cestě, a tím, který se vymkne kontrole. Aspose.Tasks pro .NET vám poskytuje plnohodnotné API pro vytváření, aktualizaci a porovnávání baseline, což vám umožní **sledovat průběh projektu** oproti původnímu plánu. V tomto tutoriálu se naučíte, jak nastavit baseline, pracovat s více typy baseline a použít data k analýze **baseline vs skutečný harmonogram** vašeho projektu.

## Rychlé odpovědi
- **What is a baseline?** Snímek rozvrhu, nákladů a pracovních dat pořízený v konkrétním bodě projektu.  
- **How many baselines can Aspose.Tasks store?** Až 11 různých baseline na projekt.  
- **Why set a baseline?** Porovnat skutečný výkon s původním plánem a identifikovat odchylky.  
- **Do I need a license to try this?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je „jak nastavit baseline“ v Aspose.Tasks?
Nastavení baseline znamená zavolat metodu `SetBaseline` na objektu `Project`. API vám umožňuje vybrat z několika hodnot `BaselineType` (Baseline, Baseline1 … Baseline10), takže můžete uchovávat historické snímky během vývoje projektu.

## Proč spravovat projektové baseline?
- **Measure variance:** Rychle zjistit, zda jsou úkoly před nebo za plánem.  
- **Cost control:** Porovnat náklady baseline s skutečnými výdaji.  
- **Stakeholder reporting:** Exportovat data baseline do PDF, XLSX nebo jiných formátů pro jasnou komunikaci.  
- **Scenario planning:** Uchovávat více baseline pro vyhodnocení „co‑kdyby“ scénářů.

## Požadavky

### 1. Znalost C# a .NET Framework
Základní pochopení tříd, metod a objektově orientovaných konceptů v C# je vyžadováno.

### 2. Instalace Aspose.Tasks pro .NET
Ujistěte se, že je knihovna přidána do vašeho projektu. Můžete ji stáhnout z [webu Aspose.Tasks](https://releases.aspose.com/tasks/net/) nebo nainstalovat přes NuGet.

### 3. Integrované vývojové prostředí (IDE)
Visual Studio (nebo jakékoli kompatibilní IDE) je doporučeno pro psaní, kompilaci a ladění C# kódu.

## Importovat jmenné prostory

Než začneme pracovat s Aspose.Tasks v našem C# projektu, musíme importovat potřebné jmenné prostory pro přístup k požadovaným třídám a metodám. Postupujte podle následujících kroků:

```csharp

```

Nyní, když jsme nastavili požadavky a importovali potřebné jmenné prostory, pojďme se ponořit do nastavení různých typů baseline pomocí Aspose.Tasks pro .NET. Rozdělíme každý příklad do několika kroků pro přehlednost a snadné pochopení.

## Jak nastavit baseline v Aspose.Tasks

### Krok 1: Načíst soubor projektu
Nejprve musíme načíst soubor projektu, na který chceme nastavit baseline. Tento krok zahrnuje inicializaci objektu `Project` a načtení souboru projektu. Zde je, jak to můžete provést:

```csharp
var project = new Project("Project2.mpp");
```

### Krok 2: Nastavit baseline
Jakmile je projekt načten, můžeme pokračovat v nastavení baseline. Baseline poskytují snímek počátečního rozvrhu projektu, který slouží jako referenční bod pro porovnání během postupu projektu. Použijte metodu `SetBaseline` k nastavení baseline. Například pro nastavení baseline pro celý projekt použijte výčtový typ `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Krok 3: Práce s projektovými baseline
Po nastavení baseline můžete pracovat s různými poli projektových baseline pro přesnou analýzu a sledování postupu projektu. Tento krok zahrnuje přístup k datům baseline, jako jsou data zahájení, ukončení, trvání a náklady. Zde můžete využít bohatou sadu funkcí poskytovaných Aspose.Tasks k manipulaci s daty baseline podle vašich požadavků.

## Časté problémy a řešení
- **Baseline not applied:** Ujistěte se, že je soubor projektu uložen po zavolání `SetBaseline`. Použijte `project.Save("output.mpp");`, pokud potřebujete změny uložit.  
- **Multiple baselines conflict:** Při nastavení více než jedné baseline uveďte správný `BaselineType` (např. `Baseline1`, `Baseline2`).  
- **Version mismatch:** Ověřte, že verze Aspose.Tasks DLL odpovídá cílovému .NET runtime.

## Často kladené otázky

**Q: Mohu nastavit více baseline pro jeden projekt pomocí Aspose.Tasks pro .NET?**  
A: Ano, Aspose.Tasks umožňuje nastavit až 11 baseline pro projekt, což poskytuje komplexní sledovací možnosti.

**Q: Je Aspose.Tasks kompatibilní s různými formáty souborů projektů?**  
A: Ano! Aspose.Tasks podporuje různé formáty souborů projektů, jako jsou MPP, XML a MPX, což zajišťuje kompatibilitu napříč různými platformami.

**Q: Jak mohu vizualizovat data baseline v mém projektu?**  
A: Můžete využít Aspose.Tasks k exportu dat projektu do populárních formátů, jako je PDF nebo XLSX, což umožňuje snadnou vizualizaci a sdílení informací o baseline.

**Q: Nabízí Aspose.Tasks podporu pro integraci s nástroji pro řízení projektů?**  
A: Aspose.Tasks poskytuje rozsáhlou dokumentaci a fóra podpory, aby pomohla vývojářům bezproblémově integrovat jeho funkce s populárními nástroji a platformami pro řízení projektů.

**Q: Mohu vyzkoušet Aspose.Tasks před zakoupením?**  
A: Ano, můžete si Aspose.Tasks vyzkoušet prostřednictvím bezplatné zkušební verze dostupné na webu, což vám umožní osobně vyzkoušet jeho funkce.

---

**Poslední aktualizace:** 2026-04-30  
**Testováno s:** Aspose.Tasks for .NET (latest stable release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}