---
title: Doba trvání úkolu v různých jednotkách s Aspose.Tasks
linktitle: Doba trvání úkolu v různých jednotkách s Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte správu trvání úkolů v projektech Java pomocí Aspose.Tasks. Přesně vypočítat a převést trvání v minutách, dnech, hodinách, týdnech a měsících.
weight: 32
url: /cs/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Doba trvání úkolu v různých jednotkách s Aspose.Tasks

## Úvod
V oblasti projektového řízení je kritickým aspektem porozumění a řízení doby trvání úkolu. Aspose.Tasks for Java poskytuje výkonnou sadu nástrojů pro efektivní zpracování. V tomto tutoriálu vás provedeme získáváním trvání úkolů v různých jednotkách pomocí Aspose.Tasks.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
- Java Development Kit (JDK) nainstalován
-  Aspose.Tasks pro knihovnu Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/java/)
- Základní znalost programování v Javě
## Importujte balíčky
Do svého projektu Java zahrňte knihovnu Aspose.Tasks. Na začátek kódu přidejte následující příkaz pro import:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Krok 1: Nastavte svůj projekt
Začněte vytvořením nového projektu Java ve vámi preferovaném integrovaném vývojovém prostředí (IDE). Ujistěte se, že jste do závislostí projektu zahrnuli knihovnu Aspose.Tasks.
## Krok 2: Přečtěte si šablonu projektu
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Přečtěte si soubor šablony MS Project
String fileName = dataDir + "project.xml";
// Přečtěte si vstupní soubor jako projekt
Project project = new Project(fileName);
```
 Zajistěte výměnu`"Your Document Directory"` se skutečnou cestou k souborům vašeho projektu.
## Krok 3: Načtěte úkol
```java
// Získejte úkol pro výpočet jeho trvání v různých formátech
Task task = project.getRootTask().getChildren().getById(1);
```
 Zde získáváme úkol z projektu. Upravit`getById(1)` na základě ID úkolu vašeho projektu.
## Krok 4: Doba trvání v minutách
```java
// Získejte dobu trvání v minutách
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Tento krok vypočítá dobu trvání úlohy v minutách.
## Krok 5: Trvání ve dnech
```java
// Získejte trvání ve dnech
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Tento krok vypočítá dobu trvání úlohy ve dnech.
## Krok 6: Doba trvání v hodinách
```java
// Získejte dobu trvání v hodinách
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Tento krok vypočítá dobu trvání úkolu v hodinách.
## Krok 7: Trvání v týdnech
```java
// Získejte dobu trvání v týdnech
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Tento krok vypočítá dobu trvání úkolu v týdnech.
## Krok 8: Doba trvání v měsících
```java
// Získejte dobu trvání v měsících
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Tento krok vypočítá dobu trvání úkolu v měsících.
## Závěr
Správa trvání úkolů je jednoduchá s Aspose.Tasks pro Java. Tento tutoriál vás provede procesem krok za krokem a objasní různé jednotky času.
## Často kladené otázky
### Otázka: Mohu použít Aspose.Tasks pro Javu s jakýmkoli Java IDE?
Ano, Aspose.Tasks for Java je kompatibilní s jakýmkoli Java Integrated Development Environment (IDE).
### Otázka: Jak mohu získat ID úkolu v souboru aplikace Microsoft Project?
Můžete si prohlédnout soubor projektu nebo použít Aspose.Tasks API k programovému načtení ID úkolů.
### Otázka: Je Aspose.Tasks vhodný pro zpracování rozsáhlých projektů?
Absolutně. Aspose.Tasks je navržen tak, aby efektivně zvládal projekty různých velikostí.
### Otázka: Kde najdu další dokumentaci?
 Navštivte[dokumentace](https://reference.aspose.com/tasks/java/)pro komplexní zdroje.
### Otázka: Mohu před nákupem vyzkoušet Aspose.Tasks for Java?
 Ano, můžete prozkoumat a[zkušební verze zdarma](https://releases.aspose.com/) zhodnotit jeho schopnosti.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
