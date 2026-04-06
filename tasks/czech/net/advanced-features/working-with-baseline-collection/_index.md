---
date: 2026-04-06
description: Naučte se, jak odstranit všechny základní linie a spravovat kolekce základních
  linií v Aspose.Tasks pro .NET pomocí krok‑za‑krokem příkladů kódu.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Smazat všechny základní linie pomocí kolekce Baseline v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Odstranit všechny základní plány pomocí kolekce Baseline v Aspose.Tasks
url: /cs/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Smazat všechny baseline pomocí kolekce Aspose.Tasks Baseline

## Úvod

Aspose.Tasks pro .NET vám umožňuje manipulovat se soubory Microsoft Project přímo z vašich .NET aplikací. Jednou z nejvýkonnějších funkcí je schopnost **delete all baselines** pro zdroj, což je nezbytné, když potřebujete resetovat sledovací data projektu nebo zahájit nové období baseline. V tomto tutoriálu vás provedeme celým procesem – od načtení souboru projektu až po odstranění každého baseline připojeného ke konkrétnímu zdroji – pomocí jasných, konverzačních vysvětlení a připraveného kódu v C#.

## Rychlé odpovědi
- **Co dělá “delete all baselines”?** Odstraňuje každý uložený záznam baseline pro vybraný zdroj, čímž vymaže historické údaje o nákladech a práci.  
- **Proč to potřebuji?** Pro resetování sledování po zásadní změně projektu nebo když původní baseline již nejsou relevantní.  
- **Která knihovna tuto funkci poskytuje?** Aspose.Tasks pro .NET.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována platná licence Aspose.Tasks; je k dispozici bezplatná zkušební verze.  
- **Je kód kompatibilní s .NET 6+?** Ano, API funguje s .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6.

## Co je baseline a proč smazat všechny baseline?

Baseline zachycuje původní plán nákladů, práce a harmonogramu v konkrétním okamžiku. Během životnosti projektu můžete vytvořit několik baseline (Baseline 1, Baseline 2, atd.), abyste porovnávali skutečný postup s různými plánovacími snímky. Existují však situace – například přeplánování projektu nebo nový začátek – kdy udržování těchto historických baseline vede ke zmatení. Smazání všech baseline vám poskytne čistý štít, což vám umožní nastavit nové baseline, které odrážejí aktuální realitu.

## Předpoklady

1. **Visual Studio** – jakékoli nedávné vydání (Community, Professional nebo Enterprise).  
2. **Aspose.Tasks pro .NET** – stáhněte jej z [download link](https://releases.aspose.com/tasks/net/).  
3. **Základní znalost C#** – měli byste být obeznámeni s proměnnými, smyčkami a výstupem do konzole.  
4. **Soubor Microsoft Project** (`.mpp`) – ve vzorcích bude použit ukázkový soubor pojmenovaný *WorkWithBaselineCollection.mpp*.

## Importovat jmenné prostory

Nejprve přidejte potřebné jmenné prostory do rozsahu, aby kompilátor věděl, kde najít třídy, které budeme používat.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Krok 1: Načíst soubor projektu

Začneme načtením existujícího souboru Project. Upravte `DataDir`, aby ukazoval na složku, která obsahuje váš soubor `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Krok 2: Získat cílový zdroj

Pro demonstraci získáme zdroj s UID = 1. Ve skutečném scénáři byste zdroj vyhledali podle názvu nebo jiného identifikátoru.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Krok 3: Zobrazit existující informace o baseline

Před smazáním je užitečné zobrazit, jaké baseline jsou aktuálně připojeny ke zdroji. To vám dává jistotu, že odstraňujete správná data.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Krok 4: Projít všechny baseline

Zde procházíme každou baseline a vypisujeme klíčové metriky, jako jsou náklady, práce a získaná hodnota (BCWP/BCWS). Tento krok je volitelný, ale užitečný pro logování nebo audit.

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

## Smazat všechny baseline

Nyní provedeme hlavní akci: **delete all baselines** pro vybraný zdroj. Nejprve zkopírujeme kolekci do seznamu, abychom se vyhnuli úpravě kolekce během iterace, a poté odstraníme každou baseline jednu po druhé.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Po spuštění tohoto bloku bude `resource.Baselines.Count` rovno `0`, což potvrzuje, že všechny záznamy baseline byly vymazány.

## Časté problémy a tipy

- **NullReferenceException** – Ujistěte se, že soubor projektu skutečně obsahuje zdroj, který cílíte; jinak `GetByUid` vrátí `null`.  
- **Licencování** – Bez platné licence Aspose.Tasks uvidíte ve výstupu vodoznak a omezenou funkčnost.  
- **Výkon** – U velmi velkých projektů zvažte iteraci pomocí `Parallel.ForEach` pro zrychlení procesu odstraňování, ale pamatujte, že podkladová kolekce není thread‑safe.

## Často kladené otázky

**Q: Dokáže Aspose.Tasks zpracovat velké soubory projektů?**  
A: Ano, Aspose.Tasks je optimalizován pro výkon a dokáže efektivně zpracovat `.mpp` soubory o velikosti několika gigabajtů.

**Q: Je knihovna kompatibilní se všemi verzemi Microsoft Project?**  
A: Aspose.Tasks podporuje Project 2000 až po Project 2024, zahrnující jak starší formáty `.mpp`, tak novější soubory založené na XML.

**Q: Mohu upravit baseline před jejich smazáním?**  
A: Rozhodně. Můžete přečíst nebo upravit jakoukoli vlastnost baseline (náklady, práce, data), než se rozhodnete ji odstranit.

**Q: Funguje Aspose.Tasks na cloudových platformách?**  
A: Ano, API běží na jakémkoli .NET‑kompatibilním prostředí, včetně Azure App Service, AWS Lambda (přes .NET Core) a Docker kontejnerů.

**Q: Kde mohu požádat komunitu o pomoc?**  
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15), kde se můžete spojit s dalšími vývojáři a zaměstnanci Aspose.

## Závěr

V tomto průvodci jsme ukázali, jak **delete all baselines** ze zdroje pomocí Aspose.Tasks pro .NET. Dodržením krok‑za‑krokem kódu můžete resetovat data baseline, udržet sledování projektu čisté a připravit svůj harmonogram na nový plánovací cyklus. Neváhejte experimentovat s vytvářením nových baseline po smazání, abyste viděli, jak knihovna aktualizuje soubor projektu.

---

**Poslední aktualizace:** 2026-04-06  
**Testováno s:** Aspose.Tasks 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}