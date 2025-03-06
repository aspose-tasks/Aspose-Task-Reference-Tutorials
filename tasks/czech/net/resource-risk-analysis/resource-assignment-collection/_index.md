---
title: Kolekce přiřazení zdrojů v Aspose.Tasks
linktitle: Kolekce přiřazení zdrojů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se spravovat přiřazení zdrojů v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. Výukový program krok za krokem s příklady kódu.
weight: 12
url: /cs/net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kolekce přiřazení zdrojů v Aspose.Tasks

## Úvod
Vítejte v tomto komplexním kurzu o správě přiřazení zdrojů v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. V tomto tutoriálu se ponoříme do procesu krok za krokem a zajistíme, že budete dobře rozumět tomu, jak efektivně manipulovat s přiřazením zdrojů. Ať už jste zkušený vývojář nebo teprve začínáte, tento průvodce vás provede vším, co potřebujete vědět.
## Předpoklady
Než se ponoříme do kódu, ujistěte se, že máte následující nastavení:
1.  Nainstalované Aspose.Tasks for .NET: Ujistěte se, že máte ve svém vývojovém prostředí nainstalované Aspose.Tasks for .NET. Pokud ne, můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Základní znalost C#: Tento tutoriál předpokládá, že máte základní znalosti programovacího jazyka C#.
3. Soubor Microsoft Project: Připravte si soubor Microsoft Project pro testovací účely. Pokud žádný nemáte, můžete vytvořit ukázkový soubor.

## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Načtěte soubor projektu
Začněte načtením souboru Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Krok 2: Přidejte úkol a zdroj
Nyní do projektu přidáme úkol a zdroj:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Krok 3: Přiřaďte zdroj k úkolu
Dále přiřadíme zdroj k úkolu:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Krok 4: Práce s různými typy přiřazení
Můžete také pracovat s úkoly zahrnujícími jednotky nebo náklady:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Nastavte vlastnosti pro přiřazení s jednotkami a náklady podobně, jak je uvedeno v kroku 3
```
## Krok 5: Tisk úloh
Vytiskněte si zadání k projektu:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Vytiskněte podrobnosti úkolu
}
```
## Krok 6: Načtení přiřazení podle UID
Úkoly můžete načíst podle UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Krok 7: Zkontrolujte stav pouze pro čtení
Ověřte, zda je kolekce přiřazení prostředků pouze pro čtení:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Krok 8: Převeďte kolekci na seznam a iterujte
Převeďte kolekci na seznam a iterujte jej:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Závěr
Gratulujeme! Naučili jste se, jak spravovat přiřazení zdrojů v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. Dodržováním těchto kroků můžete efektivně manipulovat s úkoly a zdroji, takže řízení projektů bude hračkou.
## FAQ
### Otázka: Mohu používat Aspose.Tasks pro .NET s různými verzemi souborů Microsoft Project?
Odpověď: Ano, Aspose.Tasks for .NET podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.
### Otázka: Je před zakoupením Aspose.Tasks pro .NET k dispozici zkušební verze?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET od[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu, pokud při používání Aspose.Tasks pro .NET narazím na nějaké problémy?
 Odpověď: Podporu můžete vyhledat na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Mohu použít dočasné licence pro Aspose.Tasks pro .NET?
 Odpověď: Ano, dočasné licence jsou k dispozici pro účely hodnocení. Můžete získat jeden od[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde si mohu zakoupit plnou licenci pro Aspose.Tasks pro .NET?
 Odpověď: Plnou licenci si můžete zakoupit v online obchodu Aspose[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
