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

## Úvod
V tomto tutoriálu se naučíte **jak přidat zdroj do projektu** a zároveň spravovat vlastnosti zpoždění levelingu pro přiřazení zdrojů pomocí Aspose.Tasks pro Java. Ať už budujete plánovací modul nebo automatizujete aktualizace projektů, provádíte tyto kroky vám umožní udržet data projektu přesná, aniž byste potřebovali nainstalovaný Microsoft Project.

## Rychlé odpovědi
- **Co znamená „add resource to project“?** Vytvořte novou položku zdroje, kterou lze přiřadit úkoly.
- **Mohu nastavit zpoždění levelingu po přiřazení?** Ano, pomocí polí `Asn.DELAY` nebo `Asn.LEVELING_DELAY`.
- **Potřebuji licenci pro spuštění tohoto kódu?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována placená licence.
- **Jaká verze Javy je podporována?** Java8nebo novější.
- **Je to kompatibilní se všemi formáty souborů MS Project?** Aspose.Tasks podporuje .MPP, .XML, .XER a další.

## Co je to „přidat zdroj do projektu“ v Aspose.Tasks?
Přidání zdrojů do projektu znamená vytvoření objektu `Resource` uvnitř modelu `Project`. Tento objekt může být později propojen s úkoly pomocí `ResourceAssignment`, což vám umožní sledovat práci, náklady a nastavení levelingu.

## Proč zacházet s vlastnostmi zpoždění vyrovnání?
Zpoždění levelingu pomáhá plánovači rozložit práci, když jsou zdroje přetížené. Nastavením zpoždění řeknete enginu, aby odložil začátek přiřazení, čímž se vyhnete konfliktům a projekt zůstane realistický.

## Předpoklady
Než začneme, zjistíme, že máte následující předpoklady:
1. Java Development Kit (JDK): přichází se, že máte nainstalovaný Java JDK na svém systému. Můžete si ji stáhnout a nainstalovat z [webové stránky](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Tasks for Java Library: Přidejte knihovnu Aspose.Tasks for Java z [stránka ke stažení](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve importujte potřebné balíčky do svého Java projektu, abyste mohli využívat funkce Aspose.Úkoly:
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

## Krok 1: Vytvoření objektu projektu
Vytvořte instanci objektu `Project`, který bude sloužit jako kontejner pro všechny úkoly, zdroje a přiřazení:
```java
Project prj = new Project();
```

## Krok 2: Vytvoření úkolu
Přidejte úkol do projektu. Toto demonstruje **how to add task** programově:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Krok 3: Nastavení data zahájení a trvání úkolu
Definujte, kdy úkol začíná a jak dlouho bude trvat:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Krok 4: Přidání zdroje
Nyní **add resource to project** vytvořením nové položky `Resource`:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Krok 5: Vytvoření přiřazení zdroje
Propojte úkol a nově přidaný zdroj:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Krok 6: Nastavení zpoždění vyrovnání
Nastavte zpoždění levelingu pro přiřazení. Nastavení na nulu znamená žádné další zpoždění, ale hodnotu můžete upravit podle potřeby:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Krok 7: Zobrazení výsledků
Vytiskněte důležité vlastnosti pro ověření, že vše bylo nastaveno správně:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Běžná úskalí a tipy
- **Pitfall:** Zapomenutí nastavení datum zahájení úkolu může způsobit, že přiřazení výchozí na začátek projektu.
- **Tip:** Použijte `prj.getDuration(value, TimeUnitType.Day)` pro zpoždění kontroly granularity.
- **Tip:** Po přidání více zdrojů zavolejte `prj.updateResourceAssignments()`, aby plánovač přepočítal levelování.

## Závěr
Postupováním podle těchto kroků nyní víte **jak přidat zdroj do projektu**, přiřadit jej k úkolu a spravovat vlastnosti zpoždění levelingu pomocí Aspose.Tasks pro Java. Tato znalost vám umožní vytvořit robustní řešení pro automatizaci projektů, která jsou v souladu s reálnými omezeními zdrojů.

## Nejčastější dotazy
### Otázka: Mohu používat Aspose.Tasks s jinými Java knihovnami?

Odpověď: Ano, Aspose.Tasks lze integrovat s jinými knihovnami Java, aby se zlepšily možnosti řízení projektů.

### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?

Odpověď: Ano, Aspose.Tasks podporuje různé verze souborů Microsoft Project a zajišťuje kompatibilitu v různých prostředích.

### Otázka: Kde najdu další podporu pro Aspose.Tasks?

Odpověď: Podporu a zdroje najdete na [Fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Otázka: Mohu si Aspose.Tasks před nákupem vyzkoušet?

Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks na [stránce vydání](https://releases.aspose.com/).

### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Tasks?

Odpověď: Na [stránce dočasné licence](https://purchase.aspose.com/temporary-license/) si můžete vyžádat dočasnou licenci pro účely hodnocení.

## Další často kladené otázky

**Q: Co se stane, když nastavím nenulové zpoždění levelingu?**
A: Plánovač odloží začátek přiřazení o zadanou dobu, což pomáhá řešit přetížení.

**O: Mohu získat zpoždění levelingu po uložení projektu?**
A: Ano, můžete znovu otevřít soubor projektu a přečíst si vlastnost `Asn.DELAY` z přiřazení.

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