---
date: 2026-01-15
description: Naučte se, jak přidat zdroj do projektu, aktualizovat data zdroje a uložit
  projekt jako MPP pomocí Aspose.Tasks pro Javu.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Přidat zdroj do projektu pomocí Aspose.Tasks pro Java
url: /cs/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání zdroje do projektu pomocí Aspose.Tasks pro Java

## Úvod
V tomto praktickém tutoriálu objevíte **how to add resource to project** soubory programově pomocí Aspose.Tasks Java API. Provedeme vás načtením existujícího souboru MS Project XML, vložením nového zdroje, aktualizací jeho vlastností a nakonec **save project as MPP**. Na konci budete mít jasný, opakovatelný vzor, který můžete použít v jakémkoli nástroji pro reportování nebo automatizaci založeném na Javě.

## Rychlé odpovědi
- **What does “add resource to project” mean?** Vytváří nový záznam zdroje (lidé, vybavení, materiál) uvnitř souboru Microsoft Project.  
- **Which library handles this?** Aspose.Tasks for Java – není potřeba mít nainstalovaný Microsoft Project.  
- **Do I need a license?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Can I convert XML to MPP?** Ano – načtěte XML soubor a **save project as MPP** pomocí `project.save(...)`.  
- **What Java version is required?** Java 6 nebo novější (doporučeno Java 8+).

## Co znamená “add resource to project”?
Přidání zdroje do projektu znamená vložení nového řádku do tabulky Resources v souboru MS Project. Tento řádek ukládá podrobnosti jako název, sazby nákladů, skupinu a vlastní pole, na které mohou úkoly později odkazovat.

## Proč používat Aspose.Tasks pro Java?
- **No Microsoft Project dependency** – funguje na jakémkoli OS nebo CI serveru.  
- **Full fidelity** – zachovává všechny nativní funkce Project při konverzi mezi formáty  
- **Rich API** – umožňuje číst, zapisovat a manipulovat s úkoly, zdroji, kalendáři a dalšími.

## Požadavky
Před zahájením se ujistěte, že máte:

1. Java Development Kit (JDK) 8 nebo novější nainstalovaný.  
2. Aspose.Tasks for Java library – stáhněte ji z [here](https://releases.aspose.com/tasks/java/).  
3. Základní znalost syntaxe Java a nastavení projektu Maven/Gradle.

## Import balíčků
Přidejte požadované třídy Aspose.Tasks do vašeho Java zdrojového souboru:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Nastavte svůj datový adresář
Definujte, kde budou umístěny zdrojové XML a výsledné MPP soubory:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Zadejte vstupní a výstupní soubory
Ukažte na XML soubor, který chcete převést (**convert XML to MPP**) a cílový MPP soubor, který bude obsahovat nový zdroj:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Krok 3: Načtěte projekt
Vytvořte objekt `Project` ze zdroje XML:

```java
Project project = new Project(file);
```

## Krok 4: Přidejte zdroj a nastavte atributy
Zde **add resource to project** a nakonfigurujeme jeho sazby a skupinu:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro tip:* Můžete opakovat volání `add` uvnitř smyčky pro **update multiple resources** v jednom běhu.

## Krok 5: Uložte projekt
Nakonec **save project as MPP** pro uložení změn:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Závěr
Právě jste se naučili **how to add resource to project**, aktualizovat jeho vlastnosti a **save project as MPP** pomocí Aspose.Tasks pro Java. Tento přístup je ideální pro automatizované reportingové pipeline, hromadné importy zdrojů nebo jakýkoli scénář, kde potřebujete manipulovat se soubory MS Project bez desktopové aplikace.

## Často kladené otázky

**Q1: Can I update multiple resources in the same project using Aspose.Tasks for Java?**  
A: Ano, iterujte přes `project.getResources()` nebo opakovaně volajte `add`, přičemž nastavíte pole každého zdroje podle potřeby.

**Q2: Does Aspose.Tasks support other file formats besides MS Project?**  
A: Rozhodně – XML, MPP, MPX, Primavera a další jsou všechny podporovány.

**Q3: Is Aspose.Tasks compatible with different versions of Java?**  
A: Knihovna funguje s Java 6 a novějšími; Java 8+ je důrazně doporučena pro nejlepší výkon.

**Q4: Can I perform other operations on MS Project files with Aspose.Tasks?**  
A: Ano, můžete číst/zapisovat úkoly, kalendáře, přiřazení, vlastní pole a dokonce generovat reporty.

**Q5: Where can I find additional help or support for Aspose.Tasks?**  
A: Navštivte [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pro komunitní pomoc a oficiální podporu.

---

**Poslední aktualizace:** 2026-01-15  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}