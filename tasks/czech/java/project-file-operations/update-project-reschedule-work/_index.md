---
date: 2026-03-29
description: Naučte se, jak přeplánovat nedokončenou práci, aktualizovat projektovou
  práci a uložit soubory MS Project jako XML pomocí Aspose.Tasks pro Javu.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Přeplánujte nedokončenou práci a aktualizujte soubory MS Project pomocí Aspose.Tasks
url: /cs/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přeplánování nedokončené práce a aktualizace souborů MS Project pomocí Aspose.Tasks

## Úvod
Microsoft Project je široce používaný nástroj pro řízení projektů, který pomáhá týmům plánovat úkoly, přidělovat zdroje a sledovat časové osy. Aspose.Tasks pro Java poskytuje vývojářům bohaté API pro programatickou manipulaci se soubory Microsoft Project. V tomto tutoriálu se naučíte, jak **aktualizovat práci na projektu**, **přeplánovat nedokončenou práci** a **uložit soubor MS Project** ve formátu XML pomocí Aspose.Tasks pro Java.

## Rychlé odpovědi
- **Co znamená „přeplánovat nedokončenou práci“?** Přesune veškerou zbývající práci úkolu tak, aby začala po zvoleném datu, přičemž dokončené části zůstávají nedotčeny.  
- **Která metoda označuje práci jako dokončenou?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Jak mohu změny uložit?** Použijte `project.save(<path>, SaveFileFormat.Xml)`.  
- **Potřebuji licenci pro produkční nasazení?** Ano, pro komerční použití je vyžadována platná licence Aspose.Tasks.  
- **Která verze Javy je podporována?** Java 8 a novější jsou plně podporovány.

## Co je „přeplánovat nedokončenou práci“?
Přeplánování nedokončené práce upravuje počáteční data všech úkolů, které ještě nejsou dokončeny, a posouvá je tak, aby začaly po zadaném datu ohraničení. To je užitečné, když se časový plán projektu posune kvůli zpožděním nebo změnám rozsahu.

## Proč použít Aspose.Tasks k aktualizaci práce na projektu a přeplánování úkolů?
- **Detailní kontrola:** Přímé nastavení procent dokončení práce a dat.  
- **Bez UI:** Automatizujte hromadné aktualizace napříč mnoha soubory projektů.  
- **Cross‑platform:** Funguje na jakémkoli systému, který spouští Javu.  
- **Zachovává integritu dat:** Všechny závislosti, omezení a zdroje zůstávají konzistentní.

## Požadavky
Než začneme, ujistěte se, že máte následující:
1. Nainstalovaný Java Development Kit (JDK) ve vašem systému.  
2. Knihovnu Aspose.Tasks pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  
3. Základní znalost programovacího jazyka Java.

## Import balíčků
Nejprve importujte potřebné balíčky ve vašem Java kódu:
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
Inicializujte nový objekt `Project`, definujte úkoly, nastavte trvání a vytvořte závislosti. Tím vytvoříte výchozí projekt, který později aktualizujeme a přeplánujeme.
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

## Krok 2: Aktualizace práce na projektu
Označte práci jako dokončenou až do konkrétního data. Tento krok demonstruje operaci **aktualizace práce na projektu**, která je často první akcí před přeplánováním.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Krok 3: Přeplánování nedokončené práce
Nyní posuneme veškerou zbývající (nedokončenou) práci tak, aby začala po stejném datu ohraničení. Toto je hlavní funkce **přeplánování nedokončené práce**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Závěr
V tomto tutoriálu jsme si ukázali, jak **aktualizovat práci na projektu**, **přeplánovat nedokončenou práci** a **uložit soubor MS Project** jako XML pomocí Aspose.Tasks pro Java. Tyto možnosti jsou nezbytné, když je potřeba upravit časové plány projektů na základě skutečného postupu nebo měnících se obchodních priorit.

## Často kladené otázky
### Q: Dokáže Aspose.Tasks pro Java zvládnout složité struktury projektů?
A: Ano, Aspose.Tasks pro Java poskytuje robustní API pro efektivní správu úkolů, závislostí, zdrojů a dalších prvků projektu.

### Q: Je k dispozici zkušební verze pro Aspose.Tasks pro Java?
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Q: Jak mohu získat podporu pro Aspose.Tasks pro Java?
A: Můžete navštívit [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.

### Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?
A: Ano, dočasné licence jsou k zakoupení [zde](https://purchase.aspose.com/temporary-license/).

### Q: Kde mohu najít podrobnou dokumentaci pro Aspose.Tasks pro Java?
A: Můžete se podívat na dokumentaci [zde](https://reference.aspose.com/tasks/java/) pro komplexní průvodce a reference API.

## Další často kladené otázky

**Q: Jak zajistím, aby uložený soubor byl kompatibilní se staršími verzemi Microsoft Project?**  
A: Uložte projekt pomocí `SaveFileFormat.Xml`; XML je široce podporováno napříč verzemi Projectu.

**Q: Mohu přeplánovat jen podmnožinu úkolů místo celého projektu?**  
A: Ano, můžete iterovat přes konkrétní úkoly a zavolat `task.setStart(date)` po vypočítání nového počátečního data.

**Q: Co se stane s přidělením zdrojů, když přeplánuji nedokončenou práci?**  
A: Přiřazení zdrojů jsou automaticky posunuta tak, aby odpovídala novým počátečním datům úkolů, zachovávají logiku přidělení.

**Q: Je možné programově vrátit operaci přeplánování?**  
A: Můžete znovu načíst původní soubor projektu (nebo zálohu), abyste vrátili jakékoli změny.

**Q: Podporuje Aspose.Tasks ukládání do jiných formátů, jako je .mpp?**  
A: Ano. Použijte `SaveFileFormat.MPP` pro uložení v nativním formátu Microsoft Project.

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}