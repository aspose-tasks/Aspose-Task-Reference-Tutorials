---
date: 2026-08-13
description: Naučte se, jak číst pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks
  pro Java. Postupujte podle podrobného návodu s ukázkami kódu a tipy na řešení problémů.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Číst pracovní týdny z kalendáře pomocí Aspose.Tasks
og_description: Jak číst pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks
  pro Java. Postupujte podle stručného tutoriálu s kroky nastavení, úryvky kódu a
  tipy na řešení problémů.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Jak číst pracovní týdny z kalendáře MS pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Jak číst pracovní týdny z kalendáře MS pomocí Aspose.Tasks
url: /cs/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst pracovní týdny z kalendáře MS pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se **naučíte, jak číst pracovní týdny** z kalendáře Microsoft Project pomocí knihovny Aspose.Tasks pro Java. Ať už vytváříte přehledový dashboard, synchronizujete plány s ERP systémem nebo automatizujete extrakci dat pro analytiku, programový přístup k definicím pracovních týdnů šetří nespočet manuálních hodin. Aspose.Tasks podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat soubory o stovkách stránek, aniž by načítal celý soubor do paměti, což vám poskytuje jak flexibilitu, tak výkon.

## Rychlé odpovědi
- **Co znamená „číst pracovní týdny“?** Jedná se o extrakci definic pracovních týdnů (dat a denních pravidel pracovní doby) ze souboru Project pomocí Java kódu.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (k dispozici bezplatná zkušební verze).  
- **Potřebuji licenci pro vývoj?** Zkušební verze stačí pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Jaké souborové formáty jsou podporovány?** Jak *.mpp*, tak Project XML soubory jsou zpracovány, plus více než 50 dalších formátů pro import/export.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut po nastavení knihovny.

## Co je pracovní týden v MS Project?
Pracovní týden definuje kalendářová pravidla, která určují, kdy jsou zdroje k dispozici během konkrétního období. Obsahuje počáteční datum, koncové datum a denní intervaly pracovní doby (např. 9 – 17). V MS Project může každý kalendář obsahovat více pracovních týdnů, což umožňuje modelovat svátky, směnové rozvrhy nebo sezónní plány.

## Jak Aspose.Tasks čte pracovní týdny z kalendáře?
Aspose.Tasks vystavuje `WorkWeekCollection` objektu `Calendar`. Vytvořením instance `Project`, výběrem požadovaného kalendáře (podle UID nebo názvu) a iterací přes jeho `WorkWeekCollection` můžete získat štítek každého pracovního týdne, platný rozsah dat a podrobné denní intervaly pracovní doby. API automaticky provádí všechny konverze datum‑čas a respektuje nastavení časové zóny projektu.

## Proč číst pracovní týdny z kalendáře Microsoft Project v Javě?
Programové čtení pracovních týdnů eliminuje ruční kopírování, zajišťuje, že podřízené systémy (ERP, HR, reporting) používají přesně stejná plánovací pravidla, a garantuje konzistenci napříč více projekty. Automatizace také snižuje lidské chyby a urychluje integrační pipeline, zejména když potřebujete každou noc zpracovat desítky projektových souborů.

## Předpoklady
Než se pustíme do kódu, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo novější nainstalovanou.  
2. **Aspose.Tasks pro Java** – stáhněte nejnovější JAR z oficiální stránky: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Ukázkový soubor Project** (`ReadWorkWeeksInformation.mpp`) umístěný ve známé složce na vašem počítači.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat pro práci s kalendáři a pracovními týdny:

`Project` představuje soubor Microsoft Project, `Calendar` poskytuje jeho kalendáře, `WorkWeek` definuje pracovní týden a `WeekDay` představuje den.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Krok 1: nastavení adresáře s daty
Definujte složku, která obsahuje soubor `.mpp`. Nahraďte zástupný text skutečnou cestou na vašem počítači:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: vytvoření instance Project a přístup ke kalendáři
Třída `Project` představuje soubor Microsoft Project a poskytuje přístup k jeho datovým strukturám, včetně kalendářů, úkolů a zdrojů.  
Instancujte objekt `Project`, vyberte kalendář, který chcete (podle UID), a získejte jeho `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Tip:** Pokud neznáte UID kalendáře, projděte `project.getCalendars()` a nejprve vypište název a UID každého kalendáře.

## Krok 3: iterace přes pracovní týdny
Třída `WorkWeek` zapouzdřuje definici pracovního týdne, obsahuje počáteční/koncová data a nastavení denní pracovní doby.  
Projděte každý `WorkWeek` a zobrazte jeho název, počáteční/koncová data a denní pracovní časy:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Co uvidíte:** Konzole vypíše štítek každého pracovního týdne (např. „Standard“), jeho platný rozsah dat a můžete se podívat na přesné pracovní hodiny pro každý den.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| `NullPointerException` při přístupu k `calendar` | Špatné UID nebo kalendář neexistuje | Ověřte UID pomocí `project.getCalendars().size()` a nejprve vypište dostupné kalendáře. |
| Žádný výstup pro pracovní týdny | Vybraný kalendář nemá vlastní pracovní týdny (používá výchozí) | Použijte výchozí kalendář (`project.getDefaultCalendar()`) nebo vytvořte pracovní týden programově. |
| Formát data vypadá podivně | `System.out.println` používá výchozí formát `java.util.Date` | Použijte `SimpleDateFormat` pro požadovaný formát data. |

## Často kladené otázky
**Q: Mohu pomocí Aspose.Tasks pro Java upravovat informace o pracovních týdnech?**  
A: Ano. API poskytuje `addWorkWeek()`, `removeWorkWeek()` a sady setterů pro změnu názvů, dat a pracovních časů.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Rozhodně. Podporuje MPP soubory od Project 98 až po nejnovější verze, stejně jako Project XML soubory.

**Q: Můžu integrovat Aspose.Tasks s jinými Java frameworky?**  
A: Ano. Knihovna je čistě Java, takže ji můžete použít spolu se Spring, Jakarta EE nebo jakýmkoli jiným frameworkem.

**Q: Je k dispozici zkušební verze Aspose.Tasks?**  
A: Ano, můžete si stáhnout bezplatnou 30‑denní zkušební verzi z oficiální stránky: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Kde najdu podporu pro Aspose.Tasks?**  
A: Nejlepší místo je komunitní fórum Aspose: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-08-13  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Načíst výjimky kalendáře s Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Jak nastavit kalendář a definovat pracovní dny v MS Project s Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}