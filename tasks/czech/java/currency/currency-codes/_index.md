---
date: 2025-12-09
description: Naučte se, jak číst soubor MS Project a efektivně spravovat měnové kódy
  pomocí Aspose.Tasks pro Javu. Zjednodušte své úkoly projektového řízení bez námahy.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak číst soubor MS Project a spravovat kódy měn pomocí Aspose.Tasks
url: /cs/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst soubor MS Project a spravovat kódy měn pomocí Aspose.Tasks

## Úvod
Vítejte! V tomto tutoriálu objevíte **jak číst soubor MS Project** a konkrétně **spravovat kódy měn** pomocí Aspose.Tasks Java API. Ať už vytváříte zprávy, konsolidujete projekty s více měnami, nebo jen potřebujete zajistit, aby se zobrazovaly správné finanční symboly, tento průvodce vás provede každým krokem – od nastavení prostředí až po programové získání kódu měny. Na konci budete pohodlně číst soubory MS Project a získávat potřebné informace o měně.

## Rychlé odpovědi
- **Co API dělá?** Čte soubory MS Project a zpřístupňuje vlastnosti jako kód měny.  
- **Jaký jazyk se používá?** Java, prostřednictvím knihovny Aspose.Tasks pro Java.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu získat kód v jednom řádku?** Ano—`prj.get(Prj.CURRENCY_CODE)` vrací řetězec s kódem měny.  
- **Je kompatibilní se všemi verzemi Project?** Aspose.Tasks podporuje jak starší (MPP), tak novější (XML, XER) formáty.

## Co je **read ms project file**?
Čtení souboru MS Project znamená programově otevřít projektový dokument *.mpp* (nebo jiný podporovaný) a přistupovat k jeho datovým strukturám – úkolům, zdrojům, kalendářům a finančním nastavením – bez ruční interakce s Microsoft Project.

## Proč použít Aspose.Tasks k **read msproject** souborům?
- **Kompletní podpora formátů** – funguje se soubory od Project 98 až po nejnovější vydání Office.  
- **Není potřeba COM ani instalace Office** – čistě Java, ideální pro automatizaci na serveru.  
- **Bohaté API** – poskytuje přímý přístup k vlastnostem jako `Prj.CURRENCY_CODE`, což vám umožní **how to retrieve currency** informace okamžitě.  
- **Výkon** – lehké parsování, ideální pro dávkové zpracování mnoha projektů.

## Požadavky
Před tím, než se ponoříme do kódu, ujistěte se, že máte následující:

### Nainstalovaný Java Development Kit (JDK)
Ujistěte se, že na vašem počítači je k dispozici aktuální JDK. Můžete si stáhnout a nainstalovat nejnovější verzi JDK z [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Knihovna Aspose.Tasks pro Java
Stáhněte a nastavte knihovnu Aspose.Tasks pro Java. Podrobná dokumentace a nejnovější binární soubory jsou k dispozici [zde](https://reference.aspose.com/tasks/java/).

## Import balíčků
Abychom mohli začít, naimportujme potřebné balíčky ve vašem Java projektu:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Krok 1: Nastavte adresář s daty
Definujte složku, která obsahuje váš *.mpp* soubor. Upravit cestu tak, aby odpovídala vašemu prostředí.
```java
String dataDir = "Your Data Directory";
```

### Krok 2: Načtěte soubor projektu
Vytvořte instanci `Project` načtením souboru MS Project. Toto je okamžik, kdy **read msproject** data načtete do paměti.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Krok 3: Získejte kód měny
Nyní, když je projekt načten, můžete **how to retrieve currency** informace získat jediným voláním. Toto demonstruje použití **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Výstup bude třípísmenný ISO kód měny (např. `USD`, `EUR`, `GBP`), který je v projektu nastaven.

### Krok 4: (Volitelné) Použijte kód měny
Možná budete chtít získaný kód použít jinde – například pro formátování nákladových hodnot v vlastním reportu nebo pro předání finančnímu API. Zde je rychlá ilustrace (není potřeba další blok kódu):
- Uložte kód do proměnné.  
- Použijte jej při vytváření peněžních řetězců.  
- Předávejte jej downstream službám, které vyžadují identifikátor měny.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Null output** | Soubor projektu nedefinuje měnu (výchozí je prázdná). | Nastavte měnu v Microsoft Project nebo ji přiřaďte pomocí `prj.set(Prj.CURRENCY_CODE, "USD");` před čtením. |
| **File not found** | Nesprávná cesta `dataDir`. | Ověřte cestu a ujistěte se, že název souboru je přesně stejný, včetně velikosti písmen. |
| **Unsupported file version** | Velmi starý nebo poškozený *.mpp* soubor. | Použijte nejnovější verzi Aspose.Tasks nebo nejprve soubor v Microsoft Project převěďte do novějšího formátu. |

## Často kladené otázky

**Q: Dokáže Aspose.Tasks zvládnout složité struktury projektů?**  
A: Ano, API může číst a manipulovat s víceúrovňovými hierarchiemi úkolů, zdrojovými fondy a vlastními poli bez problémů.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů MS Project?**  
A: Rozhodně. Podporuje MPP, XML, XER a další formáty napříč mnoha vydáními Microsoft Project.

**Q: Poskytuje Aspose.Tasks dokumentaci a podporu?**  
A: Komplexní dokumentace, ukázky kódu a dedikovaná podpora jsou k dispozici na webu Aspose.

**Q: Mohu vyzkoušet Aspose.Tasks před zakoupením?**  
A: Ano, je k dispozici bezplatná zkušební verze, abyste mohli vyhodnotit všechny funkce, včetně čtení kódů měn.

**Q: Kde mohu získat dočasné licence pro Aspose.Tasks?**  
A: Dočasné licence lze získat na [webu](https://purchase.aspose.com/temporary-license/) pro krátkodobé hodnocení.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-09  
**Testováno s:** Aspose.Tasks for Java (nejnovější verze)  
**Autor:** Aspose