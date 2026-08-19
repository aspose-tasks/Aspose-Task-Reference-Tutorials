---
date: 2026-02-28
description: Zjistěte, jak používat Aspose.Tasks pro Javu k správě časově rozdělených
  dat úkolů, stáhněte knihovnu, vyzkoušejte ji zdarma a zefektivněte sledování projektů.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak použít Aspose.Tasks pro správu časově fázovaných dat úkolů (Java)
url: /cs/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak používat Aspose.Tasks pro časově fázovaná data úkolů

## Úvod
Pokud hledáte **jak používat Aspose**, abyste měli pevnou kontrolu nad harmonogramem svého projektu, jste na správném místě. Přesné sledování časově fázovaných dat úkolů je základním kamenem úspěšného řízení projektů a Aspose.Tasks pro Java vám poskytuje nástroje potřebné k automatizaci tohoto procesu. V tomto tutoriálu projdeme kompletním příkladem od začátku do konce, který vám ukáže, jak pomocí Aspose.Tasks vytvořit projekt, přiřadit zdroje, nastavit baseline a nakonec získat a zobrazit časově fázovaná data.

## Rychlé odpovědi
- **Co znamená „časově fázovaná data“?** Jedná se o data rozdělená podle časových intervalů (dny, týdny, měsíce), která ukazují práci, náklady nebo zbývající práci během časové osy projektu.  
- **Která knihovna tuto funkci poskytuje?** Aspose.Tasks pro Java.  
- **Potřebuji licenci pro spuštění ukázky?** Pro vývoj stačí bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Jaká verze Javy je požadována?** Java 8 nebo vyšší.  
- **Mohu exportovat výsledky do Excelu?** Ano – můžete iterovat kolekci `TimephasedData` a zapisovat hodnoty do libovolného formátu, který potřebujete.

## Co jsou časově fázovaná data úkolu?
Časově fázovaná data úkolu představují množství práce (nebo nákladů) naplánované pro úkol během každého časového úseku kalendáře projektu. Umožňují vám vidět, jak je práce rozložena, odhalit přetížení a porovnat plánovaný a skutečný postup.

## Proč používat Aspose.Tasks pro správu časově fázovaných dat?
- **Plná kontrola** – programově vytvářet, upravovat a dotazovat se na časově fázované informace bez otevírání Microsoft Project.  
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.  
- **Bez COM závislostí** – ideální pro automatizaci na serveru.  
- **Bohaté API** – podporuje baseline, pracovní kontury a vlastní pole přímo z krabice.

## Požadavky
Před tím, než se ponoříte do kódu, ujistěte se, že máte:

- **Vývojové prostředí Javy** – nainstalovaný JDK 8+ a nastavenou proměnnou `JAVA_HOME`.  
- **Knihovnu Aspose.Tasks pro Java** – Stáhněte a zahrňte knihovnu Aspose.Tasks do svého projektu. Knihovnu najdete [zde](https://releases.aspose.com/tasks/java/).  
- **Adresář dokumentů** – Složku ve vašem počítači, odkud bude načten a kam bude zapsán soubor ukázkového projektu (`project.xml`).

## Import balíčků
Ve svém Java projektu importujte potřebné třídy Aspose.Tasks:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Krok 1: Nastavení počátečního data projektu
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Vysvětlení:* Vytvoříme instanci `Project`, inicializujeme `Calendar` na požadované počáteční datum a přiřadíme jej vlastnosti `START_DATE` projektu.

## Krok 2: Definice úkolu a zdroje
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Vysvětlení:* Pod kořenovým úkolem se přidá nový úkol s názvem **Task**. Také vytvoříme zdroj s názvem **Rsc** a nastavíme jeho standardní a přesčasy.

## Krok 3: Nastavení trvání úkolu
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Vysvětlení:* Úkol je naplánován na **6 dní**.

## Krok 4: Přiřazení zdroje k úkolu
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Vysvětlení:* Dříve definovaný zdroj je propojen s úkolem pomocí `ResourceAssignment`.

## Krok 5: Konfigurace přiřazení zdroje
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Vysvětlení:* Nastavíme datumy ukončení a obnovení přiřazení (pomocí zástupné hodnoty) a použijeme **Back‑Loaded** pracovní konturu, která posouvá více práce ke konci přiřazení.

## Krok 6: Nastavení baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Vysvětlení:* Zachycení baseline vám umožní později porovnat plánované a skutečné hodnoty.

## Krok 7: Aktualizace dokončení úkolu
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Vysvětlení:* Úkol je označen jako **50 % dokončen**, což ovlivní výpočty zbývající práce.

## Krok 8: Získání časově fázovaných dat
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Vysvětlení:* Tento volání získá **zbývající práci** pro přiřazení, rozdělenou podle časových intervalů projektu.

## Krok 9: Zobrazení časově fázovaných dat
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Vysvětlení:* Jednoduše vypíšeme počet časově fázovaných položek a hodnotu první položky. Ve skutečném scénáři byste iterovali seznam a exportovali data do reportu nebo uživatelského rozhraní.

## Časté problémy a řešení
- **NullPointerException při `getTimephasedData`** – Ujistěte se, že jsou před voláním metody nastaveny datumy `START` a `FINISH` přiřazení.  
- **Nesprávná pracovní kontura** – Ověřte, že zvolený `WorkContourType` odpovídá vaší plánovací strategii; `BackLoaded` je jen jednou z několika možností.  
- **Baseline neodráží změny** – Nezapomeňte volat `project.setBaseline` *po* definování úkolů, zdrojů a přiřazení.

## Často kladené otázky
### Q: Mohu použít Aspose.Tasks pro Java v libovolném Java projektu?
A: Ano, Aspose.Tasks pro Java je kompatibilní s jakýmkoli projektem založeným na Javě.

### Q: Kde mohu najít další podporu pro Aspose.Tasks pro Java?
A: Navštivte [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) pro podporu a diskuze.

### Q: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
A: Ano, bezplatnou zkušební verzi můžete vyzkoušet [zde](https://releases.aspose.com/).

### Q: Jak získat dočasnou licenci pro Aspose.Tasks pro Java?
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Q: Kde si mohu zakoupit Aspose.Tasks pro Java?
A: Zakoupit Aspose.Tasks pro Java můžete [zde](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-02-28  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}