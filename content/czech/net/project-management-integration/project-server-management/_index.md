---
title: Správa MS Project Server pomocí Aspose.Tasks
linktitle: Správa Project Server pomocí Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odemkněte bezproblémovou správu MS Project Server pomocí Aspose.Tasks pro .NET. Automatizujte projektové úkoly bez námahy.
type: docs
weight: 23
url: /cs/net/project-management-integration/project-server-management/
---
## Úvod
tomto tutoriálu se ponoříme do správy MS Project Server pomocí Aspose.Tasks pro .NET. Aspose.Tasks je výkonná knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project programově, což umožňuje bezproblémovou integraci a manipulaci s daty projektu.
## Předpoklady
Než se pustíme do správy MS Project Server pomocí Aspose.Tasks, ujistěte se, že máte nastaveny následující předpoklady:
1. Microsoft Project Server: Potřebujete přístup k instanci Microsoft Project Server, kde máte oprávnění správce nebo alespoň oprávnění k vytváření a správě projektů.
2.  Aspose.Tasks for .NET Library: Ujistěte se, že jste si stáhli a nainstalovali knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/tasks/net/).
3. Přihlašovací údaje: Získejte potřebná pověření k ověření s instancí serveru MS Project Server. To obvykle zahrnuje uživatelské jméno a heslo.
## Importovat jmenné prostory
Než začnete, ujistěte se, že jste do svého kódu C# importovali požadované jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Krok 1: Nastavte ověřovací údaje
Nejprve musíte nastavit ověřovací údaje pro připojení k instanci serveru MS Project Server. To zahrnuje adresu domény, uživatelské jméno a heslo.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Krok 2: Načtěte projekt
Dále načtěte soubor MS Project, který chcete spravovat pomocí Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Krok 3: Vytvořte Project Server Manager
 Instantovat a`ProjectServerManager` objekt pomocí dříve definovaných přihlašovacích údajů.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Krok 4: Definujte možnosti uložení
Definujte jakékoli konkrétní možnosti uložení pro váš projekt. Můžete například nastavit časový limit operace.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Krok 5: Vytvořte nebo aktualizujte projekt
Nakonec vytvořte nebo aktualizujte projekt na MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Gratulujeme! Úspěšně jste spravovali MS Project Server pomocí Aspose.Tasks for .NET.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak spravovat MS Project Server programově pomocí Aspose.Tasks for .NET. S poskytnutými kroky můžete bezproblémově integrovat Aspose.Tasks do vašich aplikací .NET pro automatizaci úloh řízení projektů na MS Project Server.
## FAQ
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project Server?
Odpověď: Aspose.Tasks podporuje integraci s různými verzemi serveru Microsoft Project Server a zajišťuje kompatibilitu v různých prostředích.
### Otázka: Mohu provádět hromadné operace na projektech pomocí Aspose.Tasks?
Odpověď: Ano, Aspose.Tasks vám umožňuje provádět hromadné operace, jako je vytváření, aktualizace a mazání projektů na MS Project Server.
### Otázka: Poskytuje Aspose.Tasks podporu pro plánování projektů a správu zdrojů?
Odpověď: Aspose.Tasks nabízí komplexní podporu pro plánování projektů, alokaci zdrojů a funkce správy úkolů.
### Otázka: Je možné automatizovat úlohy sestavování pomocí Aspose.Tasks?
Odpověď: Ano, Aspose.Tasks vám umožňuje automatizovat generování vlastních zpráv na základě projektových dat, což usnadňuje efektivní monitorování a analýzu projektu.
### Otázka: Mohu vyzkoušet Aspose.Tasks před jeho zakoupením?
 Odpověď: Ano, můžete prozkoumat možnosti Aspose.Tasks přístupem k bezplatné zkušební verzi z[webová stránka](https://purchase.aspose.com/temporary-license/).