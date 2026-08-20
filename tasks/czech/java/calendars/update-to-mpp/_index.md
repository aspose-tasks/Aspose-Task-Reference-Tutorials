---
date: 2026-08-13
description: Naučte se, jak přidat svátky do calendar, přiřadit calendar k projektu
  a uložit soubor MS Project jako MPP pomocí Aspose.Tasks for Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Aktualizovat calendar do formátu MPP v Aspose.Tasks
og_description: Přidejte svátky do calendar, přiřaďte jej k projektu a převeďte schedule
  na MPP pomocí Aspose.Tasks for Java. Naučte se automatizaci krok za krokem.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Přidat svátky do calendar a uložit jako MPP pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Přidat svátky do calendar a uložit jako MPP pomocí Aspose.Tasks
url: /cs/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání svátků do kalendáře a uložení jako MPP pomocí Aspose.Tasks

## Úvod

V moderním řízení projektů často potřebujete **přidat svátky do kalendáře** souborů, vytvořit **kalendář MS Project** a poté sdílet harmonogram v nativním formátu MPP. Ať už konsolidujete časové osy z více zdrojů nebo migrujete stará data, programové generování kalendáře eliminuje manuální chyby a urychluje dodání. Tento tutoriál vás provede kompletním procesem vytvoření kalendáře v MS Project, jeho přizpůsobením svátky, **přiřazením kalendáře k projektu** a nakonec **převodem projektu na MPP** pomocí Aspose.Tasks Java API.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání svátků do kalendáře, přiřazení kalendáře k projektu a uložení výsledku jako soubor MPP s Aspose.Tasks pro Java.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší (JDK 8+).  
- **Mohu kalendář přizpůsobit?** Ano – můžete přidávat pracovní časy, výjimky i svátky.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní kalendář.  

## Co znamená „create calendar MS Project“?

Vytvoření kalendáře MS Project znamená definovat pracovní dny, hodiny a výjimky, které řídí plánování úkolů v souboru Microsoft Project. Pomocí Aspose.Tasks můžete tento kalendář programově vytvořit, nastavit svátky a vložit jej do projektu bez otevření uživatelského rozhraní MS Project.

## Proč použít Aspose.Tasks pro tento úkol?

Měli byste použít Aspose.Tasks, protože nabízí plnou kompatibilitu s Javou, nevyžaduje Microsoft Office a umožňuje přímo generovat a ukládat nativní soubory MPP z kódu. Knihovna podporuje všechny funkce kalendáře, funguje na jakémkoli serverovém prostředí a zpracovává projekty až s 10 000 úkoly za méně než sekundu.

## Předpoklady

1. **Java Development Kit (JDK) 8+** – ujistěte se, že `java -version` vrací 1.8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli editor dle vašeho výběru.  
4. **Základní znalost Javy** – povědomí o třídách, metodách a souborovém I/O.

## Jak přidat svátky do kalendáře

Pro přidání svátků vytvoříte nový objekt `Calendar`, získáte jeho kolekci `Exceptions` a přidáte položky `DateException` pro každé datum svátku. `DateException` představuje jeden nepracovní den nebo rozsah v kalendáři. Aspose.Tasks pak tyto datumy považuje za nepracovní dny, což zajišťuje, že úkoly jsou plánovány okolo definovaných svátků.

### Krok 1: import požadovaných balíčků

Nejprve načtěte třídy Aspose.Tasks a Java utility do rozsahu.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Krok 2: nastavení adresáře s daty

Definujte, kde budou umístěny vstupní šablony a výstupní soubory. Nahraďte zástupný text skutečnou cestou na vašem počítači.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: definování názvů vstupních a výstupních souborů

Načteme existující soubor MPP (nebo prázdný projekt) a zapíšeme výsledek do nového souboru.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Krok 4: načtení projektu a přidání nového kalendáře

Třída `Project` představuje soubor MS Project v paměti a poskytuje přístup k jeho kalendářům, úkolům a zdrojům.

Vytvořte instanci `Project` ze zdrojového souboru a přidejte kalendář pojmenovaný **„Calendar 1“**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Krok 5: přizpůsobení kalendáře (volitelné)

Objekt `Calendar` definuje pracovní dny, hodiny a výjimky pro plán projektu.

Pokud potřebujete specifické pracovní časy, svátky nebo výjimky, zavolejte vlastní pomocnou metodu. Ve vzorku je použita metoda `GetTestCalendar` jako zástupná.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Můžete přímo manipulovat s `cal1.getWeekDays()` pro nastavení pracovních hodin pro každý den v týdnu, nebo použít `cal1.getExceptions()` k **přidání svátků do kalendáře**.

### Krok 6: přiřazení kalendáře k projektu

Řekněte projektu, aby používal nově vytvořený kalendář pro všechny výpočty plánování.

```java
project.set(Prj.CALENDAR, cal1);
```

### Krok 7: uložení projektu jako MPP

Výčtová hodnota `SaveFileFormat` určuje výstupní formát, přičemž `Mpp` označuje nativní formát Microsoft Project.

Nyní **převést projekt na MPP** uložením s volbou `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Krok 8: potvrzení úspěšného dokončení

Jednoduchá zpráva v konzoli vás informuje, že proces byl dokončen bez chyb.

```java
System.out.println("Process completed Successfully");
```

## Běžné případy použití

- **Automatizovaná generace harmonogramu** pro opakující se projekty (např. týdenní sprinty).  
- **Migrace starých kalendářů CSV nebo Excel** do plně funkčního souboru MS Project.  
- **Server‑side reporting**, kde webová služba vrací soubor MPP na vyžádání.  

## Řešení problémů a běžné úskalí

| Problém | Příčina | Oprava |
|---------|----------|--------|
| `NullPointerException` on `project.save` | `dataDir` ukazuje na neexistující složku | Zajistěte, aby adresář existoval, nebo jej vytvořte programově. |
| Calendar not applied to tasks | Úkoly stále odkazují na výchozí kalendář | Po nastavení `Prj.CALENDAR` také aktualizujte `Task.CALENDAR` u každého úkolu, pokud byl dříve přepsán. |
| Output file is 0 KB | Chybějící oprávnění k zápisu | Spusťte JVM s odpovídajícími oprávněními k souborovému systému nebo zvolte zapisovatelnou cestu. |

## Často kladené otázky

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?**  
A: Ano, Aspose.Tasks podporuje všechny formáty souborů Microsoft Project od Project 2007 až po Project 2024, což zahrnuje více než 10 verzí.

**Q: Mohu přizpůsobit kalendáře podle konkrétních požadavků projektu?**  
A: Rozhodně. Můžete definovat pracovní dny, nastavit vlastní pracovní týdny, přidat svátky a dokonce vytvořit více kalendářů v rámci jednoho souboru projektu.

**Q: Nabízí Aspose.Tasks pro Java podporu při řešení problémů a pomoc?**  
A: Ano, můžete získat pomoc na fóru komunity Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?**  
A: Ano, plně funkční bezplatná zkušební verze je dostupná [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Dočasné licence lze požádat přes web Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

**Poslední aktualizace:** 2026-08-13  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Jak definovat pracovní dny v kalendářích MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Vytvořit vlastní výjimky kalendáře s Aspose.Tasks pro Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}