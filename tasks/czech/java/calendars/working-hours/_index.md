---
title: Získejte pracovní dobu z kalendáře pomocí Aspose.Tasks
linktitle: Získejte pracovní dobu z kalendáře pomocí Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Extrahujte pracovní dobu z kalendářů MS Project snadno pomocí Aspose.Tasks pro Javu. Zjednodušte úkoly projektového řízení.
weight: 13
url: /cs/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získejte pracovní dobu z kalendáře pomocí Aspose.Tasks

## Úvod
Správa projektových kalendářů a extrahování pracovní doby je zásadní pro efektivní řízení projektu. Aspose.Tasks for Java poskytuje robustní funkce pro snadné načítání pracovní doby z kalendářů MS Project. V tomto tutoriálu vás provedeme procesem krok za krokem.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Knihovna Aspose.Tasks pro Java byla stažena a přidána do vašeho projektu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
3. Základní znalost programovacího jazyka Java.
## Importujte balíčky
Nejprve importujte potřebné balíčky pro práci s Aspose.Tasks for Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Načtěte soubor projektu
Začněte načtením souboru MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Krok 2: Získejte informace o úkolu a kalendáři
Extrahujte podrobnosti úkolu a kalendáře z projektu:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Krok 3: Definujte počáteční a koncové datum
Nastavte datum zahájení a ukončení úkolu:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Krok 4: Iterujte přes data
Iterujte data v rámci trvání úkolu:
```java
java.util.Calendar tempDate = calStartDate;
```
## Krok 5: Vypočítejte dobu trvání
Vypočítejte dobu trvání v minutách, hodinách a dnech:
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
## Závěr
tomto tutoriálu jsme se zabývali tím, jak načíst pracovní dobu z kalendáře MS Project pomocí Aspose.Tasks for Java. Podle těchto kroků můžete efektivně spravovat plány projektů a snadno vypočítat dobu trvání úkolů.
## FAQ
### Otázka: Dokáže Aspose.Tasks for Java zvládnout složité projektové struktury?
Odpověď: Ano, Aspose.Tasks for Java poskytuje komplexní podporu pro zpracování složitých projektových struktur, včetně úkolů, zdrojů a kalendářů.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými verzemi MS Project?
Odpověď: Rozhodně, Aspose.Tasks for Java podporuje různé verze MS Project a zajišťuje kompatibilitu v různých prostředích.
### Otázka: Mohu upravit pracovní dobu a svátky v kalendáři projektu?
Odpověď: Ano, pomocí Aspose.Tasks for Java API můžete snadno přizpůsobit pracovní dobu a svátky podle požadavků vašeho projektu.
### Otázka: Nabízí Aspose.Tasks for Java podporu a dokumentaci?
Odpověď: Ano, Aspose.Tasks for Java poskytuje rozsáhlou dokumentaci a vyhrazená fóra podpory, která vývojářům pomáhají efektivně využívat jeho funkce.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Aspose.Tasks for Java z[tady](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
