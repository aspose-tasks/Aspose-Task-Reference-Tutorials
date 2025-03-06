---
title: Extrahujte informace o projektu MS v Aspose.Tasks
linktitle: Extrahování informací o projektu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak bez námahy extrahovat informace z MS Project pomocí Aspose.Tasks for .NET. Ponořte se do našeho komplexního tutoriálu.
type: docs
weight: 20
url: /cs/net/project-management-integration/project-information/
---
## Úvod
Hledáte efektivně extrahovat informace ze souborů Microsoft Project pomocí Aspose.Tasks for .NET? V tomto tutoriálu vás provedeme procesem krok za krokem. Než se však vrhneme na detaily implementace, nejprve se ujistěte, že máte vše, co potřebujete.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
### 1. Aspose.Tasks pro .NET
 Ujistěte se, že jste nainstalovali knihovnu Aspose.Tasks for .NET. Pokud jste tak ještě neučinili, můžete si jej stáhnout z[Web Aspose.Tasks pro .NET](https://releases.aspose.com/tasks/net/).
### 2. Přihlašovací údaje pro SharePoint
Pro přístup k SharePointu, kde jsou uloženy vaše soubory MS Project, budete potřebovat přihlašovací údaje. Ujistěte se, že máte následující informace:
- Adresa domény SharePoint
- Uživatelské jméno
- Heslo
## Import jmenných prostorů
Jakmile máte své předpoklady vyřešené, je čas naimportovat potřebné jmenné prostory do vašeho projektu.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Nyní si rozdělme proces extrahování informací z MS Project do několika kroků.
## Krok 1: Zadejte přihlašovací údaje
Nejprve musíte zadat své přihlašovací údaje SharePoint pro přístup k serveru Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Krok 2: Inicializujte Project Server Manager
 Dále inicializujte a`ProjectServerManager` instance s poskytnutými přihlašovacími údaji.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Krok 3: Načtěte seznam projektů
Nyní můžete načíst seznam projektů z Project Serveru.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Krok 4: Vytiskněte informace o projektu
Nakonec projděte seznam projektů a vytiskněte si jejich informace.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak extrahovat informace z MS Project pomocí Aspose.Tasks for .NET. S těmito znalostmi nyní můžete tuto funkcionalitu bez problémů integrovat do svých aplikací .NET.
## FAQ
### Q1: Mohu použít Aspose.Tasks pro .NET s jakoukoli verzí aplikace Microsoft Project?
Odpověď: Ano, Aspose.Tasks for .NET podporuje různé verze Microsoft Project, včetně 2003, 2007, 2010, 2013, 2016 a 2019.
### Q2: Je Aspose.Tasks for .NET kompatibilní s platformami Windows i Linux?
Odpověď: Ano, Aspose.Tasks for .NET je kompatibilní s platformami Windows i Linux, takže je univerzální pro různá vývojová prostředí.
### Q3: Mohu extrahovat závislosti úloh pomocí Aspose.Tasks pro .NET?
A: Rozhodně! Aspose.Tasks for .NET poskytuje robustní funkce pro extrahování nejen základních informací o projektu, ale také závislostí úkolů a dalších složitých detailů.
### Q4: Nabízí Aspose.Tasks for .NET technickou podporu?
 Odpověď: Ano, technickou podporu pro Aspose.Tasks pro .NET můžete získat prostřednictvím[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a hledat pomoc u odborníků.
### Q5: Mohu vyzkoušet Aspose.Tasks pro .NET před jeho zakoupením?
 A: Určitě! Můžete využít bezplatnou zkušební verzi Aspose.Tasks for .NET od[stránka vydání](https://releases.aspose.com/), což vám umožní prozkoumat jeho funkce před rozhodnutím o nákupu.