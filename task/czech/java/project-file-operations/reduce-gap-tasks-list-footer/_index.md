---
title: Snížení mezery mezi seznamem úkolů a zápatím v Aspose.Tasks
linktitle: Snížení mezery mezi seznamem úkolů a zápatím v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak zmenšit mezeru mezi seznamy úkolů a zápatí MS Project pomocí Aspose.Tasks for Java. Optimalizujte rozvržení projektového dokumentu bez námahy.
type: docs
weight: 10
url: /cs/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Úvod
V tomto tutoriálu se ponoříme do zmenšení mezery mezi seznamem úkolů a zápatím v souborech Microsoft Project pomocí Aspose.Tasks for Java. Podle těchto kroků budete moci snadno optimalizovat rozvržení vašich projektových dokumentů.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Knihovna Aspose.Tasks for Java: Stáhněte si a zahrňte knihovnu Aspose.Tasks for Java do svého projektu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Než se ponoříme do kódovací části, importujme potřebné balíčky:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Krok 1: Zadejte cestu k vašemu datovému adresáři
```java
String dataDir = "Your Data Directory";
```
 Nezapomeňte vyměnit`"Your Data Directory"` s cestou k vašemu skutečnému datovému adresáři, kde je váš soubor Microsoft Project (`HomeMovePlan.mpp` v tomto příkladu) se nachází.
## Krok 2: Přečtěte si soubor MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Tento řádek kódu přečte soubor aplikace Microsoft Project s názvem`HomeMovePlan.mpp`.
## Krok 3: Nastavte ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Nakonfigurujte možnosti uložení obrázku, nastavení`ReduceFooterGap` na`true` zmenšit mezeru mezi seznamem úkolů a zápatím.
## Krok 4: Uložit jako obrázek
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Uložte projekt jako obrázek s nakonfigurovanými možnostmi.
## Krok 5: Nastavte možnosti PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Definujte možnosti uložení PDF a ujistěte se, že je nastavíte`ReduceFooterGap` na`true`.
## Krok 6: Uložit jako PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Uložte projekt jako PDF s nakonfigurovanými možnostmi.
## Krok 7: Nastavte možnosti HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // nastaveno na true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Zadejte možnosti uložení HTML, nastavení`ReduceFooterGap` na`true`.
## Krok 8: Uložit jako HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Uložte projekt jako soubor HTML s nakonfigurovanými možnostmi.

## Závěr
Závěrem lze říci, že zmenšení mezery mezi seznamem úkolů a zápatím v souborech Microsoft Project je s Aspose.Tasks for Java jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete efektivně optimalizovat rozvržení vašich projektových dokumentů.

## FAQ

### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?

Odpověď: Aspose.Tasks podporuje formáty Microsoft Project 2003-2019 a zajišťuje kompatibilitu napříč různými verzemi.

### Otázka: Mohu upravit vzhled zápatí v mých projektových dokumentech?

Odpověď: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení vzhledu zápatí, včetně zmenšení mezer a úpravy umístění obsahu.

### Otázka: Podporuje Aspose.Tasks ukládání projektů v jiných formátech než PNG, PDF a HTML?

Odpověď: Ano, Aspose.Tasks podporuje širokou škálu formátů, mimo jiné včetně XLSX, XML a MPP.

### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks?

 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).

### Otázka: Kde mohu získat podporu, pokud při používání Aspose.Tasks narazím na nějaké problémy?

 Odpověď: Pomoc můžete získat na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).