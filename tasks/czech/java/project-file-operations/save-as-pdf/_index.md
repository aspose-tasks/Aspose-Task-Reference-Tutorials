---
title: Uložit jako PDF v Aspose.Tasks
linktitle: Uložit jako PDF v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se převádět soubory projektu do PDF pomocí Aspose.Tasks for Java. Jednoduché kroky pro efektivní konverzi.
weight: 17
url: /cs/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložit jako PDF v Aspose.Tasks

## Úvod
tomto tutoriálu vás provedeme procesem uložení projektu jako PDF pomocí Aspose.Tasks for Java. Pomocí Aspose.Tasks můžete efektivně převádět soubory projektu do formátu PDF, což zajišťuje kompatibilitu a snadné sdílení. Pojďme se ponořit do kroků:
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java Library: Stáhněte a nainstalujte knihovnu Aspose.Tasks. Odkaz ke stažení najdete[tady](https://releases.aspose.com/tasks/java/).
3. Soubor projektu: Připravte si soubor projektu (např. HomeMovePlan.mpp), který chcete převést do PDF.

## Importujte balíčky
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Krok 1: Přečtěte si soubor vstupního projektu
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Ujistěte se, že vyměníte`"Your Data Directory"` s cestou k vašemu datovému adresáři obsahujícímu soubor projektu.
## Krok 2: Uložte projekt jako PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Tento fragment kódu uloží projekt jako soubor PDF s názvem „Project5.pdf“.
## Krok 3: Přizpůsobení obsahu velikosti buňky
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Zde nastavujeme možnosti pro uložení PDF, včetně přizpůsobení obsahu, časové osy a formátu prezentace.
## Krok 4: Skryjte legendy
```java
o.setLegendOnEachPage(false);
```
Tento krok skryje legendy na každé stránce PDF.
## Krok 5: Uložte projekt s použitými možnostmi
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Nakonec tento kód uloží projekt s aplikovanými možnostmi do souboru PDF.

## Závěr
V tomto tutoriálu jsme se naučili používat Aspose.Tasks pro Javu k uložení projektu jako PDF. Pomocí těchto jednoduchých kroků můžete efektivně převádět soubory projektu pro snadné sdílení a distribuci.
## FAQ
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Java?
Odpověď: Ano, Aspose.Tasks podporuje verze Java začínající od JDK 6 a vyšší.
### Otázka: Mohu přizpůsobit vzhled výstupu PDF?
A: Rozhodně! Aspose.Tasks poskytuje různé možnosti přizpůsobení výstupu PDF podle vašich požadavků.
### Otázka: Podporuje Aspose.Tasks jiné formáty souborů pro převod?
Odpověď: Ano, Aspose.Tasks podporuje širokou škálu formátů souborů, včetně MPP, XML, XLSX a dalších.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks od[tady](https://releases.aspose.com/).
### Otázka: Kde mohu získat podporu pro Aspose.Tasks?
 Odpověď: Pro podporu a pomoc můžete navštívit stránku[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
