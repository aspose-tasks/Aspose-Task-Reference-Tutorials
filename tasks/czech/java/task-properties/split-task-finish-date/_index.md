---
date: 2026-02-26
description: Naučte se, jak rozdělit termíny dokončení úkolů a spravovat časové osy
  projektů pomocí Aspose.Tasks pro Javu. Tento průvodce ukazuje, jak úkoly rozdělit
  efektivně.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Správa časových os projektů – Datum dokončení rozděleného úkolu v Aspose.Tasks
url: /cs/java/task-properties/split-task-finish-date/
weight: 28
---

 backtop button shortcode.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozdělení data dokončení úkolu v Aspose.Tasks

## Úvod
Efektivní **správa časových os projektů** je základním kamenem úspěšného dodání projektu. Když se změní doba trvání úkolu, jeho datum dokončení musí být přepočítáno, aby byl plán přesný. V tomto tutoriálu vám ukážeme **jak rozdělit datum dokončení úkolu** pomocí Aspose.Tasks pro Java, což vám poskytne přesnou kontrolu nad časovou osou vašeho projektu.

## Rychlé odpovědi
- **Co dosahuje rozdělení data dokončení úkolu?** Umožňuje vám vypočítat koncové datum pro libovolnou dobu trvání, což vám pomáhá upravovat plány za běhu.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (ke stažení z oficiálního webu).  
- **Potřebuji licenci pro vývoj?** Dočasná licence stačí pro testování; pro produkci je vyžadována plná licence.  
- **Mohu to použít s libovolným kalendářem projektu?** Ano, API používá kalendář projektu k respektování pracovních dnů a svátků.  
- **Kolik řádků kódu je potřeba?** Méně než deset řádků pro získání data dokončení pro libovolnou dobu trvání.

## Co znamená „správa časových os projektů“ v kontextu Aspose.Tasks?
Správa časových os projektů znamená udržovat startovní a koncová data všech úkolů synchronizovaná s celkovým plánem, přičemž se zohledňují kalendáře, zdroje a závislosti úkolů. Přesné výpočty data dokončení jsou nezbytné pro realistické projekce a důvěru zainteresovaných stran.

## Proč rozdělit datum dokončení úkolu?
- **Flexibilita:** Rychle zjistit, jak různé přidělení pracovních hodin ovlivňuje dodání.  
- **Posouzení rizik:** Vyhodnotit scénáře „co‑by‑když“ bez změny původního plánu.  
- **Plánování zdrojů:** Přizpůsobit dobu trvání úkolů kapacitě týmu a omezením kalendáře.

## Předpoklady
- Základní znalost programování v Javě.  
- Knihovna Aspose.Tasks pro Java nainstalována. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  
- Nastavené vývojové prostředí Java.

## Import balíčků
Začněte zahrnutím potřebných balíčků do vašeho Java projektu:
```java
import com.aspose.tasks.*;
```

## Krok 1: Najděte úkol k rozdělení
Vyhledejte úkol, který chcete rozdělit, v rámci projektu:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Krok 2: Najděte kalendář projektu
Získejte kalendář projektu pro přesné výpočty dat:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Krok 3: Vypočítejte datum dokončení úkolu s různými dobami trvání
Nyní vypočítejte datum dokončení úkolu pro různé doby trvání.

### Krok 3.1: Doba trvání 8 hodin
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*Opakujte výše uvedený kód pro různé doby trvání, upravte hodiny podle potřeby, abyste viděli, jak každá změna ovlivní datum dokončení.*

## Časté problémy a řešení
- **Nesprávná reference na kalendář:** Ujistěte se, že získáváte kalendář projektu (`project.get(Prj.CALENDAR)`) místo vytváření nového.  
- **Špatné UID úkolu:** UID musí odpovídat úkolu, který skutečně existuje; jinak `getByUid` vrátí `null` a způsobí `NullPointerException`.  
- **Neshoda časových pásem:** API pracuje s časovým pásmem kalendáře; ověřte výchozí pásmo vašeho systému, pokud výsledky vypadají nesprávně.

## Závěr
Osvojení umění **správy časových os projektů** rozdělením dat dokončení úkolů je klíčové pro efektivní řízení projektů. Aspose.Tasks pro Java tento proces zjednodušuje a umožňuje vám bez námahy optimalizovat vaše plány.

## Často kladené otázky
### Q1: Jak si mohu stáhnout Aspose.Tasks pro Java?
A1: Můžete si jej stáhnout [zde](https://releases.aspose.com/tasks/java/).

### Q2: Kde najdu dokumentaci k Aspose.Tasks?
A2: Odkaz na dokumentaci [zde](https://reference.aspose.com/tasks/java/).

### Q3: Jak získat dočasnou licenci pro Aspose.Tasks?
A3: Získejte dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Q4: Kde mohu získat podporu pro Aspose.Tasks?
A4: Navštivte fórum podpory [zde](https://forum.aspose.com/c/tasks/15).

### Q5: Můžu si zakoupit Aspose.Tasks?
A5: Ano, můžete si jej zakoupit [zde](https://purchase.aspose.com/buy).

## Další často kladené otázky

**Q: Mohu tuto techniku použít s vlastním kalendářem?**  
A: Rozhodně. Stačí nahradit `project.get(Prj.CALENDAR)` vaší vlastní instancí `Calendar`.

**Q: Zohledňuje metoda nepracovní dny?**  
A: Ano, definice pracovního času kalendáře jsou použity při výpočtu data dokončení.

**Q: Existuje způsob, jak získat datum dokončení pro zlomkové hodiny (např. 3,5 hodiny)?**  
A: Předávejte `double` hodnotu jako `3.5d` do `getTaskFinishDateFromDuration`; API zvládne zlomkové doby trvání.

**Q: Jak naformátovat výstupní datum?**  
A: Použijte `java.time.format.DateTimeFormatter` na vrácený objekt `Date`, abyste jej zobrazili v požadovaném formátu.

---

**Poslední aktualizace:** 2026-02-26  
**Testováno s:** Aspose.Tasks pro Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}