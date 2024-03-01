---
title: Spravujte kritéria skupiny MS Project pomocí Aspose.Tasks
linktitle: Správa kolekce kritérií skupiny v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zjistěte, jak spravovat kolekci Group Criterion MS Project pomocí Aspose.Tasks for .NET. Podrobný průvodce pro vývojáře.
type: docs
weight: 28
url: /cs/net/tasks-project-management/group-criterion-collection/
---
## Úvod
Aspose.Tasks for .NET je výkonné API, které umožňuje vývojářům pracovat se soubory Microsoft Project programově. V tomto tutoriálu prozkoumáme, jak spravovat kolekci Group Criterion v rámci MS Project pomocí Aspose.Tasks.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1.  Aspose.Tasks for .NET: Ujistěte se, že máte v projektu .NET nainstalovanou knihovnu Aspose.Tasks. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

2. Soubor Microsoft Project: Připravte si soubor Microsoft Project (MPP), se kterým budete pracovat.

## Importovat jmenné prostory

Nejprve musíte do kódu C# importovat potřebné jmenné prostory. Tento krok je zásadní pro přístup k funkcím poskytovaným Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Krok 1: Načtěte soubor projektu

 Inicializovat a`Project` objekt načtením souboru MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Krok 2: Přístupová kritéria skupiny

Načtěte skupinu z projektu a získejte přístup k jejím kritériím.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Krok 3: Iterujte přes skupinová kritéria

Projděte každé kritérium ve skupině a zobrazte jeho vlastnosti.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Krok 4: Vymažte kritéria skupiny

Vymažte existující kritéria skupiny, pokud není jen pro čtení.

```csharp
group.GroupCriteria.Clear();
```

## Krok 5: Přidejte nové kritérium

Vytvořte nové skupinové kritérium a přidejte jej do skupiny.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Krok 6: Zkopírujte kritéria do jiné skupiny

Zkopírujte kritéria z jedné skupiny do druhé.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Závěr

V tomto tutoriálu jsme se naučili, jak spravovat kolekci Group Criterion MS Project pomocí Aspose.Tasks for .NET. Pomocí těchto kroků můžete efektivně manipulovat s kritérii skupiny v rámci souborů aplikace programově.

## FAQ

### Q1: Je Aspose.Tasks kompatibilní se všemi verzemi aplikace Microsoft Project?

Odpověď: Ano, Aspose.Tasks podporuje soubory Microsoft Project různých verzí, včetně 2003, 2007, 2010, 2013 a 2016.

### Q2: Mohu použít více kritérií na jednu skupinu?

Odpověď: Rozhodně můžete do skupiny přidat více kritérií tím, že je budete opakovat a podle toho je přidat.

### Q3: Je k dispozici zkušební verze pro Aspose.Tasks?

 Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks od[tady](https://releases.aspose.com/).

### Q4: Kde najdu dokumentaci pro Aspose.Tasks?

 Odpověď: Můžete se podívat do dokumentace[tady](https://reference.aspose.com/tasks/net/).

### Q5: Jak mohu získat podporu, pokud narazím na nějaké problémy?

 Odpověď: Pokud máte nějaké otázky nebo se potýkáte s nějakými problémy, můžete vyhledat podporu na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).