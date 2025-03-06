---
title: Nastavení databáze v Aspose.Tasks
linktitle: Nastavení databáze v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se importovat projekty z databáze Primavera pomocí Aspose.Tasks for .NET. Získejte podrobné pokyny v tomto komplexním tutoriálu.
weight: 29
url: /cs/net/calendar-scheduling/database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení databáze v Aspose.Tasks

## Úvod

Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project v jejich aplikacích .NET. V tomto tutoriálu se zaměříme na import projektů z databáze Primavera pomocí Aspose.Tasks.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#.
- Visual Studio nainstalované ve vašem systému.
-  Nainstalovaná knihovna Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
- Přístup k databázi Primavera spolu s nezbytnými oprávněními.

## Importovat jmenné prostory

Nejprve musíte do projektu C# importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro práci s Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Nyní rozdělme poskytnutý příklad kódu do několika kroků:

## Krok 1: Definujte připojovací řetězec

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 V tomto kroku definujeme připojovací řetězec pro připojení k databázi Primavera. Ujistěte se, že jste vyměnili`DataDir` s adresářem, kde se nachází váš databázový soubor.

## Krok 2: Vytvořte nastavení databáze

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Zde vytvoříme instanci`PrimaveraDbSettings` třídy, předáním připojovacího řetězce a ID projektu jako parametrů. Upravte ID projektu podle svých požadavků.

## Krok 3: Nastavte neměnný název poskytovatele

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Zadejte invariantní název poskytovatele. V tomto příkladu používáme SQLite, ale můžete jej změnit na základě vašeho poskytovatele databáze.

## Krok 4: Načtěte projekt

```csharp
var project = new Project(settings);
```

 Vytvoř nový`Project` objekt, předá nastavení databáze jako parametr.

## Krok 5: Uložte projekt

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Nakonec uložte projekt do požadovaného umístění se zadaným formátem souboru.

## Závěr

V tomto tutoriálu jsme se naučili importovat projekty z databáze Primavera pomocí Aspose.Tasks for .NET. Dodržováním uvedených kroků můžete bezproblémově integrovat funkci importu projektu do aplikací .NET.

## FAQ

### Q1: Mohu importovat projekty od různých poskytovatelů databází pomocí Aspose.Tasks for .NET?

Odpověď 1: Ano, můžete importovat projekty od různých poskytovatelů databází odpovídajícím přizpůsobením připojovacího řetězce a invariantního názvu poskytovatele.

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?

 A2: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET od[tady](https://releases.aspose.com/).

### Q3: Kde najdu dokumentaci pro Aspose.Tasks pro .NET?

 A3: Můžete najít dokumentaci[tady](https://reference.aspose.com/tasks/net/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

 Odpověď 4: Podporu můžete získat na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).

### Q5: Potřebuji dočasnou licenci k používání Aspose.Tasks pro .NET?

 A5: Pokud chcete otestovat plnou funkčnost knihovny, můžete získat dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
