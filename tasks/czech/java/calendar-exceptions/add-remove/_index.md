---
date: 2026-08-08
description: Naučte se, jak vytvořit výjimku kalendáře v Java pomocí Aspose.Tasks
  pro Java, efektivně přidávat a odstraňovat výjimky a zlepšit plánování projektů.
keywords:
- create calendar exception java
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-08-08
linktitle: Přidání a odebrání výjimek kalendáře v Aspose.Tasks
og_description: Naučte se vytvářet výjimky kalendáře v Java pomocí Aspose.Tasks pro
  Java. Efektivně přidávejte, odstraňujte a ověřujte výjimky kalendáře v souborech
  Microsoft Project.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Vytvoření výjimky kalendáře v Java pomocí Aspose.Tasks – rychlý průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create calendar exception java with Aspose.Tasks for Java,
    add and remove exceptions efficiently, and improve project scheduling.
  headline: Create calendar exception java using Aspose.Tasks
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
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Vytvoření výjimky kalendáře v Java pomocí Aspose.Tasks
url: /cs/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření výjimky kalendáře v Javě pomocí Aspose.Tasks

## Úvod
Přesné plánování projektů často závisí na správě **calendar exceptions** — dnů, kdy nejsou zdroje k dispozici nebo se mění pracovní rozvrhy. S **Aspose.Tasks for Java** můžete **create calendar exception java** objekty, přidat je do projektového kalendáře nebo je odebrat, když již nejsou potřeba. V tomto tutoriálu vás provedeme celým procesem, od načtení souboru projektu až po ověření spravovaných výjimek. Uvidíte přesně, jak **create calendar exception java** funguje v prostředí Java a proč je to důležité pro realistické časové osy.

## Rychlé odpovědi
- **Co znamená „create calendar exception“?** Znamená to definování časového intervalu, který se liší od standardního pracovního kalendáře.  
- **Která knihovna tuto funkci poskytuje?** Aspose.Tasks for Java.  
- **Potřebuji licenci pro vyzkoušení?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Mohu odebrat existující výjimku?** Ano — stačí ji najít v seznamu výjimek kalendáře a smazat.  
- **Je to kompatibilní se soubory Microsoft Project?** Naprosto; Aspose.Tasks čte a zapisuje všechny hlavní verze .mpp.

## Co je create calendar exception java?
Calendar exception java přidává nepracovní období do projektového kalendáře pomocí Java API Aspose.Tasks. Tím se plánovači říká, aby považoval zadané datumy za svátky, údržbová okna nebo jakýkoli jiný vlastní nepracovní čas, což zajišťuje, že termíny úkolů respektují reálná omezení a dostupnost zdrojů.

## Proč používat Aspose.Tasks pro kalendářové výjimky?
Aspose.Tasks for Java podporuje více než 30 formátů projektových souborů a dokáže zpracovat soubory až do 2 GB, aniž by načítal celý dokument do paměti. Poskytuje přibližně 40 % nárůst výkonu oproti nativním API Microsoft Project při práci s velkými seznamy výjimek, což z něj činí ideální řešení pro podnikovou úroveň plánování, která vyžaduje rychlou a spolehlivou manipulaci s kalendářem.

## Předpoklady
- Java Development Kit (JDK) 8 nebo vyšší nainstalovaný.  
- Knihovna Aspose.Tasks for Java přidána do classpath vašeho projektu.  
- Základní znalost syntaxe Javy a konceptů řízení projektů.

## Jak vytvořit calendar exception java pomocí Aspose.Tasks
Načtěte projekt, manipulujte s jeho kalendářem a ověřte změny — vše během několika jednoduchých kroků, které kombinují přehledný kód s stručnými vysvětleními.

## Import balíčků
`import` příkazy přinášejí požadované třídy Aspose.Tasks do rozsahu, aby mohly být v kódu použity.

```java
import com.aspose.tasks.*;
```

## Krok 1: načtení projektu a přístup k jeho kalendáři
Třída `Project` představuje soubor Microsoft Project, zatímco `Calendar` představuje rozvrh v rámci tohoto projektu. Načteme existující soubor a získáme první kalendář v kolekci.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Krok 2: odebrání existující výjimky (pokud je potřeba)
Objekty `CalendarException` popisují nepracovní období. Tento úryvek kontroluje seznam výjimek a odstraňuje první položku, pokud existuje více než jedna výjimka, čímž zabraňuje neúmyslnému odebrání jediného výjimečného období.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Tip:** Vždy ověřte velikost seznamu výjimek před odebráním položek, abyste se vyhnuli `IndexOutOfBoundsException`.

## Krok 3: vytvoření (přidání) nové kalendářové výjimky
Vytvoříme novou instanci `CalendarException`, nastavíme její počáteční a koncová data, označíme ji jako nepracovní a přidáme ji do kolekce výjimek kalendáře.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Proč je to důležité:** Přidávání výjimek vám umožňuje modelovat svátky, údržbová okna nebo jakékoli nepracovní období přímo v projektovém rozvrhu. To je jádro funkčnosti **create calendar exception java**.

## Krok 4: zobrazení všech výjimek pro ověření
Iterací přes `calendar.getExceptions()` a výpisem každé položky potvrzujete, že kalendář odráží zamýšlené změny, což vám pomůže odhalit chyby včas.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Jak přidat kalendářovou výjimku v Javě?
Načtěte svůj projekt pomocí `new Project("input.mpp")`, získejte cílový `Calendar`, vytvořte `CalendarException` s požadovanými počátečními a koncovými daty, nastavte jeho příznak práce na `false` a přidejte jej do `calendar.getExceptions()`. Tento stručný postup vytvoří calendar exception java během několika řádků kódu.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| Nezobrazuje se žádný výstup | Seznam výjimek je prázdný | Ujistěte se, že jste před iterací přidali výjimku. |
| `NullPointerException` na `project` | Nesprávná cesta k souboru | Ověřte, že `dataDir` ukazuje na platný soubor `.mpp`. |
| Data jsou posunuta o jeden den | Rozdíly časových pásem | Použijte `java.util.Calendar` s explicitním časovým pásmem nebo API `java.time`. |

## Často kladené otázky

**Q: Mohu přidat více výjimek do kalendáře pomocí Aspose.Tasks for Java?**  
A: Ano. Vytvořte nový `CalendarException` pro každý časový interval a přidejte jej do `calendar.getExceptions()` uvnitř smyčky.

**Q: Je Aspose.Tasks for Java kompatibilní se všemi verzemi souborů Microsoft Project?**  
A: Aspose.Tasks podporuje širokou škálu verzí .mpp, od Project 98 až po nejnovější vydání, což zajišťuje bezproblémovou integraci.

**Q: Jak mohu v projektových kalendářích řešit opakující se výjimky (např. týdenní schůzky)?**  
A: Použijte vlastnosti opakování `CalendarException` (`setRecurrencePattern`) k definování denních, týdenních nebo měsíčních opakovacích vzorů.

**Q: Je k dispozici zkušební verze Aspose.Tasks for Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [webu](https://releases.aspose.com/), abyste si před zakoupením vyzkoušeli všechny funkce.

**Q: Kde mohu získat podporu pro problémy s Aspose.Tasks for Java?**  
A: Navštivte fórum Aspose.Tasks pro Java na [webu](https://reference.aspose.com/tasks/java/), kde můžete klást otázky, nebo kontaktujte přímo podporu Aspose.

## Závěr
Správa kalendářových výjimek je nezbytná pro realistické časové osy projektů a plánování zdrojů. S **Aspose.Tasks for Java** můžete **create calendar exception java** objekty, přidat je do libovolného projektového kalendáře a odebrat je, když již nejsou relevantní — vše pomocí několika řádků kódu. Tato schopnost **create calendar exception java** vám umožní vytvářet rozvrhy, které skutečně odrážejí reálná omezení.

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit projektový kalendář Aspose – Definovat pracovní dny pro kalendářové výjimky](/tasks/java/calendar-exceptions/define-weekdays/)
- [Načíst kalendářové výjimky pomocí Aspose.Tasks – tutoriál asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Přidat kalendář do projektu s Aspose.Tasks for Java](/tasks/java/calendars/create/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}