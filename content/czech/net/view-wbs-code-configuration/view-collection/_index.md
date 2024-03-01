---
title: Snadná správa zobrazení MS Project s Aspose.Tasks .NET
linktitle: Kolekce pohledů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte Aspose.Tasks for .NET a ovládněte umění správy MS Project Views bez námahy. Stáhněte si nyní pro bezproblémové řízení projektů.
type: docs
weight: 11
url: /cs/net/view-wbs-code-configuration/view-collection/
---
## Úvod
Vítejte ve světě Aspose.Tasks for .NET, výkonné knihovny, která umožňuje vývojářům efektivně spravovat Microsoft Project Views v jejich aplikacích .NET. V tomto tutoriálu se ponoříme do základů manipulace s MS Project Views pomocí Aspose.Tasks a poskytneme vám podrobného průvodce pro vylepšení schopností řízení projektů.
## Předpoklady
Než se vydáme na tuto cestu, ujistěte se, že máte splněny následující předpoklady:
-  Knihovna Aspose.Tasks: Stáhněte a nainstalujte knihovnu Aspose.Tasks z[tady](https://releases.aspose.com/tasks/net/).
- .NET Framework: Ujistěte se, že máte na svém vývojovém počítači nainstalováno rozhraní .NET Framework.
## Importovat jmenné prostory
Chcete-li začít, importujte do projektu potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Nastavte svůj projekt
Začněte inicializací projektu pomocí knihovny Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
## Krok 2: Upravte existující pohledy
Procházejte seznam pohledů a podle potřeby provádějte úpravy. V tomto příkladu změníme text záhlaví každého zobrazení.
```csharp
List<View> list = project.Views.ToList();
for (var index = 0; index < list.Count; index++)
{
    var viewToChange = list[index];
    viewToChange.PageInfo.Header.CenteredText = "Header " + index;
}
```
## Krok 3: Přidejte nový pohled
Rozšiřte svůj projekt přidáním nového pohledu, jako je Ganttův diagram.
```csharp
var view = new GanttChartView();
if (!project.Views.IsReadOnly)
{
    project.Views.Add(view);
}
```
## Krok 4: Opakujte zobrazení
Zobrazí informace o existujících pohledech v rámci projektu.
```csharp
Console.WriteLine("Iterate over views of " + project.Views.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Project view count: " + project.Views.Count);
Console.WriteLine();
foreach (var projectView in project.Views)
{
    Console.WriteLine("Name: " + projectView.Name);
}
```
## Krok 5: Odeberte pohledy
Přečtěte si, jak odebrat zobrazení buď všechna najednou, nebo jeden po druhém.
### Přístup 1:
```csharp
List<View> listToDelete = project.Views.ToList();
foreach (var v in listToDelete)
{
    if (project.Views.Contains(v))
    {
        project.Views.Remove(v);
    }
}
```
### Přístup 2:
```csharp
var array = new View[project.Views.Count];
project.Views.CopyTo(array, 0);
foreach (var v in array)
{
    if (project.Views.Contains(v))
    {
        project.Views.Remove(v);
    }
}
```
## Závěr
Gratulujeme! Úspěšně jste prošli prostředím Aspose.Tasks for .NET a zvládli jste umění správy MS Project Views. Nyní využijte plný potenciál této knihovny ve svých projektech pro bezproblémové řízení projektů.
## Nejčastější dotazy
### Je Aspose.Tasks kompatibilní s nejnovějšími verzemi rozhraní .NET Framework?
Aspose.Tasks je navržen tak, aby byl kompatibilní s různými verzemi rozhraní .NET Framework. Konkrétní podrobnosti naleznete v dokumentaci.
### Mohu přizpůsobit vzhled zobrazení Ganttova diagramu?
Absolutně! Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení vzhledu zobrazení Ganttova diagramu tak, aby vyhovoval potřebám vašeho projektu.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat podporu komunity pro Aspose.Tasks?
 Zapojte se do komunity Aspose.Tasks na[Fórum](https://forum.aspose.com/c/tasks/15) pro jakékoli dotazy nebo pomoc.
### Jsou pro Aspose.Tasks dostupné dočasné licence?
 Ano, prozkoumat dočasné licence[tady](https://purchase.aspose.com/temporary-license/).