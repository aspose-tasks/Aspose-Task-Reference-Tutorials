---
title: Správa vlastní kolekce vlastností projektu v Aspose.Tasks
linktitle: Správa vlastní kolekce vlastností projektu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat vlastní vlastnosti projektu v Aspose.Tasks pro .NET, a zlepšit tak své zkušenosti s řízením projektů.
weight: 24
url: /cs/net/calendar-scheduling/custom-project-property-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa vlastní kolekce vlastností projektu v Aspose.Tasks

## Úvod

Jste připraveni zlepšit své zkušenosti s řízením projektů pomocí Aspose.Tasks pro .NET? Správa vlastních vlastností projektu je zásadním aspektem řízení projektu, který vám umožňuje přidávat specifická metadata přizpůsobená požadavkům vašeho projektu. V tomto tutoriálu se ponoříme do toho, jak můžete efektivně pracovat s vlastními kolekcemi projektových vlastností pomocí Aspose.Tasks for .NET.

## Předpoklady

Než budeme pokračovat, ujistěte se, že máte nastaveny následující předpoklady:

1. Prostředí Visual Studio: Mějte na svém systému nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory

Začněte importem jmenných prostorů nezbytných pro práci s Aspose.Tasks pro .NET:

```csharp
using Aspose.Tasks;
using System;


```

Pojďme si ukázkový kód rozdělit do několika kroků pro komplexní pochopení:

## Krok 1: Inicializujte projekt

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Tento krok inicializuje nový projekt pomocí Aspose.Tasks.

## Krok 2: Zkontrolujte připravenost kolekce uživatelských vlastností

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Tento kód kontroluje, zda je kolekce uživatelských vlastností pouze pro čtení.

## Krok 3: Přidejte uživatelské vlastnosti

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Zde přidáme do projektu vlastní vlastnosti, které podporují typy Boolean, DateTime, Double a String.

## Krok 4: Přístup k uživatelským vlastnostem

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Tato smyčka nám umožňuje procházet uživatelskými vlastnostmi a zobrazovat jejich typ, název a hodnotu.

## Krok 5: Načtěte hodnotu vlastní vlastnosti

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Tento kód načte hodnotu konkrétní uživatelské vlastnosti s názvem "Custom Name".

## Krok 6: Iterujte přes názvy uživatelských vlastností

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Zde iterujeme názvy uživatelských vlastností a zobrazujeme je.

## Krok 7: Odeberte nebo vymažte uživatelské vlastnosti

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Můžete odebrat konkrétní uživatelskou vlastnost podle jejího názvu nebo vymazat celou kolekci.

## Závěr

Zvládnutí vlastních kolekcí vlastností projektu v Aspose.Tasks for .NET vám umožňuje efektivně spravovat metadata projektu. Dodržováním tohoto podrobného průvodce můžete bez problémů integrovat uživatelské vlastnosti do pracovního postupu projektového řízení a zlepšit tak organizaci a efektivitu.

## FAQ

### Q1: Mohu do svého projektu pomocí Aspose.Tasks for .NET přidat vlastní vlastnosti libovolného datového typu?

Odpověď 1: Ano, můžete přidat vlastní vlastnosti podporující typy Boolean, DateTime, Double a String.

### Q2: Je možné iterovat přes názvy vlastních vlastností v Aspose.Tasks pro .NET?

 A2: Rozhodně můžete iterovat názvy vlastních vlastností pomocí`Names` vlastnictví.

### Q3: Jak mohu odebrat konkrétní vlastní vlastnost z mého projektu?

 A3: Můžete odebrat vlastní vlastnost podle jejího názvu pomocí`Remove` metoda.

### Q4: Poskytuje Aspose.Tasks for .NET podporu pro dočasné licence?

A4: Ano, můžete získat dočasnou licenci z webu Aspose pro účely hodnocení.

### Q5: Kde najdu podporu nebo další pomoc týkající se Aspose.Tasks pro .NET?

 A5: Můžete navštívit fórum Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15) pro jakékoli dotazy nebo pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
