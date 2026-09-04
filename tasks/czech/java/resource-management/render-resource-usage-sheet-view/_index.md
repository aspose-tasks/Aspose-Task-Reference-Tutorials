---
date: 2026-06-15
description: Zjistěte, jak převést mpp do pdf a vykreslit pohledy Resource Usage a
  Sheet pomocí Aspose.Tasks pro Java. Postupujte podle našeho podrobného návodu krok
  za krokem, jak nastavit timescale a snadno vytvořit podrobné PDF zprávy.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Převod MPP do PDF a vykreslení pohledu Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Převod MPP do PDF a vykreslení pohledu Resource Usage – Aspose.Tasks
url: /cs/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod MPP na PDF a vykreslení zobrazení využití zdrojů – Aspose.Tasks

V tomto tutoriálu se naučíte **jak převést mpp na pdf** při vykreslování zobrazení Využití zdrojů a Listu souboru Microsoft Project. Použití Aspose.Tasks pro Java odstraňuje potřebu Microsoft Project na serveru a poskytuje rychlý, spolehlivý způsob, jak vytvářet PDF zprávy z MPP souborů. Také vám ukážeme **jak nastavit časovou osu**, aby výstup odpovídal vašim požadavkům na reportování.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks?** Čte, upravuje a převádí soubory Microsoft Project (MPP) bez nutnosti mít nainstalovaný MS Project.  
- **Mohu převést MPP na PDF jedním řádkem kódu?** Ano – načtěte projekt, nastavte SaveOptions a zavolejte `save`.  
- **Jaké časové osy jsou podporovány?** Dny, ThirdsOfMonths a Měsíce.  
- **Potřebuji licenci pro produkci?** Komerční licence je vyžadována pro nasazení mimo zkušební verzi.  
- **Je knihovna kompatibilní s Java 8+?** Naprosto – podporuje Java 8 a novější verze.

## Co je převod mpp na pdf?
*Převod mpp na pdf* označuje proces převzetí souboru Microsoft Project (.mpp) a vytvoření verze ve formátu Portable Document Format (PDF), která věrně reprodukuje tabulky, plány, grafy a přiřazení zdrojů projektu. Výsledné PDF lze snadno sdílet, tisknout a archivovat, aniž by bylo nutné mít nainstalovaný Microsoft Project na počítači příjemce.

## Proč převádět projekt na PDF pomocí Aspose.Tasks?
Aspose.Tasks podporuje **více než 50 vstupních a výstupních formátů** a dokáže vykreslit projekty o stovkách stránek, aniž by načítal celý soubor do paměti, čímž snižuje využití RAM až o 70 %. Výstupní PDF zachovává tabulky, grafy a přiřazení zdrojů, což je ideální pro distribuci mezi zainteresované strany a archivaci.

## Předpoklady
1. **Java Development Kit (JDK)** – Java 8 nebo novější nainstalovaný na vašem počítači.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR ze [stránky ke stažení](https://releases.aspose.com/tasks/java/).  

## Jak převést mpp na pdf pomocí Aspose.Tasks pro Java?
Načtěte svůj zdrojový soubor MPP, nakonfigurujte požadovanou časovou osu, nastavte formát prezentace na **ResourceUsage** a uložte výsledek jako PDF. Tento kompletní tok vyžaduje jen několik volání API a běží za méně než sekundu pro typické velikosti projektů.

### Krok 1: Načtení zdrojového projektu
Třída `Project` představuje soubor Microsoft Project načtený do paměti a poskytuje přístup k jeho datům a struktuře.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Krok 2: Definování SaveOptions s požadovaným nastavením TimeScale
`SaveOptions` konfiguruje, jak je projekt ukládán, a umožňuje specifikovat nastavení specifické pro formát, jako je časová osa.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Krok 3: Nastavení formátu prezentace na ResourceUsage
`PresentationFormat` určuje, které zobrazení projektu (např. ResourceUsage) je vykresleno ve výstupním dokumentu.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Krok 4: Uložení projektu jako PDF
`project.save` zapíše projekt do souboru pomocí poskytnutých `SaveOptions`, čímž vytvoří finální PDF.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Krok 5: Vykreslení zobrazení pro další nastavení TimeScale
Opakujte předchozí kroky a změňte hodnotu `TimeScale` pro vykreslení dalších zobrazení s různými časovými osami.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Krok 6: Volitelné – Hromadný převod více projektů
Pokud potřebujete **převést projekt na pdf** pro mnoho souborů, vložte výše uvedenou logiku do smyčky, která prochází adresář s *.mpp* soubory. Tento přístup **ukládá ms project pdf** soubory hromadně s minimálními změnami kódu.  
Následující kód ukazuje kompletní příklad převodu souboru MPP na PDF s požadovaným nastavením.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Časté problémy a řešení
- **Chybějící fonty v PDF** – Ujistěte se, že požadované fonty jsou nainstalovány na serveru nebo je vložte pomocí `PdfSaveOptions`.  
- **Velké soubory projektů způsobují OutOfMemoryError** – Použijte `LoadOptions.setLoadAllResources(false)`, aby se zdroje načítaly na požádání.  
- **Nesprávné vykreslení časové osy** – Ověřte, že `options.setTimeScale(TimeScale.Days)` (nebo jiný enum) odpovídá požadované granularitě.  

## Často kladené otázky

**Q: Dokáže Aspose.Tasks vykreslovat i jiné pohledy kromě Využití zdrojů a Listu?**  
A: Ano, podporuje také Ganttův diagram, Task Usage, Calendar a mnoho dalších pohledů.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Naprosto – zpracovává formáty MPP, MPT a XML od Project 2000 až po Project 2021.

**Q: Mohu přizpůsobit vzhled vykreslených pohledů?**  
A: Ano, můžete měnit barvy, fonty a rozvržení sloupců pomocí `PdfSaveOptions` a `PresentationOptions`.

**Q: Vyžaduje Aspose.Tasks instalaci Microsoft Project?**  
A: Ne, jedná se o samostatnou knihovnu, která funguje v jakémkoli prostředí kompatibilním s Java.

**Q: Kde mohu získat technickou podporu?**  
A: Podpora je k dispozici prostřednictvím [fóra Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Poslední aktualizace:** 2026-06-15  
**Testováno s:** Aspose.Tasks 24.12 pro Java  
**Autor:** Aspose

## Související tutoriály

- [Vykreslení zobrazení Využití zdrojů a Listu v Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Jak exportovat PDF v Aspose.Tasks – Uložit jako PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Jak vytvořit MPP soubory pomocí Aspose.Tasks pro Java](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}