---
date: 2026-01-28
description: Naučte se, jak vytvořit výjimku kalendáře pomocí Aspose.Tasks pro Javu,
  efektivně přidávat a odstraňovat výjimky kalendáře a zlepšit plánování projektu.
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Vytvořit výjimku kalendáře Aspose pro Javu
url: /cs/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření výjimky kalendáře Aspose pro Java

## Úvod
Přesné plánování projektů často závisí na správném zacházení s **calendar exceptions** — dny, kdy nejsou zdroje k dispozici nebo se mění pracovní rozvrhy. S **Aspose.Tasks for Java** můžete **create calendar exception** objekty, přidávat je do kalendáře projektu nebo je odstraňovat, když již nejsou potřeba. V tomto tutoriálu projdeme celý proces, od načtení souboru projektu až po ověření výjimek, které jste spravovali. Tento průvodce vám ukáže přesně, jak **create calendar exception aspose** v prostředí Java.

### Rychlé odpovědi
- **Co znamená „create calendar exception“?** Znamená to definování časového intervalu, který se liší od standardního pracovního kalendáře.  
- **Která knihovna tuto funkci poskytuje?** Aspose.Tasks pro Java.  
- **Potřebuji licenci k vyzkoušení?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Mohu odstranit existující výjimku?** Ano — stačí ji najít v seznamu výjimek kalendáře a smazat.  
- **Je to kompatibilní se soubory Microsoft Project?** Naprosto; Aspose.Tasks čte a zapisuje všechny hlavní verze .mpp.

#### Požadavky
Než začnete, ujistěte se, že máte:

- Nainstalovaný Java Development Kit (JDK).  
- Knihovna Aspose.Tasks pro Java přidaná do classpath vašeho projektu.  
- Základní znalost Javy a terminologie projektového řízení.

## Jak vytvořit výjimku kalendáře Aspose pomocí Javy
Níže je podrobný průvodce krok za krokem, který před spuštěním vysvětluje účel každého úryvku kódu. Postupujte podle těchto sekcí v pořadí, abyste zajistili správné zpracování výjimek kalendáře.

## Import balíčků
Nejprve importujte základní třídy Aspose.Tasks, které umožňují manipulaci s kalendářem.

```java
import com.aspose.tasks.*;
```

## Krok 1: Načtení projektu a přístup k jeho kalendáři
Začínáme načtením existujícího souboru Microsoft Project (`input.mpp`) a získáním prvního kalendáře ve sbírce. Index můžete upravit, pokud potřebujete jiný kalendář.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Krok 2: Odstranění existující výjimky (pokud je potřeba)
Někdy kalendář již obsahuje výjimky, které chcete vymazat. Níže uvedený úryvek kontroluje seznam výjimek a odstraňuje první položku, pokud existuje více než jedna výjimka.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** Vždy ověřte velikost seznamu výjimek před odstraňováním položek, abyste se vyhnuli `IndexOutOfBoundsException`.

## Krok 3: Vytvoření (přidání) nové výjimky kalendáře
Nyní **create calendar exception** objekty. V tomto příkladu definujeme výjimku, která zahrnuje 1. – 3. leden 2009. Přizpůsobte data podle časového plánu vašeho projektu.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Proč je to důležité:** Přidávání výjimek vám umožňuje modelovat svátky, údržbová okna nebo jakékoli nepracovní období přímo v harmonogramu projektu. Toto je jádro funkčnosti **create calendar exception aspose**.

## Krok 4: Zobrazení všech výjimek pro ověření
Po přidání (nebo odebrání) výjimek je dobré je vypsat. Pomůže vám to potvrdit, že kalendář odráží požadované změny.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|---------|----------|--------|
| Žádný výstup se neobjeví | Seznam výjimek je prázdný | Ujistěte se, že jste před iterací přidali výjimku. |
| `NullPointerException` na `project` | Nesprávná cesta k souboru | Ověřte, že `dataDir` ukazuje na platný soubor `.mpp`. |
| Data jsou posunuta o jeden den | Rozdíly časových pásem | Použijte `java.util.Calendar` s explicitním časovým pásmem nebo API `java.time`. |

## Často kladené otázky

**Q: Mohu pomocí Aspose.Tasks for Java přidat do kalendáře více výjimek?**  
A: Ano. Stačí vytvořit nový `CalendarException` pro každý časový interval a přidat jej do `cal.getExceptions()` v rámci smyčky.

**Q: Je Aspose.Tasks for Java kompatibilní se všemi verzemi souborů Microsoft Project?**  
A: Aspose.Tasks podporuje širokou škálu verzí .mpp, od Project 98 až po nejnovější vydání, což zajišťuje bezproblémovou integraci.

**Q: Jak mohu v kalendářích projektu řešit opakující se výjimky (např. týdenní schůzky)?**  
A: Použijte vlastnosti opakování `CalendarException` (`setRecurrencePattern`) k definování složitých vzorů, jako jsou denní, týdenní nebo měsíční opakování.

**Q: Existuje zkušební verze Aspose.Tasks for Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [webu](https://releases.aspose.com/), abyste si před zakoupením vyzkoušeli všechny funkce.

**Q: Kde mohu získat podporu pro případné problémy nebo dotazy týkající se Aspose.Tasks for Java?**  
A: Navštivte fórum Aspose.Tasks pro Java na [webu](https://reference.aspose.com/tasks/java/), kde můžete klást otázky, nebo kontaktujte přímo podporu Aspose.

## Závěr
Správa výjimek kalendáře je nezbytná pro realistické časové plány projektů a plánování zdrojů. S **Aspose.Tasks for Java** můžete **create calendar exception** objekty, přidávat je do libovolného kalendáře projektu a odstraňovat je, když již nejsou relevantní — vše pomocí několika řádků kódu. Tato schopnost **create calendar exception aspose** vám umožní vytvářet harmonogramy, které skutečně odrážejí reálné omezení.

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}