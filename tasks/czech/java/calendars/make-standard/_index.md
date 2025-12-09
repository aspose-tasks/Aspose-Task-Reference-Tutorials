---
date: 2025-12-03
description: Naučte se, jak vytvořit kalendář v Javě pomocí Aspose.Tasks. Tento krok‑za‑krokem
  průvodce vám ukáže, jak vytvořit standardní kalendář MS Project, přidat standardní
  kalendář a efektivně používat Aspose.Tasks.
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak vytvořit kalendář – vytvořit standardní kalendář v Aspose.Tasks
url: /cs/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit kalendář – vytvořit standardní kalendář v Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **jak vytvořit kalendář** objekty pro soubory Microsoft Project pomocí knihovny Aspose.Tasks for Java. Provedeme vás vytvořením standardního kalendáře MS Project, nastavením jako výchozí (standardní) kalendář a uložením souboru projektu. Na konci průvodce budete schopni integrovat vytváření kalendáře do jakéhokoli řešení pro řízení projektů založeného na Javě.

## Rychlé odpovědi
- **Co znamená „standardní kalendář“?** Jedná se o výchozí definici pracovního času, která se používá u úkolů, které neurčují vlastní kalendář.  
- **Která knihovna je vyžadována?** Aspose.Tasks for Java (část „jak použít Aspose“).  
- **Potřebuji licenci?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Jaký formát souboru je vytvořen?** XML‑založený soubor Microsoft Project (`.xml`).  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní kalendář.

## Co je standardní kalendář v Microsoft Project?
**Standardní kalendář** definuje výchozí pracovní dny a hodiny pro projekt. Když přidáte standardní kalendář, všechny úkoly, které nemají přiřazen konkrétní kalendář, budou následovat jeho rozvrh.

## Proč použít Aspose.Tasks k vytvoření kalendáře?
Aspose.Tasks poskytuje čistě Java API, které umožňuje manipulovat se soubory Project bez nutnosti mít nainstalovaný Microsoft Project. To je ideální pro automatizaci na serveru, CI pipeline nebo jakoukoli Java aplikaci, která potřebuje **programově vytvořit MS Project kalendář** objekty.

## Požadavky
Před zahájením se ujistěte, že máte následující:

### Instalace Java Development Kit (JDK)
Nainstalujte nejnovější JDK z webu Oracle nebo z distribuce OpenJDK.

### Knihovna Aspose.Tasks for Java
Stáhněte knihovnu ze [stránky ke stažení](https://releases.aspose.com/tasks/java/). Přidejte JAR do classpath vašeho projektu.

## Import balíčků
Potřebujeme pouze jeden import pro tento tutoriál:

```java
import com.aspose.tasks.*;
```

## Postupný průvodce

### Krok 1: Nastavte adresář dat
Definujte, kam bude vygenerovaný soubor projektu uložen.

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní cestou na vašem počítači (např. `C:/Projects/Output/`).

### Krok 2: Vytvořte instanci projektu
Vytvořte novou, prázdnou instanci objektu Project, která bude obsahovat kalendář.

```java
Project project = new Project();
```

### Krok 3: Definujte a nastavte kalendář jako standardní
Přidejte nový kalendář pojmenovaný **„My Cal“** a povýšte jej na standardní kalendář projektu.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro tip:** Metoda `makeStandardCalendar` automaticky označí předaný kalendář jako výchozí pro projekt, což je přesně to, co potřebujete, když chcete **přidat funkci standardního kalendáře**.

### Krok 4: Uložte projekt
Uložte projekt (včetně nového kalendáře) do XML souboru.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Můžete změnit název souboru nebo formát (`SaveFileFormat.Pp`), pokud preferujete jinou verzi Projectu.

### Krok 5: Zobrazte zprávu o dokončení
Dejte si vizuální indikaci, že proces skončil bez chyb.

```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| **File not found** | `dataDir` ukazuje na neexistující složku | Vytvořte složku nebo použijte absolutní cestu |
| **License exception** | Spouštění bez platné licence Aspose.Tasks v produkci | Načtěte licenční soubor pomocí `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Empty calendar** | Zapomenutí přidat definice pracovního času | Použijte `cal1.getWeekDays().add(WeekDay.DayType.Monday)` atd., pokud potřebujete vlastní hodiny |

## Často kladené otázky

**Q: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?**  
A: Ano, Aspose.Tasks podporuje širokou škálu verzí Microsoft Project, od verze 2000 až po nejnovější vydání.

**Q: Mohu dále přizpůsobit nastavení kalendáře?**  
A: Rozhodně! Můžete měnit pracovní dny, přidávat výjimky a definovat konkrétní pracovní časy pomocí tříd `WeekDay` a `WorkingTime`.

**Q: Je Aspose.Tasks vhodný pro aplikace úrovně podniku?**  
A: Určitě. Knihovna je navržena pro vysoce výkonné, škálovatelné prostředí a nabízí komplexní podporu pro velké soubory Project.

**Q: Poskytuje Aspose.Tasks technickou podporu pro vývojáře?**  
A: Ano, Aspose nabízí vyhrazená fóra, podporu na bázi ticketů a rozsáhlou dokumentaci, která vám pomůže rychle vyřešit jakékoli problémy.

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano, můžete si vyzkoušet bezplatnou zkušební verzi dostupnou na [webu](https://purchase.aspose.com/buy), která vám umožní otestovat všechny funkce před závazným rozhodnutím.

## Závěr
Nyní víte **jak vytvořit kalendář** objekty v Aspose.Tasks pro Java, nastavit je jako standardní kalendář a uložit výsledný soubor Project. Tato schopnost vám umožní automatizovat plánování projektů, vynutit jednotné pracovní časy a integrovat data Microsoft Project přímo do vašich Java aplikací.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-03  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

---