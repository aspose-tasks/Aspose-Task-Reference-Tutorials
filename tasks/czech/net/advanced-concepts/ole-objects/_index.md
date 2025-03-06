---
title: Práce s objekty OLE v Aspose.Tasks
linktitle: Práce s objekty OLE v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně pracovat s objekty OLE v aplikacích .NET pomocí Aspose.Tasks, čímž se rozšíří možnosti řízení projektů.
type: docs
weight: 22
url: /cs/net/advanced-concepts/ole-objects/
---
## Úvod

Aspose.Tasks for .NET poskytuje komplexní funkce pro práci s objekty OLE (Object Linking and Embedding) v rámci souborů projektu. Tento tutoriál vás provede procesem efektivní správy objektů OLE pomocí Aspose.Tasks ve vašich aplikacích .NET.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Instalace: Ujistěte se, že máte ve vývojovém prostředí nainstalovaný Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

2. Základní znalosti: Seznamte se s programovacím jazykem C# a koncepty frameworku .NET.

3. Vývojové prostředí: Nastavte vhodné vývojové prostředí, jako je Visual Studio.

## Importovat jmenné prostory

Nejprve importujte potřebné jmenné prostory pro přístup k funkci Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;


```

Nyní si každý příklad rozdělíme do několika kroků ve formátu podrobného průvodce:

## Práce s OLE objekty

### Krok 1: Načtěte soubor projektu
```csharp
var project = new Project("TaskImage2010.mpp");
```

### Krok 2: Přístup k objektům OLE
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

### Krok 3: Iterace přes objekty OLE
```csharp
foreach (var oleObject in oleObjects)
{
    // Přístup a tisk vlastností objektu OLE
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Pokračujte pro další vlastnosti
}
```

### Krok 4: Načtení bajtů obsahu
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

## Vymazání objektů OLE

### Krok 1: Načtěte soubor projektu
```csharp
var project = new Project("TaskImage2010.mpp");
```

### Krok 2: Vymažte objekty OLE
```csharp
project.OleObjects.Clear();
```

### Krok 3: Uložte projekt
```csharp
project.Save("ClearedProject.mpp");
```

## Získání vlastností umístění vizuálních objektů

### Krok 1: Načtěte soubor projektu
```csharp
var project = new Project("TaskImage2010.mpp");
```

### Krok 2: Přístup k objektu OLE a umístění vizuálního objektu
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

### Krok 3: Načtení vlastností
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak efektivně pracovat s objekty OLE v Aspose.Tasks for .NET. Podle těchto podrobných příkladů můžete do svých aplikací .NET bez problémů integrovat možnosti správy objektů OLE a vylepšit tak jejich funkčnost a použitelnost.

## FAQ

### Q1: Může Aspose.Tasks zpracovat různé formáty objektů OLE?

Odpověď 1: Ano, Aspose.Tasks podporuje širokou škálu formátů objektů OLE včetně obrázků, dokumentů a multimediálních souborů.

### Q2: Je Aspose.Tasks kompatibilní s různými verzemi souborů aplikace?

Odpověď 2: Ano, Aspose.Tasks podporuje různé verze souborů aplikace Microsoft Project, což zajišťuje kompatibilitu a bezproblémovou integraci.

### Q3: Mohu manipulovat s umístěním objektu OLE v rámci zobrazení projektu?

A3: Absolutně, Aspose.Tasks poskytuje rozhraní API pro správu umístění a vzhledu vlastností objektů OLE v rámci zobrazení projektu.

### Q4: Je Aspose.Tasks vhodný pro projekty na podnikové úrovni?

Odpověď 4: Ano, Aspose.Tasks se dobře hodí pro malé projekty i projekty na podnikové úrovni a nabízí robustní funkce a spolehlivý výkon.

### Q5: Nabízí Aspose.Tasks zákaznickou podporu a dokumentaci?

Odpověď 5: Ano, Aspose.Tasks poskytuje rozsáhlou dokumentaci, fóra a zákaznickou podporu, která vývojářům pomáhá efektivně využívat její funkce.