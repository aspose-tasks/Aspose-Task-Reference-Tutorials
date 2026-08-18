---
date: 2026-08-18
description: Jednoduše vytvořte vlastní výjimky kalendáře, integrujte kalendář MS
  Project a spravujte, definujte, zpracovávejte a načítejte výjimky kalendáře v Java
  projektech s Aspose.Tasks. Zjednodušte pracovní postupy projektů pro efektivní řízení
  projektů.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Výjimky kalendáře
og_description: Naučte se, jak vytvořit výjimky kalendáře, spravovat projektový kalendář
  a nastavit nepracovní dny v Java pomocí Aspose.Tasks. Rychlý průvodce pro vývojáře.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Jak vytvořit výjimky kalendáře pomocí Aspose.Tasks pro Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Jak vytvořit výjimky kalendáře pomocí Aspose.Tasks pro Java
url: /cs/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit výjimky kalendáře pomocí Aspose.Tasks pro Java

## Úvod

`Aspose.Tasks` je knihovna pro Java, která umožňuje programové vytváření, manipulaci a konverzi souborů Microsoft Project. V tomto tutoriálu se naučíte, jak **vytvořit výjimky kalendáře** — vlastní nepracovní období, která přepíší výchozí kalendář projektu. Přesná kontrola nad pracovními a nepracovními dny je nezbytná pro přesné předpovídání harmonogramu, alokaci zdrojů a dodržování regionálních svátků. Na konci tohoto průvodce také budete vědět, jak **integrovat kalendář MS Project** do vaší Java aplikace a jak jeho výjimky načíst nebo upravit.

## Rychlé odpovědi
- **Co mohu dosáhnout?** Vytvářet, upravovat a načítat vlastní výjimky kalendáře v Java projektech.  
- **Která knihovna je vyžadována?** Aspose.Tasks for Java (latest stable release).  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu pracovat se soubory MS Project?** Rozhodně – můžete importovat, upravovat a exportovat data kalendáře MS Project.  
- **Je potřeba nějaké speciální nastavení?** Stačí přidat Aspose.Tasks JAR do classpath a importovat příslušné třídy.

## Jak vytvořit vlastní výjimky kalendáře v Aspose.Tasks pro Java?

Třída `Project` představuje soubor Microsoft Project a poskytuje přístup k jeho obsahu. Objekt `Calendar` definuje pracovní a nepracovní časy pro projekt. Metoda `addException()` přidá novou výjimku kalendáře do kalendáře.

Načtěte cílový projekt pomocí `Project project = new Project("example.mpp")`, získejte jeho objekt `Calendar` a zavolejte `addException()` s požadovaným rozsahem dat a nastavením pracovní doby. Tento dvoukrokový vzor okamžitě vytvoří novou výjimku a uloží ji při uložení projektu. Pro opakující se svátky nakonfigurujte `RecurrencePattern` na výjimce před uložením.

Vytváření výjimek kalendáře tímto způsobem vám umožní **přesně nastavit nepracovní dny**, ať už jde o jednorázové odstávky nebo roční svátky. Po přidání výjimky můžete zavolat `project.save("updated.mpp")`, aby se změny zapsaly na disk.

### Přehled kroků
1. Načtěte soubor projektu.  
2. Získejte nebo vytvořte instanci `Calendar`.  
3. Definujte časové rozmezí výjimky a pracovní dobu.  
4. (Volitelné) Nakonfigurujte opakování pro roční svátky.  
5. Uložte projekt.

## Správa výjimek kalendáře v Aspose.Tasks
[Zjistěte, jak efektivně přidávat a odstraňovat výjimky kalendáře v Aspose.Tasks pro Java](./add-remove/). Když jde o řízení projektů, flexibilita je klíčová. Aspose.Tasks vám umožňuje snadno spravovat výjimky kalendáře, což umožňuje dynamické úpravy časových plánů projektů. Tento tutoriál poskytuje krok‑za‑krokem návod, který vám pomůže proces pochopit efektivně. Objevte, jak s lehkostí vylepšit své pracovní postupy v řízení projektů.

## Definování pracovních dnů pro výjimky kalendáře pomocí Aspose.Tasks
[Ovládněte umění definovat pracovní dny pro výjimky kalendáře v Java projektech](./define-weekdays/) pomocí Aspose.Tasks. Přesné plánování projektů vyžaduje pečlivou pozornost k detailům. S Aspose.Tasks můžete přesně definovat pracovní dny pro výjimky kalendáře, což zajišťuje, že vaše projekty budou bezproblémově sladěny s konkrétními časovými rámci. Tento tutoriál vás vybaví znalostmi pro optimalizaci plánování a dává vám kontrolu nad časovými osami projektů.

## Zpracování výskytů ve výjimkách kalendáře pomocí Aspose.Tasks
[Efektivně zpracovávejte výjimky kalendáře v Java projektech](./handle-occurrences/) s Aspose.Tasks pro Java. Řízení projektů je dynamický proces, který často vyžaduje úpravy kvůli nečekaným událostem. Aspose.Tasks vám umožňuje výjimky kalendáře zpracovávat efektivně, poskytuje zjednodušený přístup k řízení projektů. Naučte se umění řídit nejistoty projektů s lehkostí prostřednictvím tohoto podrobného tutoriálu.

## Načtení výjimek kalendáře pomocí Aspose.Tasks
[Zjistěte, jak načíst výjimky kalendáře z MS Project pomocí Aspose.Tasks pro Java](./retrieve/). Bezproblémově integrujte výjimky kalendáře do svého procesu řízení projektů s Aspose.Tasks. Tento tutoriál vás provede krok‑za‑krokem procesem načítání výjimek kalendáře, což zajišťuje hladkou a efektivní integraci do vašich projektů. Odemkněte sílu Aspose.Tasks a rozšiřte své schopnosti v řízení projektů.

## Jak integrovat kalendář MS Project s Aspose.Tasks?

Třída `Project` načte soubor Microsoft Project a odhalí jeho kalendáře a další data projektu. Importujte existující soubor MS Project pomocí `new Project("source.mpp")`; knihovna automaticky načte výchozí kalendář a všechny vlastní výjimky. Poté můžete tyto výjimky číst, upravovat nebo sloučit před tím, než projekt opět uložíte na disk. Tento přístup vám umožní **programově upravovat data kalendáře MS Project** bez ručního zásahu v uživatelském rozhraní MS Project.

## Běžné případy použití
- **Plánování svátků** – Definujte národní svátky jako nepracovní dny napříč více projekty.  
- **Směnná práce** – Nastavte vlastní pracovní týdny pro týmy pracující na nestandardních rozvrzích.  
- **Fázové blokování projektu** – Zablokujte období, během nichž by neměla být naplánována žádná práce, například údržbová okna.  
- **Migrace starých verzí** – Importujte kalendáře ze starších souborů MS Project a upravujte je programově.

## Tipy a osvědčené postupy
- **Profesionální tip:** Vždy načtěte existující kalendář před přidáním nových výjimek, aby nedocházelo k duplicitám.  
- **Varování:** Změna kalendáře, který je již přiřazen úkolům, může posunout termíny úkolů; po úpravách přepočítejte harmonogram.  
- **Výkon:** Hromadně aktualizujte více výjimek v jedné transakci, abyste snížili zátěž I/O souborů. Aspose.Tasks zpracovává soubory až do 500 MB, aniž by načítal celý dokument do paměti, a zvládá více než 50 volání API souvisejících s kalendářem za sekundu na typickém serverovém hardware.

## Tutoriály k výjimkám kalendáře
### [Správa výjimek kalendáře v Aspose.Tasks](./add-remove/)
Naučte se, jak efektivně přidávat a odstraňovat výjimky kalendáře v Aspose.Tasks pro Java. Vylepšete pracovní postupy řízení projektů bez námahy.
### [Definování pracovních dnů pro výjimky kalendáře pomocí Aspose.Tasks](./define-weekdays/)
Naučte se, jak definovat pracovní dny pro výjimky kalendáře v Java projektech pomocí Aspose.Tasks pro přesné plánování projektů.
### [Zpracování výskytů ve výjimkách kalendáře pomocí Aspose.Tasks](./handle-occurrences/)
Naučte se, jak efektivně zpracovávat výjimky kalendáře v Java projektech s Aspose.Tasks pro Java. Zjednodušte svůj proces řízení projektů nyní.
### [Načtení výjimek kalendáře pomocí Aspose.Tasks](./retrieve/)
Naučte se, jak načíst výjimky kalendáře z MS Project pomocí Aspose.Tasks pro Java. Krok‑za‑krokem tutoriál pro bezproblémovou integraci.

## Často kladené otázky

**Q: Mohu upravit výjimky kalendáře po publikaci projektu?**  
A: Ano. Použijte API add‑remove a define‑weekdays k aktualizaci kalendáře a poté projektový soubor znovu uložte.

**Q: Podporuje Aspose.Tasks opakující se výjimky (např. každý první pondělí v měsíci)?**  
A: Rozhodně. Tutoriál „zpracování výskytů“ popisuje, jak nastavit opakující se vzory.

**Q: Jak zajistit, aby můj vlastní kalendář byl používán všemi úkoly v projektu?**  
A: Přiřaďte kalendář jako výchozí kalendář projektu nebo jej explicitně nastavte na vlastnost `Calendar` každého úkolu.

**Q: Je možné sloučit kalendáře z více souborů MS Project?**  
A: Ano. Načtěte každý kalendář, programově zkombinujte jejich výjimky a poté přiřaďte sloučený kalendář cílovému projektu.

**Q: Jaká verze Aspose.Tasks je pro tyto funkce vyžadována?**  
A: Všechny funkce jsou dostupné v aktuálním stabilním vydání Aspose.Tasks pro Java (2025.x).

---

**Poslední aktualizace:** 2026-08-18  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Vytvoření kalendáře projektu Aspose – Definování pracovních dnů pro výjimky kalendáře](/tasks/java/calendar-exceptions/define-weekdays/)
- [Načtení výjimek kalendáře s Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Vytvoření výjimky kalendáře Aspose pro Java](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}