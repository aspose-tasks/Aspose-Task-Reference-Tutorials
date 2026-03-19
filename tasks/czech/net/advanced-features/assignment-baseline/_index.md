---
date: 2026-03-19
description: Naučte se, jak nastavit základní linii projektu a efektivně spravovat
  základní linie přiřazení pomocí Aspose.Tasks pro .NET, což zajišťuje přesné sledování
  postupu projektu.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Nastavit projektovou základní linii – Správa základní linie přiřazení v Aspose.Tasks
url: /cs/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení projektové základní linie – Správa základních linií přiřazení v Aspose.Tasks

## Úvod

Při práci na úkolech projektového řízení je **nastavení projektové základní linie** nezbytné pro měření skutečného postupu oproti původnímu plánu. Aspose.Tasks pro .NET vám nejen umožní **nastavit projektovou základní linii**, ale také poskytuje plnou kontrolu nad základními liniemi přiřazení, což umožňuje přesné sledování výkonnosti. V tomto tutoriálu projdeme celý proces – načtení projektu, nastavení základní linie, čtení dat o základní linii přiřazení a porovnání základních linií – abyste mohli sebejistě sledovat své projekty.

## Rychlé odpovědi
- **Co znamená „nastavit projektovou základní linii“?** Zaznamená původní data o harmonogramu a nákladech pro pozdější srovnání se skutečným výkonem.  
- **Která metoda API nastavuje základní linii?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Vyžadují základní linie přiřazení samostatné volání?** Ne, jsou uloženy automaticky při nastavení projektové základní linie.  
- **Jaké formáty jsou podporovány?** MPP, XML, MPX a další prostřednictvím Aspose.Tasks.  
- **Je pro produkční použití vyžadována licence?** Ano, pro ne‑zkušební použití je potřeba komerční licence.

## Požadavky

Než začnete, ujistěte se, že máte:

- Základní znalosti programování v C#.  
- Visual Studio (libovolná aktuální verze).  
- Knihovnu Aspose.Tasks pro .NET přidanou do vašeho projektu. Můžete ji stáhnout [zde](https://releases.aspose.com/tasks/net/).  
- Přístup k projektovému souboru ve formátu MPP (např. `AssignmentBaseline2007.mpp`).

## Importujte jmenné prostory

Přidejte požadované jmenné prostory na začátek vašeho souboru C#, aby kompilátor věděl, kde najít třídy Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Krok 1: Načtení projektu a nastavení projektové základní linie

Nejprve načtěte existující soubor MPP a poté zavolejte `SetBaseline`, abyste **nastavili projektovou základní linii** pro celý projekt.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Krok 2: Načtení informací o základní linii přiřazení

Po nastavení základní linie obsahuje každé přiřazení zdroje své vlastní záznamy základní linie. Smyčka níže extrahuje a vypíše tyto podrobnosti, včetně dat zahájení/ukončení, nákladů, práce a případných časově fázovaných dat.

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

## Krok 3: Porovnání základních linií přiřazení

Můžete porovnávat základní linie různých přiřazení pomocí vestavěných operátorů rovnosti a porovnání. To je užitečné, když potřebujete zjistit posuny v harmonogramu nebo překročení nákladů mezi úkoly.

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

## Časté problémy a řešení

| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Data základní linie jsou prázdná** | Projektový soubor byl otevřen v režimu jen pro čtení nebo základní linie nebyla nikdy nastavena. | Zavolejte `project.SetBaseline(BaselineType.Baseline)` před čtením základních linií přiřazení. |
| **`NullReferenceException` u `TimephasedData`** | Ne všechny základní linie obsahují časově fázované položky. | Vždy kontrolujte `baseline.TimephasedData != null` (jak je ukázáno v kódu). |
| **Nesprávné získání UID** | Hodnoty UID se liší mezi verzemi souborů. | Použijte `ResourceAssignments.GetByUid` s správným UID nebo iterujte, abyste našli požadované přiřazení. |

## Často kladené otázky

**Q: Dokáže Aspose.Tasks zpracovat více základních linií pro jedno přiřazení?**  
A: Ano, Aspose.Tasks podporuje více základních linií pro každé přiřazení, což umožňuje komplexní sledování postupu projektu v čase.

**Q: Je Aspose.Tasks kompatibilní s různými formáty projektových souborů kromě MPP?**  
A: Ano, Aspose.Tasks podporuje širokou škálu formátů projektových souborů, včetně XML, MPX a MPP, což zajišťuje kompatibilitu s různými nástroji pro řízení projektů.

**Q: Mohu programově upravovat informace o základní linii pomocí Aspose.Tasks?**  
A: Rozhodně, Aspose.Tasks poskytuje rozsáhlé API pro dynamickou úpravu informací o základní linii podle požadavků projektu, což nabízí flexibilitu a kontrolu nad procesy řízení projektů.

**Q: Nabízí Aspose.Tasks dokumentaci a podpůrné zdroje pro vývojáře?**  
A: Ano, vývojáři mají přístup k podrobné dokumentaci, tutoriálům a fórům na webu Aspose.Tasks, což usnadňuje hladkou integraci a řešení problémů.

**Q: Existuje zkušební verze Aspose.Tasks pro .NET?**  
A: Ano, vývojáři si mohou stáhnout bezplatnou zkušební verzi Aspose.Tasks pro .NET [zde](https://releases.aspose.com/), aby mohli vyzkoušet její funkce a možnosti před rozhodnutím o koupi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-03-19  
**Testováno s:** Aspose.Tasks 24.12 pro .NET  
**Autor:** Aspose  

---