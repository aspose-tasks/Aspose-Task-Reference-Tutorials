---
date: 2026-09-09
description: Naučte se, jak změnit symbol měny v projektech Aspose.Tasks v jazyce
  Java, nastavit kódy měn, upravit symboly a použít vlastní formáty pro soubory Microsoft
  Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Nastavení vlastností měny v projektech Aspose.Tasks
og_description: Jak změnit symbol měny v Aspose.Tasks pomocí jazyka Java. Objevte
  podrobné instrukce, předpoklady a tipy pro přizpůsobení formátování nákladů projektu.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Jak změnit symbol měny v Aspose.Tasks – průvodce pro Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Jak změnit symbol měny v projektech Aspose.Tasks – průvodce pro Java
url: /cs/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit symbol měny v Aspose.Tasks – průvodce pro Java

## Úvod

V tomto tutoriálu se naučíte **jak změnit symbol měny** pro soubor Microsoft Project pomocí Aspose.Tasks Java API. Ať už připravujete zprávy pro zahraničního klienta, konsolidujete rozpočty napříč více regiony, nebo jen potřebujete sladit účetní standardy vaší společnosti, úprava symbolu měny zajistí, že každé pole související s náklady zobrazí správný měnový znak. Průvodce vás provede všemi kroky, od nastavení vývojového prostředí až po uložení změn do nového nebo existujícího souboru projektu.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Tasks for Java.  
- **Mohu změnit symbol měny?** Ano – nastavte `Prj.CURRENCY_SYMBOL` a vyberte `CurrencySymbolPositionType`.  
- **Jaké formáty souborů jsou podporovány?** XML, MPP a mnoho dalších přes `SaveFileFormat`.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze stačí pro testování; licence je vyžadována pro produkci.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní nastavení.

## Jak změnit symbol měny v Aspose.Tasks pomocí Java?
Načtěte cílový projekt (nebo vytvořte nový), nastavte požadované vlastnosti měny a soubor uložte. Celá operace se skládá ze tří volání API: vytvoření nebo načtení objektu `Project`, přiřazení kódu měny, symbolu a pozice, a následné volání `project.save`. Tento přístup funguje jak pro nové projekty, tak pro existující soubory, aniž by bylo nutné mít nainstalovaný Microsoft Project.

## Proč použít Aspose.Tasks ke změně měny?
Aspose.Tasks poskytuje **úplné pokrytí API pro více než 30 vlastností souvisejících s měnou**, což vám umožní definovat kód, symbol, počet desetinných míst a umístění na jednom místě. Knihovna zpracuje stovky stránek projektových souborů za méně než sekundu na typickém serverovém hardware a funguje na Windows, Linuxu i macOS bez dalších závislostí.

## Předpoklady
Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK) 8 nebo vyšší** – API vyžaduje alespoň JDK 8.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA nebo jakýkoli editor podporující Javu.  
4. **Zapisovatelnou složku** – kam bude uložen vygenerovaný soubor projektu.

## Importovat balíčky
Následující třídy vám poskytují přístup k vlastnostem projektu, práci se soubory a nastavením měny.  

`Project` – představuje soubor Microsoft Project v paměti.  
`Prj` – obsahuje konstanty pro všechny vlastnosti na úrovni projektu, včetně polí měny.  
`CurrencySymbolPositionType` – vyjmenovává možné pozice symbolu měny (před nebo za částkou).  

Tyto importy jsou vyžadovány před tím, než může jakýkoli kód manipulovat s projektem.

## Průvodce krok za krokem

### Krok 1: Definovat adresář s daty
Vyberte složku, která obsahuje vaše zdrojové soubory a kam bude zapisován výstup. Ujistěte se, že adresář existuje a že váš Java proces má právo zápisu.

### Krok 2: Vytvořit novou instanci projektu
Třída `Project` je hlavní objekt Aspose.Tasks, který představuje jeden soubor Project v paměti. Jeho vytvoření vytvoří prázdný projekt připravený k nastavení.

### Krok 3: Nastavit vlastnosti měny
Zde nakonfigurujete kód měny, počet desetinných míst, samotný symbol a jeho pozici.  

- **Currency code** – třípísmenný kód ISO 4217, například `AUD` nebo `USD`.  
- **Decimal digits** – typicky 2 pro většinu měn.  
- **Currency symbol** – znak nebo řetězec zobrazovaný u částek, např. `$` nebo `€`.  
- **Symbol position** – `CurrencySymbolPositionType.Before` umístí symbol před číslo; `After` ho umístí za číslo.

Toto nastavení ovlivní každé pole související s náklady (sazby zdrojů, rozpočty úkolů atd.) v projektu.

> **Pro tip:** Pokud potřebujete změnit měnu v existujícím souboru, načtěte jej pomocí `new Project("file.mpp")` před aplikací výše uvedených nastavení.

### Krok 4: Uložit aktualizovaný projekt
Zapište projekt zpět na disk ve požadovaném formátu. Formát XML je čitelný pro člověka, zatímco `SaveFileFormat.MPP` zachovává plnou kompatibilitu s Microsoft Project.

### Krok 5: Potvrdit úspěch
Vytiskněte krátkou zprávu nebo záznam do logu, abyste věděli, že operace proběhla bez chyb. To je zvláště užitečné v automatizovaných pipelinech.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` není platná cesta nebo nemá právo zápisu. | Ujistěte se, že adresář existuje a že váš Java proces má přístup k zápisu. |
| **Symbol měny se nezobrazuje** | Pozice symbolu je nastavena nesprávně pro vaši lokalitu. | Použijte `CurrencySymbolPositionType.Before`, pokud má symbol předcházet částce. |
| **Soubor projektu se neotevře v MS Project** | Ukládání ve starším formátu s nekompatibilními nastaveními. | Uložte pomocí `SaveFileFormat.MPP` pro plnou kompatibilitu s aktuálními verzemi MS Project. |

## Často kladené otázky

**Q: Mohu v jednom projektu nastavit více měn pomocí Aspose.Tasks?**  
A: Ano, můžete přiřadit různá nastavení měny jednotlivým zdrojům nebo úkolům úpravou jejich příslušných polí nákladů po definování měny na úrovni projektu.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Rozhodně. Knihovna podporuje MPP soubory od Project 2000 až po nejnovější vydání, stejně jako XML a další výměnné formáty.

**Q: Poskytuje Aspose.Tasks podporu pro vlastní formáty měny?**  
A: Ano, můžete definovat vlastní symboly, počet desetinných míst a jejich umístění tak, aby vyhovovaly jakýmkoli regionálním požadavkům, a tato nastavení jsou uložena v souboru.

**Q: Můžu integrovat Aspose.Tasks s jinými Java frameworky?**  
A: Samozřejmě. API je čistě Java, takže funguje hladce se Spring, Hibernate, Maven, Gradle a dalšími ekosystémy.

**Q: Kde najdu další pomoc nebo příklady?**  
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro komunitní podporu nebo si prostudujte oficiální dokumentaci pro podrobné reference API.

## Závěr
Nyní víte **jak změnit symbol měny** v projektech Aspose.Tasks pomocí Javy, jak nastavit kód měny, upravit počet desetinných míst a aplikovat vlastní symbol. Tyto možnosti vám umožní generovat lokálně specifické nákladové zprávy, sladit rozpočty projektů s regionálními účetními standardy a udržet soubory Microsoft Project konzistentní napříč globálními týmy.

---

**Poslední aktualizace:** 2026-09-09  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Související tutoriály

- [java project properties – Extrahovat symbol měny z MPP pomocí Aspose.Tasks pro Java](/tasks/java/currency/currency-symbols/)
- [Číst vlastnosti měny v Javě s projekty Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Spravovat kódy měn v Javě s Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}