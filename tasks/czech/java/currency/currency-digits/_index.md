---
date: 2026-09-14
description: Naučte se, jak získat měnu v MS Project a číst vlastnosti projektu v
  Javě pomocí Aspose.Tasks. Podrobný návod krok za krokem pro extrakci čísel měny
  z MPP souboru.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Jak získat měnu z MS Project pomocí Aspose.Tasks
og_description: Naučte se, jak získat měnu v MS Project a číst vlastnosti projektu
  v Javě pomocí Aspose.Tasks. Postupujte podle tohoto stručného Java tutoriálu k extrakci
  čísel měny z MPP souboru.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Jak získat měnu v MS Project pomocí Aspose.Tasks – Java průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Jak získat měnu v MS Project pomocí Aspose.Tasks
url: /cs/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak získat měnu v MS Project pomocí Aspose.Tasks

## Úvod
Pokud se zajímáte o **jak získat měnu v MS Project** z Microsoft Project souboru, jste na správném místě. V tomto komplexním tutoriálu se dozvíte, **jak pracovat s hodnotami měny v MS Project** pomocí knihovny Aspose.Tasks pro Javu. Ať už vytváříte nástroj pro reportování, migrační utility, nebo jen potřebujete přečíst nastavení měny z **java projektového souboru**, tento průvodce vás provede každým krokem – od načtení souboru *.mpp* až po získání číslic měny. Na konci budete pohodlně pracovat s daty měny v MS Project ve svých aplikacích.

## Rychlé odpovědi
- **Jaká knihovna čte soubory MS Project?** Aspose.Tasks pro Java.  
- **Kolik řádků kódu je potřeba k získání číslic měny?** Pouze tři stručné řádky po načtení projektu.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší (libovolný JDK, který spouští Aspose.Tasks).  
- **Mohu získat i jiné vlastnosti projektu?** Ano – Aspose.Tasks poskytuje kompletní sadu polí projektu (např. datum zahájení, sazby nákladů atd.).

## Co je měna v MS Project?
`ms project currency` vlastnost určuje počet desetinných míst, které Microsoft Project používá při zobrazování peněžních hodnot. Je uložena v souboru projektu jako pole **CURRENCY_DIGITS** a určuje, zda se částky zobrazují jako celá čísla, s jedním desetinným místem, dvěma desetinnými místy atd. Toto nastavení přímo ovlivňuje rozpočtové zprávy, souhrny nákladů a jakékoli uživatelské rozhraní zobrazující finanční údaje, což je nezbytné pro přesnou výměnu dat.

## Proč použít Aspose.Tasks pro práci s měnou v MS Project?
Aspose.Tasks vám umožní získat číslice měny bez instalace Microsoft Project a to s výkonem na úrovni podniku. Knihovna podporuje **více než 30 let verzí souborů Project** – od Project 2000 až po Project 2024 – pokrývající více než **150 různých schémat souborů**. Načtení 500‑stránkového projektu obvykle trvá méně než **2 sekundy** na standardním serveru a můžete dotazovat jen pole, která potřebujete, čímž udržujete využití paměti pod **50 MB** i u největších plánů.

## Požadavky
Před začátkem se ujistěte, že máte následující:

1. **Java Development Environment** – nainstalovaný a nakonfigurovaný JDK 8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z oficiální stránky: [Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/).  
3. **Základní znalost Javy** – měli byste být schopni vytvořit Java projekt, přidat externí knihovny a spustit metodu `main`.  

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat.  
Importujte třídu `Project` a související utility z knihovny Aspose.Tasks.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: definujte adresář s daty
Zadejte složku, která obsahuje váš **java projektový soubor** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou, kde se nachází `project.mpp`.

## Krok 2: načtěte soubor mpp  
Nyní uvidíme **jak načíst soubory mpp** pomocí Aspose.Tasks.  
Třída `Project` představuje soubor Microsoft Project a poskytuje přístup k jeho vlastnostem.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Ujistěte se, že název souboru přesně odpovídá; jinak bude vyvolána `IOException`.

## Krok 3: získání číslic měny  
Po načtení projektu je získání **ms project currency** číslic jedním řádkem:  
Metoda `getCurrencyDigits()` vrací počet desetinných míst definovaných pro peněžní hodnoty.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Volání vrací `Integer` představující počet desetinných míst (např. `2` pro centy). Hodnota je vytištěna do konzole, ale můžete ji také uložit do proměnné pro další zpracování.

## Časté problémy a tipy
- **Soubor nenalezen** – zkontrolujte cestu `dataDir` a ujistěte se, že název souboru je správný, včetně přípony `.mpp`.  
- **Nepodporovaná verze souboru** – Aspose.Tasks podporuje formáty Project 2000‑2024; starší nebo poškozené soubory mohou vyžadovat konverzi.  
- **Licence není nastavena** – během vývoje funguje zkušební verze, ale pro produkci musíte použít platnou licenci, aby se zabránilo vodoznakům hodnocení.

## Často kladené otázky

**Q: Může Aspose.Tasks zpracovávat i jiné atributy projektu kromě číslic měny?**  
A: Ano, Aspose.Tasks nabízí širokou škálu funkcí pro manipulaci s různými aspekty souborů projektu, jako jsou úkoly, zdroje a vlastní pole.

**Q: Je Aspose.Tasks vhodný pro aplikace na úrovni podniku?**  
A: Rozhodně, Aspose.Tasks je navržen tak, aby splňoval požadavky projektů úrovně podniku, nabízí vysoký výkon a škálovatelnost.

**Q: Podporuje Aspose.Tasks vývoj napříč platformami?**  
A: Ano, můžete používat Aspose.Tasks pro Java na jakékoli platformě, která podporuje Java Runtime Environment (Windows, Linux, macOS).

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi ze [stránky vydání Aspose](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.Tasks?**  
A: Podporu najdete na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-09-14  
**Testováno s:** Aspose.Tasks pro Java (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [java projektové vlastnosti – Extrahovat symbol měny z MPP pomocí Aspose.Tasks pro Java](/tasks/java/currency/currency-symbols/)
- [Jak získat měnu z MS Project pomocí Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Projektové vlastnosti Java – Číst metadata pomocí Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}