---
date: 2026-08-24
description: Naučte se, jak přidat kalendář svátků, určit pracovní dny a vypočítat
  dobu trvání úkolu extrahováním pracovních hodin z kalendářů MS Project pomocí Aspose.Tasks
  for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Jak přidat kalendář svátků a určit pracovní dny
og_description: Naučte se, jak přidat kalendář svátků, určit pracovní dny a vypočítat
  dobu trvání úkolu extrahováním pracovních hodin z kalendářů MS Project pomocí Aspose.Tasks
  for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Jak přidat kalendář svátků a určit pracovní dny
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Jak přidat kalendář svátků a určit pracovní dny
url: /cs/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat kalendář svátků a určit pracovní dny

Správa kalendářů projektů je základní součástí úspěšného plánování projektů. V tomto tutoriálu **přidáte kalendář svátků**, **určíte pracovní dny** pro jakýkoli úkol a **extrahujete pracovní hodiny** z kalendáře MS Project pomocí Aspose.Tasks pro Java. Na konci průvodce budete schopni **vypočítat dobu trvání úkolu**, přizpůsobit pracovní hodiny a spolehlivě **načíst soubor MPP** k získání potřebných dat – vše bez instalace Microsoft Project.

## Rychlé odpovědi
- **Co znamená „určování pracovních dnů“?** Znamená to identifikaci, které kalendářní datumy jsou považovány za pracovní dny pro daný úkol.  
- **Kterou knihovnu mám použít?** Aspose.Tasks pro Java poskytuje plnohodnotné API pro práci se soubory MS Project.  
- **Jak dlouho trvá implementace?** Obvykle 10–15 minut pro základní extrakci.  
- **Potřebuji licenci?** Je k dispozici bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Mohu přizpůsobit pracovní hodiny?** Ano – můžete upravit kalendáře, přidat svátky a nastavit vlastní pracovní časové intervaly.  

## Co je „určování pracovních dnů“?
**Určování pracovních dnů** znamená dotazování na kalendář projektu, aby se zjistilo, které datumy jsou označeny jako pracovní dny oproti nepracovním dnům (víkendy, svátky nebo vlastní výjimky). Tyto informace jsou nezbytné pro přesné **vypočítání doby trvání úkolu**, protože pouze pracovní dny přispívají k uplynulému času úkolu.

## Proč použít Aspose.Tasks k získání pracovních hodin?
Aspose.Tasks vám umožní číst soubory MS Project bez nainstalovaného Microsoft Project, což umožňuje automatizaci na jakékoli platformě. Také poskytuje vysoce výkonné zpracování, širokou podporu formátů a podrobnou dokumentaci.  

- **Plná podpora kalendářů** – výchozí, zdrojové a úkolové kalendáře jsou všechny přístupné.  
- **Vysoký výkon** – dokáže zpracovat projekty obsahující **10 000+ úkolů za méně než 2 sekundy** na standardním 2,5 GHz CPU.  
- **Rozsáhlá podpora formátů** – podporuje **více než 50 vstupních a výstupních formátů**, včetně MPP, MPX, XML a Primavera.  
- **Komplexní dokumentace** – jsou k dispozici ukázky kódu, reference API a komunitní fóra.  

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo vyšší.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Základní znalost programování v Javě.  

## Import balíčků
`Project` třída je hlavní objekt Aspose.Tasks, který představuje jeden soubor MS Project v paměti. Importujte požadovaný balíček před zahájením:

Import balíčků

```java
import com.aspose.tasks.*;
```

## Jak načíst soubor MPP pomocí Aspose.Tasks?
`Project` třída načte soubor MS Project a poskytne přístup k jeho datům. Načtěte soubor projektu jedním řádkem kódu; není vyžadováno UI ani COM interop. Tento jednoduchý krok vám poskytne plný přístup ke kalendářům, úkolům a zdrojům.

Načítání souboru MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Získání informací o úkolu a kalendáři
`Task` představuje úkol projektu a `Calendar` definuje jeho pravidla pracovní doby. Vyberte úkol, který chcete analyzovat, a získejte jeho přidružený kalendář. Objekt `Task` poskytuje metody `getStart()` a `getFinish()`, zatímco objekt `Calendar` odhaluje definice pracovní doby.

Získávání úkolu a kalendáře

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definování počátečního a koncového data
Objekty `Date` určují časové okno pro analýzu kalendáře. Nastavte časové okno, pro které chcete **určovat pracovní dny**. Použití počátečního a koncového data úkolu zajišťuje, že hodnotíte pouze relevantní období.

Definování dat

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Procházení datumů
`for` smyčka může iterovat přes každý den v rozsahu datumů. Procházejte každé datum v trvání úkolu. Tato smyčka vám později umožní **přizpůsobit pracovní hodiny**, pokud bude potřeba, a je základem pro výpočet celkového pracovního času.

Iterování datumů

```java
java.util.Calendar tempDate = calStartDate;
```

## Výpočet trvání
`Duration` agreguje celkový pracovní čas vypočítaný z iterace. Během iterace kontrolujete, zda je každý den pracovním dnem, sčítáte pracovní hodiny a nakonec vypočítáte trvání úkolu v minutách, hodinách a dnech. Toto ukazuje, jak programově **vypočítat pracovní dny** a **vypočítat dobu trvání úkolu**.

Výpočet trvání

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

## Jak přizpůsobit pracovní hodiny a svátky
Můžete upravit pracovní časové intervaly kalendáře a přidat výjimky, jako jsou svátky. Použijte `taskCalendar.addWorkingTime()` k nastavení nových pracovních období a `taskCalendar.addException()` k vložení svátku. To je užitečné, když výchozí rozvrh 9‑5 neodpovídá politikám vaší organizace.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Úkol vrací `null` pro kalendář** | Ujistěte se, že úkol má skutečně přiřazený kalendář; jinak dědí výchozí kalendář projektu. |
| **Nesprávná doba trvání kvůli svátkům** | Zkontrolujte, že svátky jsou definovány v kalendáři úkolu nebo v základním kalendáři projektu. |
| **Neshoda časových pásem** | Použijte `java.util.TimeZone` k nastavení časového pásma kalendáře podle vašeho systému, pokud je to potřeba. |

## Často kladené otázky
### Q: Dokáže Aspose.Tasks pro Java zvládnout složité struktury projektů?
A: Ano, Aspose.Tasks pro Java poskytuje komplexní podporu pro práci se složitými strukturami projektů, včetně úkolů, zdrojů a kalendářů.

### Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?
A: Rozhodně, Aspose.Tasks pro Java podporuje různé verze MS Project, což zajišťuje kompatibilitu napříč různými prostředími.

### Q: Mohu přizpůsobit pracovní hodiny a svátky v kalendářích projektu?
A: Ano, můžete snadno přizpůsobit pracovní hodiny a svátky podle požadavků vašeho projektu pomocí API Aspose.Tasks pro Java.

### Q: Nabízí Aspose.Tasks pro Java podporu a dokumentaci?
A: Ano, Aspose.Tasks pro Java poskytuje rozsáhlou dokumentaci a vyhrazená fóra podpory, která pomáhají vývojářům efektivně využívat jeho funkce.

### Q: Je k dispozici zkušební verze Aspose.Tasks pro Java?
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro Java na [Aspose releases page](https://releases.aspose.com/).

## Závěr
V tomto průvodci jsme ukázali, jak **přidat kalendář svátků**, **určovat pracovní dny**, **získat pracovní hodiny** a **vypočítat dobu trvání úkolu** z kalendáře MS Project pomocí Aspose.Tasks pro Java. Dodržením výše uvedených kroků můžete automatizovat analýzu harmonogramu, přizpůsobit kalendáře a udržet své projektové plány přesné a aktuální. Nyní máte nástroje k **čtení dat MS Project**, **načtení souboru MPP** a provádění přesných výpočtů trvání bez potřeby samotného Microsoft Project.

---

**Poslední aktualizace:** 2026-08-24  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Přidat svátky do kalendáře a uložit jako MPP pomocí Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Vytvořit vlastní výjimky kalendáře pomocí Aspose.Tasks pro Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}