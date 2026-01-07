---
date: 2026-01-07
description: Naučte se, jak přidat zdroj do projektu a spravovat vlastnosti zpoždění
  vyrovnávání při přiřazování zdrojů pomocí Aspose.Tasks pro Javu.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak přidat zdroj do projektu a pracovat s vlastnostmi zpoždění vyrovnání v
  Aspose.Tasks
url: /cs/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat zdroj do projektu a spravovat vlastnosti zpoždění levelingu v Aspose.Tasks

## Introduction
V tomto tutoriálu se naučíte **jak přidat zdroj do projektu** a zároveň spravovat vlastnosti zpoždění levelingu pro přiřazení zdrojů pomocí Aspose.Tasks pro Java. Ať už budujete plánovací engine nebo automatizujete aktualizace projektů, zvládnutí těchto kroků vám umožní udržet data projektu přesná, aniž byste potřebovali nainstalovaný Microsoft Project.

## Quick Answers
- **Co znamená „add resource to project“?** Vytvoří novou položku zdroje, kterou lze přiřadit úkolům.  
- **Mohu nastavit zpoždění levelingu po přiřazení?** Ano, pomocí polí `Asn.DELAY` nebo `Asn.LEVELING_DELAY`.  
- **Potřebuji licenci pro spuštění tohoto kódu?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována placená licence.  
- **Jaká verze Javy je podporována?** Java 8 nebo novější.  
- **Je to kompatibilní se všemi formáty souborů MS Project?** Aspose.Tasks podporuje .MPP, .XML, .XER a další.

## What is “add resource to project” in Aspose.Tasks?
Přidání zdroje do projektu znamená vytvoření objektu `Resource` uvnitř modelu `Project`. Tento objekt může být později propojen s úkoly pomocí `ResourceAssignment`, což vám umožní sledovat práci, náklady a nastavení levelingu.

## Why handle leveling delay properties?
Zpoždění levelingu pomáhá plánovači rozložit práci, když jsou zdroje přetížené. Nastavením zpoždění řeknete enginu, aby odložil začátek přiřazení, čímž se vyhnete konfliktům a projekt zůstane realistický.

## Prerequisites
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte nainstalovaný Java JDK na svém systému. Můžete jej stáhnout a nainstalovat z [webové stránky](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: Stáhněte knihovnu Aspose.Tasks for Java z [download page](https://releases.aspose.com/tasks/java/).

## Import Packages
Nejprve importujte potřebné balíčky do svého Java projektu, abyste mohli využívat funkce Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Create a Project Object
Vytvořte instanci objektu `Project`, který bude sloužit jako kontejner pro všechny úkoly, zdroje a přiřazení:
```java
Project prj = new Project();
```

## Step 2: Create a Task
Přidejte úkol do projektu. Toto demonstruje **how to add task** programově:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Step 3: Set Task Start Date and Duration
Definujte, kdy úkol začíná a jak dlouho bude trvat:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Step 4: Add a Resource
Nyní **add resource to project** vytvořením nové položky `Resource`:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Step 5: Create a Resource Assignment
Propojte úkol a nově přidaný zdroj:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Step 6: Set Leveling Delay
Nastavte zpoždění levelingu pro přiřazení. Nastavení na nulu znamená žádné další zpoždění, ale hodnotu můžete upravit podle potřeby:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Step 7: Display Results
Vytiskněte důležité vlastnosti pro ověření, že vše bylo nastaveno správně:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Common Pitfalls & Tips
- **Pitfall:** Zapomenutí nastavit datum zahájení úkolu může způsobit, že přiřazení výchozí na začátek projektu.  
- **Tip:** Použijte `prj.getDuration(value, TimeUnitType.Day)` pro kontrolu granularity zpoždění.  
- **Tip:** Po přidání více zdrojů zavolejte `prj.updateResourceAssignments()`, aby plánovač přepočítal leveling.

## Conclusion
Postupováním podle těchto kroků nyní víte **jak přidat zdroj do projektu**, přiřadit jej k úkolu a spravovat vlastnosti zpoždění levelingu pomocí Aspose.Tasks pro Java. Tato znalost vám umožní vytvářet robustní řešení pro automatizaci projektů, která zůstávají v souladu s reálnými omezeními zdrojů.

## FAQ's
### Q: Can I use Aspose.Tasks with other Java libraries?

A: Yes, Aspose.Tasks can be integrated with other Java libraries to enhance project management capabilities.

### Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?

A: Yes, Aspose.Tasks supports various versions of Microsoft Project files, ensuring compatibility across different environments.

### Q: Where can I find additional support for Aspose.Tasks?

A: You can find support and resources on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q: Can I try Aspose.Tasks before purchasing?

A: Yes, you can obtain a free trial of Aspose.Tasks from the [releases page](https://releases.aspose.com/).

### Q: How can I obtain a temporary license for Aspose.Tasks?

A: You can request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/) for evaluation purposes.

## Additional Frequently Asked Questions

**Q: Co se stane, když nastavím nenulové zpoždění levelingu?**  
A: Plánovač odloží začátek přiřazení o zadanou dobu, což pomáhá řešit přetížení.

**Q: Mohu získat zpoždění levelingu po uložení projektu?**  
A: Ano, můžete znovu otevřít soubor projektu a přečíst vlastnost `Asn.DELAY` z přiřazení.

**Q: Existuje způsob, jak aplikovat zpoždění levelingu na všechna přiřazení najednou?**  
A: Můžete iterovat přes `prj.getResourceAssignments()` a nastavit zpoždění pro každé přiřazení ve smyčce.

---

**Poslední aktualizace:** 2026-01-07  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}