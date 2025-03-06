---
title: Zvládnutí kritérií filtru MS Project pomocí Aspose.Tasks
linktitle: Filtrovat kritéria v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se implementovat kritéria filtru v MS Project pomocí Aspose.Tasks pro .NET. Zvyšte efektivitu projektového řízení pomocí cílené analýzy dat.
weight: 18
url: /cs/net/tasks-project-management/filter-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí kritérií filtru MS Project pomocí Aspose.Tasks

## Úvod
V oblasti projektového řízení je Microsoft Project spolehlivým nástrojem, který nabízí nepřeberné množství funkcí, které pomáhají projektantům a manažerům. Mezi jeho mnoha funkcemi patří schopnost filtrovat data projektu, což uživatelům umožňuje soustředit se na konkrétní aspekty úkolů jejich projektu. Zvládnutí těchto možností filtrování však může být bez správného vedení skličujícím úkolem. Tento tutoriál si klade za cíl demystifikovat proces poskytnutím podrobného průvodce implementací kritérií filtru v MS Project pomocí Aspose.Tasks for .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Základní porozumění C#: Pro pochopení pojmů obsažených v tomto tutoriálu je nezbytná znalost programovacího jazyka C#.
2.  Instalace Aspose.Tasks for .NET: Ujistěte se, že máte Aspose.Tasks for .NET nainstalované ve svém vývojovém prostředí. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
3. Soubor Microsoft Project: Připravte si soubor Microsoft Project (např. Project2003.mpp), který použijete pro implementaci kritérií filtru.

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro práci s Aspose.Tasks for .NET. Následuj tyto kroky:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Krok 1: Načtěte soubor projektu
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Vysvětlení: Tento řádek kódu inicializuje novou instanci souboru`Project` třídy a načte soubor Microsoft Project určený jeho cestou.
## Krok 2: Načtěte filtr úloh
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Vysvětlení: Zde načteme filtr úloh z projektu. Upravte index (`[1]`) podle vašeho požadavku vyberte požadovaný filtr.
## Krok 3: Zobrazte řádky kritérií
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Vysvětlení: Tato část prochází každý řádek kritérií filtru a zobrazuje jeho pole, operaci, test a hodnoty (pokud existují).
## Krok 4: Tisk kritérií filtru
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Vysvětlení: Vytiskne operaci kritérií filtru.
## Krok 5: Zobrazení podrobností kritérií
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Vysvětlení: Tato část načítá a zobrazuje podrobné informace o každém řádku kritérií a poskytuje přehled o konfiguraci filtru.

## Závěr
Zvládnutí kritérií filtru v MS Project pomocí Aspose.Tasks for .NET je cenná dovednost, která může výrazně zvýšit efektivitu řízení projektů. Podle tohoto kurzu jste se naučili, jak programově manipulovat s kritérii filtru, což vám umožňuje přizpůsobit zobrazení projektu vašim konkrétním potřebám.
## FAQ
### Otázka: Mohu v MS Project použít více filtrů současně?
Odpověď: Ano, můžete kombinovat více filtrů a dále zpřesnit data projektu.
### Otázka: Podporuje Aspose.Tasks starší verze souborů Microsoft Project?
Odpověď: Ano, Aspose.Tasks poskytuje zpětnou kompatibilitu a umožňuje vám pracovat s různými verzemi souborů Microsoft Project.
### Otázka: Je Aspose.Tasks kompatibilní s jinými frameworky .NET?
Odpověď: Aspose.Tasks podporuje .NET Framework, .NET Core a .NET Standard, což zajišťuje flexibilitu napříč různými vývojovými prostředími.
### Otázka: Mohu přizpůsobit kritéria filtru na základě dynamických podmínek?
Odpověď: Kritéria filtru můžete programově upravit na základě dynamických parametrů, což umožňuje adaptivní analýzu dat projektu.
### Otázka: Kde mohu vyhledat pomoc, pokud narazím na problémy s Aspose.Tasks?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) hledat podporu od komunity nebo přímo kontaktovat Aspose.Tasks podporu pro personalizovanou pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
