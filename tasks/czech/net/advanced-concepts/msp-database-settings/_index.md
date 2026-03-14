---
date: 2026-03-14
description: Naučte se, jak pomocí Aspose.Tasks specifikovat schéma databáze pro databázi
  Microsoft Project a jak importovat projektová data do aplikací .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Specifikujte schéma databáze pro projektovou databázi s Aspose.Tasks
url: /cs/net/advanced-concepts/msp-database-settings/
weight: 19
---

ychlé odpovědi". Good.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení databáze Microsoft Project v Aspose.Tasks

## Úvod

Pokud pracujete s databázemi Microsoft Project ve svých .NET aplikacích pomocí Aspose.Tasks, budete muset **specifikovat schéma databáze** a nakonfigurovat potřebná nastavení pro **bezproblémový import dat projektu**. Tento tutoriál vás provede procesem krok za krokem a ukáže vám **jak nakonfigurovat připojení**, **vytvořit .NET connection string** a nakonec **uložit projekt jako MPP**.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Specifikovat schéma databáze a importovat databázi Project do .NET aplikace.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro .NET.  
- **Jak se připojím k Project Serveru?** Vytvořením správného SQL connection stringu a použitím `MspDbSettings`.  
- **Jaký formát souboru se vytvoří?** Soubor MPP uložený pomocí `SaveFileFormat.Mpp`.  
- **Mohu změnit název schématu?** Ano, nastavte vlastnost `Schema` na `MspDbSettings`.

## Jak specifikovat schéma databáze pro Project DB

Pochopení toho, proč můžete potřebovat **specifikovat schéma databáze**, je zásadní. V mnoha podnikových prostředích databáze Project Serveru sídlí pod vlastním schématem (např. `dbo`, `psdata`). Explicitním nastavením schématu zajistíte, že Aspose.Tasks dotazuje správné tabulky, čímž předejdete chybám za běhu a zajistíte přesný import dat.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Aspose.Tasks pro .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks z [zde](https://releases.aspose.com/tasks/net/).  
2. Přístup k databázi Microsoft Project: Měli byste mít přístup k databázi Microsoft Project, ze které chcete importovat data.  

## Import jmenných prostor

Nejprve se ujistěte, že do svého projektu importujete potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Krok 1: Vytvoření connection stringu

Sestavte connection string k vaší databázi Microsoft Project. Zde **vytvoříte .NET connection string** a také definujete, jak **se připojit k Project Serveru**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Tip:** Dvakrát zkontrolujte hodnoty `DataSource` a `InitialCatalog`; musí odpovídat adrese vašeho serveru a názvu publikované databáze.

## Krok 2: Konfigurace MspDbSettings

Vytvořte instanci `MspDbSettings`, předávejte connection string a **specifikujte schéma databáze** nastavením vlastnosti `Schema`. Tím řeknete Aspose.Tasks, které schéma má dotazovat.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Zde také poskytujeme GUID projektu, který identifikuje konkrétní projekt, který chcete načíst.

## Krok 3: Načtení dat projektu

Vytvořte objekt `Project` pomocí nakonfigurovaných nastavení. Tento krok efektivně **importuje data projektu** z databáze do .NET objektu.

```csharp
var project = new Project(settings);
```

## Krok 4: Uložení dat projektu

Nakonec uložte načtený projekt do souboru MPP na disku. Toto ukazuje **uložení projektu jako MPP** pomocí API Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Po spuštění kódu najdete soubor `ImportProjectDataFromDatabase_out.mpp` ve výstupním adresáři, připravený k otevření v Microsoft Project.

## Závěr

V tomto tutoriálu jste se naučili, jak **specifikovat schéma databáze** pro databázi Microsoft Project, **konfigurovat připojení**, **importovat data projektu** a **uložit projekt jako MPP** pomocí Aspose.Tasks pro .NET. Tyto kroky umožňují bezproblémovou integraci dat Project Serveru do vašich vlastních aplikací a pomáhají vám vytvářet robustní řešení pro řízení projektů.

## Často kladené otázky

### Q1: Mohu použít Aspose.Tasks s různými verzemi databází Microsoft Project?
A1: Ano, Aspose.Tasks podporuje různé verze databází Microsoft Project, což umožňuje flexibilní integraci.

### Q2: Jak mohu řešit problémy s připojením k databázi?
A2: Ujistěte se, že je váš connection string správně nakonfigurován s odpovídajícími přihlašovacími údaji a podrobnostmi o databázi. Můžete také nahlédnout do dokumentace nebo požádat o podporu na [Aspose.Tasks fóru](https://forum.aspose.com/c/tasks/15).

### Q3: Je k dispozici zkušební verze Aspose.Tasks?
A3: Ano, můžete získat bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

### Q4: Mohu přizpůsobit schéma pro interakci s databází?
A4: Ano, můžete specifikovat schéma pro objekt `MspDbSettings` podle struktury vaší databáze.

### Q5: Kde najdu podrobnější dokumentaci k používání Aspose.Tasks?
A5: Podrobnou dokumentaci můžete prozkoumat [zde](https://reference.aspose.com/tasks/net/) pro detailní informace o funkcionalitách Aspose.Tasks.

**Q: Funguje tento přístup s databázemi Azure SQL?**  
A: Rozhodně. Stačí upravit `DataSource` na název vašeho Azure serveru a zajistit, aby byly povoleny nastavení TLS/SSL.

**Q: Jak zvládnout velké databáze Project bez časového limitu?**  
A: Zvyšte hodnotu `ConnectTimeout` v connection stringu a v případě potřeby načítejte projekty po dávkách.

---

**Poslední aktualizace:** 2026-03-14  
**Testováno s:** Aspose.Tasks 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}