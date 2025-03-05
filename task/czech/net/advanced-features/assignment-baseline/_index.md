---
title: Správa základního plánu přiřazení v Aspose.Tasks
linktitle: Správa základního plánu přiřazení v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat základní linie zadání pomocí Aspose.Tasks pro .NET, což zajišťuje přesné sledování průběhu a výkonu projektu.
type: docs
weight: 14
url: /cs/net/advanced-features/assignment-baseline/
---
## Úvod

Při práci na úkolech projektového řízení je pro přesné sledování pokroku zásadní řízení výchozích linií přiřazení. Aspose.Tasks for .NET poskytuje komplexní sadu nástrojů pro efektivní zpracování základních linií přiřazení. V tomto tutoriálu se krok za krokem ponoříme do procesu správy základních linií přiřazení.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Visual Studio nainstalované ve vašem systému.
- Do vašeho projektu byla přidána knihovna Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
- Přístup k souboru projektu ve formátu MPP.

## Importovat jmenné prostory

Chcete-li začít pracovat s Aspose.Tasks, musíte do svého projektu C# importovat potřebné jmenné prostory. Na začátek souboru C# přidejte následující jmenné prostory:

```csharp
using Aspose.Tasks;
using System;


```

## Krok 1: Načtěte projekt a nastavte základní plán

 Nejprve načtěte soubor projektu pomocí`Project` třídy z Aspose.Tasks. Poté nastavte typ výchozího plánu pro projekt pomocí`SetBaseline` metoda.

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Krok 2: Přečtěte si informace o základním plánu přiřazení

Projděte každé přiřazení zdrojů v projektu a načtěte základní informace pro každé přiřazení.

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

## Krok 3: Zkontrolujte základní rovnost

Porovnejte základní informace pro různá přiřazení pomocí různých porovnávacích metod poskytovaných Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Zkontrolujte základní rovnost
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Zkontrolujte základní srovnání
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Zobrazit základní hashkódy
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Závěr

Správa základních linií přiřazení je nedílnou součástí projektového řízení a umožňuje přesné sledování postupu a výkonu. S Aspose.Tasks for .NET se manipulace se základními liniemi přiřazení zjednoduší a zefektivní a poskytuje vývojářům výkonné nástroje pro zlepšení pracovních postupů projektového řízení.

## FAQ

### Q1: Může Aspose.Tasks zpracovat více směrných plánů pro jeden úkol?

Odpověď 1: Ano, Aspose.Tasks podporuje více směrných plánů pro každé zadání, což umožňuje komplexní sledování průběhu projektu v průběhu času.

### Q2: Je Aspose.Tasks kompatibilní s různými formáty souborů projektu jinými než MPP?

Odpověď 2: Ano, Aspose.Tasks podporuje širokou škálu formátů souborů projektu, včetně XML, MPX a MPP, což zajišťuje kompatibilitu s různými nástroji pro správu projektů.

### Q3: Mohu upravit informace podle směrného plánu programově pomocí Aspose.Tasks?

A3: Absolutně, Aspose.Tasks poskytuje rozsáhlá rozhraní API pro dynamickou úpravu základních informací podle požadavků projektu a nabízí flexibilitu a kontrolu nad procesy projektového řízení.

### Q4: Nabízí Aspose.Tasks dokumentaci a zdroje podpory pro vývojáře?

Odpověď 4: Ano, vývojáři mají přístup ke komplexní dokumentaci, výukovým programům a fórům na webu Aspose.Tasks, což usnadňuje hladkou integraci a odstraňování problémů.

### Q5: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?

 A5: Ano, vývojáři mohou získat bezplatnou zkušební verzi Aspose.Tasks for .NET od[tady](https://releases.aspose.com/), což jim umožňuje vyhodnotit jeho vlastnosti a možnosti před rozhodnutím o koupi.