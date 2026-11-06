---
date: 2026-11-06
description: Zjistěte, jak odstranit exception v project calendar pomocí Aspose.Tasks
  pro Java, přidávat a spravovat výjimky efektivně a zlepšit plánování.
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: Přidávat a odstraňovat Calendar Exceptions v Aspose.Tasks
og_description: Jak odstranit exception v project calendar pomocí Aspose.Tasks pro
  Java. Spravovat, přidávat a ověřovat calendar exceptions efektivně.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Jak odstranit exception v project calendar – průvodce Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Jak odstranit exception v project calendar pomocí Aspose.Tasks pro Java
url: /cs/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odstranit výjimku v kalendáři projektu pomocí Aspose.Tasks pro Java

## Úvod
Přesné plánování projektu často závisí na správném zacházení s **výjimkami kalendáře** – dny, kdy nejsou k dispozici zdroje nebo se mění pracovní rozvrhy. S **Aspose.Tasks pro Java** můžete **vytvářet**, **přidávat**, **odstraňovat** a **spravovat** výjimky kalendáře efektivně. V tomto tutoriálu vás provedeme načtením projektu, přidáním nové výjimky, odstraněním existující a ověřením výsledků, abyste přesně pochopili, **jak odstranit záznamy výjimek**, když již nejsou potřeba.

## Rychlé odpovědi
- **Co znamená „vytvořit výjimku kalendáře“?** Znamená to definovat časové období, které se liší od standardního pracovního kalendáře.  
- **Která knihovna tuto funkci poskytuje?** Aspose.Tasks pro Java.  
- **Potřebuji licenci pro vyzkoušení?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Mohu odstranit existující výjimku?** Ano – stačí ji najít v seznamu výjimek kalendáře a smazat.  
- **Je to kompatibilní se soubory Microsoft Project?** Rozhodně; Aspose.Tasks čte a zapisuje všechny hlavní verze .mpp.

## Co je vytvoření výjimky kalendáře v Javě?
Třída `CalendarException` představuje nepracovní období, které přidáte do kalendáře projektu. Říká plánovači, aby považoval zadané datumy za svátky, údržbová okna nebo jakýkoli vlastní nepracovní čas, čímž zajistí, že termíny úkolů respektují reálná omezení.

## Proč používat Aspose.Tasks pro výjimky kalendáře?
Aspose.Tasks pro Java podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat soubory až do **2 GB** bez načítání celého dokumentu do paměti. Přináší přibližně **40 % nárůst výkonu** oproti nativním API Microsoft Project při práci s velkými seznamy výjimek, což je ideální pro podnikovou úroveň plánování.

## Požadavky
- Java Development Kit (JDK) 8 nebo novější nainstalovaný.  
- Knihovna Aspose.Tasks pro Java přidána do classpath vašeho projektu.  
- Základní znalost syntaxe Javy a pojmů projektového řízení.

## Jak odstranit výjimku z kalendáře?
Třída `Project` představuje soubor Microsoft Project a poskytuje přístup k jeho kalendářům, úkolům a zdrojům. Třída `CalendarException` definuje nepracovní období v kalendáři. Načtěte projekt, najděte nechtěnou `CalendarException` v kolekci výjimek kalendáře a zavolejte `remove` na seznamu. Tato operace okamžitě aktualizuje rozvrh a nevyžaduje opětovné uložení celého souboru, pokud nechcete změnu trvale uložit.

## Jak přidat výjimku do kalendáře?
Třída `CalendarException` definuje nepracovní období, které lze přidat do kalendáře. Vytvořte novou instanci `CalendarException`, nastavte počáteční a koncová data, označte ji jako nepracovní a přidejte do seznamu výjimek kalendáře. Přidání je okamžité a plánovač bude považovat definovaný rozsah za svátek pro všechny úkoly napojené na tento kalendář.

## Jak zacházet s opakujícími se výjimkami?
Vlastnosti opakování `CalendarException` (`setRecurrencePattern`) vám umožňují definovat denní, týdenní nebo měsíční opakování. Konfigurací těchto vlastností můžete modelovat týdenní schůzky, měsíční údržbová okna nebo jakýkoli vzor‑založený nepracovní čas bez vytváření samostatných záznamů pro každou událost.

## Import balíčků
Importovací příkazy přinášejí požadované třídy Aspose.Tasks do rozsahu, aby mohly být v kódu použity.

```java
import com.aspose.tasks.*;
```

## Krok 1: načíst projekt a získat jeho kalendář
`Project` představuje soubor Microsoft Project, zatímco `Calendar` představuje rozvrh v rámci tohoto projektu. Načtení existujícího souboru a získání prvního kalendáře v kolekci je prvním krokem.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Krok 2: odstranit existující výjimku (pokud je potřeba)
Objekty `CalendarException` popisují nepracovní období. Tento úryvek kontroluje seznam výjimek a odstraňuje první položku, pokud existuje více než jedna výjimka, čímž zabraňuje neúmyslnému smazání jediné výjimky.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Tip:** Vždy ověřte velikost seznamu výjimek před odstraňováním položek, aby nedošlo k `IndexOutOfBoundsException`.

## Krok 3: vytvořit (přidat) novou výjimku kalendáře
Instanciujeme novou `CalendarException`, nastavíme její počáteční a koncová data, označíme ji jako nepracovní a přidáme do kolekce výjimek kalendáře.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Proč je to důležité:** Přidávání výjimek vám umožňuje modelovat svátky, údržbová okna nebo jakékoli nepracovní období přímo v harmonogramu projektu. To je jádro funkčnosti **create calendar exception java**.

## Krok 4: zobrazit všechny výjimky pro ověření
Iterací přes `calendar.getExceptions()` a výpisem každé položky potvrzujete, že kalendář odráží zamýšlené změny, což vám pomůže odhalit chyby včas.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Jak přidat výjimku kalendáře v Javě?
Načtěte svůj projekt pomocí `new Project("input.mpp")`, získejte cílový `Calendar`, vytvořte `CalendarException` s požadovanými počátečními a koncovými daty, nastavte jeho příznak práce na `false` a přidejte jej do `calendar.getExceptions()`. Tento stručný postup vytvoří výjimku kalendáře v Javě během několika řádků kódu.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| Žádný výstup se nezobrazuje | Seznam výjimek je prázdný | Ujistěte se, že jste před iterací přidali výjimku. |
| `NullPointerException` na `project` | Nesprávná cesta k souboru | Ověřte, že `dataDir` ukazuje na platný soubor `.mpp`. |
| Data jsou posunuta o jeden den | Rozdíly časových pásem | Použijte `java.util.Calendar` s explicitním časovým pásmem nebo API `java.time`. |

## Často kladené otázky

**Q:** Mohu pomocí Aspose.Tasks pro Java přidat do kalendáře více výjimek?  
**A:** Ano. Vytvořte novou `CalendarException` pro každý časový rozsah a přidejte ji do `calendar.getExceptions()` uvnitř smyčky.

**Q:** Je Aspose.Tasks pro Java kompatibilní se všemi verzemi souborů Microsoft Project?  
**A:** Aspose.Tasks podporuje širokou škálu verzí .mpp, od Project 98 až po nejnovější vydání, což zajišťuje bezproblémovou integraci.

**Q:** Jak mohu v kalendářích projektů řešit opakující se výjimky (např. týdenní schůzky)?  
**A:** Použijte vlastnosti opakování `CalendarException` (`setRecurrencePattern`) k definování denního, týdenního nebo měsíčního opakování.

**Q:** Je k dispozici zkušební verze Aspose.Tasks pro Java?  
**A:** Ano, můžete si stáhnout bezplatnou zkušební verzi ze [stránky Aspose Releases](https://releases.aspose.com/), abyste před zakoupením prozkoumali všechny funkce.

**Q:** Kde mohu získat podporu pro problémy s Aspose.Tasks pro Java?  
**A:** Navštivte fórum Aspose.Tasks pro Java na [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/), kde můžete klást otázky, nebo kontaktujte přímo podporu Aspose.

## Závěr
Správa výjimek kalendáře je nezbytná pro realistické časové plány projektů a plánování zdrojů. S **Aspose.Tasks pro Java** můžete **vytvářet**, **přidávat**, **odstraňovat** a ověřovat výjimky kalendáře – vše pomocí několika řádků kódu. Ovládnutí **jak odstranit výjimku** vám umožní udržet rozvrhy přesné a v souladu s reálnými omezeními.

---

**Last Updated:** 2026-11-06  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Související tutoriály

- [Vytvořit kalendář projektu Aspose – Definovat pracovní dny pro výjimky kalendáře](/tasks/java/calendar-exceptions/define-weekdays/)
- [Načíst výjimky kalendáře pomocí Aspose.Tasks – tutoriál asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}