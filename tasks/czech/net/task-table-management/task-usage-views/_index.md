---
title: Mastering Task Usage Views v Aspose.Tasks for .NET
linktitle: Konfigurace zobrazení využití úkolů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte Aspose.Tasks for .NET a zjistěte, jak nakonfigurovat zobrazení využití úloh. Přizpůsobte nastavení časové osy a vylepšete vizuály řízení projektů.
weight: 24
url: /cs/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Task Usage Views v Aspose.Tasks for .NET

## Úvod
oblasti projektového managementu je vizualizace využití úkolů klíčová pro efektivní plánování a realizaci. Aspose.Tasks for .NET poskytuje robustní řešení pro vykreslování zobrazení využití úloh, což vám umožňuje přizpůsobit nastavení časové osy a formáty prezentace. V tomto tutoriálu si projdeme kroky ke konfiguraci zobrazení využití úloh pomocí Aspose.Tasks.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Tasks for .NET: Ujistěte se, že máte knihovnu Aspose.Tasks integrovanou do vašeho projektu .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
2. Prostředí .NET: Mějte na svém počítači nastavené funkční prostředí .NET.
## Importovat jmenné prostory
Ve svém projektu .NET importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Tasks. Přidejte do kódu následující řádky:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Krok 1: Nastavte cestu k adresáři dokumentu
 Než začnete pracovat s funkcemi Aspose.Tasks, nastavte cestu k adresáři vašich dokumentů. Nahradit`"Your Document Directory"` se skutečnou cestou.
```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Načtěte projekt
 Inicializujte soubor Aspose.Tasks`Project` objekt načtením souboru vašeho projektu (např. TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Krok 3: Definujte možnosti SaveOptions
 Vytvořit`SaveOptions`objekt k určení možností vykreslování. Nastavte časovou os na 'Dny' a formát prezentace na 'TaskUsage'.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Krok 4: Uložte s časovou osou dnů
Uložte projekt s předdefinovaným nastavením časové osy 'Dny'.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Krok 5: Uložte s časovou osou ThirdsOfMonths
Změňte nastavení časové osy na 'ThirdsOfMonths' a uložte projekt.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Krok 6: Uložte s časovou osou měsíců
Nastavte časové měřítko na „Měsíce“ a uložte projekt s aktualizovaným nastavením.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Závěr
Konfigurace zobrazení využití úloh pomocí Aspose.Tasks for .NET je jednoduchý proces. Přizpůsobením nastavení časové osy můžete přizpůsobit vizualizaci úkolů projektu podle svých konkrétních potřeb.
 Neváhejte a prozkoumejte další vlastnosti a funkce v[dokumentace](https://reference.aspose.com/tasks/net/).
## Často kladené otázky
### Mohu přizpůsobit časovou os nad rámec předdefinovaných nastavení?
Ano, můžete nastavit vlastní časové měřítko zadáním intervalů a jednotek.
### Jsou k dispozici další formáty prezentace?
Aspose.Tasks podporuje různé formáty prezentací, včetně GanttChart, ResourceUsage a dalších.
### Je Aspose.Tasks kompatibilní s různými formáty souborů projektu?
Ano, Aspose.Tasks podporuje oblíbené formáty projektových souborů, jako jsou MPP, XML a CSV.
### Mohu na konkrétní úkoly použít různá nastavení časové osy?
Absolutně si můžete přizpůsobit nastavení časové osy pro jednotlivé úkoly v rámci vašeho projektu.
### Jak mohu získat podporu nebo vyhledat pomoc pro Aspose.Tasks?
 Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu a vedení komunity.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
