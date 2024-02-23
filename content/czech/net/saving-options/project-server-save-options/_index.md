---
title: Server Uložit možnosti MS Project pro Aspose.Tasks
linktitle: Možnosti uložení Project Server pro Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Přečtěte si, jak uložit možnosti aplikace Microsoft Project pro Aspose.Tasks pomocí integrace Project Server. Vylepšete své pracovní postupy projektového řízení.
type: docs
weight: 16
url: /cs/net/saving-options/project-server-save-options/
---
## Úvod
V tomto tutoriálu se ponoříme do ukládání možností aplikace Microsoft Project pro Aspose.Tasks pomocí serveru Project Server. Aspose.Tasks je výkonné rozhraní .NET API, které umožňuje vývojářům pracovat se soubory Microsoft Project programově. Využitím možností Project Serveru můžeme bezproblémově integrovat Aspose.Tasks do našich pracovních postupů projektového řízení. Tento tutoriál vás provede procesem krok za krokem.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1.  Aspose.Tasks pro .NET: Nainstalujte Aspose.Tasks pro .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
   
2. Přístup k serveru Project Server: Budete potřebovat přístupové údaje a adresu URL instance serveru Project Server. Pokud jej nemáte, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).
3. Soubor Microsoft Project: Připravte soubor Microsoft Project (.mpp), který chcete uložit pomocí Aspose.Tasks.

## Importovat jmenné prostory
Nejprve musíte do projektu importovat potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Krok 1: Inicializujte projekt a přihlašovací údaje
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Ujistěte se, že vyměníte`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,a`Password` s vašimi skutečnými hodnotami.
## Krok 2: Vytvořte Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Krok 3: Definujte možnosti uložení
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Upravte`ProjectGuid`, `ProjectName`, `Timeout` ,a`PollingInterval` dle vašich požadavků.
## Krok 4: Uložte projekt na server
```csharp
manager.CreateNewProject(project, options);
```
Tím se projekt uloží na Project Server se zadanými možnostmi.

## Závěr
V tomto tutoriálu jsme se naučili, jak uložit možnosti aplikace Microsoft Project pro Aspose.Tasks pomocí integrace Project Server. Dodržováním těchto kroků můžete bez problémů začlenit Aspose.Tasks do svých pracovních postupů projektového řízení, čímž zvýšíte efektivitu a produktivitu.
## FAQ
### Otázka: Mohu používat Aspose.Tasks s různými verzemi aplikace Microsoft Project?
Odpověď: Ano, Aspose.Tasks podporuje různé verze Microsoft Project a zajišťuje kompatibilitu v různých prostředích.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks od[tady](https://releases.aspose.com/).
### Otázka: Podporuje Aspose.Tasks vícevláknové zpracování?
Odpověď: Ano, Aspose.Tasks je navržen tak, aby byl bezpečný pro vlákna a umožňoval souběžný přístup k datům projektu.
### Otázka: Mohu přizpůsobit možnosti ukládání při použití integrace Project Server?
Odpověď: Ano, můžete přizpůsobit možnosti ukládání, jako je název projektu, časový limit a interval dotazování, aby vyhovovaly vašim požadavkům.
### Otázka: Kde najdu podporu pro Aspose.Tasks?
 Odpověď: Podporu a pomoc najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).