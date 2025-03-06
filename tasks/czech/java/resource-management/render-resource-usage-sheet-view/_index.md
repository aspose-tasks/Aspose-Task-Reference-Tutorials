---
title: Vykreslení využití zdrojů a zobrazení listu v Aspose.Tasks
linktitle: Vykreslení využití zdrojů a zobrazení listu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se vykreslovat MS Project Resource Us a zobrazení listu v Aspose.Tasks pro Java. Postupujte podle našeho podrobného průvodce a snadno vygenerujte podrobné zprávy ve formátu PDF.
type: docs
weight: 16
url: /cs/java/resource-management/render-resource-usage-sheet-view/
---
## Úvod
V tomto tutoriálu se naučíme, jak používat Aspose.Tasks pro Javu k vykreslení MS Project Resource Usage a zobrazení listu. Aspose.Tasks je výkonná Java knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project bez nutnosti instalace Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte nainstalované a nastavené následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit. Nejnovější verzi JDK si můžete stáhnout a nainstalovat z webu Oracle.
2.  Aspose.Tasks for Java: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java z[stránka ke stažení](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve musíte do svého projektu Java importovat potřebné balíčky:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Krok 1: Přečtěte si zdrojový projekt
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
// Přečtěte si zdrojový projekt
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
V tomto kroku určíme cestu ke zdrojovému souboru projektu (`ResourceUsageView.mpp` ) a použijte`Project` třídy, aby si to přečetl.
## Krok 2: Definujte SaveOptions s požadovaným nastavením TimeScale
```java
// Definujte SaveOptions s požadovaným nastavením TimeScale jako dny
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Zde definujeme`SaveOptions` s požadovaným`TimeScale` nastavení. V tomto příkladu nastavíme`TimeScale` do Dnů.
## Krok 3: Nastavte formát prezentace na ResourceUsage
```java
// Nastavte formát prezentace na ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Formát prezentace jsme nastavili na`ResourceUsage`, což znamená, že chceme vykreslit zobrazení Využití zdrojů.
## Krok 4: Uložte projekt
```java
// Uložte projekt
project.save(dataDir + days, options);
```
Nakonec projekt uložíme se zadanými možnostmi. V tomto příkladu bude výstupní soubor uložen jako`result_days.pdf`.
## Krok 5: Vykreslení zobrazení pro jiná nastavení časového měřítka
Opakujte kroky 2 až 4 pro vykreslování pohledů s různým nastavením časového měřítka (ThirdsOfMonths a Months).
```java
// Nastavte nastavení časové osy na ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Uložte projekt
project.save(thirds, options);
// Nastavte nastavení Časové osy na Měsíce
options.setTimescale(Timescale.Months);
// Uložte projekt
project.save(dataDir + months, options);
```
 Ujistěte se, že jste změnili`Timescale` odpovídajícím způsobem pro každý pohled.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak používat Aspose.Tasks pro Javu k vykreslení MS Project Resource Usage a zobrazení listu. Podle výše uvedených kroků můžete efektivně generovat tyto pohledy ve formátu PDF, což usnadňuje vizualizaci a analýzu dat vašeho projektu.
## FAQ
### Může Aspose.Tasks vykreslovat jiná zobrazení kromě Využití zdrojů a List?
Aspose.Tasks podporuje vykreslování různých zobrazení, jako je Ganttův diagram, Používání úkolů a zobrazení kalendáře, mezi ostatními.
### Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?
Ano, Aspose.Tasks podporuje širokou škálu formátů souborů aplikace Microsoft Project, včetně formátů MPP, MPT a XML.
### Mohu upravit vzhled vykreslených pohledů pomocí Aspose.Tasks?
Absolutně! Aspose.Tasks poskytuje rozsáhlé možnosti pro přizpůsobení vzhledu a rozvržení vykreslených pohledů tak, aby vyhovovaly vašim specifickým požadavkům.
### Vyžaduje Aspose.Tasks, aby byl v systému nainstalován Microsoft Project?
Ne, Aspose.Tasks je samostatná knihovna a ke svému fungování nevyžaduje instalaci Microsoft Project.
### Je pro uživatele Aspose.Tasks k dispozici technická podpora?
 Ano, uživatelé Aspose.Tasks mohou využívat technickou podporu prostřednictvím[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).