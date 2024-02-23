---
title: Správa kódů osnovy projektu v Aspose.Tasks pro .NET
linktitle: Správa kódů osnovy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se spravovat osnovy MS Project kódy pomocí Aspose.Tasks pro .NET. Zjednodušte organizaci projektu bez námahy.
type: docs
weight: 10
url: /cs/net/outline-code-page-settings/outline-codes/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak spravovat obrysové kódy Microsoft Project pomocí Aspose.Tasks for .NET. Kódy osnovy jsou vlastní pole v aplikaci Microsoft Project, která uživatelům umožňují kategorizovat a organizovat úkoly podle konkrétních kritérií. Aspose.Tasks zjednodušuje proces čtení a manipulaci s těmito kódy osnovy programově.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Aspose.Tasks for .NET Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[webová stránka](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Nastavte vhodné vývojové prostředí pro programování .NET, jako je Visual Studio.
3. Základní znalost C#: Pro pochopení příkladů kódu bude přínosem znalost programovacího jazyka C#.

## Import jmenných prostorů
Chcete-li začít, musíte do projektu C# importovat potřebné jmenné prostory. To vám umožní přístup ke třídám a metodám poskytovaným knihovnou Aspose.Tasks.
1. Otevřete Visual Studio: Spusťte své IDE sady Visual Studio.
2. Vytvořit nový projekt: Spusťte nový projekt C# nebo otevřete existující, kde hodláte použít Aspose.Tasks.
3. Přidat referenci Aspose.Tasks: Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení, vyberte „Spravovat balíčky NuGet“, vyhledejte „Aspose.Tasks“ a nainstalujte nejnovější verzi.
4. Import jmenného prostoru Aspose.Tasks: V horní části souboru C# přidejte následující příkaz pomocí:
```csharp
using Aspose.Tasks;
using System;

```
## Krok 1: Definujte adresář dokumentů
Nejprve nastavte cestu k adresáři obsahujícímu váš soubor MS Project.
```csharp
String DataDir = "Your Document Directory";
```
 nahradit`"Your Document Directory"` se skutečnou cestou k souboru vašeho projektu.
## Krok 2: Načtěte soubor projektu
 Vytvořte nový`Project` objekt načtením souboru MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Tím se inicializuje objekt projektu se zadaným souborem.
## Krok 3: Přečtěte si obrysové kódy
Projděte všechny úkoly v projektu a načtěte jejich obrysové kódy.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Tento fragment kódu prochází každou úlohou, kontroluje, zda obsahuje kódy osnovy, a vytiskne podrobnosti, jako je ID pole, guid hodnoty a ID hodnoty pro každý kód osnovy spojený s úlohou.

## Závěr
Závěrem lze říci, že Aspose.Tasks for .NET poskytuje výkonné funkce pro programovou správu kódů osnovy Microsoft Project. Podle kroků uvedených v tomto kurzu můžete efektivně číst a manipulovat s kódy osnovy v souborech MS Project pomocí C#.
## FAQ
### Otázka: Mohu upravit kódy osnovy pomocí Aspose.Tasks?
Odpověď: Ano, kódy osnovy můžete upravit programově pomocí Aspose.Tasks pro .NET. Jednoduše přistupujte k obrysovým kódům úkolů a podle potřeby aktualizujte jejich hodnoty.
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
Odpověď: Aspose.Tasks podporuje širokou škálu verzí Microsoft Project, včetně 2003, 2007, 2010, 2013, 2016 a 2019.
### Otázka: Vyžaduje Aspose.Tasks licenci pro komerční použití?
Odpověď: Ano, pro komerční použití Aspose.Tasks je vyžadována platná licence. Licenci můžete získat z webu Aspose.
### Otázka: Mohu vyzkoušet Aspose.Tasks před nákupem?
Odpověď: Ano, z webu si můžete stáhnout bezplatnou zkušební verzi Aspose.Tasks, abyste mohli vyhodnotit její funkce a schopnosti.
### Otázka: Kde mohu získat podporu pro Aspose.Tasks?
 Odpověď: Podporu pro Aspose.Tasks můžete získat návštěvou fóra na adrese[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Kompletní zdrojový kód