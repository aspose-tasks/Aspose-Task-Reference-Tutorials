---
title: Nastavení pro databázi Microsoft Project v Aspose.Tasks
linktitle: Nastavení pro databázi Microsoft Project v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se konfigurovat nastavení databáze Microsoft Project pomocí Aspose.Tasks pro bezproblémovou integraci do aplikací .NET.
weight: 19
url: /cs/net/advanced-concepts/msp-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení pro databázi Microsoft Project v Aspose.Tasks

## Úvod

Pokud pracujete s databázemi Microsoft Project ve svých aplikacích .NET pomocí Aspose.Tasks, budete muset nakonfigurovat potřebná nastavení pro bezproblémový import dat projektu. Tento tutoriál vás provede procesem krok za krokem.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks z[tady](https://releases.aspose.com/tasks/net/).
2. Přístup k databázi Microsoft Project: Měli byste mít přístup k databázi Microsoft Project pro import dat.

## Importovat jmenné prostory

Nejprve se ujistěte, že jste do projektu importovali potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Krok 1: Vytvořte připojovací řetězec

Vytvořte připojovací řetězec k databázi Microsoft Project. Zde je příklad:

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

Zajistěte, aby byly zástupné hodnoty nahrazeny vašimi skutečnými přihlašovacími údaji k databázi.

## Krok 2: Nakonfigurujte MspDbSettings

 Vytvořte instanci`MspDbSettings` a zadejte připojovací řetězec spolu s GUID projektu:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Krok 3: Načtěte data projektu

 Instantovat a`Project` objekt pomocí nakonfigurovaných nastavení:

```csharp
var project = new Project(settings);
```

## Krok 4: Uložte data projektu

Uložte načtená data projektu do souboru:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Závěr

V tomto kurzu jste se naučili, jak nakonfigurovat nastavení pro přístup k databázím Microsoft Project pomocí Aspose.Tasks for .NET. Dodržováním těchto kroků můžete bezproblémově importovat data projektu do svých aplikací a usnadnit tak efektivní správu projektů.

## FAQ

### Q1: Mohu použít Aspose.Tasks s různými verzemi databází aplikace Microsoft Project?

Odpověď 1: Ano, Aspose.Tasks podporuje různé verze databází Microsoft Project, což umožňuje flexibilitu při integraci.

### Q2: Jak mohu řešit problémy s připojením k databázi?

 A2: Ujistěte se, že váš připojovací řetězec je správně nakonfigurován s příslušnými pověřeními a podrobnostmi o databázi. Můžete se také podívat do dokumentace nebo požádat o podporu u[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: Je k dispozici zkušební verze pro Aspose.Tasks?

 A3: Ano, máte přístup k bezplatné zkušební verzi z[tady](https://releases.aspose.com/).

### Q4: Mohu přizpůsobit schéma pro interakci s databází?

 A4: Ano, můžete zadat schéma pro`MspDbSettings` objekt podle struktury vaší databáze.

### Q5: Kde najdu podrobnější dokumentaci k používání Aspose.Tasks?

 A5: Můžete prozkoumat komplexní dokumentaci[tady](https://reference.aspose.com/tasks/net/) pro podrobné informace o funkcích Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
