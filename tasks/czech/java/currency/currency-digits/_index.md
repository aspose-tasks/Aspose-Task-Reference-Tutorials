---
date: 2025-12-05
description: Naučte se efektivně pracovat s měnovými číslicemi v MS Project pomocí
  Aspose.Tasks pro Javu. Podrobný návod krok za krokem, který zahrnuje manipulaci
  s projektovými soubory v Javě a načítání souborů MPP.
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zpracujte číslice měny v MS Project pomocí Aspose.Tasks
url: /cs/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zpracování číslic měny v MS Project pomocí Aspose.Tasks

## Úvod
V tomto komplexním tutoriálu objevíte **jak pracovat s hodnotami měny v MS Project** pomocí knihovny Aspose.Tasks pro Javu. Ať už vytváříte nástroj pro reportování, migrační utility, nebo jen potřebujete přečíst nastavení měny z **souboru projektu v Javě**, tento průvodce vás provede každým krokem – od načtení souboru *.mpp* až po získání číslic měny. Na konci budete pohodlně zpracovávat data měny v MS Project ve svých aplikacích.

## Rychlé odpovědi
- **Jaká knihovna čte soubory MS Project?** Aspose.Tasks for Java.  
- **Kolik řádků kódu je potřeba k získání číslic měny?** Pouze tři stručné řádky po načtení projektu.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební ver stačí pro testování; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší (libovolný JDK, který spouští Aspose.Tasks).  
- **Mohu získat i jiné vlastnosti projektu?** Ano – Aspose.Tasks poskytuje kompletní sadu polí projektu (např. datum zahájení, sazby nákladů atd.).

## Co je měna v MS Project?
`ms project currency` označuje číselnou přesnost (počet desetinných míst), kterou Microsoft Project používá při zobrazování peněžních hodnot. Je uložena v souboru projektu jako vlastnost **CURRENCY_DIGITS** a určuje, zda se částky zobrazují jako celá čísla, s jedním desetinným místem, dvěma desetinnými místy atd.

## Proč použít Aspose.Tasks pro zpracování měny v MS Project?
- **Není vyžadována instalace Microsoft Project** – pracujte přímo se soubory *.mpp* na jakékoli platformě podporující Javu.  
- **Silná typová bezpečnost** – API vrací silně typované hodnoty, což snižuje chyby při parsování.  
- **Optimalizovaný výkon** – rychle načtěte velké projekty a extrahujte jen potřebná pole.  
- **Cross‑platform** – běží na Windows, Linuxu nebo macOS bez úprav.

## Předpoklady
Před zahájením se ujistěte, že máte následující:

1. **Java vývojové prostředí** – nainstalovaný a nakonfigurovaný JDK 8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z oficiální stránky: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Základní znalost Javy** – měli byste být schopni vytvořit Java projekt, přidat externí knihovny a spustit `main` metodu.  

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Definice adresáře s daty
Zadejte složku, která obsahuje váš **soubor projektu v Javě** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou, kde se nachází `project.mpp`.

## Krok 2: Načtení souboru MPP  
Nyní uvidíme **jak načíst soubory mpp** pomocí Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Ujistěte se, že název souboru je přesně shodný; jinak bude vyvolána `IOException`.

## Krok 3: Získání číslic měny  
Po načtení projektu je získání **číslic měny v MS Project** jedním řádkem:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Volání vrací `Integer` představující počet desetinných míst (např. `2` pro centy). Hodnota je vytištěna do konzole, ale můžete ji také uložit do proměnné pro další zpracování.

## Časté problémy a tipy
- **Soubor nenalezen** – dvakrát zkontrolujte cestu `dataDir` a ujistěte se, že název souboru je správný, včetně přípony `.mpp`.  
- **Nepodporovaná verze souboru** – Aspose.Tasks podporuje formáty Project 2000‑2024; starší nebo poškozené soubory mohou vyžadovat konverzi.  
- **Licence není nastavena** – během vývoje funguje zkušební verze, ale pro produkci musíte použít platnou licenci, aby se předešlo vodoznakům hodnocení.

## Často kladené otázky

**Q: Může Aspose.Tasks zpracovávat i jiné atributy projektu kromě číslic měny?**  
A: Ano, Aspose.Tasks nabízí širokou škálu funkcí pro manipulaci s různými aspekty souborů projektu, jako jsou úkoly, zdroje a vlastní pole.

**Q: Je Aspose.Tasks vhodný pro aplikace úrovně podniku?**  
A: Rozhodně, Aspose.Tasks je navržen tak, aby splňoval požadavky podnikově úrovňových projektů, poskytuje vysoký výkon a škálovatelnost.

**Q: Podporuje Aspose.Tasks vývoj napříč platformami?**  
A: Ano, můžete použít Aspose.Tasks pro Javu na jakékoli platformě, která podporuje Java Runtime Environment (Windows, Linux, macOS).

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.Tasks?**  
A: Podporu najdete na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2025-12-05  
**Testováno s:** Aspose.Tasks for Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}