---
title: Správa kolekce zdrojů projektu v Aspose.Tasks
linktitle: Správa kolekce zdrojů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se efektivně spravovat kolekce prostředků Microsoft Project v .NET pomocí Aspose.Tasks API. Zvyšte produktivitu a flexibilitu.
type: docs
weight: 13
url: /cs/net/resource-risk-analysis/managing-resource-collection/
---
## Úvod
V tomto kurzu prozkoumáme, jak efektivně spravovat kolekce prostředků Microsoft Project pomocí Aspose.Tasks for .NET. Aspose.Tasks je výkonné API, které umožňuje vývojářům pracovat se soubory Microsoft Project programově, což umožňuje bezproblémovou integraci a manipulaci s daty projektu.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1. Znalost C# a .NET Framework: Tento tutoriál předpokládá znalost programovacího jazyka C# a .NET Framework.
2. Instalace Aspose.Tasks pro .NET: Ujistěte se, že jste nainstalovali Aspose.Tasks pro .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
3. Nastavení vývojového prostředí: Nastavte své vývojové prostředí pomocí sady Visual Studio nebo jiného preferovaného IDE.

## Importovat jmenné prostory
Než začneme, importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Krok 1: Načtěte soubor projektu
Nejprve načtěte soubor Microsoft Project do objektu projektu Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Krok 2: Přidejte prázdný zdroj
Dále do projektu přidáme prázdný zdroj:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Krok 3: Přidejte zdroj s názvem
Nyní do projektu přidejte zdroj se zadaným názvem:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Krok 4: Přidejte zdroj před další zdroj
Přidejte zdroj se zadaným názvem před jiný zdroj na základě jeho ID:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Krok 5: Přístup ke zdrojům podle ID nebo UID
Ke zdrojům můžete přistupovat buď pomocí jejich ID nebo UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Krok 6: Tisk informací o zdrojích
Tisk informací o zdrojích projektu:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Krok 7: Odstranění zdrojů
Odstranit zdroje z projektu:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Závěr
Správa kolekcí zdrojů Microsoft Project pomocí Aspose.Tasks for .NET poskytuje vývojářům robustní sadu nástrojů pro efektivní programové zacházení se zdroji projektu. Podle kroků popsaných v tomto kurzu můžete bez problémů manipulovat se zdroji ve svých projektech, čímž zvýšíte produktivitu a flexibilitu v úlohách projektového řízení.
## FAQ
### Otázka: Dokáže Aspose.Tasks zpracovat rozsáhlé soubory projektů?

Odpověď: Ano, Aspose.Tasks je navržen tak, aby efektivně zpracovával rozsáhlé soubory projektů a nabízí vysoký výkon a spolehlivost.

### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi Microsoft Project?

Odpověď: Aspose.Tasks podporuje různé verze aplikace Microsoft Project a zajišťuje kompatibilitu v různých prostředích.

### Otázka: Mohu upravit vlastnosti prostředků pomocí Aspose.Tasks?

Odpověď: Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení vlastností zdrojů podle konkrétních požadavků projektu.

### Otázka: Podporuje Aspose.Tasks vícevláknové zpracování pro souběžné operace?

Odpověď: Ano, Aspose.Tasks podporuje multi-threading, což umožňuje souběžné operace s daty projektu pro zlepšení výkonu.

### Otázka: Je pro uživatele Aspose.Tasks k dispozici technická podpora?

 Odpověď: Ano, uživatelé Aspose.Tasks mají přístup k technické podpoře prostřednictvím fóra[tady](https://forum.aspose.com/c/tasks/15).