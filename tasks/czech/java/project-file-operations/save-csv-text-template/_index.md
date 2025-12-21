---
date: 2025-12-21
description: Naučte se, jak uložit projekt jako šablonu, exportovat MPP do CSV a převést
  MPP na text pomocí Aspose.Tasks pro Javu.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Uložte projekt jako šablonu, CSV a text s Aspose.Tasks pro Javu
url: /cs/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení projektu jako šablony, CSV a textu pomocí Aspise.Tasks

## Úvod
V tomto tutoriálu se dozvíte **jak uložit projekt jako šablonu** a také jak exportovat soubory Microsoft Project (MPP) do formátů CSV a prostého textu pomocí knihovny Aspose.Tasks pro Javu. Ať už potřebujete vytvořit znovupoužitelnou šablonu projektu, generovat CSV zprávy pro analytiku, nebo vytvořit jednoduché textové výpisy pro integraci, tyto kroky vás rychle a efektivně provedou procesem.

## Rychlé odpovědi
- **Mohu exportovat MPP do CSV?** Ano – použijte `project.save(..., SaveFileFormat.CSV)`.  
- **Jak exportovat text?** Uložte pomocí `SaveFileFormat.TEXT`.  
- **Co dělá „uložit projekt jako šablonu“?** Vytvoří soubor `.mpt`, který odstraní skutečné a základní hodnoty a je připraven k opětovnému použití.  
- **Potřebuji licenci?** K dispozici je zkušební verze; pro produkční nasazení je vyžadována komerční licence.  
- **Jaká verze Javy je požadována?** Je podporována Java 8+.

## Co je „uložit projekt jako šablonu“?
Uložení projektu jako šablony (`.mpt`) zachytí strukturu, hierarchii úkolů a přiřazení zdrojů, přičemž odstraní skutečné datum zahájení/ukončení a data základní linie. To činí šablonu ideální pro opakované použití standardního rozvržení projektu v několika nových projektech.

## Proč používat Aspose.Tasks pro Javu?
Aspose.Tasks vám umožní manipulovat se soubory Microsoft Project, aniž byste museli instalovat samotný Microsoft Project. Podporuje **jak exportovat MPP**, **jak exportovat text** a **převod MPP do CSV**, vše z čistého Java kódu, což je ideální pro server‑side automatizaci, CI pipeline nebo desktopové nástroje.

## Předpoklady
1. Java Development Kit (JDK) 8 nebo vyšší nainstalovaný.  
2. Knihovna Aspose.Tasks pro Javu přidaná do vašeho projektu. Stáhněte ji z [zde](https://releases.aspose.com/tasks/java/).  
3. Základní znalost syntaxe Javy a nastavení projektu Maven/Gradle.

## Import balíčků
Nejprve importujte požadované třídy ve vašem Java zdrojovém souboru:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Uložení projektu jako CSV (Export MPP do CSV)
Export MPP souboru do CSV je užitečný pro analýzu dat v Excelu nebo nástrojích BI.

### Krok 1: Načtení projektu
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Krok 2: Uložení jako CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Uložení projektu jako text (Jak exportovat text)
Pokud potřebujete prostý textový výstup úkolů, zdrojů nebo přiřazení, uložte projekt jako textový soubor.

### Krok 1: Načtení projektu
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Krok 2: Uložení jako text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Uložení projektu jako šablonu (Vytvoření šablony projektu v Javě)
Vytvoření znovupoužitelné šablony odstraní skutečná data a základní linie, čímž zanechá čistý kostru pro nové projekty.

### Krok 1: Načtení projektu
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Krok 2: Nastavení možností šablony
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Krok 3: Uložení jako šablonu
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Časté problémy a tipy
- **Soubor nenalezen:** Ujistěte se, že cesta k `YourProject.mpp` je správná, nebo použijte absolutní cestu.  
- **Výjimky licence:** Bez platné licence knihovna běží v evaluačním režimu a může přidávat vodoznaky. Aplikujte licenci co nejdříve v kódu (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Velké projekty:** U velmi velkých MPP souborů zvažte zvýšení velikosti haldy JVM (`-Xmx2g`), aby se předešlo `OutOfMemoryError`.

## Závěr
Probrali jsme **jak uložit projekt jako šablonu**, stejně jako **export MPP do CSV** a **převod MPP na text** pomocí Aspose.Tasks pro Javu. Tyto možnosti vám umožní automatizovat zpracování projektových dat, generovat znovupoužitelné šablony a integrovat informace o projektu do dalších systémů – vše bez nutnosti instalace Microsoft Project.

## Často kladené otázky
### Q: Dokáže Aspose.Tasks pro Javu zpracovat složité projektové soubory?
A: Rozhodně! Aspose.Tasks pro Javu dokáže snadno zpracovat projekty různé složitosti a poskytuje komplexní podporu pro formáty souborů Microsoft Project.  
### Q: Je k dispozici zkušební verze Aspose.Tasks pro Javu?
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro Javu z [zde](https://releases.aspose.com/).  
### Q: Kde mohu najít podporu pro Aspose.Tasks pro Javu?
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy týkající se Aspose.Tasks pro Javu.  
### Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Javu?
A: Ano, můžete zakoupit dočasnou licenci na [zde](https://purchase.aspose.com/temporary-license/), což vám umožní vyzkoušet plný potenciál knihovny.  
### Q: Je Aspose.Tasks pro Javu kompatibilní s různými operačními systémy?
A: Ano, Aspose.Tasks pro Javu je kompatibilní s různými operačními systémy, včetně Windows, macOS a Linuxu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose