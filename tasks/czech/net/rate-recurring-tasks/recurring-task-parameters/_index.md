---
title: Nastavení parametrů opakujících se úloh v Aspose.Tasks
linktitle: Nastavení parametrů opakujících se úloh v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zjistěte, jak nastavit parametry opakujících se úloh v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. Komplexní tutoriál s průvodcem krok za krokem.
weight: 14
url: /cs/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení parametrů opakujících se úloh v Aspose.Tasks

## Úvod
tomto tutoriálu vás provedeme procesem nastavení parametrů opakujících se úloh Microsoft Project pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Základní znalost programovacího jazyka C#.
2. Nainstalované Visual Studio nebo jakékoli jiné IDE C#.
3. Aspose.Tasks pro knihovnu .NET nainstalovanou a odkazovanou ve vašem projektu.

## Importovat jmenné prostory
Nejprve musíte do kódu C# importovat potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;

```
## Krok 1: Definujte adresář dokumentů
```csharp
String DataDir = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou k adresáři s dokumenty.
## Krok 2: Načtěte soubor projektu
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Tento řádek kódu načte soubor Microsoft Project do`project` variabilní.
## Krok 3: Definujte parametry opakujících se úloh
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Zde definujete parametry pro opakující se úlohu, jako je název úlohy, trvání, vzor opakování, rozsah opakování a zda se má ignorovat kalendář zdrojů.
## Krok 4: Nastavte kalendář pro opakující se úkoly
```csharp
parameters.SetCalendar(project, "Standard");
```
Tento krok nastaví kalendář pro opakovaný úkol. V tomto příkladu nastaví kalendář na "Standardní".
## Krok 5: Přidejte parametry do projektu
```csharp
project.RootTask.Children.Add(parameters);
```
Nakonec přidejte parametry do kořenové úlohy projektu.

## Závěr
tomto tutoriálu jsme si ukázali, jak nastavit parametry opakujících se úloh aplikace Microsoft Project pomocí Aspose.Tasks for .NET. Pomocí těchto kroků můžete efektivně spravovat opakující se úkoly ve svých projektech.
## Nejčastější dotazy
### Mohu si vzor opakování dále přizpůsobit?
Ano, Aspose.Tasks poskytuje různé vzory opakování a možnosti přizpůsobení podle požadavků vašeho projektu.
### Je před zakoupením k dispozici zkušební verze?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z Aspose.Tasks[webová stránka](https://purchase.aspose.com/buy) zhodnotit vlastnosti knihovny.
### Podporuje Aspose.Tasks jiné formáty souborů projektu?
Ano, Aspose.Tasks podporuje různé formáty projektových souborů včetně MPP, XML, XLSX a dalších.
### Mohu získat podporu, pokud během implementace narazím na nějaké problémy?
Ano, můžete navštívit fórum Aspose.Tasks pro pomoc od komunity nebo kontaktovat podporu pro přímou pomoc.
### Jak mohu získat dočasnou licenci pro Aspose.Tasks?
 Dočasnou licenci můžete získat od[webová stránka](https://purchase.aspose.com/temporary-license/) pro testovací účely.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
