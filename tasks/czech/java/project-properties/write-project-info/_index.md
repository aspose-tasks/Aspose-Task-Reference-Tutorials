---
date: 2025-12-31
description: Naučte se, jak nastavit datum zahájení projektu, zapsat informace o projektu
  a uložit projekt jako XML pomocí Aspose.Tasks pro Javu.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Nastavte počáteční datum projektu v MS Project pomocí Aspose.Tasks pro Javu
url: /cs/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení počátečního data projektu v MS Project pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se dozvíte, jak **set project start date** a zapisovat další informace o MS Project pomocí Aspose.Tasks pro Java. Ať už automatizujete harmonogramy projektů, generujete zprávy nebo integrujete data projektu do většího systému, programové nastavení počátečního data vám poskytuje přesnou kontrolu nad vašimi časovými osami. Provedeme vás každým krokem – od nastavení prostředí až po uložení aktualizovaného projektu jako XML souboru – abyste mohli tyto techniky okamžitě použít.

## Rychlé odpovědi
- **Jaká je hlavní třída pro manipulaci s projektem?** `Project` from the Aspose.Tasks library.  
- **Jak nastavit počáteční datum projektu?** Use `project.set(Prj.START_DATE, <date>)`.  
- **Mohu také nastavit datum stavu?** Yes, with `project.set(Prj.STATUS_DATE, <date>)`.  
- **Jaký formát použít pro export projektu?** Save as XML with `SaveFileFormat.Xml`.  
- **Potřebuji licenci pro produkční použití?** A valid Aspose.Tasks license is required for full functionality.

## Co je **set project start date**?
Nastavení počátečního data projektu určuje kalendářní den, od kterého začínají všechny naplánované úkoly. Je to výchozí bod pro výpočty, jako jsou trvání úkolů, závislosti a kritické cesty. Programovým nastavením tohoto data zajistíte konzistenci napříč více soubory projektů a eliminujete chyby při ručním zadávání.

## Proč používat Aspose.Tasks pro Java pro zápis informací o projektu?
- **Kompletní pokrytí API:** Read, modify, and write every Project property without needing Microsoft Project installed.  
- **Cross‑platform:** Works on Windows, Linux, and macOS.  
- **Automation‑ready:** Ideal for batch processing, CI pipelines, or back‑end services that generate project schedules on the fly.  

## Předpoklady
1. **Java Development Kit (JDK)** – any recent version (8+ recommended).  
2. **Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.  

## Import balíčků
First, import the necessary packages in your Java project:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Krok 1: Nastavení adresáře dat
Definujte adresář, kde budou uložena data vašeho projektu.
```java
String dataDir = "Your Data Directory";
```

## Krok 2: Vytvoření instance projektu
Inicializujte novou instanci projektu.
```java
Project project = new Project();
```

## Krok 3: Nastavení vlastností informací o projektu
Zde nastavujeme **project start date**, plánování od začátku a datum stavu – pokrýváme primární a sekundární klíčová slova *write project information* a *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Krok 4: Uložení projektu jako XML
Nakonec uložíme aktualizovaný soubor projektu. Toto demonstruje sekundární klíčové slovo **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Nesprávné počáteční datum** | Calendar month is zero‑based in Java. | Use `Calendar.JULY` (or add 1 to month index) as shown. |
| **Soubor neuložen** | `dataDir` does not exist or lacks write permission. | Create the directory beforehand or choose a writable path. |
| **Upozornění na licenci** | Running without a license adds a watermark. | Apply a valid Aspose.Tasks license before creating the `Project` object. |

## Často kladené otázky
### Q: Mohu použít Aspose.Tasks pro Java k načtení souborů MS Project?
A: Ano, Aspose.Tasks pro Java poskytuje robustní funkce pro čtení i zápis souborů MS Project.  
### Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?
A: Ano, Aspose.Tasks pro Java podporuje různé verze MS Project, což zajišťuje kompatibilitu napříč různými formáty souborů.  
### Q: Existují nějaká omezení zkušební verze Aspose.Tasks pro Java?
A: Zatímco zkušební verze vám umožní prozkoumat možnosti knihovny, má určitá omezení, jako jsou vodoznaky na výstupních souborech.  
### Q: Jak mohu získat podporu pro Aspose.Tasks pro Java?
A: Můžete požádat o pomoc na fóru komunity Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).  
### Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?
A: Ano, dočasné licence jsou k dispozici pro krátkodobé použití. Můžete ji získat [here](https://purchase.aspose.com/temporary-license/).

## Závěr
Nyní jste se naučili, jak **set project start date**, zapisovat základní informace o projektu a **save project as XML** pomocí Aspose.Tasks pro Java. Tyto stavební bloky vám umožní automatizovat pracovní postupy projektového řízení, generovat konzistentní harmonogramy a integrovat data MS Project do vašich Java aplikací.

---

**Poslední aktualizace:** 2025-12-31  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}