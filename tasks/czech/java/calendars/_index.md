---
date: 2026-08-08
description: Naučte se, jak definovat pracovní dny v kalendářích MS Project pomocí
  Aspose.Tasks pro Java. Tento průvodce vám ukáže, jak upravit kalendář MS Project,
  vytvořit vlastní kalendář Java a efektivně naplánovat pracovní dny.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Kalendáře
og_description: Naučte se, jak definovat pracovní dny v kalendářích MS Project pomocí
  Aspose.Tasks pro Java. Tento průvodce vám ukáže, jak upravit kalendář MS Project,
  vytvořit vlastní kalendář Java a efektivně naplánovat pracovní dny.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Jak definovat pracovní dny v kalendářích MS Project – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: Jak definovat pracovní dny v kalendářích MS Project – Aspose.Tasks Java
url: /cs/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalendáře

## Úvod

Pokud jste vývojář Java a hledáte **definovat pracovní dny** ve svém projektovém plánu, jste na správném místě. V tomto hubu shromažďujeme všechny tutoriály Aspose.Tasks pro Java, které ukazují **jak definovat pracovní dny** v kalendářích MS Project, upravovat pracovní hodiny a udržet vaše časové osy průhledně jasné. Ať už budujete nový plánovací engine nebo upravujete existující plán, zvládnutí definice pracovních dnů vám poskytuje přesnou kontrolu nad vzory pracovních dnů, svátky a vlastními směnami. Tento průvodce také vysvětluje **jak programově upravit nastavení kalendáře MS Project**, takže můžete automatizovat vytváření kalendářů napříč desítkami projektů.

## Rychlé odpovědi
- **Jaký je hlavní účel definování pracovních dnů?**  
  Říci MS Project, které dny jsou pracovní a jaké jsou jejich pracovní hodiny.
- **Která knihovna zajišťuje definování pracovních dnů v Javě?**  
  Aspose.Tasks for Java poskytuje plynulé API pro manipulaci s kalendářem.
- **Potřebuji licenci?**  
  Bezplatná evaluační licence funguje pro testování; pro produkci je vyžadována komerční licence.
- **Mohu definovat více kalendářů pro různé týmy?**  
  Ano – každý projekt může obsahovat několik kalendářů, každý s vlastními nastaveními pracovních dnů.
- **Existuje ukázkový projekt, od kterého začít?**  
  Tutoriál „Define Weekdays in Calendar“ uvedený níže obsahuje připravený spustitelný příklad.

## Jak definovat pracovní dny v kalendářích MS Project?

`Project` třída představuje soubor MS Project a poskytuje přístup k jeho datovým strukturám. Objekt `Calendar` ukládá definice pracovního času a výjimky pro projekt. Načtěte svůj projekt pomocí `new Project("myproject.mpp")`, získejte (nebo vytvořte) objekt `Calendar` a poté zavolejte `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Tento jediný řádek vytvoří záznam pracovního dne pondělí s 8‑hodinovou směnou. Opakujte pro další dny a nakonec uložte projekt pomocí `project.save("updated.mpp")`. Tento stručný vzor vám umožní definovat, upravit nebo odstranit pracovní dny pomocí několika volání API, čímž eliminuje potřebu ruční interakce s UI.

## Co je objekt WeekDay?

`WeekDay` objekt představuje jedinečný záznam dne v týdnu v kalendáři Aspose.Tasks, ukládající jeho pracovní stav a intervaly pracovního času. Můžete nastavit časy začátku/konce, označit jej jako nepracovní, nebo připojit přesčasy. Může obsahovat více intervalů `WorkingTime` pro modelování rozdělených směn a podporuje příznaky pro výchozí pracovní dny. Použijte API `WeekDay` k povolení nebo zakázání dne, přiřazení běžných hodin nebo specifikaci pravidel přesčasů pro pokročilé scénáře plánování.

## Proč použít Aspose.Tasks pro Java k definování pracovních dnů?

- **Plná kontrola API** – Žádná omezení UI; můžete programově vytvářet, upravovat nebo mazat záznamy pracovních dnů.  
- **Cross‑platform** – Funguje v jakémkoli prostředí kompatibilním s JVM, od desktopových aplikací po cloudové služby.  
- **Přesnost** – Nastavte různé pracovní časy pro každý pracovní den, přidejte výjimky pro svátky a synchronizujte kalendáře napříč více projekty.  
- **Výkon** – Zpracovávejte projekty s více než 500 úkoly a kalendáře obsahující více než 100 týdnů bez načítání celé UI, dosahující dobu konverze pod 2 sekundy na standardním 2,5 GHz serveru (kvantifikované tvrzení založené na benchmarku Aspose).  

## Prerequisites
- Java 8 nebo vyšší nainstalována.  
- Knihovna Aspose.Tasks pro Java (stažená z webu Aspose nebo přidaná přes Maven/Gradle).  
- Platná licence Aspose.Tasks (evaluační licence funguje pro výuku).  

## Správa vlastností kalendáře MS Project v Aspose.Tasks

Odemkněte plný potenciál správy vlastností kalendáře MS Project v Javě pomocí Aspose.Tasks. Náš tutoriál vás provede složitostmi správy kalendáře a nabídne cenné postřehy o přizpůsobení a optimalizaci. Od úpravy pracovních hodin po definování speciálních dat, zvládnete vše.

Připraveni převzít kontrolu nad časovými osami vašeho projektu? [Explore the tutorial here](./properties/).

## Vytvoření kalendářů MS Project pomocí Aspose.Tasks

Bez námahy zefektivněte správu projektů vytvořením kalendářů MS Project pomocí Aspose.Tasks pro Java. Náš tutoriál zjednodušuje proces a zajišťuje, že můžete nastavit kalendáře přizpůsobené jedinečným potřebám vašeho projektu. Udělejte první krok k efektivnímu plánování a organizaci projektů.

Připraveni snadno vytvořit kalendáře? [Check out the tutorial](./create/).

## Definování pracovních dnů v kalendáři pomocí Aspose.Tasks

Přizpůsobte své kalendáře MS Project definováním pracovních dnů pomocí Aspose.Tasks pro Java. Tento tutoriál vás provede procesem úpravy pracovních dnů a časů, poskytující flexibilitu potřebnou pro úspěšnou správu projektů. Nechte své kalendáře pracovat pro vás.

Připraveni snadno definovat pracovní dny? [Get started here](./define-weekdays/).

Při procházení těmito tutoriály objevíte další témata zahrnující extrakci pracovních hodin, vytvoření standardního kalendáře, čtení pracovních týdnů a aktualizaci kalendářů do formátu MPP. Každý tutoriál je vytvořen tak, aby vám poskytl praktické znalosti, a zajistil, že můžete získané poznatky přímo aplikovat ve svých Java projektech.

## Získání pracovních hodin z kalendáře pomocí Aspose.Tasks

Zjednodušte úkoly správy projektů extrahováním pracovních hodin z kalendářů MS Project pomocí Aspose.Tasks pro Java. Tento tutoriál vás vybaví dovednostmi potřebnými k efektivní optimalizaci časových os vašich projektů.

Připraveni snadno extrahovat pracovní hodiny? [Explore the tutorial](./working-hours/).

## Vytvoření standardního kalendáře v Aspose.Tasks

Zvyšte své schopnosti správy projektů tím, že se naučíte vytvořit standardní kalendář MS Project v Javě s Aspose.Tasks. Tento krok‑za‑krokem tutoriál vám zajistí, že můžete implementovat standardizovaný přístup k časovým osám vašich projektů.

Připraveni vytvořit standardní kalendář? [Check out the tutorial](./make-standard/).

## Čtení pracovních týdnů z kalendáře MS Project pomocí Aspose.Tasks

Získejte komplexní přehled o čtení pracovních týdnů z kalendářů MS Project pomocí Aspose.Tasks pro Java. Tento tutoriál nabízí podrobné instrukce, které vám umožní efektivně spravovat harmonogramy vašich projektů.

Připraveni snadno číst pracovní týdny? [Get started here](./read-work-weeks/).

## Aktualizace kalendářů MS Project do formátu MPP pomocí Aspose.Tasks

Bez námahy aktualizujte kalendáře MS Project do formátu MPP pomocí Aspose.Tasks pro Java. Tento tutoriál poskytuje plynulý přístup, který zajistí, že data vašeho projektu jsou ve správném formátu pro optimální kompatibilitu.

Připraveni aktualizovat kalendáře do formátu MPP? [Explore the tutorial](./update-to-mpp/).

Odemkněte plný potenciál Aspose.Tasks pro Java a posuňte své dovednosti ve správě projektů na vyšší úroveň. Každý tutoriál je navržen tak, aby vyhovoval vývojářům všech úrovní, a zajišťuje plynulý učební zážitek. Ponořte se a revolučně změňte svou cestu správy Java projektů ještě dnes!

## Tutoriály kalendářů
### [Správa vlastností kalendáře MS Project v Aspose.Tasks](./properties/)
Zjistěte, jak spravovat vlastnosti kalendáře MS Project v Javě pomocí Aspose.Tasks. Poskytuje krok‑za‑krokem návod pro kalendář ve vašich Java aplikacích.
### [Vytvoření kalendářů MS Project pomocí Aspose.Tasks](./create/)
Naučte se vytvářet kalendáře MS Project pomocí Aspose.Tasks pro Java. Zjednodušte správu projektů s lehkostí.
### [Definování pracovních dnů v kalendáři pomocí Aspose.Tasks](./define-weekdays/)
Naučte se definovat pracovní dny v kalendáři MS Project pomocí Aspose.Tasks pro Java. Přizpůsobte pracovní dny a časy s lehkostí.
### [Získání pracovních hodin z kalendáře pomocí Aspose.Tasks](./working-hours/)
Jednoduše extrahujte pracovní hodiny z kalendářů MS Project pomocí Aspose.Tasks pro Java. Zjednodušte úkoly správy projektů.
### [Vytvoření standardního kalendáře v Aspose.Tasks](./make-standard/)
Naučte se vytvořit standardní kalendář MS Project v Javě pomocí Aspose.Tasks. Zvyšte své schopnosti správy projektů pomocí tohoto krok‑za‑krokem tutoriálu.
### [Čtení pracovních týdnů z kalendáře MS Project pomocí Aspose.Tasks](./read-work-weeks/)
Naučte se číst pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks pro Java. Získejte krok‑za‑krokem instrukce v tomto komplexním tutoriálu.
### [Aktualizace kalendářů MS Project do formátu MPP pomocí Aspose.Tasks](./update-to-mpp/)
Naučte se snadno aktualizovat kalendáře MS Project do formátu MPP pomocí Aspose.Tasks pro Java.

## Často kladené otázky

**Q: Mohu definovat různé pracovní hodiny pro každý pracovní den?**  
A: Ano. Aspose.Tasks vám umožňuje nastavit časy začátku a konce individuálně pro pondělí až neděli.

**Q: Jak zacházím se svátky nebo nepracovními dny?**  
A: Po definování pracovních dnů můžete přidat výjimky (data) k označení svátků nebo vlastních nepracovních období.

**Q: Je možné zkopírovat definici pracovního dne z jednoho kalendáře do druhého?**  
A: Rozhodně. Můžete získat objekt `WeekDay` z existujícího kalendáře a přidat jej do jiné instance kalendáře.

**Q: Musím po aktualizaci pracovních dnů znovu načíst projekt?**  
A: Ne. Změny jsou aplikovány přímo na objekt `Project` v paměti; stačí projekt uložit, až budete hotovi.

**Q: Která verze Aspose.Tasks je vyžadována pro manipulaci s pracovními dny?**  
A: Všechny nedávné verze (20.10 a novější) podporují kompletní API pro pracovní dny. Doporučujeme používat nejnovější stabilní vydání pro nejlepší výkon.

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Určení pracovních dnů a pracovních hodin pomocí Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Vytvořit vlastní výjimky kalendáře pomocí Aspose.Tasks pro Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}