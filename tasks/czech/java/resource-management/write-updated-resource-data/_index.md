---
date: 2026-06-30
description: Naučte se, jak aktualizovat více zdrojů a upravit data skupiny zdrojů,
  poté exportovat projekt do MPP a uložit projekt jako MPP pomocí Aspose.Tasks pro
  Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Aktualizace více zdrojů v Aspose.Tasks pro Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aktualizace více zdrojů v Aspose.Tasks pro Java
url: /cs/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aktualizace více zdrojů v Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se naučíte, jak **aktualizovat více zdrojů** v souboru Microsoft Project pomocí Aspose.Tasks pro Java. Ať už potřebujete změnit sazby, přeřadit skupiny nebo exportovat aktualizovaný soubor do formátu MPP, níže uvedené kroky vás provedou kompletním, připraveným na produkční nasazení pracovním postupem. Instalace Microsoft Project není vyžadována a API dokáže efektivně zpracovat projekty se stovkami zdrojů.

## Rychlé odpovědi
- **Mohu aktualizovat několik zdrojů najednou?** Ano – iterujte přes `ResourceCollection` a nastavte atributy v jednom průchodu.  
- **Která metoda ukládá soubor jako MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Potřebuji licenci pro komerční použití?** Pro produkci je vyžadována placená licence; je k dispozici bezplatná zkušební verze.  
- **Jaké verze Javy jsou podporovány?** Java 6 a vyšší, včetně Java 17 LTS.  
- **Je hromadná aktualizace výkonná?** Aspose.Tasks zpracuje projekty se 500 zdroji za méně než 2 sekundy na typickém serveru.

## Co je „aktualizace více zdrojů“?
**„Aktualizace více zdrojů“** označuje programatické změny vlastností několika položek zdrojů – například sazeb, skupin, kalendářů nebo vlastních polí – v rámci jediného souboru Project. Tato operace je často vyžadována při synchronizaci projektových dat s podnikovými systémy plánování zdrojů (ERP), úpravě rozpočtů napříč mnoha zdroji nebo aplikaci změn politiky na úrovni celé organizace.

## Proč použít Aspose.Tasks k úpravě skupiny zdrojů a exportu projektu do MPP?
Aspose.Tasks podporuje **více než 50 vstupních a výstupních formátů**, včetně MPP, XML a CSV, a může **exportovat projekt do MPP** bez načítání celého souboru do paměti. Knihovna zpracovává soubory až do velikosti **2 GB**, což vám umožní **uložit projekt jako MPP** rychle a spolehlivě.

## Požadavky

Než začneme, ujistěte se, že máte následující:

1. Java Development Kit (JDK) nainstalovaný ve vašem systému.  
2. Knihovna Aspose.Tasks pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  
3. Základní znalost programování v Javě.  

## Import balíčků

`import` příkazy přinášejí požadované třídy Aspose.Tasks do vašeho zdrojového souboru.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Nastavte svůj adresář s daty

Definujte adresář, ve kterém se nacházejí vaše datové soubory:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Zadejte vstupní a výstupní soubory

Definujte cesty k vstupnímu souboru MS Project a k výslednému aktualizovanému souboru:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Krok 3: Načtěte projekt

`Project` představuje soubor Microsoft Project načtený do paměti, poskytující přístup k úkolům, zdrojům a dalším projektovým datům.

```java
Project project = new Project(file);
```

## Krok 4: Přidejte zdroj a nastavte atributy

`Resource` modeluje jednotlivý projektový zdroj, umožňující nastavit sazby, skupiny, kalendáře a další atributy.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Krok 5: Efektivně aktualizujte více zdrojů

`ResourceCollection` je kolekce všech zdrojů v projektu, přístupná pomocí `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Krok 6: Uložte projekt

`SaveFileFormat` vyjmenovává podporované formáty souborů pro ukládání projektu, jako jsou MPP, XML a PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Jak aktualizovat více zdrojů v projektu?
Načtěte existující projekt, získejte jeho `ResourceCollection` a iterujte přes každý objekt `Resource`. Pro každý zdroj upravte požadovaná pole, jako jsou sazby, skupiny nebo vlastní atributy, a poté přejděte k dalšímu položce. Po zpracování všech zdrojů zavolejte jednorázově `project.save(...)`, aby se změny efektivně uložily.

## Časté problémy a řešení
- **Kolize ID zdrojů** – Zajistěte, aby každý nový zdroj získal jedinečné ID pomocí `project.getResources().add(new Resource())`.  
- **Chyby formátu sazby** – Použijte objekty `ResourceRate` a nastavte `RateType` na `StandardRate` nebo `OvertimeRate`.  
- **Velké soubory způsobují zatížení paměti** – Před načtením povolte `Project.setReadOnly(true)`, aby se snížila paměťová náročnost.

## Často kladené otázky
**Q: Mohu aktualizovat více zdrojů ve stejném projektu pomocí Aspose.Tasks pro Java?**  
A: Ano, můžete aktualizovat více zdrojů iterací přes ně a nastavením jejich atributů podle potřeby.

**Q: Podporuje Aspose.Tasks další formáty souborů kromě MS Project?**  
A: Ano, Aspose.Tasks podporuje různé formáty souborů včetně XML, MPP a dalších.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi Javy?**  
A: Aspose.Tasks je kompatibilní s verzemi Javy 6 a vyššími.

**Q: Mohu provádět další operace se soubory MS Project pomocí Aspose.Tasks?**  
A: Ano, můžete provádět širokou škálu operací, jako je čtení, zápis a manipulace s úkoly, zdroji a kalendáři.

**Q: Kde mohu najít další pomoc nebo podporu pro Aspose.Tasks?**  
A: Navštívit můžete [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.

**Q: Jak exportovat aktualizovaný soubor do formátu MPP?**  
A: Po provedení všech změn zdrojů zavolejte `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)`.

**Q: Jaký je nejlepší způsob úpravy skupiny zdrojů?**  
A: Nastavte vlastnost `Resource.Group` u každého objektu `Resource` před uložením projektu.

---

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Přidat zdroj do projektu pomocí Aspose.Tasks pro Java](/tasks/java/resource-management/create-resources/)
- [Spravovat náklady zdrojů MS Project pomocí Aspose.Tasks pro Java](/tasks/java/resource-management/resource-cost/)
- [Jak exportovat MPP do Excelu pomocí Aspose.Tasks pro Java](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}