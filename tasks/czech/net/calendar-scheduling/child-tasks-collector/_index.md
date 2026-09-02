---
date: 2026-04-13
description: Naučte se, jak vytvořit sběrač podúkolů pomocí Aspose.Tasks pro .NET.
  Zlepšete řízení projektů ve svých .NET aplikacích.
keywords:
- create child tasks collector
- Aspose.Tasks child tasks
- .NET project management
- collect child tasks
- Aspose.Tasks API
linktitle: Vytvořit sběrač podúkolů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak vytvořit sběrač podřízených úkolů v Aspose.Tasks
url: /cs/net/calendar-scheduling/child-tasks-collector/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření sběrače podřízených úkolů v Aspose.Tasks

## Úvod

Pokud potřebujete **vytvořit sběrač podřízených úkolů** pro soubor Microsoft Project, Aspose.Tasks pro .NET to usnadňuje. V tomto tutoriálu vás provedeme přesnými kroky potřebnými k sesbírání všech podřízených úkolů pod nadřazeným úkolem, abyste je mohli s jistotou zpracovávat, analyzovat nebo exportovat. Na konci průvodce budete mít znovupoužitelný úryvek, který se přirozeně hodí do jakéhokoli .NET‑založeného řešení pro řízení projektů.

## Rychlé odpovědi
- **Co dělá ChildTasksCollector?** Prochází hierarchii úkolů a shromažďuje všechny podřízené úkoly do kolekce.  
- **Která knihovna tuto funkci poskytuje?** Aspose.Tasks pro .NET.  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut po instalaci knihovny.

## Co je sběrač podřízených úkolů?

**Sběrač podřízených úkolů** je pomocný objekt, který prochází strom úkolů souboru Project, počínaje zadaným kořenovým úkolem, a agreguje každý podřízený (sub‑task), na který narazí. To je zvláště užitečné, když chcete provádět hromadné operace — například aktualizaci polí, export dat nebo generování reportů — bez nutnosti ručně iterovat přes každou úroveň hierarchie.

## Proč vytvořit sběrač podřízených úkolů?

- **Zjednodušení rekurze:** Sběrač interně provádí průchod do hloubky, takže se vyhnete psaní vlastních rekurzivních smyček.  
- **Zvýšení produktivity:** Získáte všechny podřízené úkoly v jedné kolekci, což usnadňuje hromadné úpravy nebo analýzy.  
- **Udržení čistého kódu:** Odděluje obchodní logiku od nízkoúrovňové navigace ve struktuře projektu.

## Požadavky

Před zahájením se ujistěte, že máte:

1. **Základní znalost C#** – měli byste být schopni psát a spouštět jednoduché konzolové aplikace.  
2. **Aspose.Tasks pro .NET nainstalováno** – stáhněte jej z [download link](https://releases.aspose.com/tasks/net/).  
3. **Vývojové prostředí** – Visual Studio, Rider nebo jakékoli IDE podporující C#.  
4. **Přístup k oficiální dokumentaci** – mějte po ruce [Aspose.Tasks for .NET documentation](https://reference.aspose.com/tasks/net/) pro referenci.

Nyní, když je základ připraven, ponořme se do kódu.

## Import jmenných prostor

Nejprve přidejte požadované jmenné prostory do rozsahu, aby kompilátor věděl, kde najít třídy, které budeme používat.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## Postupný návod

### Krok 1: Inicializace objektu Project

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

Tento řádek načte existující soubor Microsoft Project (`ParentChildTasks.mpp`) ze složky `DataDir` do objektu `Project`, čímž získáme programový přístup k jeho úkolům.

### Krok 2: Vytvoření instance ChildTasksCollector

```csharp
var collector = new ChildTasksCollector();
```

Zde **vytváříme sběrač podřízených úkolů** – instanci `ChildTasksCollector`, která bude ukládat každý nalezený podřízený úkol.

### Krok 3: Použití sběrače na kořenový úkol

```csharp
TaskUtils.Apply(project.RootTask, collector, 0);
```

Řekneme Aspose.Tasks, aby zahájil sběr na kořenovém úkolu projektu. Metoda `Apply` prochází hierarchii rekurzivně a naplňuje `collector.Tasks` všemi podřízenými úkoly.

### Krok 4: Procházení sesbíraných úkolů

```csharp
foreach (var task in collector.Tasks)
{
    Console.WriteLine(task.Get(Tsk.Name));
}
```

Nakonec procházíme sesbírané úkoly a vypisujeme název každého úkolu do konzole. Ve skutečném scénáři můžete `Console.WriteLine` nahradit libovolným vlastním zpracováním (např. export do CSV, aktualizace polí atd.).

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Žádné úkoly nebyly vráceny** | Sběrač byl aplikován na nesprávný úkol (např. listový uzel). | Použijte `TaskUtils.Apply` na `project.RootTask` nebo na konkrétního nadřazeného úkolu, od kterého chcete začít. |
| **NullReferenceException** | `DataDir` nebo cesta k souboru jsou nesprávné. | Ověřte, že `DataDir` ukazuje na složku obsahující `ParentChildTasks.mpp`. |
| **Licence není nastavena** | Aspose.Tasks vyhazuje varování o licencování v režimu zkušební verze. | Načtěte licenci pomocí `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` před vytvořením objektu `Project`. |

## Často kladené otázky

**Q: Je Aspose.Tasks pro .NET kompatibilní se všemi verzemi .NET?**  
A: Ano, Aspose.Tasks pro .NET funguje s .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6+.

**Q: Mohu pomocí Aspose.Tasks pro .NET vytvořit nové soubory projektů?**  
A: Rozhodně! Knihovna vám umožní programově vytvářet, číst a manipulovat se soubory projektů.

**Q: Podporuje Aspose.Tasks pro .NET více platforem?**  
A: Přestože je navržena pro .NET, můžete ji spustit na jakékoli platformě, která podporuje .NET runtime, včetně Windows, Linuxu a macOS.

**Q: Je k dispozici technická podpora pro Aspose.Tasks pro .NET?**  
A: Ano, pomoc získáte prostřednictvím [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Můžu vyzkoušet Aspose.Tasks pro .NET před zakoupením?**  
A: Samozřejmě! Bezplatná zkušební verze je k dispozici na [release page](https://releases.aspose.com/).

---

**Poslední aktualizace:** 2026-04-13  
**Testováno s:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}