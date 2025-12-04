---
date: 2025-12-03
description: Naučte se, jak vytvořit kalendář v MS Project, převést projekt na MPP
  a snadno uložit projekt MPP pomocí Aspose.Tasks pro Javu.
language: cs
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Vytvořit kalendář MS Project a uložit jako MPP pomocí Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření kalendáře MS Project a uložení jako MPP pomocí Aspose.Tasks

## Úvod

V moderním řízení projektů často potřebujete **vytvořit kalendář MS Project** soubory a poté je sdílet v nativním formátu MPP. Ať už konsolidujete plány z více zdrojů nebo migrujete stará data, schopnost programově generovat kalendář šetří čas a eliminuje ruční chyby. Tento tutoriál vás provede kompletním procesem vytvoření kalendáře v MS Project, jeho přizpůsobení a nakonec **převodu projektu do MPP** pomocí Aspose.Tasks Java API.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Vytvoření kalendáře v MS Project a uložení jako soubor MPP pomocí Aspose.Tasks pro Java.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší (JDK 8+).  
- **Mohu kalendář přizpůsobit?** Ano – můžete přidat pracovní časy, výjimky a svátky.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní kalendář.

## Co je „vytvořit kalendář MS Project“?

Vytvoření kalendáře MS Project znamená programově definovat pracovní dny, hodiny a výjimky, které řídí plánování úkolů v souboru Microsoft Project. Pomocí Aspose.Tasks můžete tyto kalendáře vytvářet, upravovat a ukládat, aniž byste kdykoli otevírali uživatelské rozhraní Microsoft Project.

## Proč použít Aspose.Tasks pro tento úkol?

- **Plná kompatibilita .NET/Java** – funguje na jakékoli platformě, která podporuje Javu.  
- **Není potřeba COM ani instalace Office** – ideální pro server‑side automatizaci.  
- **Bohaté API** – podporuje každou vlastnost kalendáře, včetně vlastních pracovních týdnů a svátků.  
- **Přímý výstup MPP** – můžete **uložit projekt jako MPP** bez mezikrokových konverzí.

## Požadavky

1. **Java Development Kit (JDK) 8+** – ujistěte se, že `java -version` hlásí 1.8 nebo novější.  
2. **Aspose.Tasks pro Java** – stáhněte nejnovější JAR z [Aspose webu](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse nebo libovolný editor, který preferujete.  
4. **Základní znalost Javy** – povědomí o třídách, metodách a souborovém I/O.  

## Postupný návod

### Krok 1: Import požadovaných balíčků

Nejprve načtěte třídy Aspose.Tasks a Java utility do rozsahu.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Krok 2: Nastavení datového adresáře

Definujte, kde budou umístěny vstupní šablony a výstupní soubory. Nahraďte zástupný znak skutečnou cestou na vašem počítači.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Definování názvů vstupních a výstupních souborů

Načteme existující soubor MPP (nebo prázdný projekt) a výsledek zapíšeme do nového souboru.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Krok 4: Načtení projektu a přidání nového kalendáře

Vytvořte instanci `Project` ze zdrojového souboru a přidejte kalendář s názvem **„Calendar 1“**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Krok 5: Přizpůsobení kalendáře (volitelné)

Pokud potřebujete konkrétní pracovní časy, svátky nebo výjimky, zavolejte vlastní pomocnou metodu. V ukázce je jako zástupný znak použita metoda `GetTestCalendar`.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Tip:** Můžete přímo manipulovat s `cal1.getWeekDays()`, abyste nastavili pracovní hodiny pro každý den v týdnu.

### Krok 6: Přiřazení kalendáře k projektu

Řekněte projektu, aby pro všechny výpočty plánování používal nově vytvořený kalendář.

```java
project.set(Prj.CALENDAR, cal1);
```

### Krok 7: Uložení projektu jako MPP

Nyní **převod projektu do MPP** uložením s volbou `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Krok 8: Potvrzení úspěšného dokončení

Jednoduchá zpráva v konzoli vám oznámí, že proces byl dokončen bez chyb.

```java
System.out.println("Process completed Successfully");
```

## Běžné případy použití

- **Automatické generování harmonogramu** pro opakující se projekty (např. týdenní sprinty).  
- **Migrace starých kalendářů CSV nebo Excel** do plně vybaveného souboru MS Project.  
- **Server‑side reportování** kde webová služba na požádání vrací soubor MPP.  

## Řešení problémů a běžné úskalí

| Problém | Příčina | Řešení |
|-------|-------|-----|
| `NullPointerException` při `project.save` | `dataDir` ukazuje na neexistující složku | Ujistěte se, že složka existuje, nebo ji vytvořte programově. |
| Kalendář není aplikován na úkoly | Úkoly stále odkazují na výchozí kalendář | Po nastavení `Prj.CALENDAR` také aktualizujte `Task.CALENDAR` u každého úkolu, pokud byl dříve přepsán. |
| Výstupní soubor má 0 KB | Chybí oprávnění k zápisu | Spusťte JVM s odpovídajícími právy k souborovému systému nebo zvolte zapisovatelnou cestu. |

## Často kladené otázky

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?**  
A: Ano, Aspose.Tasks pro Java podporuje širokou škálu verzí MS Project, od Project 2007 až po nejnovější vydání, což zajišťuje bezproblémovou kompatibilitu.

**Q: Mohu kalendáře přizpůsobit konkrétním požadavkům projektu?**  
A: Rozhodně. Můžete definovat pracovní dny, nastavit vlastní pracovní týdny, přidat svátky a dokonce vytvořit více kalendářů v jednom souboru projektu.

**Q: Nabízí Aspose.Tasks pro Java podporu při řešení problémů a asistenci?**  
A: Ano, můžete získat pomoc na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?**  
A: Ano, plně funkční bezplatná zkušební verze je k dispozici [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Dočasné licence lze požádat prostřednictvím webu Aspose [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2025-12-03  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}