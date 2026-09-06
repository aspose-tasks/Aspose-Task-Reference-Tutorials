---
date: 2026-08-24
description: Naučte se, jak načíst výjimky kalendáře v Java ze souborů MS Project
  a jak číst kalendář mpp pomocí Aspose.Tasks pro Java. Tento tutoriál poskytuje krok‑za‑krokem
  ukázky kódu.
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: Jak načíst výjimky kalendáře v Java pomocí Aspose.Tasks
og_description: Naučte se, jak načíst výjimky kalendáře v Java ze souborů MS Project
  a jak číst kalendář mpp pomocí Aspose.Tasks pro Java. Tento krok‑za‑krokem průvodce
  vám pomůže přidat přesné zpracování kalendáře do vašich Java aplikací.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Jak načíst výjimky kalendáře v Java pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: Jak načíst výjimky kalendáře v Java pomocí Aspose.Tasks
url: /cs/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak získat výjimky kalendáře v Javě s Aspose.Tasks

## Úvod
V tomto **asp tasks java tutorial** se naučíte, jak získat výjimky kalendáře z souboru Microsoft Project pomocí knihovny Aspose.Tasks pro Javu. Výjimky kalendáře představují nepracovní období, jako jsou svátky nebo vlastní pravidla pracovní doby, a jejich programové čtení je nezbytné pro vyrovnávání zdrojů, reportování a vlastní logiku plánování. Provedeme vás celým procesem krok za krokem, abyste tuto funkci mohli s jistotou integrovat do svých Java aplikací.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Získání výjimek kalendáře z souboru MPP pomocí Aspose.Tasks pro Java.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní nastavení.  
- **Požadavky?** JDK, Aspose.Tasks pro Java a IDE (IntelliJ IDEA nebo Eclipse).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Podporované verze Projectu?** Všechny hlavní formáty MS Project (MPP, MPT, XML).

## Co je asp tasks java tutorial?
**asp tasks java tutorial** vysvětluje, jak používat API Aspose.Tasks v Java projektech. Poskytuje konkrétní ukázky kódu, vysvětlení osvědčených postupů a reálné scénáře, aby vývojáři mohli manipulovat se soubory Projectu bez nutnosti instalace Microsoft Projectu. Následováním takového tutoriálu získají vývojáři jasné, praktické pochopení struktury API, běžných vzorů použití a toho, jak integrovat jeho funkce do větších podnikových aplikací.

## Proč získávat výjimky kalendáře?
Získání výjimek kalendáře vám umožní vytvářet přesné časové osy projektů, které respektují svátky a vlastní pracovní rozvrhy, vytvářet nástroje pro reportování, které zvýrazňují nepracovní dny, a synchronizovat kalendáře Projectu s externími systémy, jako jsou ERP nebo HR platformy. Aspose.Tasks dokáže číst výjimky z **30+** typů kalendářů a podporuje **3 hlavní** formáty souborů MS Project (MPP, MPT, XML) bez načítání celého souboru do paměti, což umožňuje efektivní zpracování projektů o stovkách stránek.

## Požadavky
Předtím, než začneme, ujistěte se, že máte následující požadavky:

1. **Java Development Kit (JDK)** – Ujistěte se, že máte nainstalovaný JDK 8 nebo novější.  
2. **Aspose.Tasks for Java** – Stáhněte a nainstalujte Aspose.Tasks for Java ze **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – Můžete použít libovolné IDE dle vašeho výběru, například IntelliJ IDEA nebo Eclipse.

## Import balíčků
Importovací příkazy přinášejí třídy Aspose.Tasks do vašeho Java zdrojového souboru, což vám umožní pracovat s projekty, kalendáři a výjimkami.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## Krok 1: nastavení adresáře s daty
Definujte složku, která obsahuje soubor Project, který chcete analyzovat. Použití absolutní cesty nebo cesty relativní k adresáři resources vašeho projektu zabraňuje `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **Tip:** Ukládejte soubory Project do vyhrazené složky resources a odkazujte na ně pomocí `Paths.get(...)` pro platformově nezávislé cesty.

## Krok 2: načtení souboru MS Project
`Project` třída představuje soubor MS Project a poskytuje přístup k jeho kalendářům, úkolům, zdrojům a dalším datům projektu. Načtěte soubor Project do objektu `Project`. Tento objekt představuje celý soubor MS Project v paměti a poskytuje přístup k kalendářům, úkolům, zdrojům a dalším.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Krok 3: získání výjimek kalendáře
Procházejte každý kalendář v projektu a poté každou výjimku kalendáře v tomto kalendáři. Vytiskněte počáteční a koncová data každé výjimky.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## Časté problémy a řešení
| Problém | Důvod | Oprava |
|-------|--------|-----|
| **Žádný výstup** | Soubor projektu neobsahuje žádné výjimky kalendáře. | Ověřte, že kalendář v MS Project má definované výjimky (např. svátky). |
| **`NullPointerException`** | Cesta `dataDir` je nesprávná nebo soubor nebyl nalezen. | Zkontrolujte znovu cestu ke složce a ujistěte se, že `project.mpp` existuje. |
| **Rozdíl časových pásem** | Data jsou zobrazena v UTC. | Použijte `calExc.getFromDate().toLocalDateTime()` pro převod na místní čas, pokud je potřeba. |

## Často kladené otázky
### Dokáže Aspose.Tasks zpracovat různé verze souborů MS Project?
Ano, Aspose.Tasks podporuje **všechny hlavní** formáty MS Project, včetně MPP, MPT a XML, napříč verzemi od roku 2000 po nejnovější vydání.

### Je k dispozici bezplatná zkušební verze Aspose.Tasks?
Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks ze **[Aspose free trial download page](https://releases.aspose.com/)**.

### Kde najdu dokumentaci k Aspose.Tasks pro Java?
Můžete se podívat na dokumentaci **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)**.

### Jak získám podporu pro Aspose.Tasks?
Podporu můžete získat na komunitním fóru **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)**.

### Existuje možnost dočasných licencí pro Aspose.Tasks?
Ano, dočasné licence můžete získat na **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)**.

**Další otázky a odpovědi**

**Q:** *Mohu po získání upravit výjimky kalendáře?*  
**A:** Rozhodně. Použijte `CalendarException.setFromDate()` a `setToDate()` pro úpravu dat, poté projekt uložte pomocí `project.save(...)`.

**Q:** *Zachovává Aspose.Tasks vlastní pole v kalendářích?*  
**A:** Ano, všechna vlastní pole a rozšířené atributy jsou při načítání a ukládání projektu zachována.

## Závěr
V tomto **asp tasks java tutorial** jsme se naučili, jak získat výjimky kalendáře z MS Project pomocí Aspose.Tasks pro Java. Dodržením těchto jednoduchých kroků můžete tuto funkci hladce integrovat do svých Java aplikací, což umožní bohatší funkce plánování a přesnější analytiku projektů.

---

**Poslední aktualizace:** 2026-08-24  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## Související tutoriály

- [Vytvořit vlastní výjimky kalendáře s Aspose.Tasks pro Java](/tasks/java/calendar-exceptions/)
- [Jak použít Aspose.Tasks k získání informací o kalendáři MS Project](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [Jak číst pracovní týdny v Javě z kalendáře MS Project pomocí Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}