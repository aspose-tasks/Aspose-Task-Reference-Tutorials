---
date: 2026-02-07
description: Naučte se, jak nastavit kód měny v Javě v projektech Aspose.Tasks, změnit
  symbol měny a použít vlastní formát měny pro soubory Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: kód měny java – Jak nastavit v projektech Aspose.Tasks
url: /cs/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit kód měny v Aspose.Tasks – Java průvodce

## Úvod
V tomto tutoriálu se naučíte **jak nastavit kód měny java** pro soubor Microsoft Project pomocí Aspose.Tasks Java API. Ať už potřebujete *změnit měnu* pro mezinárodní týmy, upravit *symbol měny*, nebo použít **vlastní formát měny**, níže uvedené kroky vás provedou procesem s jasnými vysvětleními a připraveným kódem.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Tasks for Java.  
- **Mohu změnit symbol měny?** Ano – použijte `CurrencySymbolPositionType` a `Prj.CURRENCY_SYMBOL`.  
- **Jaké formáty souborů jsou podporovány?** XML, MPP a mnoho dalších přes `SaveFileFormat`.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní nastavení.

## Jak nastavit kód měny Java v Aspose.Tasks
Měna projektu určuje, jak jsou zobrazovány hodnoty nákladů – kód (např. `AUD`), počet desetinných míst, symbol (`$`) a pozice symbolu. Nastavením těchto vlastností zajistíte, že každé pole související s náklady (sazby zdrojů, rozpočty úkolů atd.) bude odrážet správný měnový formát pro vaše publikum.

## Proč použít Aspose.Tasks pro změnu měny?
- **Není potřeba instalace Microsoft Project** – manipulujte se soubory na jakémkoli serveru.  
- **Kompletní pokrytí API** – všechna pole související s měnou jsou zpřístupněna přes konstanty `Prj`.  
- **Cross‑platform** – funguje na Windows, Linuxu a macOS s jakýmkoli Java‑kompatibilním IDE.  
- **Vysoký výkon** – zpracovávejte velké soubory projektů rychle a spolehlivě.  
- **Podporuje vlastní formát měny** – můžete definovat symboly, desetinná místa a jejich umístění podle regionálních standardů.

## Požadavky
Před začátkem se ujistěte, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo vyšší.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA nebo jakýkoli editor, který preferujete.  
4. **Zapisovatelný adresář** – kam bude uložen vygenerovaný soubor projektu.

## Import balíčků
Nejprve importujte třídy, které poskytují přístup k vlastnostem projektu a manipulaci se soubory.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Průvodce krok za krokem

### Krok 1: Definujte adresář s daty
Zadejte složku, která obsahuje vaše zdrojové soubory a kam bude zapisován výstup.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Vytvořte novou instanci Project
Vytvořte novou instanci objektu `Project`. Tento objekt představuje soubor Microsoft Project v paměti.

```java
Project project = new Project();
```

### Krok 3: Nastavte vlastnosti měny
Zde nastavíme podrobnosti **jak nastavit měnu**, jako je kód, počet desetinných míst, symbol a pozice symbolu.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** Pokud potřebujete **změnit měnu projektu** pro existující soubor, jednoduše jej načtěte pomocí `new Project("file.mpp")` před aplikací výše uvedených nastavení.

### Krok 4: Uložte aktualizovaný projekt
Zapište projekt zpět na disk v požadovaném formátu. V tomto příkladu používáme formát XML, ale můžete také zvolit `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Krok 5: Potvrďte úspěch
Vytiskněte přátelskou zprávu, abyste věděli, že operace byla dokončena bez chyb.

```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **`NullPointerException` při `project.save`** | `dataDir` není platná cesta nebo chybí oprávnění k zápisu. | Ujistěte se, že adresář existuje a váš Java proces má právo zápisu. |
| **Symbol měny se nezobrazuje** | Pozice symbolu je nastavena nesprávně pro vaši lokalitu. | Použijte `CurrencySymbolPositionType.Before`, pokud má symbol předcházet částce. |
| **Soubor projektu se neotevře v MS Project** | Ukládání ve starším formátu s nekompatibilními nastaveními. | Uložte pomocí `SaveFileFormat.MPP` pro plnou kompatibilitu s aktuálními verzemi MS Project. |

## Často kladené otázky

**Q: Mohu nastavit více měn v jednom projektu pomocí Aspose.Tasks?**  
A: Ano, Aspose.Tasks vám umožňuje pracovat s více měnami v jednom souboru projektu nastavením vlastností měny na úrovni zdroje nebo úkolu.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Rozhodně. Knihovna podporuje MPP soubory od Project 2000 až po nejnovější verze, stejně jako XML a další formáty.

**Q: Poskytuje Aspose.Tasks podporu pro vlastní formáty měny?**  
A: Ano, můžete definovat vlastní symboly, desetinná místa a jejich umístění tak, aby vyhovovaly jakýmkoli regionálním požadavkům.

**Q: Můžu integrovat Aspose.Tasks s jinými knihovnami nebo frameworky v Javě?**  
A: Samozřejmě. API je čistě Java, takže funguje hladce se Spring, Hibernate, Maven, Gradle a dalšími ekosystémy.

**Q: Kde mohu najít další podporu nebo pomoc pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro komunitní pomoc, nebo si prostudujte oficiální dokumentaci pro podrobné odkazy na API.

## Závěr
Nyní víte **jak nastavit kód měny java**, jak **změnit hodnoty měny** a jak **změnit symbol měny** pomocí Aspose.Tasks pro Java. Tyto možnosti vám umožní přizpůsobit nákladová data pro globální týmy, generovat zprávy specifické pro konkrétní locale a udržovat soubory projektů konzistentní napříč hranicemi.

---

**Poslední aktualizace:** 2026-02-07  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}