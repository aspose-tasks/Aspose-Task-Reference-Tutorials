---
title: Denní opakování práce v Aspose.Tasks
linktitle: Denní opakování práce v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se vytvářet každodenní opakující se úkoly v souborech Microsoft Project pomocí Aspose.Tasks for .NET. Zvyšte produktivitu a organizaci bez námahy.
type: docs
weight: 26
url: /cs/net/calendar-scheduling/daily-work-repetition/
---
## Úvod

Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům snadno manipulovat se soubory aplikace Microsoft Project. Mezi jeho nesčetné funkce patří schopnost efektivně zvládat opakující se úkoly. V tomto tutoriálu se ponoříme do funkce Denní opakování práce, která umožňuje vytvářet úkoly, které se v rámci projektu denně opakují.

## Předpoklady

Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující:

- Základní znalost C# a .NET frameworku.
- Visual Studio nainstalované ve vašem systému.
-  Aspose.Tasks pro knihovnu .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
- Znalost souborů Microsoft Project (.mpp).

## Importovat jmenné prostory

Než začneme, ujistěte se, že jste importovali potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Rozdělme poskytnutý příklad do několika kroků:

## Krok 1: Načtěte soubor projektu

 Nejprve načtěte soubor projektu pomocí`Project` třída:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Krok 2: Definujte parametry opakujících se úloh

Definujte parametry pro opakující se úlohu:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Krok 3: Nastavte kalendář a datum zahájení úkolu

Nastavte kalendář a datum zahájení úkolu:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak využít Aspose.Tasks pro .NET k vytváření opakujících se úkolů s každodenním opakováním práce. Dodržováním těchto kroků můžete efektivně spravovat úkoly v rámci svých projektů a zajistit tak hladký pracovní tok a organizaci.

## FAQ

### Q1: Mohu si vzor opakování dále přizpůsobit?

Odpověď 1: Ano, můžete upravit parametry, jako je datum zahájení, číslo výskytu a interval opakování, abyste přizpůsobili vzor opakování podle svých požadavků.

### Q2: Je Aspose.Tasks kompatibilní s různými verzemi aplikace Microsoft Project?

Odpověď 2: Ano, Aspose.Tasks podporuje různé verze aplikace Microsoft Project, což zajišťuje kompatibilitu a bezproblémovou integraci.

### Q3: Jak mohu zpracovat výjimky nebo úpravy opakujících se úkolů?

A3: Aspose.Tasks poskytuje robustní funkce pro správu výjimek a úprav v rámci opakujících se úloh, což umožňuje flexibilitu a přizpůsobení.

### Q4: Mohu exportovat projekt do různých formátů?

A4: Rozhodně, Aspose.Tasks nabízí podporu pro export projektů do různých formátů včetně PDF, HTML, XML a dalších, což usnadňuje sdílení a spolupráci.

### Q5: Nabízí Aspose.Tasks technickou podporu?

Odpověď 5: Ano, Aspose.Tasks poskytuje komplexní technickou podporu prostřednictvím svého fóra, kde můžete hledat pomoc, sdílet zkušenosti a komunikovat s ostatními uživateli.