---
date: 2025-12-21
description: Naučte se, jak v Javě vytvořit SVG ze souborů MPP a uložit projekt jako
  SVG pomocí knihovny Aspose.Tasks. Průvodce krok za krokem s ukázkami kódu.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak vytvořit SVG z MPP v Javě pomocí Aspose.Tasks
url: /cs/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit SVG z MPP v Javě

## Úvod
V tomto tutoriálu se naučíte, jak **vytvořit SVG z MPP** souborů pomocí Aspose.Tasks pro Javu. Převod souboru Microsoft Project (MPP) na škálovatelnou vektorovou grafiku (SVG) vám umožní vložit vysoce kvalitní, rozlišením nezávislé diagramy přímo do webových stránek, reportů nebo dashboardů. Provedeme vás potřebným nastavením, ukážeme přesný kód, který potřebujete, a vysvětlíme každý krok, abyste mohli sebejistě **uložit projekt jako SVG** ve svých aplikacích.

## Rychlé odpovědi
- **Co znamená „vytvořit SVG z MPP“?**  
  Převádí soubor Microsoft Project (.mpp) do SVG obrázku, který lze zobrazit v libovolném prohlížeči bez ztráty kvality.  
- **Která knihovna provádí převod?**  
  Aspose.Tasks pro Javu poskytuje jednorázovou metodu `save`, která převod provede.  
- **Potřebuji licenci?**  
  Pro komerční použití je vyžadována dočasná licence; k dispozici je také bezplatná zkušební verze.  
- **Jaké jsou předpoklady?**  
  Java JDK 8+ a Aspose.Tasks pro Javu JAR.  
- **Jak dlouho převod trvá?**  
  Obvykle méně než sekundu pro standardní soubory projektů.

## Co je „vytvořit SVG z MPP“?
Vytvoření SVG z MPP souboru znamená export vizuální reprezentace harmonogramu projektu – úkolů, časových os a zdrojů – do formátu Scalable Vector Graphics. SVG je založeno na XML, je lehké a dokonale se škáluje na displejích s vysokým rozlišením.

## Proč použít Aspose.Tasks k uložení projektu jako SVG?
- **Není vyžadována instalace Microsoft Project** – knihovna funguje samostatně.  
- **Plná věrnost** – grafy, Ganttovy pruhy a milníky si zachovávají své styly.  
- **Cross‑platform** – kód lze spustit na Windows, Linuxu i macOS.  
- **Jednoduchá integrace** – jednorázové volání API se přirozeně vejde do existujících Java pipeline.

## Předpoklady
- **Java Development Kit (JDK)** – verze 8 nebo novější. Stáhněte z webu Oracle.  
- **Aspose.Tasks pro Javu** – získáte knihovnu na oficiální stránce ke stažení **[zde](https://releases.aspose.com/tasks/java/)**.  

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Importní blok zůstává nezměněn.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Krok 1: Definujte adresář s daty
Určete, kde se nachází váš zdrojový MPP soubor a kam bude zapsáno SVG.

```java
String dataDir = "Your Data Directory";
```

> **Tip:** Použijte absolutní cestu nebo cestu relativní k adresáři zdrojů vašeho projektu, aby nedošlo k `FileNotFoundException`.

## Krok 2: Načtěte MPP soubor
Vytvořte instanci `Project` načtením existujícího souboru Microsoft Project.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Tento řádek načte *HomeMovePlan.mpp* ze složky, kterou jste definovali výše.

## Krok 3: Uložte projekt jako SVG
Nyní můžete **uložit projekt jako SVG** jediným příkazem.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metoda zapíše `project5.svg` do stejného adresáře. Výsledné SVG lze otevřít v libovolném moderním prohlížeči nebo vložit přímo do HTML.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|---------|-------|--------|
| **Soubor nenalezen** | Nesprávná cesta `dataDir` | Ověřte, že řetězec adresáře končí oddělovačem (`/` nebo `\\`). |
| **Prázdný SVG výstup** | Projekt načten bez pohledů | Ujistěte se, že MPP soubor obsahuje Ganttův pohled před uložením. |
| **Výjimka licence** | Žádná platná licence nebyla použita | Aplikujte dočasnou licenci pomocí `License.setLicense("path/to/license.xml")` před voláním `save`. |

## Často kladené otázky

**Q: Je Aspose.Tasks pro Javu kompatibilní se všemi verzemi souborů Microsoft Project?**  
A: Ano, podporuje formáty MPP, MPT i XML od starších po nejnovější verze Projectu.

**Q: Mohu přizpůsobit vzhled výstupního SVG?**  
A: Rozhodně. Použijte `SvgOptions` k nastavení fontů, barev a možností rozvržení před voláním `save`.

**Q: Vyžaduje Aspose.Tasks pro Javu licenci pro komerční použití?**  
A: Ano, pro produkční nasazení je nutná platná licence. Dočasnou licenci získáte **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Můžu si Aspose.Tasks pro Javu vyzkoušet před zakoupením?**  
A: Ano, k dispozici je bezplatná zkušební verze **[zde](https://purchase.aspose.com/buy)**.

**Q: Kde mohu získat podporu pro Aspose.Tasks pro Javu?**  
A: Navštivte komunitní fórum **[zde](https://forum.aspose.com/c/tasks/15)**, kde můžete klást otázky a sdílet zpětnou vazbu.

## Závěr
Nyní víte, jak **vytvořit SVG z MPP** souborů v Javě a efektivně **uložit projekt jako SVG** pomocí Aspose.Tasks. Tato schopnost vám umožní integrovat bohaté vizualizace projektů do webových portálů, reportovacích dashboardů nebo kamkoli, kde jsou potřeba škálovatelné grafiky. Experimentujte s `SvgOptions` pro doladění výstupu a budete mít výkonný nástroj ve svém vývojářském arzenálu.

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.Tasks pro Javu 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}