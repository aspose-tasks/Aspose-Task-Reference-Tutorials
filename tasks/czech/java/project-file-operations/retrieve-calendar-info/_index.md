---
date: 2026-03-27
description: Naučte se, jak používat Aspose a Aspose.Tasks k extrakci podrobností
  kalendáře projektu z Microsoft Project souborů pomocí Javy. Krok‑za‑krokem průvodce
  s ukázkami kódu.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak použít Aspose.Tasks k získání informací o kalendáři MS Project
url: /cs/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít Aspose.Tasks k získání informací o kalendáři MS Project

## Úvod
V tomto tutoriálu **objevíte, jak použít Aspose.Tasks** k programovému získání informací o kalendáři ze souborů Microsoft Project. Přístup k datům kalendáře, jako jsou pracovní dny, hodiny a výjimky, je nezbytný, když potřebujete **extrahovat kalendář projektu** pro reportování, integraci nebo vlastní logiku plánování. Projdeme proces krok za krokem a uvidíte přesně **jak použít Aspose** k získání těchto dat ze souboru *.mpp*.

## Rychlé odpovědi
- **Jaká knihovna se v tomto tutoriálu používá?** Aspose.Tasks pro Java.  
- **Které hlavní klíčové slovo je pokryto?** *how to use aspose*.  
- **Co můžete extrahovat?** Kalendáře projektu, včetně pracovních dnů a hodin.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkci.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.

## Co je Aspose.Tasks a proč jej použít?
Aspose.Tasks je výkonné Java API, které umožňuje vývojářům číst, zapisovat a manipulovat se soubory Microsoft Project bez nutnosti samotného Microsoft Project. Používáním Aspose.Tasks můžete **how to extract calendar** informace, automatizovat výpočty plánů a integrovat data projektu s jinými podnikovými systémy — vše z čistého Java kódu.

## Proč extrahovat informace o kalendáři projektu?
Kalendáře projektu určují data úkolů, přidělení zdrojů a celkové výpočty časové osy. Extrahováním těchto dat můžete:
- Vytvářet vlastní zprávy, které odrážejí skutečné pracovní plány.  
- Synchronizovat časové osy Microsoft Project s externími systémy (ERP, BI, atd.).  
- Provádět what‑if analýzu úpravou nastavení kalendáře programově.  
- **Extrahovat data kalendáře MS Project** pro migraci do jiných plánovacích nástrojů.

## Předpoklady
Než začneme, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Nainstalovaný Java Development Kit (JDK) ve vašem systému.  
- Knihovnu Aspose.Tasks pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/java/).

## Import balíčků
Nejprve importujte potřebné třídy Aspose.Tasks do vašeho Java projektu.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Krok 1: Nastavení adresáře s daty
Definujte složku, která obsahuje váš soubor *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní cestou ke složce, kde se nachází **project.mpp**.

## Krok 2: Definice časových jednotek
Vytvořte konstanty, které pomáhají převést interní časovou reprezentaci na lidsky čitelné hodiny.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Tyto hodnoty jsou vyjádřeny v mikrosekundách, což je způsob, jakým Aspose.Tasks interně ukládá čas.

## Krok 3: Vytvoření instance projektu
Načtěte soubor Microsoft Project do objektu `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Konstruktor `Project` parsuje soubor *.mpp* a zpřístupňuje všechna data projektu, včetně kalendářů, prostřednictvím API.

## Krok 4: Získání informací o kalendářích
Získejte kolekci kalendářů definovaných v projektu.

```java
CalendarCollection alCals = project.getCalendars();
```

Projekt může obsahovat více kalendářů (standardní, zdrojové a vlastní kalendáře). Tato kolekce vám poskytuje přístup k jednotlivým kalendářům.

## Krok 5: Procházení kalendářů
Projděte každý kalendář, zobrazte jeho UID, název a pracovní dny s odpovídajícími hodinami.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Vnitřní smyčka kontroluje každý objekt `WeekDay`. Pokud je den označen jako pracovní, vytiskne typ dne (Monday, Tuesday, …) spolu s vypočtenými pracovními hodinami.

## Krok 6: Zobrazení zprávy o dokončení
Signalizujte, že proces extrakce byl dokončen.

```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Žádné kalendáře nebyly vráceny** | Soubor projektu nemusí obsahovat žádné vlastní kalendáře. | Ověřte, že *.mpp* skutečně definuje kalendáře, nebo jej otevřete v Microsoft Project pro potvrzení. |
| **Nesprávné pracovní hodiny** | Konstanty pro převod času jsou nesprávné pro jinou verzi Projectu. | Upravte `OneSec`, `OneMin`, `OneHour`, pokud pracujete s novější verzí Aspose.Tasks, která mění interní časovou jednotku. |
| **`NullPointerException` při `cal.getName()`** | Některé objekty kalendáře mohou být null. | Přidejte kontrolu null před přístupem k vlastnostem (již ukázáno). |

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks podporuje více platforem a programovacích jazyků, včetně .NET, C++, Pythonu a Javy.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.Tasks?**  
A: Podporu můžete získat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks?**  
A: Ano, dočasné licence jsou k zakoupení [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu najít podrobnou dokumentaci pro Aspose.Tasks?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/tasks/java/).

## Závěr
Podle těchto kroků **nyní víte, jak použít Aspose.Tasks k extrahování informací o kalendáři projektu** z souboru MS Project pomocí Javy. Můžete tuto logiku integrovat do větších aplikací, automatizovat reportování nebo synchronizovat plány s jinými podnikovými systémy. Pamatujte, že zvládnutí **how to use aspose** otevírá dveře k mnoha pokročilým scénářům automatizace řízení projektů.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}