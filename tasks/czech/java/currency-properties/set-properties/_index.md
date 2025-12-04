---
date: 2025-12-04
description: Naučte se, jak nastavit měnu v projektech Aspose.Tasks Java, včetně toho,
  jak změnit měnu a symbol měny v Javě. Jednoduše manipulujte se soubory Microsoft
  Project.
language: cs
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Jak nastavit měnu v projektech Aspose.Tasks – Průvodce pro Javu
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit měnu v projektech Aspose.Tasks – Průvodce pro Java

## Úvod
V tomto tutoriálu se naučíte **jak nastavit měnu** pro soubor Microsoft Project pomocí Aspose.Tasks Java API. Ať už potřebujete *změnit měnu* pro mezinárodní týmy nebo upravit *symbol měny* v Javě, níže uvedené kroky vás provedou procesem s jasnými vysvětleními a připraveným kódem.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Tasks for Java.  
- **Mohu změnit symbol měny?** Ano – použijte `CurrencySymbolPositionType` a `Prj.CURRENCY_SYMBOL`.  
- **Jaké formáty souborů jsou podporovány?** XML, MPP a mnoho dalších přes `SaveFileFormat`.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní nastavení.

## Co je „měna“ v souboru Project?
Měna projektu určuje, jak jsou zobrazovány hodnoty nákladů — kód (např. `AUD`), počet desetinných míst, symbol (`$`) a pozice symbolu. Nastavením těchto vlastností zajistíte, že každé pole související s náklady (sazby zdrojů, rozpočty úkolů atd.) bude odrážet správný měnový formát pro vaše publikum.

## Proč použít Aspose.Tasks pro změnu měny?
- **Není potřeba instalace Microsoft Project** – manipulujte se soubory na jakémkoli serveru.  
- **Kompletní pokrytí API** – všechna pole související s měnou jsou dostupná přes konstanty `Prj`.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS s jakýmkoli Java‑kompatibilním IDE.  
- **Vysoký výkon** – zpracovávejte velké soubory projektů rychle a spolehlivě.

## Požadavky
Před začátkem se ujistěte, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo vyšší.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA nebo jakýkoli editor, který preferujete.  
4. **Zapisovatelnou složku** – kam bude uložen vygenerovaný soubor projektu.

## Import balíčků
Nejprve importujte třídy, které poskytují přístup k vlastnostem projektu a manipulaci se soubory.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Průvodce krok za krokem

### Krok 1: Definujte adresář dat
Určete složku, která obsahuje vaše zdrojové soubory a kam bude zapisován výstup.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Vytvořte novou instanci projektu
Vytvořte novou instanci objektu `Project`. Tento objekt představuje soubor Microsoft Project v paměti.

```java
Project project = new Project();
```

### Krok 3: Nastavte vlastnosti měny
Zde **nastavíte měnu** – podrobnosti jako kód, počet desetinných míst, symbol a pozice symbolu.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Tip:** Pokud potřebujete **změnit měnu** v existujícím projektu, jednoduše načtěte soubor pomocí `new Project("file.mpp")` před aplikací výše uvedených nastavení.

### Krok 4: Uložte aktualizovaný projekt
Zapište projekt zpět na disk v požadovaném formátu. V tomto příkladu používáme formát XML, ale můžete také zvolit `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Krok 5: Potvrďte úspěch
Vytiskněte přátelskou zprávu, abyste věděli, že operace proběhla bez chyb.

```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|---------|-------|--------|
| **`NullPointerException` při `project.save`** | `dataDir` není platná cesta nebo nemá oprávnění k zápisu. | Ujistěte se, že adresář existuje a váš Java proces má právo zapisovat. |
| Symbol měny se nezobrazuje | Pozice symbolu je nastavena nesprávně pro vaši lokalitu. | Použijte `CurrencySymbolPositionType.Before`, pokud má symbol předcházet částce. |
| Soubor projektu se neotevírá v MS Project | Ukládání ve starším formátu s nekompatibilními nastaveními. | Uložte pomocí `SaveFileFormat.MPP` pro plnou kompatibilitu s aktuálními verzemi MS Project. |

## Často kladené otázky

**Q: Mohu nastavit více měn v jednom projektu pomocí Aspose.Tasks?**  
A: Ano, Aspose.Tasks vám umožňuje pracovat s více měnami v jednom souboru projektu nastavením vlastností měny na úrovni jednotlivých zdrojů nebo úkolů.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Rozhodně. Knihovna podporuje MPP soubory od Project 2000 až po nejnovější vydání, stejně jako XML a další formáty.

**Q: Poskytuje Aspose.Tasks podporu pro vlastní formáty měny?**  
A: Ano, můžete definovat vlastní symboly, počet desetinných míst a pozicování tak, aby vyhovovaly jakýmkoli regionálním požadavkům.

**Q: Mohu integrovat Aspose.Tasks s dalšími knihovnami nebo frameworky v Javě?**  
A: Samozřejmě. API je čistě Java, takže funguje hladce se Spring, Hibernate, Maven, Gradle a dalšími ekosystémy.

**Q: Kde mohu najít další podporu nebo pomoc pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro komunitní pomoc nebo si prostudujte oficiální dokumentaci pro podrobné reference API.

## Závěr
Nyní víte **jak nastavit měnu**, jak **změnit hodnoty měny** a jak **změnit symbol měny v Javě** pomocí Aspose.Tasks pro Java. Tyto možnosti vám umožní přizpůsobit nákladová data pro globální týmy, generovat zprávy specifické pro konkrétní lokalitu a udržet vaše soubory projektů konzistentní napříč hranicemi.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}