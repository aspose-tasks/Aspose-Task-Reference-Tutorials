---
date: 2026-02-05
description: Naučte se, jak přidat svátky do kalendáře, přiřadit kalendář k projektu
  a uložit soubor MS Project jako MPP pomocí Aspose.Tasks pro Javu.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Přidejte svátky do kalendáře a uložte jako MPP pomocí Aspose.Tasks
url: /cs/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání svátků do kalendáře a uložení jako MPP pomocí Aspose.Tasks

## Úvod

V moderním řízení projektů často potřebujete **přidat svátky do kalendáře** souborů, vytvořit **kalendář MS Project** a poté sdílet plán v nativním formátu MPP. Ať už konsolidujete časové osy z více zdrojů nebo migrujete stará data, programové generování kalendáře eliminuje ruční chyby a urychluje dodání. Tento tutoriál vás provede kompletním procesem vytvoření kalendáře v MS Project, jeho přizpůsobení svátky, **přiřazením kalendáře k projektu** a nakonec **převodem projektu na MPP** pomocí Aspose.Tasks Java API.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání svátků do kalendáře, přiřazení kalendáře k projektu a uložení výsledku jako soubor MPP pomocí Aspose.Tasks pro Javu.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší (JDK 8+).  
- **Mohu kalendář přizpůsobit?** Ano – můžete přidávat pracovní časy, výjimky i svátky.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní kalendář.  

## Co je „create calendar MS Project“?

Vytvoření kalendáře MS Project znamená programově definovat pracovní dny, hodiny a výjimky, které řídí plánování úkolů v souboru Microsoft Project. Pomocí Aspose.Tasks můžete **java create project calendar**, upravit jej a uložit změny, aniž byste kdykoli otevírali uživatelské rozhraní Microsoft Project.

## Proč použít Aspose.Tasks pro tento úkol?

- **Plná kompatibilita .NET/Java** – funguje na jakékoli platformě, která podporuje Javu.  
- **Bez COM ani instalace Office** – ideální pro automatizaci na serveru a **automate schedule generation**.  
- **Bohaté API** – podporuje všechny vlastnosti kalendáře, včetně vlastních pracovních týdnů a svátků.  
- **Přímý výstup MPP** – můžete **save project as MPP** bez mezikroků konverze.

## Předpoklady

1. **Java Development Kit (JDK) 8+** – ujistěte se, že `java -version` vrací 1.8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli editor, který preferujete.  
4. **Základní znalost Javy** – povědomí o třídách, metodách a souborovém I/O.

## Jak přidat svátky do kalendáře

Níže procházíme každý krok, od nastavení prostředí až po uložení finálního souboru MPP. Kódové bloky zůstávají beze změny; okolní vysvětlení byla rozšířena pro větší přehlednost.

### Krok 1: Import požadovaných balíčků

Nejprve načtěte třídy Aspose.Tasks a Java utility do rozsahu.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Krok 2: Nastavení adresáře s daty

Definujte, kde budou umístěny vstupní šablony a výstupní soubory. Nahraďte zástupný text skutečnou cestou na vašem počítači.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Definice názvů vstupního a výstupního souboru

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

Pokud potřebujete konkrétní pracovní časy, svátky nebo výjimky, zavolejte vlastní pomocnou metodu. V ukázce slouží jako zástupce `GetTestCalendar`.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Tip:** Můžete přímo manipulovat s `cal1.getWeekDays()` pro nastavení pracovních hodin pro každý den v týdnu, nebo použít `cal1.getExceptions()` k **add holidays to calendar**.

### Krok 6: Přiřazení kalendáře k projektu

Nastavte projekt tak, aby používal nově vytvořený kalendář pro všechny výpočty plánování.

```java
project.set(Prj.CALENDAR, cal1);
```

### Krok 7: Uložení projektu jako MPP

Nyní **convert project to MPP** uložením s volbou `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Krok 8: Potvrzení úspěšného dokončení

Jednoduchá zpráva v konzoli vás informuje, že proces proběhl bez chyb.

```java
System.out.println("Process completed Successfully");
```

## Běžné případy použití

- **Automatizovaná generace plánů** pro opakující se projekty (např. týdenní sprinty).  
- **Migrace starých CSV nebo Excel kalendářů** do plnohodnotného souboru MS Project.  
- **Server‑side reporting**, kde webová služba na požádání vrací soubor MPP.  

## Řešení problémů a běžné úskalí

| Problém | Příčina | Řešení |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` ukazuje na neexistující složku | Ujistěte se, že adresář existuje, nebo jej vytvořte programově. |
| Kalendář se nepoužije u úkolů | Úkoly stále odkazují na výchozí kalendář | Po nastavení `Prj.CALENDAR` také aktualizujte `Task.CALENDAR` u každého úkolu, pokud byl dříve přepsán. |
| Výstupní soubor má 0 KB | Chybějící oprávnění k zápisu | Spusťte JVM s odpovídajícími právy k souborovému systému nebo zvolte zapisovatelnou cestu. |

## Často kladené otázky

**Q: Je Aspose.Tasks for Java kompatibilní s různými verzemi MS Project?**  
A: Ano, Aspose.Tasks for Java podporuje širokou škálu verzí MS Project, od Project 2007 až po nejnovější vydání, což zajišťuje bezproblémovou kompatibilitu.

**Q: Mohu kalendáře přizpůsobit podle konkrétních požadavků projektu?**  
A: Rozhodně. Můžete definovat pracovní dny, nastavit vlastní pracovní týdny, přidat svátky a dokonce vytvořit více kalendářů v jednom souboru projektu.

**Q: Nabízí Aspose.Tasks for Java podporu při řešení problémů a asistenci?**  
A: Ano, můžete získat pomoc na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks for Java?**  
A: Ano, plně funkční bezplatná zkušební verze je k dispozici [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks for Java?**  
A: Dočasné licence lze požádat prostřednictvím webu Aspose [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-02-05  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}