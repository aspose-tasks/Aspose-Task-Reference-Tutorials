---
date: 2026-03-03
description: Naučte se, jak v Aspose.Tasks pro Javu převyčíslit WBS, spravovat rozdělení
  práce a efektivně přizpůsobit kódy WBS s příklady krok za krokem.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak přenumerovat WBS v Aspose.Tasks pro Javu
url: /cs/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přečíslovat WBS v Aspose.Tasks pro Java

## Úvod
Pokud potřebujete **jak přečíslovat WBS** v souboru Microsoft Project pomocí Aspose.Tasks pro Java, jste na správném místě. Tento tutoriál vás provede čtením existujících kódů WBS, jejich přizpůsobením a následným přečíslováním hierarchie, aby váš projekt zůstal uspořádaný. Ať už čistíte starý plán nebo vytváříte nový od nuly, zvládnutí těchto kroků vám pomůže **spravovat struktury rozdělení práce** s jistotou.

## Rychlé odpovědi
- **Co dělá přečíslování WBS?** Přepočítá hierarchické číslování úkolů tak, aby odráželo jakékoli strukturální změny.  
- **Která třída provádí přečíslování?** `Project.renumberWBSCode`.  
- **Potřebuji licenci pro spuštění kódu?** Pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu přizpůsobit formát WBS?** Ano — použijte `Task.set(Tsk.WBS, "...")` k přiřazení libovolného řetězce.  
- **Jaké jsou hlavní předpoklady?** Java JDK, knihovna Aspose.Tasks pro Java a platný soubor projektu (.mpp).

## Co je Work Breakdown Structure (WBS)?
Work Breakdown Structure (WBS) je hierarchické znázornění výstupů a úkolů projektu. Každý úkol získá kód (např. 1.2.3), který odráží jeho pozici v hierarchii. Přečíslování se stává nezbytným, když jsou úkoly přidány, odebrány nebo přeuspořádány, aby kódy zůstaly logické a snadno čitelné.

## Proč spravovat rozdělení práce a přizpůsobovat kódy WBS?
- **Přehlednost:** Jasné kódy WBS usnadňují zúčastněným stranám nalezení úkolů.  
- **Reportování:** Mnoho nástrojů pro reportování se spoléhá na konzistentní číslování.  
- **Flexibilita:** Vlastní kódy vám umožní sladit strukturu projektu s interními standardy.  

## Předpoklady
Než se ponoříme do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovna Aspose.Tasks pro Java přidaná do vašeho projektu. Můžete ji získat [zde](https://releases.aspose.com/tasks/java/).  

## Importovat balíčky
Ujistěte se, že importujete potřebné balíčky pro zahájení vašeho projektu:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Číst kódy WBS
Nejprve načteme existující kódy WBS, abyste viděli, s čím pracujete.

### Krok 1: Načíst projekt
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Krok 2: Shromáždit úkoly
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Krok 3: Analyzovat a přizpůsobit
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Ukázkový kód výše vypíše aktuální WBS a úroveň každého úkolu a poté demonstruje **přizpůsobení kódů WBS** přiřazením nového řetězce.

## Přečíslovat WBS kódy úkolů
Nyní skutečně přečíslujeme hierarchii WBS.

### Krok 1: Načíst projekt (příklad přečíslování)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Krok 2: Vybrat všechny úkoly
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Krok 3: Vypsat počáteční kódy WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Krok 4: Přečíslovat kódy WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Krok 5: Vypsat aktualizované kódy WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Dodržením těchto kroků efektivně **přečíslujete WBS** pro libovolnou sadu úkolů ve vašem souboru projektu.

## Časté problémy a řešení
- **WBS se po volání `set` nezmění:** Ujistěte se, že pracujete se správnou instancí úkolu a že je projekt po úpravách uložen.  
- **`renumberWBSCode` vyvolá výjimku:** Ověřte, že seznam ID odpovídá počtu úkolů nejvyšší úrovně; jinak metoda nemůže správně přiřadit nová čísla.  
- **Chybějící hodnoty WBS:** Některé úkoly mohou mít `null` WBS, pokud byly importovány ze souboru, který žádný nedefinoval. Použijte náhradní hodnotu před výpisem.

## Často kladené otázky

**Q: Kde mohu najít dokumentaci pro Aspose.Tasks pro Java?**  
A: Dokumentace je k dispozici [zde](https://reference.aspose.com/tasks/java/).

**Q: Jak mohu stáhnout Aspose.Tasks pro Java?**  
A: Můžete jej stáhnout [zde](https://releases.aspose.com/tasks/java/).

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.Tasks pro Java?**  
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro podporu.

**Q: Mohu získat dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Ano, získáte dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

**Q: Mohu po přečíslování přejmenovat formát WBS?**  
A: Rozhodně. Po volání `renumberWBSCode` můžete iterovat přes úkoly a použít `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` podle vašich pojmenovacích konvencí.

**Q: Ovlivňuje přečíslování závislosti úkolů?**  
A: Ne. Metoda aktualizuje pouze řetězec WBS; odkazy a omezení úkolů zůstávají beze změny.

---

**Poslední aktualizace:** 2026-03-03  
**Testováno s:** Aspose.Tasks for Java 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}