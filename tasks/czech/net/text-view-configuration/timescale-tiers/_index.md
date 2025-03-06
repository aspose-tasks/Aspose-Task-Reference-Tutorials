---
title: Konfigurace vrstev časové osy Ganttova diagramu v Aspose.Tasks
linktitle: Konfigurace vrstev časové osy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte Aspose.Tasks for .NET a nakonfigurujte úrovně časové osy v zobrazení Ganttova diagramu pro přesnou vizualizaci časové osy projektu. #Apose.Tasks #MS Project
weight: 16
url: /cs/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurace vrstev časové osy Ganttova diagramu v Aspose.Tasks

## Úvod
V dynamickém prostředí projektového řízení je efektivní vizualizace zásadní pro pochopení časových os a termínů. Aspose.Tasks for .NET poskytuje výkonnou sadu nástrojů a v tomto tutoriálu prozkoumáme, jak nakonfigurovat vrstvy časové osy pro optimální reprezentaci v zobrazení Ganttova diagramu. Chcete-li zlepšit vizualizaci projektu, postupujte podle těchto podrobných pokynů.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující:
- Základní znalost C# a .NET.
-  Nainstalovaná knihovna Aspose.Tasks for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
- Vývojové prostředí nastavené pro vývoj aplikací .NET.
## Importovat jmenné prostory
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Nyní si rozeberme jednotlivé kroky poskytnutého příkladu.
## Krok 1: Inicializujte projekt a přidejte odkazy na úkoly
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Zde vytvoříme projekt a vytvoříme propojení úkolů mezi „Úkolem 1“ a „Úkolem 2“.
## Krok 2: Konfigurace zobrazení Ganttova diagramu
```csharp
var view = (GanttChartView)project.DefaultView;
```
Přístup k zobrazení Ganttova diagramu pro přizpůsobení.
## Krok 3: Vylaďte střední časovou úroveň
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Přizpůsobte střední časovou osu tak, aby zobrazovala týdny s konkrétními štítky a zarovnáním.
## Krok 4: Přidejte nejvyšší časovou úroveň
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Přidejte nejvyšší časovou úroveň, která bude představovat měsíce.
## Krok 5: Přizpůsobte data střední úrovně
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Přizpůsobte si štítky měsíců pro lepší vizualizaci.
## Krok 6: Nastavte časovou os projektu
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Definujte časovou osu projektu, abyste řídili celkovou časovou osu.
## Krok 7: Uložte projekt s přizpůsobenou časovou osou
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Uložte projekt s definovaným nastavením časové osy.
## Závěr
Na závěr lze konstatovat, že konfigurace vrstev časové osy v Aspose.Tasks pro .NET umožňuje lépe přizpůsobenou a vizuálně přitažlivou reprezentaci časových os projektů. Tyto kroky vám umožní vytvořit zobrazení Ganttova diagramu, které přesně vyhovuje vašim potřebám projektového řízení.
## Nejčastější dotazy
### Mohu používat Aspose.Tasks s jinými knihovnami .NET?
Ano, Aspose.Tasks se hladce integruje s ostatními knihovnami .NET a nabízí flexibilitu ve vašem vývojovém zásobníku.
### Je k dispozici dočasná licence pro účely testování?
 Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro hodnocení.
### Existují další možnosti přizpůsobení zobrazení Ganttova diagramu?
Aspose.Tasks rozhodně poskytuje rozsáhlé možnosti přizpůsobení pro zobrazení Ganttova diagramu, aby vyhovoval různým požadavkům projektu.
### Mohu vykreslit časové osy v různých formátech?
Jistě můžete prozkoumat různé formáty a styly pro reprezentaci časové osy, aby co nejlépe odpovídaly kontextu vašeho projektu.
### Existuje komunitní fórum pro podporu Aspose.Tasks?
 Ano, navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a diskuze.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
