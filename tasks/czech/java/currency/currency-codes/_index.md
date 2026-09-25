---
date: 2026-09-25
description: Naučte se, jak získat kódy měn ze souborů MS Project pomocí Aspose.Tasks
  pro Java – rychlý způsob, jak získat kód měny, který potřebují vývojáři Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Správa kódů měn v Aspose.Tasks
og_description: Získání kódu měny java ze souborů MS Project pomocí Aspose.Tasks.
  Tento průvodce vám ukáže, jak načíst projekt, extrahovat ISO identifikátor měny
  a použít jej v Java aplikacích.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Získání kódu měny java z MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Získání kódu měny java z MS Project pomocí Aspose.Tasks
url: /cs/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Načtení měnového kódu java z MS Project pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **jak načíst měnový kód java** z souboru MS Project pomocí Aspose.Tasks Java API. Ať už potřebujete generovat více‑měnové finanční zprávy, konsolidovat projekty napříč různými regiony, nebo jen zobrazit správný měnový symbol v následném systému, níže uvedené kroky vás provedou od nastavení prostředí až po jednorázové volání, které vrátí ISO identifikátor měny. Na konci průvodce budete pohodlně načítat jakýkoli podporovaný formát souboru Project a získávat třípísmenný měnový kód, například `USD`, `EUR` nebo `GBP`.

## Rychlé odpovědi
- **Co API dělá?** Čte soubory MS Project a zpřístupňuje vlastnosti, jako je měnový kód.  
- **Jaký jazyk se používá?** Java, prostřednictvím knihovny Aspose.Tasks pro Java.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu získat kód v jednom řádku?** Ano — `prj.get(Prj.CURRENCY_CODE)` okamžitě vrátí řetězec s měnovým kódem.  
- **Je kompatibilní se všemi verzemi Project?** Aspose.Tasks podporuje více než 20 vstupních formátů, včetně starších MPP, XML a XER souborů.

## Co je čtení souboru MS Project?
Čtení souboru MS Project znamená programově otevřít soubor *.mpp* (nebo jakýkoli jiný podporovaný formát, jako XML nebo XER) a přistupovat k jeho vnitřním datovým strukturám. Tyto struktury zahrnují úkoly, zdroje, kalendáře, tabulky nákladů a finanční nastavení. Parsováním souboru můžete získat informace bez spouštění Microsoft Project, což umožňuje automatizované reportování, migraci a integrační workflow.

## Proč používat Aspose.Tasks k čtení souborů msproject?
Aspose.Tasks nabízí čistě Java řešení, které odstraňuje potřebu COM interop nebo lokální instalace Microsoft Project. Podporuje více než 20 formátů souborů, dokáže zpracovat projekty s tisíci úkoly při využití méně než 100 MB paměti a poskytuje bohatý objektový model. Přímý přístup ke konstantám jako `Prj.CURRENCY_CODE` vám umožní získat měnové informace okamžitě a spolehlivě.

## Požadavky
Než se ponoříte do kódu, ujistěte se, že máte následující:

### Java Development Kit (JDK) nainstalován
Požadován je aktuální JDK (11 nebo novější). Stáhněte jej z oficiálního Oracle webu: [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Knihovna Aspose.Tasks pro Java
Získejte nejnovější binární soubory Aspose.Tasks pro Java a přidejte je do classpath vašeho projektu. Kompletní dokumentace a odkazy ke stažení jsou k dispozici [zde](https://reference.aspose.com/tasks/java/).

## Import balíčků
Třída `Project` a konstanty `Prj` se nacházejí v jmenném prostoru `com.aspose.tasks`. Importujte je na začátku vašeho Java zdrojového souboru:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Postupný návod

### Krok 1: nastavení adresáře s daty
Definujte složku, která obsahuje váš *.mpp* soubor. Upravit cestu tak, aby odpovídala vašemu prostředí, aby runtime mohl soubor projektu najít.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: načtení souboru projektu
Třída `Project` je hlavní objekt Aspose.Tasks, který představuje jeden soubor MS Project v paměti. Vytvořením instance se soubor načte a vytvoří se model v paměti, který můžete dotazovat.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Krok 3: načtení měnového kódu
Konstanta `Prj.CURRENCY_CODE` identifikuje vlastnost, která ukládá ISO identifikátor měny. Volání `prj.get(Prj.CURRENCY_CODE)` vrátí třípísmenný kód v jedné operaci.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Výstup bude třípísmenný ISO měnový kód (např. `USD`, `EUR`, `GBP`), který je v projektu nastaven.

### Krok 4: jak načíst měnový kód v Javě (další kontext)
Načtěte svůj projekt, zavolejte `prj.get(Prj.CURRENCY_CODE)` a výsledek uložte do `String`. Tento hodnotu můžete následně předat jakékoli finanční službě, reportovacímu enginu nebo UI komponentě, která vyžaduje měnový identifikátor.

### Krok 5: (volitelné) použití měnového kódu
Typické scénáře downstream zahrnují:

- **Generování reportu** – připojte kód před sloupce nákladů (`USD 1,200`).  
- **Integrace API** – odešlete ISO kód platebním branám, které vyžadují parametr měny.  
- **Konsolidace dat** – seskupte více projektů podle měny pro analýzu na úrovni portfolia.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Null výstup** | Soubor projektu nedefinuje měnu (výchozí je prázdná). | Nastavte měnu v Microsoft Project nebo ji při čtení přiřaďte pomocí `prj.set(Prj.CURRENCY_CODE, "USD");`. |
| **Soubor nenalezen** | Nesprávná cesta `dataDir`. | Ověřte cestu a ujistěte se, že název souboru přesně odpovídá, včetně velikosti písmen. |
| **Nepodporovaná verze souboru** | Velmi starý nebo poškozený *.mpp* soubor. | Aktualizujte na nejnovější verzi Aspose.Tasks nebo nejprve soubor v Microsoft Project převedete do novějšího formátu. |

## Často kladené otázky

**Q: Dokáže Aspose.Tasks zvládnout složité struktury projektů?**  
A: Ano, API čte víceúrovňové hierarchie úkolů, zdrojové pooly, vlastní pole a kalendáře bez omezení.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů MS Project?**  
A: Rozhodně. Podporuje MPP, XML, XER a další formáty od Project 98 až po nejnovější verze Office.

**Q: Poskytuje Aspose.Tasks dokumentaci a podporu?**  
A: Komplexní reference API, příklady kódu a dedikovanou technickou podporu najdete na webu Aspose.

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano, je k dispozici bezplatná zkušební verze, která vám umožní vyhodnotit všechny funkce, včetně extrakce měnového kódu.

**Q: Kde mohu získat dočasnou licenci pro hodnocení?**  
A: Dočasné licence jsou k dispozici na [webu](https://purchase.aspose.com/temporary-license/).

**Poslední aktualizace:** 2026-09-25  
**Testováno s:** Aspose.Tasks for Java (nejnovější verze)  
**Autor:** Aspose

## Související tutoriály

- [Vlastnosti projektu Java – Čtení metadat s Aspose.Tasks](/tasks/java/project-properties/)
- [Jak číst informace o projektu z Microsoft Project s Aspose.Tasks pro Java](/tasks/java/project-properties/read-project-info/)
- [Načtení outline kódů MS Project v Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}