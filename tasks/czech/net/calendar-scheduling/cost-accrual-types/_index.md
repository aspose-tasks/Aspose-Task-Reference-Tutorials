---
date: 2026-07-05
description: Zjistěte, jak sledovat rozpočet projektu a spravovat náklady projektu
  pomocí Aspose.Tasks pro .NET. Definujte cost accrual types pro přesné sledování
  nákladů.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Sledujte rozpočet projektu pomocí Cost Accrual Types v Aspose.Tasks
url: /cs/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sledujte rozpočet projektu pomocí typů nákladových akruací v Aspose.Tasks

## Úvod

Přesné **sledování rozpočtu projektu** je základem úspěšného dodání projektu. Když jsou informace o nákladech zachyceny ve správných okamžicích, můžete předpovídat překročení rozpočtu, upravit zdroje a informovat zainteresované strany. Aspose.Tasks pro .NET poskytuje vývojářům detailní kontrolu nad akumulací nákladů, což vám umožní rozhodnout *kdy* je náklad zaznamenán — ať už na začátku práce, průběžně, nebo jen po dokončení práce. Tento tutoriál vás provede koncepty, ukáže, jak nastavit typ akumulace, a představí osvědčené postupy pro spolehlivé sledování rozpočtu.

## Rychlé odpovědi
- **Jaký je hlavní účel typů akumulace nákladů?** Určují okamžik v životním cyklu úkolu, kdy jsou náklady uznány, což umožňuje přesné sledování rozpočtu.  
- **Která hodnota výčtu odkládá náklady až do dokončení práce?** `CostAccrualType.End`.  
- **Potřebuji licenci pro spuštění kódu?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu změnit typy akumulace pro více zdrojů najednou?** Ano — projděte kolekci `Resources` a přiřaďte požadovaný typ.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je typ akumulace nákladů?
Typ **akumulace nákladů** říká Aspose.Tasks, kdy použít náklad zdroje na rozpočet projektu. Je reprezentován výčtem `CostAccrualType` a může být nastaven na úrovni zdroje nebo úkolu. Výběr správného typu zajišťuje, že data o nákladech odpovídají fakturační politice vaší organizace, ať už potřebujete náklady zaznamenávat na začátku práce, poměrně během trvání, nebo jen po dokončení.

## Proč sledovat rozpočet projektu pomocí typů akumulace nákladů?
Aspose.Tasks podporuje **čtyři** možnosti akumulace — `Start`, `Prorated`, `Duration` a `End` — pokrývající celý rozsah typických scénářů projektového účetnictví. Výběrem vhodné možnosti můžete sladit uznání nákladů s fakturačními cykly, snížit odchylky ve finančních zprávách a generovat výkazy nákladů, které se hladce integrují s ERP systémy, a to vše při nízké spotřebě paměti u velkých projektů.

## Požadavky

Než začneme, ujistěte se, že máte následující požadavky:

### 1. Nainstalujte Aspose.Tasks pro .NET
Pro zahájení potřebujete mít Aspose.Tasks pro .NET nainstalovaný ve vašem vývojovém prostředí. Knihovnu můžete stáhnout ze [stránky ke stažení](https://releases.aspose.com/tasks/net/) a postupovat podle poskytnutých instalačních instrukcí.

### 2. Znalost .NET Framework
Základní znalost .NET frameworku a programovacího jazyka C# je vyžadována pro sledování příkladů v tomto tutoriálu.

## Jak nastavit typ akumulace nákladů pro zdroj?

Načtěte projekt, najděte cílový zdroj a přiřaďte požadovaný `CostAccrualType`. Níže uvedený dvouřádkový vzor je standardní přístup: vytvořte instanci `Project`, načtěte zdroj podle jeho ID a poté nastavte `CostAccrualType`. Tento stručný postup zajišťuje, že **sledujete rozpočet projektu** přesně od okamžiku, kdy je zdroj přidán.

### Krok 1: Importovat jmenné prostory
Let's start by importing the necessary namespaces to access Aspose.Tasks functionality in our .NET project:

```csharp

```

Now that we have the namespaces ready, we can move on to loading a project file.

### Krok 2: Načíst soubor projektu
The `Project` class represents a Microsoft Project file and provides access to its tasks, resources, and other data.

```csharp
var project = new Project("Project2.mpp");
```

First, we need to load the project file into our application. We create a new `Project` object and initialize it with the path to our project file.

### Krok 3: Přístup ke zdroji
The `Resources` collection holds all resources defined in the project. The `GetById` method retrieves a resource by its unique identifier.

```csharp
var resource = project.Resources.GetById(1);
```

Next, we access the resource to which we want to apply the cost accrual type. We use the `GetById` method of the `Resources` collection and pass the resource ID as an argument. This demonstrates **přístup ke zdroji podle id**, a common requirement when automating cost updates.

### Krok 4: Nastavit typ akumulace nákladů
The `Set` method assigns a value to a resource field.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Here, we set the cost accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`, which means costs will not be accrued until remaining work is zero. Choosing `End` is ideal when you want to **sledovat rozpočet projektu** only after a task is fully completed.

### Krok 5: Pokračovat v práci s projektem
After setting the cost accrual type, you can continue working with the project as needed, performing additional operations or calculations such as generating cost reports, updating assignments, or exporting the file.

## Časté úskalí a tipy profesionálů
- **Tip:** Vždy zavolejte `project.Save` po úpravě typů akumulace, aby se změny uložily.  
- **Úskalí:** Nastavení `CostAccrualType.Start` na zdroj, který nikdy nezačne pracovat, způsobí nadhodnocení rozpočtových zpráv — nejprve ověřte plány úkolů.  
- **Tip:** Použijte `project.Resources.ToList()`, když potřebujete hromadně aktualizovat mnoho zdrojů; tím se vyhnete opakovaným vyhledáváním v kolekci a zlepšíte výkon u velkých projektů.

## Často kladené otázky

**Q: Mohu změnit typ akumulace nákladů pro více zdrojů najednou?**  
A: Ano, projděte `project.Resources` a přiřaďte požadovaný `CostAccrualType` každému zdroji ve smyčce `foreach`.

**Q: Jaké jsou další dostupné typy akumulace nákladů kromě `End`?**  
A: Aspose.Tasks poskytuje `Start`, `Prorated` a `Duration` — každý odpovídá jiné fakturační strategii.

**Q: Jak mohu zjistit aktuální typ akumulace nákladů pro konkrétní zdroj?**  
A: Získejte hodnotu pomocí `resource.Get(TskResource.CostAccrualType)`; vrací výčet představující aktuální nastavení.

**Q: Je možné aplikovat různé typy akumulace nákladů na různé úkoly ve stejném projektu?**  
A: Rozhodně. Jak úkoly, tak zdroje mají vlastnost `CostAccrualType`, což umožňuje nezávislé nastavení pro každou entitu.

**Q: Podporuje Aspose.Tasks vlastní typy akumulace nákladů?**  
A: Ne, knihovna v současnosti podporuje pouze čtyři vestavěné typy; vlastní logiku je třeba implementovat externě, pokud je potřeba.

---

**Poslední aktualizace:** 2026-07-05  
**Testováno s:** Aspose.Tasks 24.8 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Kalendář a plánování v Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Zpracování sazeb MS Project s Aspose.Tasks pro .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Jednoduchá správa zdrojů MS Project s Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}