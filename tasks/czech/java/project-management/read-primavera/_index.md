---
date: 2026-04-24
description: Naučte se, jak pomocí Aspose.Tasks Java importovat XML soubory z Primavera
  do MS Project, což umožňuje bezproblémovou výměnu dat a zlepšený projektový management.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Načíst projekt z Primavera v Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Načíst XML Primavera do MS Project
url: /cs/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Načtení MS Project z Primavera pomocí Aspose.Tasks pro Java

## Úvod
V dnešním rychle se rozvíjejícím světě řízení projektů často potřebujete přesouvat harmonogramy mezi Primavera P6 a Microsoft Project, aniž byste přišli o jakýkoli detail. Tento tutoriál ukazuje **jak číst soubory Primavera XML** a importovat je do MS Project pomocí **aspose tasks java**. Na konci průvodce budete schopni načíst specifické vlastnosti úkolů z Primavera do Java aplikace, což vám poskytne jediný zdroj pravdy pro analýzu, reportování nebo další automatizaci.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks pro Java?** Čte a zapisuje mnoho formátů projektových souborů, včetně Primavera XML a Microsoft Project (MPP).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkční použití.  
- **Která verze Javy je podporována?** Je vyžadována Java 8 nebo novější.  
- **Mohu importovat jiné formáty kromě Primavera XML?** Ano, aspose tasks java také podporuje MPP, XML a mnoho dalších.  
- **Je tento přístup vhodný pro velké podnikové projekty?** Rozhodně — Aspose.Tasks je navržen pro výkonné, podnikové scénáře.

## aspose tasks java – Čtení Primavera XML
Čtení Primavera XML znamená parsování XML exportu z Oracle Primavera P6 za účelem získání dat harmonogramu projektu — úkolů, trvání, zdrojů a specifických atributů Primavera — aby mohla být použita v dalších nástrojích, jako je Microsoft Project.

## Proč použít Aspose.Tasks pro Java k čtení Primavera XML?
- **Plná věrnost:** Všechny specifické vlastnosti Primavera jsou zachovány.  
- **Žádné externí závislosti:** Čistá Java knihovna, není potřeba instalovat Primavera ani MS Project.  
- **Škálovatelnost:** Efektivně zpracovává velké projekty s tisíci úkoly.  
- **Cross‑platform:** Funguje na Windows, Linuxu i macOS.

## Požadavky
Před začátkem se ujistěte, že máte následující:
1. **Java Development Kit (JDK)** – Nainstalována Java 8 nebo novější.  
2. **Aspose.Tasks for Java** – Stáhněte jej z [zde](https://releases.aspose.com/tasks/java/).  
3. Soubor Primavera XML (např. `PrimaveraProject.xml`), který chcete načíst.

## Jak načíst soubor projektu v Javě pomocí Aspose.Tasks?
Níže je krok‑za‑krokem průvodce, který vás provede celým procesem.

### Importovat balíčky
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Krok 1: Nastavit adresář dat
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní cestou, kde se nachází váš soubor Primavera XML.

### Krok 2: Načíst projekt z Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Aktualizujte `"PrimaveraProject.xml"` na skutečný název souboru vašeho exportu Primavera.

### Krok 3: Procházet úkoly a získat specifické vlastnosti Primavera
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
Tato smyčka vypisuje specifické detaily každého úkolu z Primavera, jako je ID aktivity, sekvence WBS, typy trvání, rozpis nákladů a další.

## Časté problémy a řešení
- **Chyba souboru nenalezen:** Ověřte, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) a že název XML souboru je správný.  
- **Chybějící vlastnosti Primavera:** Ujistěte se, že XML bylo exportováno se všemi požadovanými poli; starší verze Primavera mohou některé atributy vynechat.  
- **Výkon u velkých souborů:** Zvažte zvýšení velikosti haldy JVM (`-Xmx2g` nebo vyšší) pro projekty s desítkami tisíc úkolů.

## Často kladené otázky
### Q: Mohu upravit specifické vlastnosti úkolů Primavera pomocí Aspose.Tasks pro Java?
A: Ano, Aspose.Tasks pro Java poskytuje API pro úpravu specifických vlastností úkolů Primavera podle potřeby.

### Q: Podporuje Aspose.Tasks pro Java čtení dalších formátů projektových souborů?
A: Ano, Aspose.Tasks pro Java podporuje čtení různých formátů projektových souborů, včetně MPP, XML a Primavera XML.

### Q: Je Aspose.Tasks pro Java vhodný pro podnikové aplikace pro řízení projektů?
A: Rozhodně, Aspose.Tasks pro Java nabízí robustní funkce a škálovatelnost, což jej činí vhodným pro podnikové aplikace pro řízení projektů.

### Q: Mohu pomocí Aspose.Tasks pro Java získat informace o zdrojích z projektů Primavera?
A: Ano, Aspose.Tasks pro Java umožňuje extrahovat informace o zdrojích spolu s detaily úkolů z projektů Primavera.

### Q: Kde najdu další podporu nebo dokumentaci pro Aspose.Tasks pro Java?
A: Kompletní dokumentaci a přístup k fórům pro podporu najdete na stránce [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Závěr
Nyní jste se naučili **jak číst soubory primavera xml** a načíst podrobné informace o úkolech do Java aplikace pomocí **aspose tasks java**. Tato schopnost překonává propast mezi Primavera a Microsoft Project, poskytuje vám úplnou přehlednost napříč platformami a zvyšuje celkovou efektivitu řízení projektů.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}