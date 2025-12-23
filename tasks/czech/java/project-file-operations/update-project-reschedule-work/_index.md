---
date: 2025-12-23
description: Naučte se, jak aktualizovat soubory MS Project a přeplánovat nedokončenou
  práci pomocí Aspose.Tasks pro Javu. Také se podívejte, jak uložit XML soubor MS
  Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aktualizujte MS Project a přeplánujte práci pomocí Aspose.Tasks
url: /cs/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aktualizace MS Project a přeplánování práce pomocí Aspose.Tasks

## Úvod
Microsoft Project je široce používaný nástroj pro řízení projektů, který pomáhá týmům plánovat, sledovat a včas doručovat práci. Když se plány posunou, často potřebujete **update MS Project** soubory programově – označit práci jako dokončenou, přesunout zbývající úkoly a udržet základní linii projektu přesnou. Aspose.Tasks pro Java vám poskytuje čisté, typově bezpečné API, které to umožní bez otevření GUI. V tomto tutoriálu uvidíte, jak aktualizovat projekt, označit práci jako dokončenou k určitému datu a poté **how to reschedule MS Project** práci, která stále čeká.

## Rychlé odpovědi
- **Co znamená „update MS Project“?** Označuje úkoly jako dokončené až do zadaného data a zapíše změny zpět do souboru.  
- **Mohu automaticky přeplánovat zbývající práci?** Ano – použijte `rescheduleUncompletedWorkToStartAfter` k posunutí nedokončených úkolů dopředu.  
- **V jakém formátu se soubor ukládá?** Příklady ukládají projekt jako XML (`SaveFileFormat.Xml`).  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební verze stačí pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaká verze Javy je požadována?** JDK 8 nebo vyšší.

## Co je „update MS Project“ v kódu?
Aktualizace projektu znamená programově měnit data úkolů, jejich trvání nebo procenta dokončení a tyto změny uložit. Aspose.Tasks poskytuje metody jako `updateProjectWorkAsComplete`, které aplikují změny na základě referenčního `Date`, který zadáte.

## Proč použít Aspose.Tasks pro Java k aktualizaci MS Project?
- **Žádná závislost na UI** – automatizujte hromadné změny napříč mnoha soubory.  
- **Vysoká věrnost** – knihovna zachovává všechna nativní data Projectu (zdroje, kalendáře, vlastní pole).  
- **Cross‑platform** – spusťte stejný kód na Windows, Linuxu nebo macOS.  
- **Ukládejte MS Project XML** – můžete exportovat aktualizovaný projekt do široce podporovaného XML formátu pro následné nástroje.

## Požadavky
1. Nainstalovaný Java Development Kit (JDK).  
2. Knihovna Aspose.Tasks pro Java – stáhněte ji [zde](https://releases.aspose.com/tasks/java/).  
3. Základní znalost syntaxe Javy a objektově orientovaných konceptů.

## Import balíčků
Nejprve importujte potřebné třídy Aspose.Tasks a utility Javy:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Nastavení projektu
Vytvořte novou instanci `Project`, definujte několik ukázkových úkolů, nastavte jejich trvání a vytvořte závislosti. Pak uložte počáteční stav, abyste viděli efekt před a po změně.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Krok 2: Aktualizace práce v projektu
Označte práci jako dokončenou až do konkrétního data uzávěrky. To je jádro **update MS Project** – API automaticky upraví postup úkolů a data.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Krok 3: Přesunutí nedokončené práce
Po označení dokončené práce často potřebujete posunout zbývající úkoly dopředu. Následující volání přesune veškerou nedokončenou práci tak, aby začínala po stejném datu uzávěrky, čímž efektivně ukazuje **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| Úkoly neukazují aktualizovaná data | Projekt byl uložen v jiném formátu (např. `.mpp`) | Použijte `SaveFileFormat.Xml` pro zachování struktury XML. |
| `updateProjectWorkAsComplete` se zdá, že nic nedělá | Referenční datum je dříve než začátek projektu | Ujistěte se, že datum `Calendar` je v rámci časové osy projektu. |
| Přesunuté úkoly se překrývají | Nebyl aplikován kalendář nebo vyrovnání zdrojů | Použijte kalendář projektu `Project` nebo po přesunutí ručně nastavte `Task.setStart`. |

## Často kladené otázky (rozšířené)

**Q: Může Aspose.Tasks pro Java zvládnout složité struktury projektů?**  
A: Ano, Aspose.Tasks pro Java poskytuje robustní API pro efektivní správu úkolů, závislostí, zdrojů a dalších prvků projektu.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak získám podporu pro Aspose.Tasks pro Java?**  
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.

**Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Ano, dočasné licence jsou k zakoupení [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu podrobnou dokumentaci pro Aspose.Tasks pro Java?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/tasks/java/) – obsahuje komplexní průvodce a reference API.

## Závěr
V tomto tutoriálu jsme prošli kompletním procesem **updating MS Project** souborů, označením práce jako dokončené a následně **how to reschedule MS Project** úkolů, které zůstaly nedokončené. Uložením projektu jako XML zachováte kompatibilitu s ostatními nástroji a získáte jasný auditní záznam změn. Použijte tyto vzory k automatizaci úpravy harmonogramů ve velkých portfoliích, integraci s CI pipeline nebo tvorbě vlastních přehledových dashboardů.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.Tasks pro Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}