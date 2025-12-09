---
date: 2025-12-05
description: Naučte se, jak určit pracovní dny a vypočítat dobu trvání úkolu tím,
  že extrahujete pracovní hodiny z kalendářů MS Project pomocí Aspose.Tasks pro Javu.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Určete pracovní dny a pracovní hodiny pomocí Aspose.Tasks
url: /cs/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Určování pracovních dnů a pracovních hodin pomocí Aspose.Tasks

## Introduction
Správa kalendářů projektů je základní součástí úspěšného plánování projektů. V tomto tutoriálu **určíte pracovní dny** pro libovolný úkol a **extrahujete pracovní hodiny** z kalendáře MS Project pomocí Aspose.Tasks for Java. Na konci průvodce budete schopni **vypočítat dobu trvání úkolu**, přizpůsobit pracovní hodiny a spolehlivě **načíst soubor MPP** pro získání potřebných dat.

## Quick Answers
- **Co znamená „určování pracovních dnů“?** Znamená to identifikaci kalendářních dat, která jsou považována za pracovní dny pro daný úkol.  
- **Kterou knihovnu mám použít?** Aspose.Tasks for Java poskytuje plnohodnotné API pro práci se soubory MS Project.  
- **Jak dlouho trvá implementace?** Obvykle 10–15 minut pro základní extrakci.  
- **Potřebuji licenci?** Je k dispozici bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Mohu přizpůsobit pracovní hodiny?** Ano – můžete upravovat kalendáře, přidávat svátky a nastavovat vlastní pracovní časové intervaly.

## What is “determine working days”?
Když je úkol naplánován, projektový kalendář určuje, které dny jsou pracovní a které nepracovní (víkendy svátky). Určování pracovních dnů tohoto kalendáře, aby bylo přesně známo, kdy může být práce vykonána, což je nezbytné pro přesné výpočty **calculate task duration**.

## Why use Aspose.Tasks to retrieve working hours?
- **Není vyžadován Microsoft Project** – pracujte se soubory .MPP na jakékoli platformě.  
- **Plná podpora kalendářů** – zahrnuje výchozí, zdrojové i úkolové kalendáře.  
- **Vysoký výkon** – rychle zpracujte velké projekty.  
- **Rozsáhlá dokumentace** – příklady a reference API jsou snadno dostupné.

## Prerequisites
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo vyšší.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z [here](https://releases.aspose.com/tasks/java/).  
3. Základní znalosti programování v Javě.  

## Import Packages
Nejprve importujte hlavní jmenný prostor Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Step 1: Load the MPP file
Načtěte svůj projektový soubor (krok **load mpp file**), abyste mohli pracovat s jeho kalendáři:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Step 2: Retrieve Task and Calendar Information
Vyberte úkol, který chcete, a získejte jeho přiřazený kalendář. Zde **retrieve working hours** pro úkol:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Step 3: Define Start and End Dates
Nastavte časové okno, pro které chcete **determine working days**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Step 4: Iterate Through Dates
Procházejte každé datum v délce úkolu. Tento cyklus vám později umožní **customize working hours**, pokud bude potřeba:

```java
java.util.Calendar tempDate = calStartDate;
```

## Step 5: Calculate Duration
Během iterace kontrolujeme, zda je každý den pracovním dnem, sčítáme pracovní hodiny a nakonec vypočítáme dobu trvání úkolu v minutách, hodinách a dnech:

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Task returns `null` for calendar** | Ujistěte se, že úkol skutečně má přiřazený kalendář; jinak dědí výchozí kalendář projektu. |
| **Incorrect duration because of holidays** | Ověřte, že svátky jsou definovány v kalendáři úkolu nebo v základním kalendáři projektu. |
| **Time zone mismatch** | Použijte `java.util.TimeZone` k synchronizaci časové zóny kalendáře s vaším systémem, pokud je to potřeba. |

## Frequently Asked Questions
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Absolutely, Aspose.Tasks for Java supports various versions of MS Project, ensuring compatibility across different environments.

### Q: Can I customize working hours and holidays in project calendars?
A: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.

### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can access a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

## Conclusion
V tomto průvodci jsme ukázali, jak **determine working days**, **retrieve working hours** a **calculate task duration** z kalendáře MS Project pomocí Aspose.Tasks for Java. Dodržením výše uvedených kroků můžete automatizovat analýzu rozvrhu, přizpůsobit kalendáře a udržet své projektové plány přesné a aktuální.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}