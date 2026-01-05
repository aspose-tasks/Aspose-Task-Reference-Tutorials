---
date: 2026-01-05
description: Naučte se, jak nastavit datum zahájení projektu a uložit XML MS Project
  pomocí Aspose.Tasks pro Javu. Průvodce krok za krokem pro vývojáře Javy.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Nastavte počáteční datum projektu pomocí Aspose.Tasks pro Javu
url: /cs/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení počátečního data projektu pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se naučíte **jak nastavit počáteční datum projektu** v souboru Microsoft Project a poté **uložit MS Project XML** pomocí knihovny Aspose.Tasks pro Java. Ať už automatizujete reportingový kanál nebo vytváříte vlastní nástroj pro řízení projektů, zvládnutí tohoto úkolu vám ušetří čas a eliminuje ruční chyby.

## Rychlé odpovědi
- **Jaká je hlavní metoda pro nastavení počátečního data?** Použijte `project.set(Prj.START_DATE, …)`.
- **V jakém formátu mám exportovat soubor?** Uložte jej jako XML pomocí `SaveFileFormat.Xml`.
- **Potřebuji licenci pro tuto operaci?** Zkušební verze funguje, ale plná licence odstraňuje vodoznaky.
- **Mohu změnit počáteční datum po vytvoření úkolů?** Ano, aktualizujte vlastnost projektu před přidáním úkolů.
- **Je to kompatibilní se všemi verzemi MS Project?** Aspose.Tasks podporuje XML, MPP a další formáty.

## Co je „Nastavení počátečního data projektu“?
Nastavení počátečního data projektu definuje základní kalendář, ze kterého začínají všechny výpočty plánování úkolů. Je to první krok při programatickém vytváření spolehlivého harmonogramu projektu.

## Proč použít Aspose.Tasks pro Java?
Aspose.Tasks poskytuje čisté Java API, které funguje na jakékoli platformě bez nutnosti instalace Microsoft Project. Umožňuje rychle vytvářet, upravovat a exportovat projektová data, což je ideální pro automatizaci na serverové straně.

## Předpoklady
1. **Java Development Kit (JDK)** – libovolná aktuální verze JDK.
2. **Aspose.Tasks pro Java** – stáhněte ze [zde](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse nebo vaše preferované Java IDE.

## Import balíčků
Nejprve importujte potřebné třídy:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Krok 1: Nastavení adresáře pro data
Definujte, kde budou ukládány generované soubory.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Vytvoření instance projektu
Instancujte nový, prázdný projekt.

```java
Project project = new Project();
```

### Krok 3: Nastavení vlastností informací o projektu
Zde **nastavíme počáteční datum projektu** a související plánovací vlastnosti.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Krok 4: Uložení MS Project XML
Exportujte nakonfigurovaný projekt do XML souboru.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
- **Nesprávný formát data:** Ujistěte se, že používáte `java.util.Calendar` a před přiřazením zavoláte `getTime()`.
- **Soubor se neuložil:** Ověřte, že `dataDir` ukazuje na existující, zapisovatelnou složku.
- **Varování o licenci:** Zkušební verze přidává vodoznaky; použijte platnou licenci k jejich odstranění.

## Často kladené otázky

### Q: Mohu pomocí Aspose.Tasks pro Java číst soubory MS Project?  
**A:** Ano, Aspose.Tasks pro Java poskytuje robustní funkce pro čtení i zápis souborů MS Project.

### Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?  
**A:** Rozhodně, Aspose.Tasks pro Java podporuje různé formáty MS Project, což zajišťuje širokou kompatibilitu.

### Q: Existují nějaká omezení zkušební verze Aspose.Tasks pro Java?  
**A:** Zkušební verze vám umožní prozkoumat knihovnu, ale do výstupních souborů přidává vodoznaky.

### Q: Jak mohu získat podporu pro Aspose.Tasks pro Java?  
**A:** Pomoc můžete získat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

### Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?  
**A:** Ano, dočasné licence jsou k dispozici pro krátkodobé použití. Získat ji můžete [zde](https://purchase.aspose.com/temporary-license/).

### Q: Zachová se při uložení jako XML vlastní pole?  
**A:** Ano, při uložení pomocí `SaveFileFormat.Xml` jsou zachována všechna vlastní atributy a rozšířená pole.

### Q: Můžu změnit počáteční datum po přidání úkolů?  
**A:** Počáteční datum můžete aktualizovat kdykoli před uložením; stačí znovu zavolat `project.set(Prj.START_DATE, …)`.

---

**Poslední aktualizace:** 2026-01-05  
**Testováno s:** Aspose.Tasks pro Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}