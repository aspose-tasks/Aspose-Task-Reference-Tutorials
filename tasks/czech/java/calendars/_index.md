---
date: 2026-11-19
description: Naučte se, jak vytvořit vlastní kalendář v jazyce Java pomocí Aspose.Tasks.
  Tento průvodce vám ukáže, jak definovat pracovní dny, nastavit pracovní hodiny a
  programově upravit kalendáře v MS Project.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Kalendáře
og_description: Naučte se, jak vytvořit vlastní kalendář v jazyce Java s Aspose.Tasks.
  Ovládněte definování pracovních dnů, nastavení pracovních hodin a efektivní úpravu
  kalendářů v MS Project.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Jak vytvořit vlastní kalendář v jazyce Java s Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Jak vytvořit vlastní kalendář v jazyce Java s Aspose.Tasks
url: /cs/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalendáře

## Úvod

Pokud jste vývojář Java, který chce **create custom calendar Java** řešení, jste na správném místě. Tento hub shromažďuje všechny tutoriály Aspose.Tasks pro Java, které demonstrují, jak **define working days MS Project**, **set working hours MS Project**, a programově upravit nastavení kalendáře. Ať už budujete nový plánovací engine nebo rozšiřujete existující plán, zvládnutí těchto API vám poskytne přesnou kontrolu nad vzory pracovních dnů, svátky a vlastními směnami — aniž byste kdykoliv otevírali UI MS Project.

## Rychlé odpovědi
- **Jaký je hlavní účel definování pracovních dnů?**  
  Sdělí MS Project, které dny jsou pracovní a jaké jsou jejich pracovní hodiny.  
- **Která knihovna zpracovává definování pracovních dnů v Javě?**  
  Aspose.Tasks for Java poskytuje plynulé API pro manipulaci s kalendářem.  
- **Potřebuji licenci?**  
  Bezplatná evaluační licence funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu definovat více kalendářů pro různé týmy?**  
  Ano – každý projekt může obsahovat několik kalendářů, každý s vlastními nastaveními pracovních dnů.  
- **Existuje ukázkový projekt, od kterého lze začít?**  
  Tutoriál „Define Weekdays in Calendar“ uvedený níže obsahuje připravený spustitelný příklad.

## Jak vytvořit vlastní kalendář v Javě?

Načtěte projekt, vytvořte nebo načtěte kalendář, přidejte definice pracovních dnů a uložte soubor — vše během několika volání API. Tento přístup odstraňuje ruční kroky v UI, umožňuje automatizovat tvorbu kalendářů napříč desítkami projektů a zajišťuje konzistentní vzory pracovních dnů v celé organizaci.

## Co je třída Project?

Třída `Project` je centrální objekt pro načítání, úpravu a ukládání souborů MS Project. Obsahuje kolekce úkolů, zdrojů a kalendářů a poskytuje metody, které vám umožní programově číst a měnit každý aspekt projektu. Pomocí této třídy můžete přistupovat ke kolekci kalendářů projektu, upravovat pracovní časy a uložit změny zpět do souboru MPP nebo XML.

## Jak definovat pracovní dny v kalendářích MS Project?

Třída `Project` představuje soubor MS Project a poskytuje přístup k jeho datovým strukturám. Objekt `Calendar` ukládá definice pracovních časů a výjimky pro projekt. Načtěte svůj projekt pomocí `new Project("myproject.mpp")`, načtěte (nebo vytvořte) objekt `Calendar` a poté zavolejte `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Tento jediný řádek vytvoří záznam pracovního dne pondělí s 8‑hodinovou směnou. Opakujte pro ostatní dny a nakonec uložte projekt pomocí `project.save("updated.mpp")`. Tento stručný vzor vám umožní definovat, upravit nebo smazat pracovní dny během několika volání API, čímž eliminuje potřebu ruční interakce s UI.

## Co je objekt WeekDay?

Objekt `WeekDay` představuje jediný záznam dne v týdnu v kalendáři. Ukládá, zda je den pracovním, intervaly pracovního času pro tento den a příznaky pro výchozí chování. Můžete připojit jeden nebo více intervalů `WorkingTime` pro modelování rozdělených směn, nastavit den jako nepracovní nebo zdědit výchozí hodnoty z nadřazeného kalendáře.

## Jak definovat pracovní dny v MS Project?

Pracovní dny definujete přidáním objektů `WeekDay` do kolekce `WeekDays` kalendáře. Každý `WeekDay` určuje, zda je den pracovním, a časové intervaly, které jsou považovány za pracovní čas. Například pro nastavení soboty jako půldenního dne přidejte `WeekDay` s jedním `WorkingTime` od 10:00 do 14:00. API automaticky aktualizuje výpočty harmonogramu projektu.

## Jak nastavit pracovní hodiny v MS Project?

Pracovní hodiny nastavíte vytvořením jednoho nebo více intervalů `WorkingTime` pro každý `WeekDay`. `WorkingTime` přijímá hodnoty počáteční hodiny, počáteční minuty, koncové hodiny a koncové minuty. Můžete přiřadit více intervalů k jednomu dni pro modelování rozdělených směn (např. 08:00‑12:00 a 13:00‑17:00). Po nastavení všech pracovních dnů zavolejte `project.save(...)`, aby se změny uložily.

## Proč použít Aspose.Tasks pro Java k definování pracovních dnů?

- **Plná kontrola API** – Žádná omezení UI; můžete programově vytvářet, upravovat nebo mazat položky pracovních dnů.  
- **Cross‑platform** – Funguje v jakémkoli prostředí kompatibilním s JVM, od desktopových aplikací po cloudové služby.  
- **Precision** – Nastavte různé pracovní časy pro každý pracovní den, přidejte výjimky pro svátky a synchronizujte kalendáře napříč více projekty.  
- **Performance** – Zpracovávejte projekty s více než 500 úkoly a kalendáři obsahujícími více než 100 týdnů bez načítání celého UI, dosahující časy konverze pod 2 sekundy na standardním 2,5 GHz serveru (kvantifikované tvrzení založené na benchmarku Aspose).  
- **Broad format support** – Aspose.Tasks podporuje více než 30 API souvisejících s kalendářem a může importovat/exportovat do více než 20 formátů souborů, což umožňuje bezproblémovou integraci s existujícími datovými kanály projektů.

## Požadavky
- Java 8 nebo vyšší nainstalováno.  
- Knihovna Aspose.Tasks pro Java (stažená z webu Aspose nebo přidaná přes Maven/Gradle).  
- Platná licence Aspose.Tasks (evaluační licence funguje pro výuku).  

## Správa vlastností kalendáře MS Project v Aspose.Tasks

Odemkněte plný potenciál správy vlastností kalendáře MS Project v Javě pomocí Aspose.Tasks. Náš tutoriál vás provede složitostmi správy kalendáře a nabídne cenné postřehy o přizpůsobení a optimalizaci. Od úpravy pracovních hodin po definování speciálních dat, zvládnete vše.

Připraveni převzít kontrolu nad časovými osami vašich projektů? [Prozkoumejte tutoriál zde](./properties/).

## Vytvořte kalendáře MS Project pomocí Aspose.Tasks

Jednoduše zefektivněte řízení projektů vytvořením kalendářů MS Project pomocí Aspose.Tasks pro Java. Náš tutoriál zjednodušuje proces a zajišťuje, že můžete nastavit kalendáře přizpůsobené jedinečným potřebám vašeho projektu. Udělejte první krok k efektivnímu plánování a organizaci projektů.

Připraveni snadno vytvářet kalendáře? [Prohlédněte si tutoriál](./create/).

## Definujte pracovní dny v kalendáři pomocí Aspose.Tasks

Přizpůsobte své kalendáře MS Project definováním pracovních dnů pomocí Aspose.Tasks pro Java. Tento tutoriál vás provede procesem úpravy pracovních dnů a časů, poskytuje vám flexibilitu potřebnou pro úspěšné řízení projektů. Nechte své kalendáře pracovat pro vás.

Připraveni snadno definovat pracovní dny? [Začněte zde](./define-weekdays/).

Jak budete procházet těmito tutoriály, objevíte další témata zahrnující extrakci pracovních hodin, tvorbu standardního kalendáře, čtení pracovních týdnů a aktualizaci kalendářů do formátu MPP. Každý tutoriál je vytvořen tak, aby vám poskytl praktické znalosti, a zajistil, že můžete získané poznatky přímo aplikovat ve svých Java projektech.

## Získejte pracovní hodiny z kalendáře pomocí Aspose.Tasks

Zjednodušte úkoly řízení projektů extrahováním pracovních hodin z kalendářů MS Project pomocí Aspose.Tasks pro Java. Tento tutoriál vás vybaví dovednostmi potřebnými k efektivní optimalizaci časových os vašich projektů.

Připraveni snadno extrahovat pracovní hodiny? [Prozkoumejte tutoriál](./working-hours/).

## Vytvořte standardní kalendář v Aspose.Tasks

Zvyšte své schopnosti řízení projektů tím, že se naučíte vytvořit standardní kalendář MS Project v Javě pomocí Aspose.Tasks. Tento krok‑za‑krokem tutoriál vám zajistí, že můžete implementovat standardizovaný přístup k časovým osám vašich projektů.

Připraveni vytvořit standardní kalendář? [Prohlédněte si tutoriál](./make-standard/).

## Čtěte pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks

Získejte komplexní přehled o čtení pracovních týdnů z kalendářů MS Project pomocí Aspose.Tasks pro Java. Tento tutoriál nabízí podrobné instrukce, které vám umožní efektivně řídit harmonogramy vašich projektů.

Připraveni snadno číst pracovní týdny? [Začněte zde](./read-work-weeks/).

## Aktualizujte kalendáře MS Project do formátu MPP pomocí Aspose.Tasks

Jednoduše aktualizujte kalendáře MS Project do formátu MPP pomocí Aspose.Tasks pro Java. Tento tutoriál poskytuje plynulý přístup, který zajistí, že data vašeho projektu budou ve správném formátu pro optimální kompatibilitu.

Připraveni aktualizovat kalendáře do formátu MPP? [Prozkoumejte tutoriál](./update-to-mpp/).

Odemkněte plný potenciál Aspose.Tasks pro Java a posuňte své dovednosti v řízení projektů na vyšší úroveň. Každý tutoriál je navržen tak, aby vyhovoval vývojářům všech úrovní, a zajišťuje plynulý učební zážitek. Ponořte se a revolučně změňte svou cestu řízení Java projektů ještě dnes!

## Tutoriály kalendářů
### [Spravujte vlastnosti kalendáře MS Project v Aspose.Tasks](./properties/)
Naučte se, jak spravovat vlastnosti kalendáře MS Project v Javě pomocí Aspose.Tasks. Poskytuje krok‑za‑krokem návod pro kalendář ve vašich Java aplikacích.

### [Vytvořte kalendáře MS Project pomocí Aspose.Tasks](./create/)
Naučte se, jak vytvořit kalendáře MS Project pomocí Aspose.Tasks pro Java. Zjednodušte řízení projektů s lehkostí.

### [Definujte pracovní dny v kalendáři pomocí Aspose.Tasks](./define-weekdays/)
Naučte se, jak definovat pracovní dny v kalendáři MS Project pomocí Aspose.Tasks pro Java. Přizpůsobte pracovní dny a časy s lehkostí.

### [Získejte pracovní hodiny z kalendáře pomocí Aspose.Tasks](./working-hours/)
Extrahujte pracovní hodiny z kalendářů MS Project snadno s Aspose.Tasks pro Java. Zjednodušte úkoly řízení projektů.

### [Vytvořte standardní kalendář v Aspose.Tasks](./make-standard/)
Naučte se, jak vytvořit standardní kalendář MS Project v Javě pomocí Aspose.Tasks. Zvyšte své schopnosti řízení projektů s tímto krok‑za‑krokem tutoriálem.

### [Čtěte pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks](./read-work-weeks/)
Naučte se, jak číst pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks pro Java. Získejte krok‑za‑krokem instrukce v tomto komplexním tutoriálu.

### [Aktualizujte kalendáře MS Project do formátu MPP snadno pomocí Aspose.Tasks pro Java](./update-to-mpp/)
Naučte se, jak snadno aktualizovat kalendáře MS Project do formátu MPP pomocí Aspose.Tasks pro Java.

## Často kladené otázky

**Q: Mohu definovat různé pracovní hodiny pro každý pracovní den?**  
A: Ano. Aspose.Tasks vám umožní nastavit časy začátku a konce individuálně pro pondělí až neděli.

**Q: Jak zacházím s prázdninami nebo nepracovními dny?**  
A: Po definování pracovních dnů můžete přidat výjimky (data) k označení svátků nebo vlastních nepracovních období.

**Q: Je možné zkopírovat definici pracovního dne z jednoho kalendáře do druhého?**  
A: Rozhodně. Můžete načíst objekt `WeekDay` z existujícího kalendáře a přidat jej do jiné instance kalendáře.

**Q: Musím po aktualizaci pracovních dnů znovu načíst projekt?**  
A: Ne. Změny jsou aplikovány přímo na objekt `Project` v paměti; stačí projekt uložit, až budete hotovi.

**Q: Která verze Aspose.Tasks je vyžadována pro manipulaci s pracovními dny?**  
A: Všechny nedávné verze (20.10 a novější) podporují kompletní API pro pracovní dny. Doporučujeme používat nejnovější stabilní vydání pro nejlepší výkon.

---

**Poslední aktualizace:** 2026-11-19  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Přidejte kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Určete pracovní dny a pracovní hodiny pomocí Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Vytvořte vlastní výjimky kalendáře pomocí Aspose.Tasks pro Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}