---
title: Časově uspořádaná data úkolu v Aspose.Tasks
linktitle: Časově uspořádaná data úkolu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte Aspose.Tasks pro Javu a ovládněte časově uspořádanou správu dat úloh. Stáhněte si knihovnu, užijte si bezplatnou zkušební verzi a zefektivněte sledování svých projektů.
type: docs
weight: 34
url: /cs/java/task-properties/task-timephased-data/
---
## Úvod
oblasti projektového řízení je přesné sledování časově uspořádaných dat pro efektivní realizaci projektu zásadní. Aspose.Tasks for Java se ukazuje jako výkonný nástroj pro zefektivnění tohoto procesu, který nabízí robustní funkce a flexibilitu. Tento tutoriál vás provede využitím Aspose.Tasks pro Java k efektivní správě časově uspořádaných dat.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou Javu.
-  Aspose.Tasks for Java Library: Stáhněte si a zahrňte knihovnu Aspose.Tasks do svého projektu. Knihovnu najdete[tady](https://releases.aspose.com/tasks/java/).
- Adresář dokumentů: Nastavte adresář pro vaše projektové dokumenty.
## Importujte balíčky
Ve svém projektu Java importujte potřebné balíčky pro Aspose.Tasks:
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
## Krok 1: Nastavte datum zahájení projektu
```java
Project project = new Project(dataDir + "project.xml");
// Dodatečný kód pro import balíků
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Vysvětlení: Inicializujte objekt kalendáře, nastavte počáteční datum a použijte jej na projekt.
## Krok 2: Definujte úkol a zdroj
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Vysvětlení: Vytvořte úkol a zdroj a nastavte sazby za standardní a přesčasové hodiny.
## Krok 3: Nastavte dobu trvání úkolu
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Vysvětlení: Definujte dobu trvání úkolu (např. 6 dní).
## Krok 4: Přiřaďte zdroj k úkolu
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Vysvětlení: Přiřaďte zdroj k úloze.
## Krok 5: Nakonfigurujte přiřazení prostředků
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Vysvětlení: Nastavte parametry, jako je zastavení, pokračování a pracovní obrys pro přiřazení zdroje.
## Krok 6: Nastavte základní linii
```java
project.setBaseline(BaselineType.Baseline);
```
Vysvětlení: Stanovte základní linii projektu.
## Krok 7: Aktualizace Dokončení úlohy
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Vysvětlení: Uveďte procento dokončení úkolu.
## Krok 8: Načtěte časově uspořádaná data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Vysvětlení: Načtěte časově uspořádaná data pro zbývající práci přiřazení.
## Krok 9: Zobrazte časově uspořádaná data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Doplňkový kód pro zobrazení dalších hodnot
```
Vysvětlení: Výstup a zobrazení časově uspořádaných dat.
## Závěr
Efektivní správa časově uspořádaných dat je pro úspěch projektu nezbytná. Aspose.Tasks for Java tento proces zjednodušuje a poskytuje komplexní sadu funkcí. Podle tohoto návodu můžete bezproblémově integrovat Aspose.Tasks do svého projektu Java a zajistit tak přesnou kontrolu nad časovými osami projektu a alokací zdrojů.
## Často kladené otázky
### Otázka: Mohu použít Aspose.Tasks for Java v jakémkoli projektu Java?
Odpověď: Ano, Aspose.Tasks for Java je kompatibilní s jakýmkoli projektem založeným na Java.
### Otázka: Kde najdu další podporu pro Aspose.Tasks for Java?
 A: Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu a diskuze.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Tasks for Java?
 Odpověď: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu zakoupit Aspose.Tasks pro Java?
 Odpověď: Můžete si zakoupit Aspose.Tasks pro Javu[tady](https://purchase.aspose.com/buy).