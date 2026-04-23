---
date: 2026-01-23
description: Naučte se, jak nastavit dobu trvání základní linie a vytvořit instanci
  projektu pomocí Aspose.Tasks pro Javu. Tento krok‑za‑krokem průvodce vám pomůže
  efektivně spravovat základní linie úkolů.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Jak nastavit trvání základní linie v Aspose.Tasks pro Javu
url: /cs/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit základní dobu trvání v Aspose.Tasks pro Java

## Úvod
Nastavení základní linie je základním krokem pro sledování postupu projektu oproti původnímu plánu. V tomto tutoriálu se naučíte **jak nastavit základní** dobu trvání úkolů v Microsoft Project pomocí knihovny Aspose.Tasks pro Java a uvidíte, proč vytvoření základní linie včas může ušetřit čas a starosti později.

## Rychlé odpovědi
- **Co znamená „nastavit základní linii“?** Zaznamená původní datum zahájení, dokončení a dobu trvání úkolu, abyste mohli porovnávat budoucí změny.  
- **Která třída Aspose.Tasks vytváří projekt?** Třída `Project` – také se naučíte, jak **vytvořit instanci projektu** správně.  
- **Potřebuji licenci pro spuštění kódu?** Pro testování stačí bezplatná evaluační licence; pro produkci je vyžadována komerční licence.  
- **Mohu získat mezilehlé základní linie?** Ano, Aspose.Tasks umožňuje dotazovat se na mezilehlé základní linie a jejich fixní náklady.  
- **Jaká verze Javy je požadována?** Doporučuje se Java 8 nebo novější.

## Co je základní linie úkolu a proč ji nastavit?
Základní linie úkolu zachycuje plánovaný rozvrh (datum zahájení, datum dokončení a dobu trvání) v konkrétním okamžiku. Nastavením základní linie vytvoříte referenční bod, který usnadňuje odhalování odchylek v rozvrhu, překročení nákladů a přetížení zdrojů, jak se projekt vyvíjí.

## Proč použít Aspose.Tasks pro správu základních linií?
- **Plná kompatibilita s .mpp** – čtení a zápis nativních souborů Microsoft Project bez nutnosti instalace Office.  
- **Bohaté API** – programový přístup k datům základních linií, mezilehlým základním liniím a časově fázovaným informacím.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS s libovolným standardním JDK.

## Předpoklady
1. **Vývojové prostředí Java** – nainstalovaný a nakonfigurovaný JDK 8+.  
2. **Aspose.Tasks pro Java** – stáhněte knihovnu z [zde](https://releases.aspose.com/tasks/java/).  
3. **IDE nebo nástroj pro sestavení** – Maven, Gradle nebo libovolné IDE dle vašeho výběru.

## Import balíčků
Nejprve importujte potřebné třídy do svého Java projektu:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Krok 1: Vytvoření instance projektu
Vytvoření instance projektu je základem pro jakoukoli další manipulaci. Tento krok ukazuje, jak **vytvořit instanci projektu** pomocí Aspose.Tasks:

```java
Project project = new Project();
```

## Krok 2: Vytvoření základní linie úkolu
Přidejte nový úkol do kořene projektu a nastavte jeho základní linii. Tím se zaznamená původní rozvrh úkolu:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Krok 3: Zobrazení informací o základní linii úkolu
Získejte základní linii, kterou jste právě vytvořili, a vytiskněte její klíčové vlastnosti. To vám pomůže ověřit, že základní linie byla nastavena správně:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Krok 4: Kontrola mezilehlé základní linie a fixního nákladu
Pokud pracujete s mezilehlými základními liniemi, můžete dotazovat, zda je aktuální základní linie mezilehlá a jaký má související fixní náklad:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Krok 5: Výpis časově fázovaných dat
Časově fázovaná data ukazují, jak je základní linie rozložena v čase. Projděte kolekci a prozkoumejte jednotlivé položky:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Dodržením těchto kroků můžete **nastavit dobu trvání základní linie** pro libovolný úkol a získat podrobné informace o základní linii pomocí Aspose.Tasks pro Java.

## Časté problémy a řešení
- **Základní linie se nezobrazuje v MS Project:** Ujistěte se, že jste volali `project.setBaseline(BaselineType.Baseline)` **po** přidání úkolu.  
- **NullPointerException při `getBaselines()`:** Ověřte, že byl úkol přidán do projektu před nastavením základní linie.  
- **Neshoda časových jednotek:** Použijte `TimeUnitType` pro správné formátování doby trvání, zejména při práci s vlastními kalendáři.

## Často kladené otázky
### Co je základní linie úkolu v MS Project?
Základní linie úkolu v MS Project je snímek počátečního plánovaného rozvrhu úkolu, zahrnující datum zahájení, datum dokončení a dobu trvání.

### Proč je důležité spravovat základní linie úkolů?
Správa základních linií úkolů pomáhá porovnávat plánovaný rozvrh se skutečným postupem projektu, což usnadňuje lepší sledování a rozhodování.

### Mohu po nastavení upravit základní linii úkolu?
Ano,Ano, Aspose.Tasks nabízí širokoudeu pro Aspose.Tasks najdete na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a komunikovat s ostatními uživateli.

## Další často kladené otázky
**Q: Musím volat `setBaseline` pro každý úkol zvlášť?**  
A: Ne. Volání `project.setBaseline(BaselineType.Baseline)` zaznamená základní linii pro všechny úkoly v projektu najednou.

**Q: Jak mohu nastavit mezilehlou základní linii pro konkrétní úkol?**  
A: Použijte `project.setBaseline(BaselineType.Baseline1)` (nebo Baseline2‑Baseline10) po aktualizaci rozvrhu úkolu.

**Q: Je možné exportovat data základní linie do CSV?**  
A: Ano. Projděte `task.getBaselines()` a zapište požadovaná pole do CSV souboru pomocí standardního Java I/O.

**Q: Můžu načíst existující .mpp soubor, který již obsahuje základní linie?**  
A: Rozhodně. Načtěte soubor pomocí `new Project("myproject.mpp")` a poté přistupujte k základním liniím jednotlivých úkolů, jak je ukázáno výše.

**Q: Zvládá Aspose.Tasks soubory s více projekty?**  
A: Aspose.Tasks pracuje s jednoprojkovými .mpp soubory. Pro scénáře s více projekty je třeba projekty kombinovat programově.

---

**Poslední aktualizace:** 2026-01-23  
**Testováno s:** Aspose.Tasks pro Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}