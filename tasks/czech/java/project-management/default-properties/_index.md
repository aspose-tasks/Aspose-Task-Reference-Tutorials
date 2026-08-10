---
date: 2026-05-31
description: Zjistěte, jak načíst soubor MPP v Java a spravovat vlastnosti projektu
  pomocí Aspose.Tasks, včetně nastavení výchozích vlastností a převodu formátů.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Správa výchozích vlastností projektu v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Načtení souboru MPP v Java – Správa vlastností projektu pomocí Aspose.Tasks
url: /cs/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Načíst soubor MPP v Javě – Spravovat vlastnosti projektu pomocí Aspose.Tasks

## Úvod
Pokud potřebujete **load MPP file Java** projekty a programově spravovat výchozí vlastnosti projektu, Aspose.Tasks pro Java to usnadňuje. V tomto tutoriálu projdeme celý proces – od načtení existujícího souboru Microsoft Project po přizpůsobení výchozích nastavení úkolů a zdrojů a nakonec uložení aktualizovaného projektu. Na konci budete mít jasný, znovupoužitelný vzor, který můžete vložit do jakéhokoli řešení pro řízení projektů založeného na Javě.

## Rychlé odpovědi
- **Co znamená “load MPP file Java”?** Znamená to čtení souboru Microsoft Project (.mpp) pomocí Java kódu prostřednictvím Aspose.Tasks.  
- **Která knihovna to zajišťuje?** Aspose.Tasks pro Java poskytuje plnohodnotné API pro manipulaci s projekty.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkční použití je vyžadována komerční licence.  
- **Mohu změnit výchozí data zahájení úkolů?** Ano – použijte `Prj.DEFAULT_START_TIME` a související vlastnosti pro nastavení výchozích hodnot.  
- **Jaké výstupní formáty jsou podporovány?** Kromě nativního MPP můžete ukládat do XML, PDF, HTML a více než 20 dalších formátů.

## Co je “load MPP file Java”?
Načtení souboru MPP v Javě znamená použití knihovny k parsování binárního formátu Microsoft Project, která vystavuje jeho objekty (úkoly, zdroje, kalendáře) jako třídy v Javě. To vám umožní číst, upravovat a ukládat data projektu, aniž byste museli otevírat samotný Microsoft Project.

## Proč používat Aspose.Tasks pro Java?
Aspose.Tasks vám umožní spravovat vlastnosti projektu bez instalace Microsoft Project, podporuje **více než 50 vstupních a výstupních formátů** a může zpracovávat projekty s **až 10 000 úkoly**, přičemž spotřeba paměti zůstává pod 200 MB. Běží na jakémkoli OS, který podporuje JDK, což z něj činí ideální řešení pro server‑side automatizaci.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte následující:

### 1. Java Development Kit (JDK)
- Nainstalujte JDK 11 nebo novější.  
- Můžete jej stáhnout [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### 2. Knihovna Aspose.Tasks pro Java
- Stáhněte nejnovější Aspose.Tasks JAR a přidejte jej do classpath vašeho projektu.  
- Získejte ji z [webu](https://releases.aspose.com/tasks/java/).

## Import balíčků
Importovací příkazy přinášejí nezbytné třídy Aspose.Tasks do vašeho Java zdrojového souboru.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Jak načíst soubor MPP v Javě a nastavit výchozí vlastnosti?
`Project` třída představuje soubor Microsoft Project a poskytuje přístup k jeho úkolům, zdrojům a nastavením. Načtěte projekt, prohlédněte si jeho výchozí hodnoty, upravte je a uložte výsledek – vše během několika jednoduchých řádků. Tento přístup vám dává plnou kontrolu nad výchozími nastaveními rozvrhu, kalendářními nastaveními a pravidly akumulace nákladů, což vám umožní vynutit konzistentní standardy projektu ve všech generovaných souborech.

### Krok 1: Načíst soubor projektu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Krok 2: Zobrazit výchozí vlastnosti
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Krok 3: Nastavit výchozí vlastnosti
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Krok 4: Uložit projekt do formátu XML
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Krok 5: Zobrazit výsledek
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Po provedení těchto kroků jste úspěšně **načetli soubor MPP v Javě**, prozkoumali jeho výchozí nastavení, upravili je a uložili aktualizovaný projekt.

## Časté problémy a tipy
- **Soubor nenalezen** – Ověřte, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`).  
- **Licence nebyla použita** – Pokud vidíte vodoznak z trial verze, přidejte svůj licenční soubor před načtením projektu: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Zpracování data** – Použijte `java.util.Calendar` nebo novější API `java.time` (před přiřazením převést na `java.util.Date`).

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks je také k dispozici pro .NET, Python a další platformy.

**Q: Je Aspose.Tasks vhodný jak pro osobní, tak pro firemní použití?**  
A: Rozhodně! Škáluje se od malých osobních projektů po rozsáhlé firemní portfolia.

**Q: Nabízí Aspose.Tasks zákaznickou podporu?**  
A: Ano, pomoc a komunitní podporu najdete na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Samozřejmě! Bezplatnou zkušební verzi můžete získat na [webu](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks?**  
A: Dočasnou licenci můžete získat na [stránce nákupu](https://purchase.aspose.com/temporary-license/) pro testovací a evaluační účely.

## Závěr
V tomto tutoriálu jsme si ukázali, jak **načíst soubor MPP v Javě** projekty, číst a měnit jejich výchozí vlastnosti a ukládat změny pomocí Aspose.Tasks pro Java. Začlenění těchto technik do vašich aplikací vám pomůže automatizovat úkoly řízení projektů, vynutit konzistentní výchozí nastavení a snížit manuální úsilí.

---

**Poslední aktualizace:** 2026-05-31  
**Testováno s:** Aspose.Tasks for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Nastavit datum zahájení projektu v MS Project pomocí Aspose.Tasks pro Java](/tasks/java/project-properties/write-project-info/)
- [Jak nastavit kalendář projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/properties/)
- [Jak vytvořit soubor MPP – Vytvořit a uložit prázdný projekt ve formátu MPP pomocí Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}