---
date: 2026-01-18
description: Naučte se, jak nastavit standardní sazbu a další vlastnosti zdrojů v
  MS Project pomocí Aspose.Tasks pro Javu, včetně toho, jak přidat zdroj do MS Project
  a efektivně spravovat zdroje.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak nastavit standardní sazbu pro zdroje v Aspose.Tasks
url: /cs/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení standardní sazby pro zdroje v Aspose.Tasks

## Úvod
Pokud vytváříte Java aplikace, které potřebují pracovat se soubory Microsoft Project, **nastavení standardní sazby** pro zdroj je jedním z nejčastějších úkolů. V tomto tutoriálu se naučíte, jak **nastavit standardní sazbu** a další vlastnosti zdroje pomocí Aspose.Tasks pro Java. Na konci průvodce budete schopni vytvořit objekt projektu, přidat zdroj do souboru MS Project a s jistotou spravovat zdroje MS Project.

## Rychlé odpovědi
- **Jaká je hlavní třída pro práci se souborem Project?** `Project`
- **Která metoda přidá nový zdroj?** `project.getResources().add()`
- **Jak nastavit standardní sazbu?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Potřebuji licenci pro produkci?** Ano, je vyžadována platná licence Aspose.Tasks.
- **Která verze Javy je podporována?** Java 8+ (doporučuje se nejnovější JDK).

## Co je „nastavení standardní sazby“?
Operace *nastavení standardní sazby* přiřadí výchozí hodinovou cenu zdroji. Projektoví manažeři tuto hodnotu používají k výpočtu nákladů na práci, generování nákladových zpráv a prognózování rozpočtů.

## Proč nastavovat sazby pomocí Aspose.Tasks?
- **Není potřeba instalace Microsoft Project** – manipulujte se soubory přímo z Javy.
- **Plná věrnost** – všechny pole zdroje, včetně přesčasových a nákladových sazeb, jsou zachována.
- **Cross‑platform** – funguje na Windows, Linuxu i macOS.
- **Přátelské k automatizaci** – ideální pro dávkové zpracování nebo integraci s CI pipeline.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

### Nastavení vývojového prostředí Java
1. Instalace JDK: Ujistěte se, že máte nainstalovaný Java Development Kit (JDK). Můžete jej stáhnout z [webu Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Nastavení IDE: Vyberte si Integrované vývojové prostředí (IDE) jako IntelliJ IDEA, Eclipse nebo NetBeans a nainstalujte jej na svůj počítač.

### Instalace Aspose.Tasks pro Java
1. Stáhněte Aspose.Tasks pro Java: Navštivte [stránku ke stažení](https://releases.aspose.com/tasks/java/) a získejte nejnovější verzi Aspose.Tasks pro Java.
2. Integrace do projektu: Začleňte knihovnu Aspose.Tasks pro Java do svého Java projektu přidáním jako závislost.

## Import balíčků
Pro začátek je potřeba importovat potřebné balíčky z Aspose.Tasks pro Java do vašeho projektu. Tento krok zajistí přístup k požadovaným funkcím.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Krok 1: Vytvoření objektu Project
Vytvoření **objektu projektu** je první krok k jakékoli manipulaci se souborem MS Project. Reprezentuje celý soubor projektu v paměti.

```java
Project project = new Project();
```

## Krok 2: Přidání zdroje (add resource ms project)
Nyní **přidáme zdroj MS Project** pomocí kolekce Resources. Název zdroje může být libovolný, pokud dává smysl vašemu rozvrhu.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Krok 3: Nastavení vlastností zdroje (how to set rates)
Zde **nastavíme standardní sazbu** a také ukážeme, jak nastavit přesčasovou sazbu. Tyto sazby jsou uloženy jako hodnoty `BigDecimal`, aby byla zachována přesnost.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Časté problémy a řešení
| Problém | Proč se to stane | Řešení |
|---------|------------------|--------|
| `NullPointerException` při volání `set` | Zdroj nebyl správně přidán. | Zajistěte, aby `project.getResources().add()` vrátil ne‑null `Resource`. |
| Sazby se v uloženém souboru zobrazují jako 0 | Použití `int` místo `BigDecimal`. | Vždy používejte `BigDecimal.valueOf()` pro peněžní hodnoty. |
| Licence nebyla nalezena | Soubor licence nebyl načten před vytvořením `Project`. | Načtěte licenci (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) na začátku programu. |

## Závěr
Postupným sledováním těchto kroků jste se naučili, jak **vytvořit objekt projektu**, **přidat zdroj MS Project** a **nastavit standardní sazbu** spolu s dalšími vlastnostmi zdroje. To vám umožní automatizovat výpočty nákladů, generovat vlastní zprávy a plně spravovat zdroje MS Project z Javy.

## Často kladené otázky
### Dokáže Aspose.Tasks pro Java zpracovat složité soubory MS Project?
Ano, Aspose.Tasks pro Java je schopno zpracovat širokou škálu formátů souborů MS Project, včetně složitých s rozsáhlými hierarchiemi úkolů.

### Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?
Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro Java [zde](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.Tasks pro Java?
Podporu a diskuze k Aspose.Tasks pro Java naleznete na [fóru podpory](https://forum.aspose.com/c/tasks/15).

### Jak získat dočasnou licenci pro Aspose.Tasks pro Java?
Dočasnou licenci můžete získat na [stránce dočasných licencí](https://purchase.aspose.com/temporary-license/) pro evaluační účely.

### Kde mohu zakoupit licencovanou verzi Aspose.Tasks pro Java?
Licencovanou verzi Aspose.Tasks pro Java můžete zakoupit na [stránce nákupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-18  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose