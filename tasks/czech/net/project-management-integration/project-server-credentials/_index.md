---
title: Správa přihlašovacích údajů serveru MS Project v Aspose.Tasks
linktitle: Správa pověření Project Server v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak bezproblémově spravovat přihlašovací údaje MS Project Server pomocí Aspose.Tasks for .NET. Zvyšte efektivitu řízení projektů.
type: docs
weight: 22
url: /cs/net/project-management-integration/project-server-credentials/
---
## Úvod
oblasti projektového řízení je pro úspěšnou realizaci projektu klíčová efektivní koordinace a bezproblémová komunikace. Aspose.Tasks for .NET poskytuje komplexní řešení pro správu pověření serveru Microsoft Project Server a umožňuje uživatelům bezpečný přístup a manipulaci s daty projektu. Tento výukový program se ponoří do procesu správy pověření MS Project Server pomocí Aspose.Tasks for .NET a provede uživatele každým krokem, aby bylo zajištěno bezproblémové používání.
## Předpoklady
Než se pustíte do správy přihlašovacích údajů MS Project Server pomocí Aspose.Tasks pro .NET, ujistěte se, že jsou splněny následující předpoklady:
### 1. Instalace Aspose.Tasks pro .NET
 Pro začátek si stáhněte a nainstalujte Aspose.Tasks for .NET z poskytnutého[odkaz ke stažení](https://releases.aspose.com/tasks/net/). Postupujte podle pokynů k instalaci a hladce integrujte knihovnu do prostředí .NET.
### 2. Přístupové údaje
Shromážděte potřebné přihlašovací údaje potřebné pro přístup k MS Project Server. To zahrnuje adresu domény SharePoint, uživatelské jméno a heslo přidružené k serveru Project Server.

## Importovat jmenné prostory
Ve svém projektu .NET naimportujte požadované jmenné prostory, abyste mohli efektivně využívat funkce poskytované Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Krok 1: Definujte cestu k adresáři dokumentu
```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Nastavte adresu domény SharePoint, uživatelské jméno a heslo
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Krok 3: Vytvořte přihlašovací údaje k serveru Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Krok 4: Načtěte soubor projektu
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Krok 5: Inicializujte Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Krok 6: Vytvořte nový projekt
```csharp
manager.CreateNewProject(newProject);
```
## Krok 7: Načtěte seznam projektů
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Krok 8: Projděte seznam projektů
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Závěr
Efektivní správa přihlašovacích údajů k MS Project Server je pro efektivní řízení projektů prvořadá. Aspose.Tasks for .NET zjednodušuje tento proces tím, že poskytuje robustní sadu funkcí. Podle podrobného průvodce popsaného v tomto tutoriálu mohou uživatelé bez problémů integrovat Aspose.Tasks for .NET do svých projektů a zajistit tak bezpečný přístup a manipulaci s daty projektu.
## FAQ
### Otázka: Je Aspose.Tasks for .NET kompatibilní se všemi verzemi Microsoft Project Server?
Odpověď: Aspose.Tasks for .NET je navržen tak, aby byl kompatibilní s různými verzemi serveru Microsoft Project Server a zajistil uživatelům všestrannost a flexibilitu.
### Otázka: Mohu integrovat Aspose.Tasks for .NET do svého stávajícího projektu .NET?
Odpověď: Ano, Aspose.Tasks for .NET lze bez problémů integrovat do stávajících projektů .NET, což umožňuje efektivní řízení projektů.
### Otázka: Poskytuje Aspose.Tasks for .NET podporu pro přístup k prostředkům projektu?
Odpověď: Aspose.Tasks for .NET nabízí komplexní podporu pro přístup a manipulaci s projektovými zdroji, čímž zvyšuje efektivitu projektového řízení.
### Otázka: Jsou pro Aspose.Tasks pro .NET k dispozici nějaké možnosti licencování?
Odpověď: Ano, Aspose.Tasks for .NET nabízí flexibilní možnosti licencování, včetně dočasných licencí pro zkušební účely a úplných licencí pro komerční použití.
### Otázka: Kde mohu hledat pomoc nebo podporu pro Aspose.Tasks pro .NET?
 Odpověď: Máte-li jakékoli dotazy nebo pomoc týkající se Aspose.Tasks pro .NET, můžete navštívit fórum podpory na adrese[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Kompletní zdrojový kód