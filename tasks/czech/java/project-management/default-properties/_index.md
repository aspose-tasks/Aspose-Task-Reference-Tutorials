---
title: Efektivně spravujte vlastnosti MS Project v Aspose.Tasks
linktitle: Spravujte výchozí vlastnosti projektu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak spravovat výchozí vlastnosti MS Project pomocí Aspose.Tasks for Java. Zjednodušte svůj pracovní postup řízení projektů bez námahy.
weight: 11
url: /cs/java/project-management/default-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Efektivně spravujte vlastnosti MS Project v Aspose.Tasks

## Úvod
Chcete zefektivnit proces řízení projektů pomocí Aspose.Tasks for Java? Správa výchozích vlastností v souborech aplikace Microsoft Project může výrazně zvýšit efektivitu. V tomto tutoriálu si krok za krokem projdeme pokyny, jak spravovat výchozí vlastnosti MS Project pomocí Aspose.Tasks.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
### 1. Java Development Kit (JDK)
   - Ujistěte se, že je ve vašem systému nainstalován JDK.
   -  Můžete si jej stáhnout z[tady](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks for Java Library
   - Stáhněte si a zahrňte do svého projektu knihovnu Aspose.Tasks for Java.
   -  Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Nejprve importujte potřebné balíčky do souboru Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Pojďme si tento proces rozdělit na zvládnutelné kroky:
## Krok 1: Načtěte soubor projektu
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Krok 2: Zobrazte výchozí vlastnosti
```java
// Zobrazit výchozí vlastnosti
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Krok 3: Nastavte výchozí vlastnosti
```java
// Nastavte výchozí vlastnosti
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Krok 4: Uložte projekt do formátu XML
```java
// Uložte projekt do formátu XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Krok 5: Zobrazení výsledku
```java
// Zobrazit výsledek konverze.
System.out.println("Process completed Successfully");
```
Pomocí těchto kroků můžete efektivně spravovat výchozí vlastnosti MS Project pomocí Aspose.Tasks for Java.
## Závěr
V tomto tutoriálu jsme se naučili, jak spravovat výchozí vlastnosti MS Project pomocí Aspose.Tasks for Java. Využitím těchto technik můžete optimalizovat pracovní tok projektového řízení, zvýšit produktivitu a organizaci.
## FAQ
### Q1: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Odpověď 1: Ano, Aspose.Tasks podporuje různé programovací jazyky, jako je .NET, Python a Java.
### Q2: Je Aspose.Tasks vhodný pro osobní i podnikové použití?
A2: Rozhodně! Ať už řídíte malé osobní projekty nebo rozsáhlé podnikové iniciativy, Aspose.Tasks vychází vstříc všem.
### Q3: Nabízí Aspose.Tasks zákaznickou podporu?
A3: Ano, pomoc a podporu komunity najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Q4: Mohu vyzkoušet Aspose.Tasks před nákupem?
 A4: Samozřejmě! Můžete využít bezplatnou zkušební verzi z[webová stránka](https://releases.aspose.com/).
### Q5: Jak mohu získat dočasnou licenci pro Aspose.Tasks?
 A5: Můžete získat dočasnou licenci z[nákupní stránku](https://purchase.aspose.com/temporary-license/) pro účely testování a hodnocení.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
