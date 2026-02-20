---
date: 2026-02-20
description: Prozkoumejte, jak přidat úkol do projektu a spravovat trvání pomocí Aspose.Tasks
  pro Javu. Naučte se, jak nastavit trvání a jak jej snadno převádět.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Přidat úkol do projektu a spravovat trvání pomocí Aspose.Tasks
url: /cs/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání úkolu do projektu a správa trvání pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **jak přidat úkol do projektu** a řídit jeho trvání pomocí Aspose.Tasks pro Java. Ať už vytváříte nový nástroj pro plánování projektů nebo rozšiřujete existující řešení, zvládnutí práce s trváním úkolů je nezbytné pro přesné plánování a reportování.

## Rychlé odpovědi
- **Co znamená „přidat úkol do projektu“?** Vytvoří nový objekt úkolu pod kořenem projektu nebo pod konkrétním souhrnným úkolem.  
- **Která třída představuje trvání?** `com.aspose.tasks.Duration`.  
- **Jak nastavit trvání?** Použijte `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Mohu převést trvání na jinou jednotku?** Ano, zavolejte `duration.convert(TimeUnitType.Hour)` nebo jiný `TimeUnitType`.  
- **Potřebuji licenci pro produkční nasazení?** Pro komerční použití je vyžadována platná licence Aspose.Tasks.

## Co je „přidat úkol do projektu“?
Přidání úkolu do projektu znamená vytvořit objekt `Task` a připojit jej do hierarchie úkolů projektu. Tato operace je prvním krokem, než budete moci definovat práci, zdroje nebo trvání pro daný úkol.

## Proč spravovat trvání úkolů?
Přesná trvání zajišťují realistické časové osy, alokaci zdrojů a analýzu kritické cesty. S Aspose.Tasks můžete programově nastavit, číst, převádět a upravovat trvání, což vám dává plnou kontrolu nad plánem projektu.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovanou Javu. Můžete ji stáhnout [zde](https://www.oracle.com/java/technologies/javase-downloads.html).
- Knihovna Aspose.Tasks: Stáhněte a zahrňte knihovnu Aspose.Tasks do svého projektu. Knihovnu najdete [zde](https://releases.aspose.com/tasks/java/).

## Import balíčků
Ve svém Java projektu importujte potřebné balíčky pro práci s Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Krok 1: Nastavení projektu
```java
// Create a new project
Project project = new Project();
```

## Krok 2: Přidání nového úkolu (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Jak nastavit trvání
Nyní, když úkol existuje, můžete definovat jeho délku. Ve výchozím nastavení jsou trvání vyjádřena ve dnech.

## Krok 3: Získání a převod trvání úkolu
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Jak převést trvání
Metoda `convert` vám umožní převést `Duration` z jednoho `TimeUnitType` na jiný (např. dny → hodiny, týdny → dny).

## Krok 4: Aktualizace trvání úkolu na 1 týden
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Krok 5: Zkrácení trvání úkolu
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Po provedení těchto kroků jste úspěšně **přidali úkol do projektu** a spravovali jeho trvání pomocí Aspose.Tasks pro Java.

## Časté chyby a tipy
- **Chyba:** Zapomenutí převést trvání před prováděním aritmetiky může vést k nesprávným výsledkům. Vždy ověřte jednotku pomocí `duration.getTimeUnit()`.
- **Tip:** Použijte `project.getDuration(value, TimeUnitType)` k vytvoření trvání v požadované jednotce místo pozdějšího převodu.
- **Chyba:** Nastavení záporného trvání vyvolá výjimku. Ověřte vstupní hodnoty.

## Závěr
V tomto průvodci jsme si ukázali, jak **přidat úkol do projektu**, přečíst jeho výchozí trvání, **nastavit trvání** a **převést trvání** na různé časové jednotky. Nyní můžete tyto techniky začlenit do větších plánovacích aplikací pro přesné plánování projektů.

## Často kladené otázky
### Je Aspose.Tasks kompatibilní se všemi verzemi Javy?
Aspose.Tasks je kompatibilní s Javou 6 a novějšími verzemi.

### Mohu používat Aspose.Tasks pro komerční projekty?
Ano, můžete Aspose.Tasks používat jak pro osobní, tak pro komerční projekty. Podrobnosti o licencování najdete [zde](https://purchase.aspose.com/buy).

### Kde najdu další podporu a zdroje?
Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro komunitní podporu a diskuze.

### Jak získat dočasnou licenci pro testovací účely?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/) pro testování a hodnocení.

### Je k dispozici bezplatná zkušební verze Aspose.Tasks?
Ano, bezplatnou zkušební verzi můžete získat [zde](https://releases.aspose.com/) a vyzkoušet si Aspose.Tasks před zakoupením.

## Často kladené otázky

**Q: Jak změním trvání úkolu po jeho nastavení?**  
A: Získejte aktuální trvání pomocí `task.get(Tsk.DURATION)`, upravte jej (např. `add`, `subtract` nebo `convert`) a poté ho nastavte zpět pomocí `task.set(Tsk.DURATION, newDuration)`.

**Q: Mohu nastavit trvání v minutách?**  
A: Ano, použijte `TimeUnitType.Minute` při volání `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Aktualizuje změna trvání automaticky datumy zahájení a dokončení úkolu?**  
A: Pouze pokud je režim plánování projektu nastaven na automatický. V opačném případě může být nutné znovu vypočítat plán pomocí `project.calculateCriticalPath()`.

**Q: Je možné získat trvání jako surové číslo?**  
A: Zavolejte `duration.getTimeSpan()` a získáte číselnou hodnotu v aktuální časové jednotce.

**Q: Co se stane, když odečtu více než aktuální trvání?**  
A: API vyvolá `ArgumentOutOfRangeException`. Vždy ověřte, že výsledné trvání zůstane kladné.

---

**Poslední aktualizace:** 2026-02-20  
**Testováno s:** Aspose.Tasks pro Java (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}