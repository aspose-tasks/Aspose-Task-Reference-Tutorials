---
date: 2026-03-27
description: Naučte se, jak exportovat MPP do SVG v Javě s Aspose.Tasks. Průvodce
  krok za krokem, ukázky kódu a tipy, jak rychle uložit projekt jako SVG.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak exportovat MPP do SVG v Javě pomocí Aspose.Tasks
url: /cs/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak exportovat MPP do SVG v Javě

## Export MPP do SVG – Úvod
V tomto tutoriálu se naučíte, jak **exportovat MPP do SVG** soubory pomocí Aspose.Tasks for Java. Převod souboru Microsoft Project (MPP) na obrázek Scalable Vector Graphics (SVG) vám umožní vložit vysoce kvalitní, rozlišením nezávislé diagramy přímo do webových stránek, reportů nebo dashboardů. Provedeme vás potřebným nastavením, ukážeme přesný kód, který potřebujete, a vysvětlíme každý krok, abyste mohli sebejistě **uložit projekt jako SVG** ve svých aplikacích.

## Rychlé odpovědi
- **Co znamená „export MPP do SVG“?**  
  Převádí soubor Microsoft Project (.mpp) na SVG obrázek, který lze zobrazit v libovolném prohlížeči bez ztráty kvality.  
- **Která knihovna provádí konverzi?**  
  Aspose.Tasks for Java poskytuje jednorázovou metodu `save` pro provedení konverze.  
- **Potřebuji licenci?**  
  Pro komerční použití je vyžadována dočasná licence; k dispozici je bezplatná zkušební verze.  
- **Jaké jsou předpoklady?**  
  Java JDK 8+ a Aspose.Tasks for Java JAR.  
- **Jak dlouho trvá konverze?**  
  Obvykle méně než sekunda pro standardní projektové soubory.

## Co je „export MPP do SVG“?
Exportování MPP do SVG znamená převést vizuální reprezentaci harmonogramu projektu — úkoly, časové osy a zdroje — do SVG souboru. SVG je XML‑založený, lehký a dokonale se škáluje na displejích s vysokým rozlišením.

## Proč exportovat MPP do SVG pomocí Aspose.Tasks?
- **Instalace Microsoft Project není vyžadována** – knihovna funguje samostatně.  
- **Plná věrnost** – grafy, Ganttovy pruhy a milníky zachovávají své styly.  
- **Cross‑platform** – kód lze spustit na Windows, Linuxu nebo macOS.  
- **Jednořádkové API** – jediným voláním uložíte projekt jako SVG, což se přirozeně začlení do existujících Java pipeline.

## Předpoklady
- **Java Development Kit (JDK)** – verze 8 nebo novější. Stáhněte z webu Oracle.  
- **Aspose.Tasks for Java** – získáte knihovnu z oficiální stránky ke stažení **[zde](https://releases.aspose.com/tasks/java/)**.  

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
Určete, kde se nachází váš zdrojový soubor MPP a kam bude SVG zapsáno.

```java
String dataDir = "Your Data Directory";
```

> **Tip:** Použijte absolutní cestu nebo cestu relativní k adresáři resources vašeho projektu, abyste se vyhnuli `FileNotFoundException`.

## Krok 2: Načtěte soubor MPP
Vytvořte instanci `Project` načtením existujícího souboru Microsoft Project.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Tento řádek načte *HomeMovePlan.mpp* z adresáře, který jste definovali dříve.

## Krok 3: Uložte projekt jako SVG
Nyní můžete **exportovat MPP do SVG** jedním příkazem.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metoda zapíše `project5.svg` do stejného adresáře. Výsledný SVG lze otevřít v libovolném moderním prohlížeči nebo vložit přímo do HTML.

## Běžné případy použití
- **Projektové dashboardy** – vložte živé Ganttovy diagramy do webových portálů, aniž by klient musel instalovat Microsoft Project.  
- **Automatizované reportování** – generujte SVG obrázky za běhu pro PDF nebo HTML zprávy.  
- **Spolupráce napříč týmy** – sdílejte vizuální plán s zainteresovanými, kteří potřebují jen prohlížeč k jeho zobrazení.

## Běžné problémy a řešení

| Problém | Příčina | Řešení |
|-------|--------|-----|
| **Soubor nenalezen** | Nesprávná cesta `dataDir` | Ověřte, že řetězec adresáře končí oddělovačem (`/` nebo `\\`). |
| **Prázdný SVG výstup** | Projekt načten bez pohledů | Ujistěte se, že soubor MPP obsahuje pohled Ganttova diagramu před uložením. |
| **Výjimka licence** | Nebyla použita platná licence | Aplikujte dočasnou licenci pomocí `License.setLicense("path/to/license.xml")` před voláním `save`. |

## Často kladené otázky

**Q: Je Aspose.Tasks for Java kompatibilní se všemi verzemi souborů Microsoft Project?**  
A: Ano, podporuje formáty MPP, MPT a XML od starších po nejnovější verze Projectu.

**Q: Mohu přizpůsobit vzhled SVG výstupu?**  
A: Rozhodně. Použijte `SvgOptions` k nastavení fontů, barev a možností rozvržení před voláním `save`.

**Q: Vyžaduje Aspose.Tasks for Java licenci pro komerční použití?**  
A: Ano, pro produkční nasazení je vyžadována platná licence. Dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Můžu vyzkoušet Aspose.Tasks for Java před zakoupením?**  
A: Ano, k dispozici je bezplatná zkušební verze **[zde](https://purchase.aspose.com/buy)**.

**Q: Kde mohu získat podporu pro Aspose.Tasks for Java?**  
A: Navštivte komunitní fórum **[zde](https://forum.aspose.com/c/tasks/15)**, kde můžete klást otázky a sdílet zpětnou vazbu.

## Závěr
Nyní víte, jak **exportovat MPP do SVG** v Javě a efektivně **uložit projekt jako SVG** pomocí Aspose.Tasks. Tato funkce vám umožní integrovat bohaté vizualizace projektů do webových portálů, reportovacích dashboardů nebo kamkoli, kde jsou potřeba škálovatelné grafiky. Experimentujte s `SvgOptions`, abyste výstup doladili, a budete mít výkonný nástroj ve svém vývojovém arzenálu.

---

**Poslední aktualizace:** 2026-03-27  
**Testováno s:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}