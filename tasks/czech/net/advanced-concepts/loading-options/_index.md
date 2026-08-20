---
date: 2026-03-08
description: Naučte se, jak importovat soubor projektu pomocí Aspose.Tasks pro .NET,
  včetně určení kódování souboru a efektivního načtení souboru Microsoft Project.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Import souboru projektu – možnosti načtení v Aspose.Tasks
url: /cs/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Import souboru projektu – Možnosti načítání v Aspose.Tasks

## Introduction

Aspose.Tasks pro .NET usnadňuje **import project file** dat z Microsoft Project, Primavera a dalších formátů. Ať už potřebujete načíst soubor chráněný heslem, nastavit vlastní kódování nebo zpracovat chyby při parsování, knihovna vám poskytuje detailní kontrolu prostřednictvím možností načítání. V tomto tutoriálu projdeme nejčastější scénáře, abyste mohli sebejistě **load Microsoft Project file** objekty ve svých .NET aplikacích.

## Quick Answers
- **Jaký je hlavní způsob importu souboru projektu?** Použijte konstruktor `Project` s instancí `LoadOptions`.  
- **Mohu otevřít soubory chráněné heslem?** Ano – nastavte vlastnost `Password` na `LoadOptions`.  
- **Jak specifikovat kódování souboru?** Přiřaďte objekt `Encoding` k `LoadOptions.Encoding`.  
- **Je možné přizpůsobit zpracování chyb?** Rozhodně – poskytněte delegáta pro `LoadOptions.ErrorHandler`.  
- **Fungují tyto možnosti i se soubory Primavera?** Ano, prostřednictvím `PrimaveraReadOptions` uvnitř `LoadOptions`.

## Prerequisites

Předtím, než se ponoříte dál, ujistěte se, že máte:

1. **Visual Studio** (nebo jakékoli preferované .NET IDE).  
2. **Aspose.Tasks pro .NET** – stáhněte jej z [webu](https://releases.aspose.com/tasks/net/).  
3. Základní znalost syntaxe **C#** a struktury projektu.

Nyní, když je vše připraveno, naimportujme požadované jmenné prostory.

## Importing Namespaces

Ve svém C# projektu přidejte následující `using` příkazy, aby byly třídy API k dispozici:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## How to Import Project File with Loading Options

Níže jsou čtyři praktické příklady, které pokrývají nejčastější scénáře načítání.

### Step 1: Load a Password‑Protected Project

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Step 2: Load a Primavera Project with Custom Options

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Step 3: **Specify File Encoding** při importu souboru XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Step 4: Load a Primavera Project with Custom Error Handling

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Dodržením těchto kroků můžete přesně **import project file** data, přizpůsobit proces načítání svým potřebám a udržet aplikaci robustní.

## Common Issues & Tips

- **Incorrect password** – vlastnost `Password` vyhodí výjimku; před načtením ověřte přihlašovací údaje.  
- **Unsupported encoding** – ujistěte se, že zadaná kódová stránka existuje na cílovém počítači (`Encoding.GetEncoding(1251)` funguje pro cyriliku).  
- **Missing Primavera options** – pokud potřebujete zachovat UID úkolů, nastavte `PreserveUids = true`; jinak se mohou objevit duplicitní ID.  
- **Error handler returning null** – vrácení `null` signalizuje parseru, aby přeskočil problematický prvek; přizpůsobte podle potřeby.

## Frequently Asked Questions

**Q: Je Aspose.Tasks pro .NET kompatibilní se všemi verzemi Microsoft Project?**  
A: Ano, podporuje širokou škálu verzí Microsoft Project, takže můžete **load Microsoft Project file** formáty od starších MPP souborů po nejnovější formáty.

**Q: Mohu integrovat Aspose.Tasks pro .NET s dalšími knihovnami třetích stran?**  
A: Rozhodně. Knihovna funguje hladce s ostatními .NET balíčky, což vám umožní kombinovat ji s reportingem, UI nebo datovými frameworky.

**Q: Poskytuje Aspose.Tasks pro .NET dokumentaci a podpůrné zdroje?**  
A: Ano, můžete se odkazovat na komplexní [documentation](https://reference.aspose.com/tasks/net/) a získat podporu prostřednictvím [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Existují licenční možnosti pro Aspose.Tasks pro .NET?**  
A: Ano, můžete prozkoumat různé licenční možnosti, včetně bezplatných zkušebních verzí a dočasných licencí, na [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: Jak často jsou vydávány aktualizace a nové funkce pro Aspose.Tasks pro .NET?**  
A: Aspose.Tasks dostává pravidelné aktualizace, které přidávají funkce, zlepšují výkon a udržují kompatibilitu s nejnovějšími verzemi Microsoft Project.

---

**Poslední aktualizace:** 2026-03-08  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}