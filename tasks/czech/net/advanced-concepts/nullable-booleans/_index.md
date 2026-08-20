---
date: 2026-03-14
description: Naučte se, jak používat nullable booly v Aspose.Tasks pro .NET, včetně
  převodu nullable bool hodnot a nastavení nullable bool vlastností.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak používat nullable boolovské hodnoty v Aspose.Tasks
url: /cs/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak používat nullable Booleany v Aspose.Tasks

V tomto tutoriálu vám ukážeme **jak používat nullable** booleany při práci s Aspose.Tasks .NET API. Nullable booleany vám poskytují tři možné stavy — `true`, `false` nebo *undefined* — což je zvláště užitečné pro nastavení na úrovni projektu, která nemusí být explicitně zadána. Uvidíte, jak vytvářet, převádět a **nastavovat nullable boolean** hodnoty a proč správná manipulace s nullable booleany může zabránit neočekávanému chování ve vašich plánovacích aplikacích.

## Rychlé odpovědi
- **Co je nullable boolean?** Typ, který může obsahovat `true`, `false` nebo být undefined.  
- **Proč používat nullable booleany v Aspose.Tasks?** Umožňují vám reprezentovat volitelné vlastnosti projektu, aniž byste museli hádat výchozí hodnotu.  
- **Jak převést nullable boolean na běžný bool?** Použijte implicitní převod nebo nejprve zkontrolujte `IsDefined`.  
- **Jaká je hlavní třída?** `NullableBool` v jmenném prostoru `Aspose.Tasks`.  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.

## Co je Nullable Boolean?

Nullable boolean (`NullableBool`) rozšiřuje běžný typ `bool` o příznak *IsDefined*. Když je `IsDefined` `false`, hodnota se považuje za undefined, což vám umožňuje rozlišovat mezi „false“ a „not set“.

## Proč zacházet s nullable Booleany v nastaveních projektu?

Mnoho možností projektu — jako **ActualsInSync** nebo **HonorConstraints** — je volitelných. Použití obyčejného `bool` vás nutí vybrat `true` nebo `false`, což může neúmyslně přepsat záměr uživatele. **Zpracováním nullable booleanů** zachováte původní stav a vyhnete se nechtěným změnám konfigurace.

## Předpoklady

Než začneme, ujistěte se, že máte:

1. **Visual Studio** (nebo jakékoli IDE kompatibilní s .NET).  
2. **Aspose.Tasks pro .NET** – stáhněte jej z [zde](https://releases.aspose.com/tasks/net/).

## Importujte jmenné prostory

Nejprve importujte požadované jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Nyní projdeme každý příklad krok za krokem.

## Práce s `NullableBool`

### Krok 1: Vytvořte novou instanci `Project`.

```csharp
var project = new Project();
```

### Krok 2: Vytvořte objekt `NullableBool` s určenými hodnotami.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Krok 3: Zkontrolujte hodnotu a stav definovanosti objektu `NullableBool`.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Krok 4: **Nastavte nullable boolean** na projektu.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Krok 5: Vytvořte další objekt `NullableBool` s jednou hodnotou.

```csharp
var honorConstraints = new NullableBool(true);
```

### Krok 6: Zobrazte řetězcovou reprezentaci objektu `NullableBool`.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Krok 7: Použijte instanci `NullableBool` nastavením v projektu.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Porovnání instancí `NullableBool`

### Krok 1: Vytvořte dva objekty `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Krok 2: Zkontrolujte řetězcovou reprezentaci každého objektu `NullableBool`.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Krok 3: Implicitní převod na `bool` a výpis výsledku.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Krok 4: Porovnejte dva objekty `NullableBool` na rovnost.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Získání hash kódu `NullableBool`

### Krok 1: Vytvořte dva objekty `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Krok 2: Vytiskněte hash kód pro každý objekt `NullableBool`.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Časté úskalí a tipy

- **Nikdy nepředpokládejte, že nullable boolean je definován.** Vždy zkontrolujte `IsDefined` před použitím `Value`.  
- **Převod na běžný bool** bez kontroly může vyvolat výjimku, pokud je hodnota undefined. Používejte implicitní převod pouze tehdy, když jste si jisti, že je definován.  
- **Při nastavování vlastností projektu** použijte metodu `Set` s `NullableBool`, abyste v případě potřeby zachovali stav undefined.

## Často kladené otázky

**Q: Co je nullable boolean?**  
A: Nullable boolean může představovat `true`, `false` nebo stav undefined, což umožňuje tři odlišné výsledky.

**Q: Jak mohu bezpečně převést nullable boolean na běžný bool?**  
A: Nejprve zkontrolujte `IsDefined`, poté použijte vlastnost `Value` nebo se spolehněte na implicitní převod, pokud jste si jisti, že je definován.

**Q: Proč bych měl používat nullable booleany místo obyčejných boolů v Aspose.Tasks?**  
A: Umožňují vám ponechat volitelné nastavení projektu nedotčené, čímž zabraňují neúmyslným přepsáním.

**Q: Mohu nastavit nullable boolean jako undefined?**  
A: Ano — použijte konstruktor, který přijímá pouze příznak definovanosti, např. `new NullableBool(false, false)`.

**Q: Kde mohu najít další dokumentaci k Aspose.Tasks pro .NET?**  
A: Podrobnou dokumentaci najdete [zde](https://reference.aspose.com/tasks/net/).

---

**Poslední aktualizace:** 2026-03-14  
**Testováno s:** Aspose.Tasks pro .NET (nejnovější verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}