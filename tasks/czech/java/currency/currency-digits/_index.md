---
date: 2026-02-10
description: Naučte se, jak získat hodnoty měny, číst soubor MS Project a převést
  projektový soubor do Javy pomocí Aspose.Tasks. Krok za krokem průvodce pro extrakci
  čísel měny.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak získat měnu z MS Project pomocí Aspose.Tasks
url: /cs/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak získat měnu z MS Project pomocí Aspose.Tasks

## Úvod
Pokud se zajímáte o **získání informací o měně** z souboru Microsoft Project, jste na správném místě. V tomto komplexním tutoriálu se dozvíte, **jak pracovat s hodnotami měny v ms project** pomocí knihovny Aspose.Tasks pro Java. Ať už vytváříte nástroj pro reportování, migrační utility nebo jen potřebujete přečíst nastavení měny z **java projektového souboru**, tento průvodce vás provede každým krokem – od načtení souboru *.mpp* až po extrakci číslice měny. Na konci budete pohodlně pracovat s daty měny v ms project ve svých aplikacích.

## Rychlé odpovědi
- **Která knihovna čte soubory MS Project?** Aspose.Tasks pro Java.  
- **Kolik řádků kódu je potřeba k získání číslice měny?** Pouze tři stručné řádky po načtení projektu.  
- **Potřebuji licenci pro vývoj?** Pro testování stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší (libovolný JDK, který spouští Aspose.Tasks).  
- **Mohu získat i jiné vlastnosti projektu?** Ano – Aspose.Tasks poskytuje kompletní sadu polí Projektu (např. datum zahájení, sazby nákladů atd.).

## Co je ms project currency?
`ms project currency` označuje číselnou přesnost (počet desetinných míst), kterou Microsoft Project používá při zobrazování peněžních hodnot. Je uložena v souboru Projektu jako vlastnost **CURRENCY_DIGITS** a určuje, zda se částky zobrazují jako celá čísla, s jedním desetinným místem, dvěma desetinnými místy atd.

## Proč použít Aspose.Tasks pro práci s ms project currency?
- **Není potřeba instalace Microsoft Project** – pracujte přímo se soubory *.mpp* na jakékoli platformě podporující Javu.  
- **Silná typová bezpečnost** – API vrací silně typované hodnoty, což snižuje chyby při parsování.  
- **Optimalizovaný výkon** – rychle načtěte velké projekty a extrahujte jen potřebná pole.  
- **Cross‑platform** – běží na Windows, Linuxu i macOS bez úprav.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

1. **Vývojové prostředí Java** – nainstalovaný a nakonfigurovaný JDK 8 nebo novější.  
2. **Aspose.Tasks pro Java** – stáhněte si nejnovější JAR z oficiální stránky: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Základní znalosti Javy** – měli byste být schopni vytvořit Java projekt, přidat externí knihovny a spustit metodu `main`.  

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Definice adresáře s daty
Určete složku, která obsahuje váš **java projektový soubor** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou, kde se nachází `project.mpp`.

## Krok 2: Načtení souboru MPP  
Nyní uvidíme, **jak načíst mpp** soubory pomocí Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Ujistěte se, že název souboru je přesně shodný; jinak bude vyhozena výjimka `IOException`.

## Krok 3: Získání číslice měny  
Po načtení projektu je extrakce **ms project currency** číslice jedním řádkem:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Volání vrací `Integer` představující počet desetinných míst (např. `2` pro centy). Hodnota je vytištěna do konzole, ale můžete ji také uložit do proměnné pro další zpracování.

## Časté problémy a tipy
- **Soubor nenalezen** – dvakrát zkontrolujte cestu `dataDir` a ujistěte se, že název souboru je správný, včetně přípony `.mpp`.  
- **Nepodporovaná verze souboru** – Aspose.Tasks podporuje formáty Project 2000‑2024; starší nebo poškozené soubory mohou vyžadovat konverzi.  
- **Licence není nastavena** – během vývoje stačí zkušební verze, ale pro produkci musíte použít platnou licenci, aby se odstranily vodotiskové značky hodnocení.

## Často kladené otázky

**Q: Dokáže Aspose.Tasks zpracovat jiné atributy Projektu kromě číslice měny?**  
A: Ano, Aspose.Tasks nabízí širokou škálu funkcí pro manipulaci s různými aspekty souborů Projektu, jako jsou úkoly, zdroje a vlastní pole.

**Q: Je Aspose.Tasks vhodný pro podnikovou úroveň aplikací?**  
A: Rozhodně, Aspose.Tasks je navržen tak, aby splňoval požadavky podnikově náročných projektů, poskytuje vysoký výkon a škálovatelnost.

**Q: Podporuje Aspose.Tasks vývoj napříč platformami?**  
A: Ano, můžete použít Aspose.Tasks pro Java na jakékoli platformě, která podporuje Java Runtime Environment (Windows, Linux, macOS).

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.Tasks?**  
A: Podporu najdete na [Aspose.Tasks fóru](https://forum.aspose.com/c/tasks/15).

## Závěr
Nyní víte, **jak získat číslice měny** z souboru MS Project pomocí Aspose.Tasks pro Java. Proces je jednoduchý: načtěte projekt, zavolejte `project.get(Prj.CURRENCY_DIGITS)` a použijte výsledek ve své aplikaci. Klidně prozkoumejte i další vlastnosti projektu stejným způsobem a integrujte tuto logiku do větších řešení pro reportování nebo migraci.

---

**Poslední aktualizace:** 2026-02-10  
**Testováno s:** Aspose.Tasks pro Java (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}