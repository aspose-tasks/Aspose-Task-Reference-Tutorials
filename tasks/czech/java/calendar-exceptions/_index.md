---
date: 2026-11-06
description: Jednoduše vytvořte vlastní výjimky kalendáře, integrujte kalendář MS
  Project a spravujte, definujte, zpracovávejte a načítejte výjimky kalendáře v Java
  projektech s Aspose.Tasks. Zefektivněte pracovní postupy projektů pro efektivní
  řízení projektů.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Výjimky kalendáře
og_description: Naučte se, jak vytvořit výjimky kalendáře v Java pomocí Aspose.Tasks.
  Spravujte kalendáře projektů, nastavujte nepracovní dny a efektivně upravujte kalendáře
  MS Project.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Vytvořte výjimky kalendáře pomocí Aspose.Tasks pro Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
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

`Aspose.Tasks` je knihovna Java, která umožňuje programové vytváření, manipulaci a konverzi souborů Microsoft Project. V tomto tutoriálu se naučíte, jak **vytvořit výjimky kalendáře** — vlastní nepracovní období, která přepisují výchozí kalendář projektu. Přesná kontrola nad pracovními a nepracovními dny je nezbytná pro přesné předpovídání harmonogramu, alokaci zdrojů a dodržování regionálních svátků. Na konci tohoto průvodce také zjistíte, jak **integrovat kalendář MS Project** do vaší Java aplikace a jak jeho výjimky načíst nebo upravit.

## Rychlé odpovědi
- **Co mohu dosáhnout?** Vytvářet, upravovat a načítat vlastní výjimky kalendáře v Java projektech.  
- **Která knihovna je vyžadována?** Aspose.Tasks for Java (nejnovější stabilní verze).  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu pracovat se soubory MS Project?** Samozřejmě – můžete importovat, upravovat a exportovat data kalendáře MS Project.  
- **Je potřeba nějaké speciální nastavení?** Stačí přidat Aspose.Tasks JAR do classpath a importovat příslušné třídy.

## Jak vytvořit vlastní výjimky kalendáře v Aspose.Tasks pro Java?

Pro vytvoření vlastních výjimek kalendáře v Aspose.Tasks pro Java načtěte cílový Project, získejte jeho Calendar, definujte počáteční a koncová data výjimky s požadovaným pracovním časem, případně nastavte vzor opakování a poté projekt uložte. Tento postup přidá výjimku okamžitě a uloží ji do souboru .mpp.

`Project` třída je hlavní objekt Aspose.Tasks, který modeluje celý soubor Microsoft Project. Třída `Project` představuje soubor Microsoft Project a poskytuje přístup k jeho obsahu. Objekt `Calendar` definuje pracovní a nepracovní časy pro projekt. Třída `Calendar` je kontejner pro všechna pravidla pracovního času, včetně výjimek. Metoda `addException()` přidá novou výjimku kalendáře do kalendáře. `addException()` je jednorázové API, které zaregistruje nepracovní období pro zadaný rozsah dat.

Načtěte cílový projekt pomocí `Project project = new Project("example.mpp")`, získejte jeho objekt `Calendar` a zavolejte `addException()` s požadovaným rozsahem dat a nastavením pracovního času. Tento dvoustupňový vzor vytvoří novou výjimku okamžitě a uloží ji při uložení projektu. Pro opakující se svátky nakonfigurujte na výjimce `RecurrencePattern` před uložením.

Vytvářením výjimek kalendáře tímto způsobem můžete **nastavit nepracovní dny** přesně, ať už jde o jednorázové odstávky nebo roční svátky. Po přidání výjimky můžete zavolat `project.save("updated.mpp")` pro zápis změn zpět na disk.

### Přehled kroků
1. Načtěte soubor projektu.  
2. Získejte nebo vytvořte instanci `Calendar`.  
3. Definujte rozsah dat výjimky a pracovní čas.  
4. (Volitelné) Nakonfigurujte opakování pro roční svátky.  
5. Uložte projekt.

## Správa výjimek kalendáře v Aspose.Tasks
[Zjistěte, jak efektivně přidávat a odstraňovat výjimky kalendáře v Aspose.Tasks pro Java](./add-remove/). Pokud jde o řízení projektů, klíčová je flexibilita. Aspose.Tasks vám umožňuje snadno spravovat výjimky kalendáře, což umožňuje dynamické úpravy časových os projektů. Tento tutoriál poskytuje krok‑za‑krokem průvodce, který vám pomůže proces efektivně pochopit. Objevte, jak snadno vylepšit své pracovní postupy řízení projektů.

## Definování pracovních dnů pro výjimky kalendáře s Aspose.Tasks
[Ovládněte umění definovat pracovní dny pro výjimky kalendáře v Java projektech](./define-weekdays/) using Aspose.Tasks. Přesné plánování projektů vyžaduje důkladnou pozornost k detailům. S Aspose.Tasks můžete přesně definovat pracovní dny pro výjimky kalendáře, což zajišťuje, že vaše projekty se bez problémů přizpůsobí konkrétním časovým rámcům. Tento tutoriál vám poskytne znalosti k optimalizaci plánování a dává vám kontrolu nad časovými osami projektu.

## Zpracování výskytů ve výjimkách kalendáře pomocí Aspose.Tasks
[Efektivně zpracovávejte výjimky kalendáře v Java projektech](./handle-occurrences/) with Aspose.Tasks for Java. Řízení projektů je dynamický proces, který často vyžaduje úpravy kvůli nečekaným událostem. Aspose.Tasks vám umožňuje efektivně zpracovávat výjimky kalendáře a poskytuje zjednodušený přístup k řízení projektů. Naučte se umění řídit nejistoty projektů snadno prostřednictvím tohoto podrobného tutoriálu.

## Načtení výjimek kalendáře s Aspose.Tasks
[Naučte se, jak načíst výjimky kalendáře z MS Project pomocí Aspose.Tasks pro Java](./retrieve/). Bez problémů integrujte výjimky kalendáře do svého procesu řízení projektů s Aspose.Tasks. Tento tutoriál vás provede krok‑za‑krokem procesem načítání výjimek kalendáře, což zajišťuje plynulou a efektivní integraci do vašich projektů. Odemkněte sílu Aspose.Tasks pro zlepšení vašich schopností řízení projektů.

## Jak integrovat kalendář MS Project s Aspose.Tasks?

Integrace kalendáře MS Project s Aspose.Tasks zahrnuje načtení zdrojového souboru .mpp pomocí třídy Project, přístup k jeho výchozím nebo vlastním objektům Calendar, úpravu nebo sloučení výjimek podle potřeby a následné uložení aktualizovaného projektu. To vám umožní programově pracovat s kalendáři MS Project bez ruční interakce s uživatelským rozhraním.

`Project` třída je hlavní objekt Aspose.Tasks, který modeluje celý soubor Microsoft Project. Importujte existující soubor MS Project pomocí `new Project("source.mpp")`; knihovna automaticky načte jeho výchozí kalendář a jakékoli vlastní výjimky. Poté můžete tyto výjimky číst, upravovat nebo sloučit před uložením projektu zpět na disk. Tento přístup vám umožní **upravit kalendář MS Project** programově bez ruční úpravy v uživatelském rozhraní MS Project.

## Běžné případy použití
- **Plánování svátků** – Definujte národní svátky jako nepracovní dny napříč více projekty.  
- **Směnná práce** – Nastavte vlastní pracovní týdny pro týmy pracující na nestandardních rozvrzích.  
- **Fázové řízení projektu** – Zablokujte období, kdy by neměla být naplánována žádná práce, například údržbová okna.  
- **Migrace starých verzí** – Importujte kalendáře ze starších souborů MS Project a upravte je programově.

## Tipy a osvědčené postupy
- **Profesionální tip:** Vždy načtěte existující kalendář před přidáním nových výjimek, aby nedocházelo k duplicitám.  
- **Varování:** Změna kalendáře, který je již přiřazen úkolům, může posunout data úkolů; po úpravách přepočítejte harmonogram.  
- **Výkon:** Hromadně aktualizujte více výjimek v jedné transakci, aby se snížila zátěž I/O souborů. Aspose.Tasks zpracovává soubory až do 1 GB při využití paměti pod 200 MB a dokáže zvládnout více než 30 API volání souvisejících s kalendářem za sekundu na typickém serverovém hardwaru.

## Tutoriály výjimek kalendáře
### [Správa výjimek kalendáře v Aspose.Tasks](./add-remove/)
Zjistěte, jak efektivně přidávat a odstraňovat výjimky kalendáře v Aspose.Tasks pro Java. Vylepšete pracovní postupy řízení projektů bez námahy.
### [Definování pracovních dnů pro výjimky kalendáře s Aspose.Tasks](./define-weekdays/)
Naučte se definovat pracovní dny pro výjimky kalendáře v Java projektech pomocí Aspose.Tasks pro přesné plánování projektů.
### [Zpracování výskytů ve výjimkách kalendáře pomocí Aspose.Tasks](./handle-occurrences/)
Naučte se efektivně zpracovávat výjimky kalendáře v Java projektech s Aspose.Tasks pro Java. Zjednodušte svůj proces řízení projektů již nyní.
### [Načtení výjimek kalendáře s Aspose.Tasks](./retrieve/)
Naučte se načíst výjimky kalendáře z MS Project pomocí Aspose.Tasks pro Java. Krok‑za‑krokem tutoriál pro bezproblémovou integraci.

## Často kladené otázky

**Q: Můžu upravit výjimky kalendáře po publikaci projektu?**  
A: Ano. Použijte API add‑remove a define‑weekdays k aktualizaci kalendáře, poté projektový soubor znovu uložte.

**Q: Podporuje Aspose.Tasks opakující se výjimky (např. každý první pondělí v měsíci)?**  
A: Rozhodně. Tutoriál „handle occurrences“ popisuje, jak nastavit opakující se vzory.

**Q: Jak zajistit, aby můj vlastní kalendář byl použit ve všech úkolech projektu?**  
A: Přiřaďte kalendář k výchozímu kalendáři projektu nebo jej explicitně nastavte na vlastnost `Calendar` každého úkolu.

**Q: Je možné sloučit kalendáře z více souborů MS Project?**  
A: Ano. Načtěte každý kalendář, programově spojte jejich výjimky a poté přiřaďte sloučený kalendář cílovému projektu.

**Q: Jaká verze Aspose.Tasks je potřebná pro tyto funkce?**  
A: Všechny funkce jsou k dispozici v aktuálním stabilním vydání Aspose.Tasks pro Java (2025.x).

## Související tutoriály

- [Vytvořit kalendář projektu Aspose – Definovat pracovní dny pro výjimky kalendáře](/tasks/java/calendar-exceptions/define-weekdays/)
- [Načíst výjimky kalendáře s Aspose.Tasks – tutoriál asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Vytvořit výjimku kalendáře Aspose pro Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Poslední aktualizace:** 2026-11-06  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}