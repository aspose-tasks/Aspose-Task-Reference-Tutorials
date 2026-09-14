---
date: 2026-09-14
description: Naučte se, jak změnit formát měny a číst vlastnosti měny v Javě pomocí
  Aspose.Tasks. Získejte kód měny, načtěte symbol měny a aktualizujte měnu projektu
  v souborech MS Project.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: Jak změnit formát měny
og_description: Naučte se, jak změnit formát měny a číst vlastnosti měny v Javě pomocí
  Aspose.Tasks. Podrobný návod krok za krokem pro získání kódu měny a aktualizaci
  měny projektu.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Jak změnit formát měny v Javě s Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Jak změnit formát měny v Javě s Aspose.Tasks
url: /cs/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení vlastností měny v Javě s Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte, jak **změnit formát měny** a číst vlastnosti měny v Java projektech používajících Aspose.Tasks. Přesná finanční data jsou nezbytná pro nadnárodní týmy a zvládnutí těchto API vám umožní získat kód ISO‑4217, načíst symbol měny a aktualizovat peněžní nastavení projektu bez ruční úpravy tabulek.

## Rychlé odpovědi
- **Co znamená „read currency“?** To znamená extrahování kódu měny, symbolu a nastavení formátu čísel uložených v souboru Project.  
- **Proč upravovat nastavení měny?** Aby se náklady v přehledech sladily s regionálními konvencemi a předešlo se chybám při převodu.  
- **Potřebuji licenci?** Ano – pro produkční nasazení je vyžadována platná licence Aspose.Tasks for Java; pro hodnocení stačí bezplatná zkušební verze.  
- **Které verze Project jsou podporovány?** Jak *.mpp* (Project 2007‑2024), tak *.xml* formáty jsou plně podporovány, pokrývají více než 20 let verzí souborů.  
- **Je potřeba nějaké další nastavení?** Stačí přidat JAR Aspose.Tasks for Java do classpath a importovat příslušné třídy.

## Čtení vlastností měny v Javě v projektech Aspose.Tasks
V dynamickém prostředí řízení projektů je získávání podrobností o měně nezbytné pro přesnou analýzu nákladů. Náš specializovaný průvodce **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)** vás provede každým krokem – od otevření souboru projektu po získání kódu měny, symbolu a formátu. Po absolvování tutoriálu budete schopni:

* Získat kód měny (např. USD, EUR) používaný v celém projektu.  
* Přistupovat k symbolu měny a nastavením formátování čísel.  
* Použít tyto informace k vytvoření lokalizovaných nákladových zpráv nebo napojení na finanční dashboardy.

Pochopení, jak číst měnu, zajišťuje, že můžete auditovat rozpočty projektů, porovnávat náklady napříč regiony a dodržovat účetní standardy.

## Jak extrahovat kód měny v Javě s Aspose.Tasks
Metoda `Project.getCurrencyCode()` vrací třípísmenný identifikátor ISO‑4217 pro peněžní jednotku projektu.

**Direct answer:** Zavolejte `project.getCurrencyCode()`, abyste získali kód měny, například **USD** nebo **EUR**; můžete jej následně uložit, zaznamenat nebo předat externím finančním službám pro konverzi. Tento jednorázový volání vám poskytuje spolehlivý, standardní identifikátor, který funguje ve všech podporovaných verzích Project.

Metoda poskytuje rychlý způsob, jak synchronizovat data projektu s ERP systémy, které očekávají standardizovaný kód.

## Jak upravit formát měny v Javě s Aspose.Tasks
Změna vizuálního zobrazení peněžních hodnot se provádí pomocí tří jednoduchých vlastností.

`project.setCurrencySymbol(String)` nastaví symbol měny zobrazovaný u peněžních hodnot.  
`project.setCurrencyDecimalSeparator(char)` určuje znak používaný k oddělení celého čísla od desetinné části.  
`project.setCurrencyThousandsSeparator(char)` určuje znak používaný k oddělení skupin tisíců.

**Direct answer:** Použijte `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")` a `project.setCurrencyThousandsSeparator(".")` k definování symbolu, desetinného oddělovače a oddělovače tisíců; tímto jedním krokem kompletně změníte formát měny. Úprava těchto nastavení zajišťuje, že každý zúčastněný vidí čísla v známém stylu, čímž se snižuje riziko špatného výkladu.

* `project.setCurrencySymbol("€")` – nastaví vizuální symbol.  
* `project.setCurrencyDecimalSeparator(",")` – určuje desetinný oddělovač.  
* `project.setCurrencyThousandsSeparator(".")` – určuje oddělovač tisíců.  

## Jak nastavit vlastnosti měny v projektech Aspose.Tasks
Když se projekt přesune na nový trh nebo klient požaduje jiný peněžní formát, budete muset měnu aktualizovat programově.

`project.setCurrencyCode(String)` definuje ISO‑4217 kód měny pro projekt.

**Direct answer:** Zavolejte `project.setCurrencyCode("GBP")` spolu s `project.setCurrencySymbol("£")` a příslušnými oddělovači, poté projekt uložte; knihovna aktualizuje všechna zobrazovací nastavení a zachová existující nákladová data. Tento přístup vám poskytuje plnou kontrolu nad finanční reprezentací vašeho harmonogramu.

Náš krok‑za‑krokem průvodce **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** vysvětluje, jak:

* Definovat nový kód měny a symbol pro celý projekt.  
* Upravit formát čísel (desetinná místa, oddělovače tisíců) tak, aby odpovídal místním konvencím.  
* Uložit aktualizovaný soubor projektu bez ztráty existujících dat.

Zvládnutím nastavení měny můžete během provozu přepínat mezi USD, GBP, JPY nebo jakoukoli podporovanou měnou.

## Proč zvládat práci s měnou v Aspose.Tasks?
Správná práce s měnou eliminuje nákladné nedorozumění a zjednodušuje globální spolupráci.

**Direct answer:** Zvládnutí práce s měnou vám umožní prezentovat náklady v nativním formátu každého týmu, zajistit přesné reportování, dodržovat regionální účetní standardy a umožnit automatizované finanční workflow – čímž ušetříte hodiny ručního přeformátování na projekt.

* **Globální spolupráce:** Týmy v různých zemích mohou vidět náklady ve svém nativním formátu.  
* **Přesné reportování:** Zabrání zaokrouhlovacím nebo konverzním chybám, které by mohly ovlivnit rozpočtování.  
* **Soulad:** Přizpůsobení se regionálním účetním standardům a specifikacím klienta.  
* **Automatizace:** Snížení ručních úprav programovým nastavením měny během generování projektu.

## Reálné příklady použití
* **Mezinárodní projekty:** Stavební firma spravující stavby v Evropě a Severní Americe potřebuje prezentovat rozpočty jak v EUR, tak v USD.  
* **Finanční audity:** Auditoři vyžadují jasný přehled o kontextu měny pro každý nákladový záznam.  
* **Dynamické cenové modely:** Poskytovatelé SaaS upravují poplatky za předplatné podle místní měny zákazníka.

## Časté úskalí a tipy
* **Úskalí:** Zapomenout aktualizovat symbol měny po změně kódu.  
  **Tip:** Vždy nastavte zároveň kód i symbol, aby nedošlo k nesouladu v zobrazení.  
* **Úskalí:** Spoléhat se na výchozí locale stroje, na kterém kód běží.  
  **Tip:** Výslovně specifikujte požadovaný formát měny ve svém kódu Aspose.Tasks, aby byla zajištěna konzistence napříč prostředími.  

## Tutoriály k vlastnostem měny
### [Čtení vlastností měny v projektech Aspose.Tasks](./read-properties/)
Naučte se, jak extrahovat informace o měně ze souborů MS Project pomocí Aspose.Tasks pro Java. Poskytnutý krok‑za‑krokem průvodce.

### [Nastavení vlastností měny v projektech Aspose.Tasks](./set-properties/)
Naučte se, jak nastavit vlastnosti měny v projektech Aspose.Tasks pomocí Javy. Snadno manipulujte se soubory Microsoft Project.

## Často kladené otázky

**Q: Mohu změnit měnu po tom, co byl projekt již uložen?**  
A: Ano. Použijte `Project.setCurrencyCode()` a související metody, poté projekt znovu uložte.

**Q: Ovlivní změna měny existující hodnoty nákladů?**  
A: Číselné hodnoty zůstávají beze změny; aktualizuje se pouze zobrazovací formát (symbol, desetinný oddělovač). Pokud potřebujete konverzi mezi měnami, musíte náklady přepočítat.

**Q: Existují nějaká omezení počtu měn, které mohu definovat?**  
A: Aspose.Tasks podporuje jakýkoli kód měny ISO‑4217, takže prakticky neexistuje limit.

**Q: Co se stane, když otevřu projekt s nepodporovaným kódem měny?**  
A: Knihovna přejde na výchozí měnu (USD) a zaznamená varování; můžete to přepsat ručním nastavením požadované měny.

**Q: Je možné číst/zapisovat vlastnosti měny v XML souboru projektu?**  
A: Rozhodně. Stejné API funguje jak pro formáty *.mpp*, tak *.xml*.

---

**Poslední aktualizace:** 2026-09-14  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [java projektové vlastnosti – Extrahovat symbol měny z MPP pomocí Aspose.Tasks pro Java](/tasks/java/currency/currency-symbols/)
- [Jak získat měnu z MS Project pomocí Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Projektové vlastnosti Java – Číst metadata pomocí Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}