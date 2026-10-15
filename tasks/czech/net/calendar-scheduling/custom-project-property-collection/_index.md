---
date: 2026-10-15
description: Naučte se, jak přidat vlastní vlastnost a spravovat vlastní vlastnosti
  projektu v Aspose.Tasks pro .NET, což zlepší kontrolu nad metadaty vašeho projektu.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Správa kolekce vlastních vlastností projektu v Aspose.Tasks
og_description: Přidejte vlastní vlastnost do souborů projektu pomocí Aspose.Tasks
  pro .NET. Tento průvodce vám ukáže, jak spravovat vlastní vlastnosti, číst je a
  efektivně přidávat logické nebo řetězcové hodnoty.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Přidejte vlastní vlastnost pomocí Aspose.Tasks .NET API pro projekty
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Jak přidat vlastní vlastnost v Aspose.Tasks pro .NET
url: /cs/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat vlastní vlastnost v Aspose.Tasks pro .NET

## Úvod

Podpora přidání vlastní vlastnosti vám umožňuje ukládat metadata specifická pro projekt, která nejsou pokryta vestavěnými poli. V tomto tutoriálu se naučíte, jak **přidat vlastní vlastnost**, jak ji načíst zpět a jak spravovat celou kolekci vlastních vlastností pomocí Aspose.Tasks pro .NET. Na konci budete schopni přizpůsobit projektové soubory hodnotami Boolean, DateTime, Double a String, které odpovídají vašim obchodním pravidlům.

## Rychlé odpovědi
- **Mohu přidat vlastní vlastnost typu Boolean?** Ano – použijte `CustomPropertyType.Boolean`.
- **Kolik typů vlastních vlastností je podporováno?** Čtyři: Boolean, DateTime, Double, String.
- **Je kolekce vlastních vlastností jen pro čtení?** Může být jen pro čtení, pokud je projekt načten ze zdroje jen pro čtení.
- **Potřebuji licenci pro použití této funkce?** Dočasná licence stačí pro vyhodnocení; pro produkci je vyžadována plná licence.
- **Které verze .NET jsou kompatibilní?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je vlastní vlastnost?

Vlastní vlastnost je uživatelem definované pole metadat, které připojíte k objektu Project. Umožňuje vám ukládat další informace, jako je „Úroveň rizika“, „ID zákazníka“ nebo jakákoli Boolean značka, která není zahrnuta ve standardních polích MS‑Project.

## Proč přidávat vlastní vlastnost v Aspose.Tasks?

Aspose.Tasks podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat projekty s **až 10 000 úkoly** bez načítání celého souboru do paměti. Přidání vlastních vlastností vám umožní vložit kritická obchodní data přímo do projektového souboru, čímž se eliminuje potřeba externích databází a zajišťuje, že data cestují s projektem.

## Požadavky

- Visual Studio (libovolná recentní edice) nainstalované na vašem pracovním stanici.  
- Aspose.Tasks pro .NET – stáhněte jej z [download link](https://releases.aspose.com/tasks/net/).  
- Základní znalost syntaxe C# a struktury .NET projektu.

## Importovat jmenné prostory

Následující jmenné prostory vám poskytují přístup k jádrovému modelu projektu a API pro vlastní vlastnosti.

```csharp
using Aspose.Tasks;
using System;


```

## Jak přidat vlastní vlastnost v Aspose.Tasks?

Pro přidání vlastní vlastnosti nejprve načtěte projekt, poté vytvořte objekt `CustomProperty`, nastavte jeho název, typ a hodnotu a nakonec jej přidejte do kolekce `CustomProperties` projektu. Tato operace vloží metadata přímo do projektového souboru a změny jsou uloženy při volání `project.Save(...)`.  

`CustomProperty` představuje jediné uživatelem definované pole připojené k projektu.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Krok 1: inicializovat projekt

`Project` je hlavní třída představující projektový soubor v Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Krok 2: zkontrolovat připravenost kolekce vlastních vlastností

`CustomProperties` je kolekce, která obsahuje všechny objekty vlastních vlastností pro projekt.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Krok 3: přidat vlastní vlastnosti

Metoda `Add` vloží novou vlastní vlastnost do kolekce projektu.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Krok 4: přístup k vlastním vlastnostem

Kolekce `CustomProperties` implementuje IEnumerable, což umožňuje iteraci přes každou `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Krok 5: získat hodnotu vlastní vlastnosti

Metoda `Get` vrací hodnotu vlastní vlastnosti podle jejího názvu.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Krok 6: iterovat přes názvy vlastních vlastností

Vlastnost `Names` poskytuje seznam všech názvů vlastních vlastností v kolekci.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Krok 7: odebrat nebo vymazat vlastní vlastnosti

Metoda `Remove` odstraní konkrétní vlastnost, zatímco `Clear` vyprázdní celou kolekci.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Časté úskalí a řešení problémů

- **Kolekce jen pro čtení** – Pokud `project.CustomProperties.IsReadOnly` vrací `true`, ujistěte se, že zdrojový soubor není otevřen s výlučným přístupem jen pro čtení, nebo jej před úpravou zkopírujte do zapisovatelného umístění.  
- **Neshoda typu** – Při přiřazení hodnoty, která neodpovídá deklarovanému `CustomPropertyType`, se vyvolá `ArgumentException`. Vždy nastavte `Value` po definování správného `Type`.  
- **Ukládání změn** – Po přidání nebo odebrání vlastností zavolejte `project.Save("output.mpp")`, aby se změny uložily; jinak zůstanou pouze v paměti.

## Často kladené otázky

**Q: Mohu do svého projektu pomocí Aspose.Tasks pro .NET přidat vlastní vlastnosti libovolného datového typu?**  
A: Ano, můžete přidat vlastní vlastnosti podporující typy Boolean, DateTime, Double a String.

**Q: Je možné iterovat přes názvy vlastních vlastností v Aspose.Tasks pro .NET?**  
A: Rozhodně, můžete iterovat přes názvy vlastních vlastností pomocí vlastnosti `Names`.

**Q: Jak mohu odebrat konkrétní vlastní vlastnost z mého projektu?**  
A: Můžete odebrat vlastní vlastnost podle jejího názvu pomocí metody `Remove`.

**Q: Poskytuje Aspose.Tasks pro .NET podporu dočasných licencí?**  
A: Ano, můžete získat dočasnou licenci na webu Aspose pro evaluační účely.

**Q: Kde mohu najít podporu nebo další pomoc ohledně Aspose.Tasks pro .NET?**  
A: Můžete navštívit fórum Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pro jakékoli dotazy nebo pomoc.

---

**Poslední aktualizace:** 2026-10-15  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak číst vestavěné projektové vlastnosti pomocí Aspose.Tasks pro .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Spravovat kolekci atributů MS Project v Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Vlastní typy polí Aspose.Tasks – Kalendář a plánování](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}