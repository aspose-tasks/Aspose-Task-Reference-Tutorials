---
date: 2026-01-28
description: Naučte se, jak vytvořit projektový kalendář v Aspose, definovat pracovní
  dny pro výjimky v kalendáři a spravovat rozvrh nepracovních dnů pomocí Aspose.Tasks
  pro Javu.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Vytvořit kalendář projektu Aspose – Definovat pracovní dny pro výjimky kalendáře
url: /cs/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření projektového kalendáře Aspose – Definování pracovních dnů pro výjimky v kalendáři

### Úvod
Když potřebujete **create project calendar aspose**, musíte být schopni modelovat nestandardní pracovní dny, jako jsou svátky, speciální směny nebo dočasné zavírky. Aspose.Tasks pro Java vám poskytuje plnou kontrolu nad definicemi kalendářů, což vám umožní přidávat výjimky, které odrážejí reálné plány. V tomto tutoriálu projdeme přesné kroky k definování pracovních dnů pro výjimky v kalendáři, aby vaše projektové časové osy zůstaly přesně a spolehlivě. Na konci také uvidíte, jak to zapadá do širší strategie **plán nepracovních dnů** pro jakýkoli podnikový projekt.

## Rychlé odpovědi
- **Co znamená „vytvořit kalendář projektu aspose“?** 
Odkazuje na použití Aspose.Tasks k vytvoření vlastního kalendářového objektu, který řídí plánování úkolů.
- **Potřebuji licenci pro spuštění ukázky?** 
Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.
- **Jaká IDE jsou podporována?** 
IntelliJ IDEA, Eclipse, NetBeans nebo jakékoli IDE podporující Java8+.
- **Mohu přidat více výjimek do stejného kalendáře?** 
Ano – můžete přidat libovolný počet objektů `CalendarException`.
- **Do jakých formátů mohu projekt uložit?** 
XML, MPP a několik dalších formátů podporovaných Aspose.Tasks.

## Co je projektový kalendář v Aspose.Tasks?
Projektový kalendář definuje pracovní dny a hodiny pro projekt. Ovlivňuje datum zahájení/ukončení úkolů, přidělování zdrojů a celkové výpočty harmonogramu. Přizpůsobením kalendáře zajistíte, že plán respektuje reálná omezení, jako jsou firemní svátky nebo politika práce o víkendech.

## Proč definovat pracovní dny pro výjimky kalendáře?
- **Přesné časové osy:** Úkoly nebudou naplánovány na označené dny jako nepracovní.
- **Plánování zdrojů:** Zdroje jsou přidělovány pouze v platných pracovních dnech.
- **Soulad:** Harmonogramy projektů jsou v souladu s firemními politikami nebo zákonnými svátky.

## Plán nepracovních dnů s kalendářními výjimkami
Pokud spravujete **plán pracovních dnů**, obvykle máte hlavní seznam svátků, údržbových oken nebo jiného období výpadku. Přidáním těchto dat jako objektů `CalendarException` zajistíte, že každý výpočet – ať už jde o analýzu kritické cesty nebo vyrovnání zdrojů – automaticky respektuje tato omezení. Tento přístup spíše ruční úpravy dat a snížení rizika v harmonogramu.

## Předpoklady
Než začnete, se, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo novější.
2. **Aspose.Tasks for Java** – stáhněte si z oficiální [Stránka ke stažení Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans nebo jakýkoli editor kompatibilní s Javou.

## Jak vytvořit projektový kalendář aspose – Definujte pracovní dny pro výjimky kalendáře

### Průvodce krok za krokem

### Krok 1: Importujte požadované balíčky
Potřebujeme základní třídy Aspose.Tasks a Java `GregorianCalendar` pro práci s daty.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Krok 2: Definování datového adresáře
Určete, kam bude vygenerovaný soubor projektu uložen.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Vytvoření instance projektu
Vytvořte novou instanci objektu `Project` – jedná se o kontejner pro všechna projektová data, včetně kalendářů.

```java
Project project = new Project();
```

### Krok 4: Definování kalendáře
Přidejte do projektu vlastní kalendář. Tento kalendář bude obsahovat naše výjimky.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Krok 5: Definování výjimky pro dny v týdnu
Vytvořte `CalendarException`, který označí rozsah dnů (např. poslední týden prosince) jako nepracovní.  
Příklad nastavuje výjimku od **24 Dec 2009** do **31 Dec 2009**, zakazuje práci v těchto dnech a považuje výjimku za denní typ.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Krok 6: Uložení projektu
Uložte projekt, včetně vlastního kalendáře a jeho výjimky, do souboru XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Běžné problémy a řešení
| Problém | Řešení |
|---------|--------|
| **Datumy výjimek nejsou aplikovány** | obvykle se, že je voláno `setEnteredByOccurrences(false)` a že hodnoty `FromDate/ToDate` jsou správné. |
| **Uložený soubor je prázdný** | Ověřte, že `dataDir` ukazuje na zapisovatelnou složku a že název souboru končí na `.xml`. |
| **Kalendář se nepromítá do plánování úkolů** | Přiřaďte kalendář úkolům nebo zdrojům pomocí `task.setCalendar(cal)` nebo `resource.setCalendar(cal)`. |

## Často kladené otázky

**Q: Mohu definovat více výjimek pro různé pracovní dny ve stejném kalendáři?**
A: Ano. Přidejte další objekty `CalendarException` do `cal.getExceptions()` pro každé samostatné období nebo pravidlo.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými Java IDE?**
A: Rozhodně. Knihovna funguje s IntelliJ IDEA, E, NetBeans podporujecli a IDE, které standardní Java projekty.

**O: Mohu přizpůsobit typy výjimek jiných než denní výjimky?**
A: Ano. Použijte `CalendarExceptionType.Weekly`, `Monthly` nebo `Yearly` podle plánování vašich potřeb.

**Q: Jak mohu dynamicky zpracovávat výjimku na základě požadavků projektu?**
A: Vytvářejte objekty výjimek programově – např. načtěte data svátků z databáze nebo konfiguračního souboru a v cyklu zkontrolujte instanci `CalendarException`.

**Otázka: Je k dispozici zkušební verze Aspose.Tasks pro Java?**
Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z [Stránka stahování Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Závěr
Počítejte s provedením těchto kroků nyní víte, jak **create project calendar aspose** a definovat výjimečné pracovní dny, které přesně odrážejí svátky nebo speciální nepracovní období. Správná konfigurace kalendáře je nezbytná pro realistické harmonogramy, přidělování zdrojů a celkový úspěch projektu. Dále můžete připojit vlastní kalendář k úkolům nebo zdrojům a experimentovat s dalšími typy výjimek a vytvořit tak komplexní **non‑working days schedule** pro jakýkoli projekt.

---

**Poslední aktualizace:** 28. 1. 2026
**Testováno s:** Aspose.Tasks for Java 24.11
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}