---
date: 2025-12-28
description: Naučte se načítat soubory XML z Primavera do MS Projectu pomocí Aspose.Tasks
  pro Javu, což umožňuje bezproblémovou výměnu dat a zlepšené řízení projektů.
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak načíst XML z Primavera do MS Project pomocí Aspose.Tasks pro Javu
url: /cs/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení MS Project z Primavera pomocí Aspose.Tasks pro Java

## Úvod
V moderním řízení projektů je přenos dat mezi nástroji bez ztráty detailů zásadní. Tento tutoriál vám ukáže **jak číst primavera xml** soubory a importovat je do Microsoft Project pomocí Aspose.Tasks pro Java. Na konci budete schopni extrahovat specifické vlastnosti úkolů z Primavera, což usnadní a zefektivní analýzu napříč platformami.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks pro Java?** Čte a zapisuje mnoho formátů projektových souborů, včetně Primavera XML a Microsoft Project (MPP).  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro hodnocení; licence je vyžadována pro produkční použití.  
- **Jaká verze Javy je podporována?** Je vyžadována Java 8 nebo vyšší.  
- **Mohu číst i jiné formáty kromě Primavera XML?** Ano, Aspose.Tasks podporuje MPP, XML a mnoho dalších.  
- **Je tento přístup vhodný pro rozsáhlé podnikově projekty?** Rozhodně – Aspose.Tasks je navrženo pro výkonné, podnikově úrovňové scénáře.

## Co je čtení primavera xml?
Čtení Primavera XML znamená parsování XML exportu z Oracle Primavera P6 za účelem získání dat rozvrhu projektu – úkolů, trvání, zdrojů a specifických atributů Primavera – aby mohly být použity v jiných nástrojích, jako je Microsoft Project.

## Proč použít Aspose.Tasks pro Java k čtení primavera xml?
- **Plná věrnost:** Všechny specifické vlastnosti Primavera jsou zachovány.  
- **Žádné externí závislosti:** Čistá Java knihovna, není potřeba instalovat Primavera ani MS Project.  
- **Škálovatelnost:** Efektivně zpracovává velké projekty s tisíci úkoly.  
- **Cross‑platform:** Funguje na Windows, Linuxu i macOS.

## Předpoklady
Před zahájením se ujistěte, že máte následující:
1. **Java Development Kit (JDK)** – Java 8 nebo novější nainstalovanou.  
2. **Aspose.Tasks pro Java** – Stáhněte si jej z [zde](https://releases.aspose.com/tasks/java/).  
3. Soubor Primavera XML (např. `PrimaveraProject.xml`), který chcete číst.

## Jak číst projektový soubor v Javě pomocí Aspose.Tasks?
Níže je krok‑za‑krokem průvodce, který vás provede celým procesem.

### Import balíčků
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Krok 1: Nastavení adresáře s daty
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní cestou, kde se nachází váš soubor Primavera XML.

### Krok 2: Načtení projektu z Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Aktualizujte `"PrimaveraProject.xml"` na skutečný název souboru vašeho exportu z Primavera.

### Krok 3: Procházení úkolů a získání specifických vlastností Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Tato smyčka vypíše pro každý úkol specifické detaily Primavera, jako je Activity ID, WBS sekvence, typy trvání, rozpis nákladů a další.

## Časté problémy a řešení
- **Chyba soubor nenalezen:** Ověřte, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) a že název XML souboru je správný.  
- **Chybějící vlastnosti Primavera:** Ujistěte se, že XML bylo exportováno se všemi požadovanými poli; starší verze Primavera mohou některé atributy vynechat.  
- **Výkon u velkých souborů:** Zvažte zvýšení velikosti haldy JVM (`-Xmx2g` nebo více) pro projekty s desítkami tisíc úkolů.

## Často kladené otázky
### Q: Mohu pomocí Aspose.Tasks pro Java upravovat specifické vlastnosti úkolů Primavera?
A: Ano, Aspose.Tasks pro Java poskytuje API pro úpravu specifických vlastností úkolů Primavera podle potřeby.

### Q: Podporuje Aspose.Tasks pro Java čtení dalších formátů projektových souborů?
A: Ano, Aspose.Tasks pro Java podporuje čtení různých formátů projektových souborů včetně MPP, XML a Primavera XML.

### Q: Je Aspose.Tasks pro Java vhodné pro podnikově úrovňové aplikace řízení projektů?
A: Rozhodně, Aspose.Tasks pro Java nabízí robustní funkce a škálovatelnost, což jej činí vhodným pro podnikově úrovňové aplikace řízení projektů.

### Q: Mohu pomocí Aspose.Tasks pro Java extrahovat informace o zdrojích z projektů Primavera?
A: Ano, Aspose.Tasks pro Java umožňuje extrahovat informace o zdrojích spolu s podrobnostmi úkolů z projektů Primavera.

### Q: Kde najdu další podporu nebo dokumentaci k Aspose.Tasks pro Java?
A: Kompletní dokumentaci a přístup k fórům pro podporu najdete na stránce [Aspose.Tasks pro Java documentation](https://reference.aspose.com/tasks/java/).

## Závěr
Nyní jste se naučili **jak číst primavera xml** soubory a načíst podrobné informace o úch do Java aplikace pomocí Aspose.Tasks. Tato schopnost překonává propast mezi Primavera a Microsoft Project, poskytuje vám plnou viditelnost napříč platformami a zvyšuje celkovou efektivitu řízení projektů.

---

**Poslední aktualizace:** 2025-12-28  
**Testováno s:** Aspose.Tasks pro Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}