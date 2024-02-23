---
title: Možnosti pro načítání v Aspose.Tasks
linktitle: Možnosti pro načítání v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak využít sílu Aspose.Tasks pro .NET k efektivní správě dokumentů Microsoft Project pomocí podrobných pokynů.
type: docs
weight: 16
url: /cs/net/advanced-concepts/loading-options/
---
## Úvod

Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům programově manipulovat s dokumenty Microsoft Project. Ať už potřebujete vytvářet, číst, zapisovat nebo převádět soubory projektu, Aspose.Tasks poskytuje širokou škálu funkcí pro zefektivnění vašich úkolů. V tomto tutoriálu se ponoříme do základů používání Aspose.Tasks pro .NET a rozdělíme klíčové procesy do jednoduchých kroků.

## Předpoklady

Než se ponoříte do Aspose.Tasks pro .NET, ujistěte se, že máte nastaveny následující předpoklady:

1. Visual Studio: Nainstalujte Visual Studio nebo jakékoli jiné IDE dle vašeho výběru.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[webová stránka](https://releases.aspose.com/tasks/net/).
3. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#.

Nyní, když máme pokryty naše předpoklady, pojďme prozkoumat základní jmenné prostory a ponořit se do podrobného průvodce.

## Import jmenných prostorů

Ve svém projektu C# importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Tasks:

1. Aspose.Tasks: Tento jmenný prostor poskytuje základní třídy a rozhraní pro práci s dokumenty projektu.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Nyní si rozdělme různé úkoly do podrobných průvodců.

## Krok 1: Načítání projektů chráněných heslem

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Inicializací FileStream načtete soubor projektu
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Vytvořte instanci LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // Nastavte heslo
        };

        // Načtěte projekt se zadanými možnostmi
        var project = new Project(stream, options);

        // Zobrazit název projektu
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Krok 2: Načtení projektů Primavera s vlastními možnostmi

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Vytvořte instanci LoadOptions
    var loadOptions = new LoadOptions();

    // Nakonfigurujte možnosti čtení Primavera
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Nastavte UID projektu
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Nastavte možnosti čtení Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Načtěte projekt Primavera se zadanými možnostmi
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Zobrazit název projektu
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Proveďte další operace s načteným projektem
}
```

## Krok 3: Určení kódování souboru

```csharp
public void SpecifyFileEncoding()
{
    // Vytvořte instanci LoadOptions
    LoadOptions lo = new LoadOptions();

    // Zadejte kódování při otevírání projektu ze souboru Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // Načtěte projekt se zadaným kódováním
    var project = new Project("encoding1251.xer", lo);

    // Proveďte další operace s načteným projektem
}
```

## Krok 4: Načítání projektů Primavera se zpracováním chyb

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Vytvořte instanci LoadOptions
    var loadOptions = new LoadOptions();

    // Nakonfigurujte možnosti čtení Primavera
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Nastavte UID projektu
    };

    // Nastavte možnosti čtení Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Nastavit vlastní zpracování chyb
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Načtěte projekt Primavera se zadanými možnostmi a řešením chyb
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Proveďte další operace s načteným projektem
}

// Vlastní metoda obsluhy chyb
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implementujte vlastní logiku zpracování chyb
}
```

Podle těchto kroků můžete efektivně využívat možnosti načítání v Aspose.Tasks for .NET k manipulaci s dokumenty projektu podle vašich požadavků.

## Závěr

V tomto tutoriálu jsme prozkoumali základy práce s možnostmi načítání v Aspose.Tasks pro .NET. Od načítání projektů chráněných heslem až po specifikaci vlastního zpracování chyb vám zvládnutí těchto technik umožní efektivně spravovat soubory projektu v rámci vašich aplikací .NET.

## FAQ

### Q1: Je Aspose.Tasks for .NET kompatibilní se všemi verzemi aplikace Microsoft Project?

Odpověď 1: Ano, Aspose.Tasks for .NET podporuje různé verze aplikace Microsoft Project a zajišťuje kompatibilitu v různých prostředích.

### Q2: Mohu integrovat Aspose.Tasks for .NET s knihovnami jiných výrobců?

Odpověď 2: Aspose.Tasks for .NET se bez problémů integruje s ostatními knihovnami .NET a nabízí vylepšené funkce a flexibilitu.

### Q3: Poskytuje Aspose.Tasks pro .NET dokumentaci a zdroje podpory?

 A3: Ano, můžete odkazovat na komplexní[dokumentace](https://reference.aspose.com/tasks/net/) a přístup k podpoře prostřednictvím[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q4: Jsou k dispozici nějaké možnosti licencování pro Aspose.Tasks pro .NET?

 A4: Ano, můžete prozkoumat různé možnosti licencování, včetně bezplatných zkušebních verzí a dočasných licencí, na[Web Aspose.Tasks](https://purchase.aspose.com/buy).

### Otázka 5: Jak často jsou pro Aspose.Tasks pro .NET vydávány aktualizace a nové funkce?

A5: Aspose.Tasks for .NET dostává pravidelné aktualizace a vylepšení funkcí, aby byl zajištěn optimální výkon a kompatibilita s vyvíjejícími se technologiemi.