---
date: 2026-08-24
description: Zjistěte, jak přidat resource ms project, nastavit standard rate a další
  resource properties v MS Project pomocí Aspose.Tasks for Java a efektivně spravovat
  resources.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Nastavit Resource Properties v Aspose.Tasks
og_description: Přidat resource ms project a nastavit standard rate pomocí Aspose.Tasks
  for Java. Zjistěte požadavky, step‑by‑step code a troubleshooting v tomto stručném
  průvodci.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Přidat resource ms project a nastavit rate pomocí Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Jak přidat resource ms project pomocí Aspose.Tasks
url: /cs/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání zdroje ms project a nastavení sazby v Aspose.Tasks

## Úvod
Pokud vyvíjíte Java aplikace, které potřebují číst nebo zapisovat soubory Microsoft Project, **adding a resource ms project** a konfigurace její standardní sazby je rutinní, ale nezbytný úkol. V tomto průvodci uvidíte, jak vytvořit objekt `Project`, přidat zdroj a nastavit jak standardní, tak přesčasové sazby pomocí Aspose.Tasks pro Java. Na konci budete schopni automatizovat výpočty nákladů a udržovat harmonogramy projektů aktuální, aniž by bylo nutné mít nainstalovaný Microsoft Project.

## Rychlé odpovědi
- **Jaká třída představuje soubor Project?** `Project`
- **Které volání přidá nový zdroj?** `project.getResources().add()`
- **Jak nastavit standardní sazbu?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Je licence vyžadována pro produkční použití?** Ano, musíte načíst platnou licenci Aspose.Tasks.
- **Jaké verze Javy jsou podporovány?** Java 8 a novější (doporučeno Java 17+).

## Co je „nastavení standardní sazby“?
Operace *nastavení standardní sazby* přiřazuje zdroji výchozí hodinovou cenu. Tuto sazbu používají projektoví manažeři k výpočtu nákladů na práci, generování nákladových zpráv a prognózování rozpočtů, což zajišťuje, že výpočty nákladů odrážejí očekávanou cenu práce prováděné každým zdrojem během celého životního cyklu projektu.

## Proč nastavovat sazby pomocí Aspose.Tasks?
Aspose.Tasks dokáže zpracovat **více než 50 vstupních a výstupních formátů**, včetně souborů MPP, MPX, XML a Primavera, a zvládá projekty o stovkách stránek, aniž by načítal celý soubor do paměti. To umožňuje vysoce výkonné dávkové zpracování na serverech Windows, Linux nebo macOS a snižuje ruční úsilí až o 90 % v typických scénářích automatizace.

## Předpoklady
Před zahájením se ujistěte, že jsou následující položky připravené:

### Nastavení vývojového prostředí Java
1. Nainstalujte JDK 8 nebo novější. Můžete jej stáhnout z [webu Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Vyberte IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans, a nakonfigurujte jej pro vývoj v Javě.

### Instalace Aspose.Tasks pro Java
1. Stáhněte nejnovější balíček Aspose.Tasks pro Java ze [stránky ke stažení](https://releases.aspose.com/tasks/java/).  
2. Přidejte soubory JAR do classpath vašeho projektu nebo deklarujte Maven/Gradle závislost, jak je uvedeno v dokumentaci produktu.

## Import balíčků
Importujte základní třídy Aspose.Tasks, které budete potřebovat. Tento krok vám poskytne přístup k typům `Project`, `Resource` a `Rsc`, které se použijí později.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Krok 1: vytvoření objektu projektu
Třída `Project` je objekt nejvyšší úrovně, který v paměti představuje celý soubor MS Project. Jeho vytvoření vytvoří prázdný projekt, který můžete naplnit úkoly, zdroji a dalšími daty.

```java
Project project = new Project();
```

## Krok 2: přidání zdroje (add resource ms project)
Třída `Resource` modeluje jediný projektový zdroj, jako je osoba, zařízení nebo materiál. Přidání zdroje pomocí `project.getResources().add()` vrátí nenulovou instanci `Resource`, připravenou k nastavení vlastností.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Krok 3: nastavení vlastností zdroje (how to set rates)
Výčtový typ `Rsc` obsahuje konstanty pro pole zdroje, jako jsou `STANDARD_RATE` a `OVERTIME_RATE`.  
Standardní a přesčasové sazby nastavíte voláním `set` na objektu `Resource` s odpovídajícími hodnotami výčtu `Rsc`. Sazby jsou uloženy jako `BigDecimal`, aby se zachovala měnová přesnost.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| `NullPointerException` when calling `set` | Resource nebyl správně přidán. | Zajistěte, aby `project.getResources().add()` vrátil nenulový `Resource`. |
| Rates appear as 0 in the saved file | Použití `int` místo `BigDecimal`. | Vždy používejte `BigDecimal.valueOf()` pro měnové hodnoty. |
| License not found | Soubor licence nebyl načten před vytvořením `Project`. | Načtěte licenci (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) při startu programu. |

## Závěr
Nyní víte, jak **add resource ms project**, vytvořit objekt `Project` a **nastavit standardní a přesčasové sazby** pomocí Aspose.Tasks pro Java. Tato schopnost vám umožní automatizovat výpočty nákladů, generovat vlastní zprávy a plně spravovat zdroje MS Project z jakékoli Java aplikace.

## Často kladené otázky
**Q: Dokáže Aspose.Tasks pro Java zpracovat složité soubory MS Project?**  
A: Ano, podporuje všechny hlavní formáty Project, včetně velkých souborů s tisíci úkoly a zdroji, přičemž zachovává všechna pole bez ztráty dat.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro Java na [stránce bezplatné zkušební verze Aspose.Tasks](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.Tasks pro Java?**  
A: Pomoc můžete získat na [fóru podpory](https://forum.aspose.com/c/tasks/15).

**Q: Jak získat dočasnou licenci pro hodnocení?**  
A: Dočasná licence je k dispozici na [stránce dočasné licence](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit licencovanou verzi?**  
A: Plnou licenci můžete zakoupit na [stránce nákupu](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-08-24  
**Testováno s:** Aspose.Tasks for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit zdroje – Správa zdrojů s Aspose.Tasks pro Java](/tasks/java/resource-management/)
- [Přidání zdroje do projektu s Aspose.Tasks pro Java](/tasks/java/resource-management/create-resources/)
- [Jak přidat zdroj do projektu a spravovat vlastnosti zpoždění vyrovnání v Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}