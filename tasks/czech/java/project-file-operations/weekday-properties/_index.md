---
date: 2026-03-29
description: Naučte se, jak změnit počet dní v měsíci a spravovat další vlastnosti
  pracovních dnů v Aspose.Tasks pro Javu. Přizpůsobte počáteční dny týdne, upravte
  kalendář projektu a uložte projekt jako XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Změňte dny v měsíci pomocí vlastností Weekday v Aspose.Tasks
url: /cs/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změna počtu dnů v měsíci pomocí vlastností pracovních dnů v Aspose.Tasks

## Úvod
Aspose.Tasks pro Java vám umožňuje **změnit počet dnů v měsíci** a jemně doladit další nastavení pracovních dnů, aniž byste potřebovali nainstalovaný Microsoft Project. Ať už přizpůsobujete kalendář projektu neobvyklému fiskálnímu měsíci nebo jen potřebujete upravit den začátku týdne, tento tutoriál vás provede nejčastějšími scénáři – získáním aktuálního dne začátku týdne, přizpůsobením data začátku týdne, úpravou kalendáře projektu a uložením projektu jako XML.

## Rychlé odpovědi
- **Mohu změnit počet dnů v měsíci?** Ano, použijte `Prj.DAYS_PER_MONTH` na objektu `Project`.  
- **Jak přizpůsobit datum začátku týdne?** Nastavte `Prj.WEEK_START_DAY` na hodnotu `DayType` (např. `DayType.Monday`).  
- **Jaký formát mohu použít pro export projektu?** Příklad ukládá soubor jako XML pomocí `SaveFileFormat.Xml`.  
- **Je licence vyžadována pro produkční použití?** Pro nasazení mimo evaluační režim je potřeba platná licence Aspose.Tasks.  
- **Jaká IDE jsou podporována?** Jakékoli Java IDE, jako IntelliJ IDEA, Eclipse nebo NetBeans, funguje.

## Co znamená „změna počtu dnů v měsíci“ v Aspose.Tasks?
Změna počtu dnů v měsíci znamená aktualizaci vlastnosti `Prj.DAYS_PER_MONTH` instance `Project`. Tato vlastnost říká enginu, kolik pracovních dnů má v každém měsíci zohlednit, což přímo ovlivňuje plánování úkolů a výpočty nákladů.

## Proč upravovat vlastnosti kalendáře projektu?
Přizpůsobení kalendáře projektu – například nastavení jiného dne začátku týdne nebo úprava minut za den – vám pomůže:
- Přizpůsobit plány regionálním pracovním týdnům.  
- Modelovat nestandardní pracovní vzorce (např. 4‑denní týdny).  
- Zajistit přesné reportování pro smlouvy používající vlastní kalendáře.

## Předpoklady
- **Java Development Kit (JDK)** – Nainstalujte nejnovější JDK od Oracle.  
- **Knihovna Aspose.Tasks pro Java** – Stáhněte ji z oficiálního webu [zde](https://releases.aspose.com/tasks/java/).  
- **IDE dle vašeho výběru** – IntelliJ IDEA, Eclipse nebo NetBeans.

## Import balíčků
Nejprve importujte základní třídy Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Načtení souboru projektu
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Tím se načte existující soubor Microsoft Project (`project.mpp`) ze složky, kterou zadáte.

## Krok 2: Zobrazení vlastností pracovních dnů
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Zde získáme a vypíšeme aktuální nastavení pracovních dnů, včetně **dne začátku týdne** a **počtu dnů v měsíci**.

## Krok 3: Nastavení vlastností pracovních dnů
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
V tomto kroku **změníme počet dnů v měsíci** na 24, nastavíme, aby týden začínal v pondělí, a upravíme minuty za den/týden. Tím se ukazuje, jak programově **upravit kalendář projektu**.

## Krok 4: Uložení projektu
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Upravený projekt se uloží pomocí formátu **save project as XML**, což je užitečné pro integraci s dalšími nástroji nebo pro úložiště pod verzovacím systémem.

## Krok 5: Zobrazení výsledku
```java
System.out.println("Process completed Successfully");
```
Jednoduché potvrzení, že operace byly dokončeny bez chyb.

## Jak přizpůsobit datum začátku týdne
Pokud vaše organizace používá kalendář, kde týden začíná nedělí, nahraďte `DayType.Monday` hodnotou `DayType.Sunday`. Používá se stejná vlastnost (`Prj.WEEK_START_DAY`), takže změna je jednoduchá.

## Jak získat den začátku týdne
Můžete kdykoli zavolat `project.get(Prj.WEEK_START_DAY)`, abyste **získali informaci o dni začátku týdne**, jak je ukázáno v kroku 2.

## Jak upravit kalendář projektu
Kromě dne začátku týdne můžete také upravit `Prj.MINUTES_PER_DAY` a `Prj.MINUTES_PER_WEEK`, aby odrážely vlastní pracovní hodiny nebo směnové vzorce.

## Časté problémy a řešení
- **Nesprávná hodnota typu dne** – Ujistěte se, že používáte výčet `DayType` (např. `DayType.Monday`).  
- **Chyby v cestě k souboru** – Ověřte, že `dataDir` končí správným oddělovačem souborů (`/` nebo `\`).  
- **Licence není nastavena** – Pokud vidíte varování o licenci, zaregistrujte svou licenci Aspose.Tasks před vytvořením objektu `Project`.

## Často kladené otázky

**Q: Dokáže Aspose.Tasks pro Java zvládnout složité struktury projektů?**  
A: Ano, Aspose.Tasks pro Java poskytuje komplexní podporu pro snadné zpracování složitých struktur projektů.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Rozhodně, Aspose.Tasks pro Java podporuje různé verze souborů Microsoft Project, což zajišťuje kompatibilitu napříč platformami.

**Q: Mohu integrovat Aspose.Tasks pro Java do svých existujících Java aplikací?**  
A: Ano, Aspose.Tasks pro Java nabízí bezproblémové možnosti integrace, což vám umožní vylepšit vaše Java aplikace výkonnými funkcemi pro řízení projektů.

**Q: Poskytuje Aspose.Tasks pro Java dokumentaci a podporu?**  
A: Ano, můžete získat rozsáhlou dokumentaci a komunitní podporu pro Aspose.Tasks pro Java na jejich [webové stránce](https://releases.aspose.com/).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro Java z jejich [webové stránky](https://reference.aspose.com/tasks/java/) a vyzkoušet funkce před zakoupením.

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** Aspose.Tasks pro Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}