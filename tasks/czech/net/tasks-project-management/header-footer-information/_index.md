---
title: Extrahujte informace o záhlaví a zápatí pomocí Aspose.Tasks
linktitle: Informace o záhlaví a zápatí v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se extrahovat informace o záhlaví a zápatí ze souborů MS Project pomocí Aspose.Tasks for .NET. Snadné, efektivní a pro vývojáře přátelské řešení.
weight: 29
url: /cs/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahujte informace o záhlaví a zápatí pomocí Aspose.Tasks

## Úvod
Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům snadno manipulovat se soubory aplikace Microsoft Project. V tomto tutoriálu se naučíme, jak získat informace o záhlaví a zápatí ze souborů MS Project pomocí Aspose.Tasks.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Visual Studio: Nainstalujte Visual Studio do svého systému.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Znalost programovacího jazyka C#.

## Importovat jmenné prostory
Nejprve musíte do projektu C# importovat potřebné jmenné prostory. To vám umožní přístup ke třídám a metodám poskytovaným knihovnou Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Inicializujte objekt projektu
 Chcete-li začít, musíte inicializovat a`Project` objekt načtením existujícího souboru MS Project.
```csharp
// Cesta k adresáři dokumentů.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Krok 2: Načtěte informace o záhlaví a zápatí
 Jakmile načtete soubor projektu, můžete získat informace o záhlaví a zápatí pomocí`PageInfo` vlastnictví.
```csharp
var info = project.DefaultView.PageInfo;
// Informace v záhlaví
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Informace v zápatí
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Pomocí těchto jednoduchých kroků můžete snadno získat informace o záhlaví a zápatí ze souborů MS Project pomocí Aspose.Tasks for .NET.

## Závěr
tomto tutoriálu jsme prozkoumali, jak extrahovat informace záhlaví a zápatí ze souborů MS Project pomocí Aspose.Tasks for .NET. Tato výkonná knihovna zjednodušuje práci se soubory Project v aplikacích C# a poskytuje vývojářům robustní nástroje pro manipulaci.
### Nejčastější dotazy
### Mohu upravit informace v záhlaví a zápatí pomocí Aspose.Tasks?
Ano, informace v záhlaví a zápatí můžete upravit programově pomocí Aspose.Tasks for .NET.
### Podporuje Aspose.Tasks jiné formáty souborů projektu kromě MS Project?
Ano, Aspose.Tasks podporuje různé formáty souborů projektu, včetně MPP, XML a MPX.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Tasks?
 Můžete najít dokumentaci k Aspose.Tasks[tady](https://reference.aspose.com/tasks/net/).
### Jak mohu získat podporu pro Aspose.Tasks?
 Podporu pro Aspose.Tasks můžete získat na adrese[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
