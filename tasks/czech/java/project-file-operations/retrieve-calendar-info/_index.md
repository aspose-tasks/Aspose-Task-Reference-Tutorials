---
date: 2025-12-20
description: Naučte se, jak pomocí Aspose.Tasks získat podrobnosti kalendáře projektu
  z Microsoft Project souborů pomocí Javy. Podrobný návod krok za krokem s ukázkami
  kódu.
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
V tomto tutoriálu **objevíte, jak použít Aspose.Tasks** k programatickému získání informací o kalendáři ze souborů Microsoft Project. Přístup k datům kalendáře, jako jsou pracovní dny, hodiny a výjimky, je nezbytný, když potřebujete **extrahovat kalendář projektu** pro reportování, integraci nebo vlastní plánovací logiku. Projděme si proces krok za krokem.

## Rychlé odpovědi
- **Jaká knihovna se v tomto tutoriálu používá?** Aspose.Tasks pro Java.  
- **Jaké hlavní klíčové slovo je pokryto?** *how to use aspose.tasks*.  
- **Co můžete extrahovat?** Kalendáře projektu, včetně pracovních dnů a hodin.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.

## Proč extrahovat informace o kalendáři projektu?
Kalendáře projektu určují termíny úkolů, přidělení zdrojů a celkové výpočty časové osy. Extrahováním těchto dat můžete:
- Vytvářet vlastní reporty, které odrážejí skutečné pracovní rozvrhy.  
- Synchronizovat časové osy Microsoft Project s externími systémy (ERP, BI atd.).  
- Provádět analýzu „co‑kdy“ úpravou nastavení kalendáře programově.

## Předpoklady
Než začneme, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Nainstalovaný Java Development Kit (JDK) na vašem systému.  
- Knihovnu Aspose.Tasks pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/java/).

## Import balíčků
Nejprve importujte potřebné třídy Aspose.Tasks do svého Java projektu.

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

Projekt může obsahovat více kalendářů (standardní, zdrojové a vlastní). Tato kolekce vám umožní přístup k jednotlivým kalendářům.

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

## Závěr
Po absolvování těchto kroků **nyní víte, jak použít Aspose.Tasks k extrakci informací o kalendáři projektu** ze souboru MS Project pomocí Javy. Tento postup můžete začlenit do větších aplikací, automatizovat reportování nebo synchronizovat rozvrhy s jinými podnikovými systémy.

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks podporuje více platforem a programovacích jazyků, včetně .NET, C++, Python a Java.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Ano, bezplatnou zkušební verzi si můžete stáhnout [zde](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.Tasks?**  
A: Podporu můžete získat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks?**  
A: Ano, dočasné licence jsou k dispozici k zakoupení [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu podrobnou dokumentaci pro Aspose.Tasks?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/tasks/java/).

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}