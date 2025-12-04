---
date: 2025-12-04
description: Naučte se, jak číst vlastnosti měny v Javě ze souborů MS Project pomocí
  Aspose.Tasks pro Javu. Postupujte podle tohoto krok‑za‑krokem průvodce a programově
  extrahujte kód měny, symbol, počet desetinných míst a pozici.
language: cs
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Čtení měnových vlastností v Javě s projekty Aspose.Tasks
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení měnových vlastností Java s projekty Aspose.Tasks

## Úvod
V tomto tutoriálu **číst měnové vlastnosti Java** z Microsoft Project souborů pomocí Aspose.Tasks for Java API. Aspose.Tasks vám umožní pracovat se soubory .mpp bez nutnosti mít nainstalovaný Microsoft Project, což je ideální pro automatizované reportování, migraci dat nebo integraci do Java‑založených podnikových aplikací. Na konci tohoto průvodce budete schopni přímo ze souboru projektu získat kód měny, symbol, počet desetinných míst a pozici symbolu.

## Rychlé odpovědi
- **Co znamená “read currency properties java”?** Odkazuje na získávání metadat souvisejících s měnou (kód, symbol, číslice, pozice) z souboru MS Project pomocí Java kódu.  
- **Potřebuji licenci k vyzkoušení?** K dispozici je bezplatná zkušební verze Aspose.Tasks; pro produkční použití je vyžadována komerční licence.  
- **Jaká verze JDK je vyžadována?** Java 8 nebo novější.  
- **Mohu po načtení měnová nastavení upravit?** Ano, Aspose.Tasks umožňuje jak čtení, tak zápis měnových vlastností.  
- **Je to kompatibilní se všemi verzemi .mpp?** API podporuje soubory vytvořené v Microsoft Project 2003‑2021.

## Co je čtení měnových vlastností v Javě?
Čtení měnových vlastností v Javě znamená přístup k nastavením na úrovni projektu, která určují, jak jsou v Microsoft Project souboru zobrazovány peněžní hodnoty. Tato nastavení zahrnují ISO kód měny (např. **USD**), symbol (**$**), počet desetinných míst a to, zda se symbol zobrazuje před nebo za částkou.

## Proč číst měnové vlastnosti v Javě pomocí Aspose.Tasks?
- **Není potřeba instalace Microsoft Project** – API funguje na jakékoli platformě, která podporuje Javu.  
- **Rychlé, v‑procesové získávání** – ideální pro dávkové zpracování velkého počtu projektových souborů.  
- **Plná kontrola** – můžete získané hodnoty kombinovat s vlastním reportováním nebo je integrovat do ERP systémů.  
- **Podpora napříč verzemi** – funguje se soubory .mpp od Project 2003 až po nejnovější verzi 2021.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK)** – Java 8 nebo novější nainstalované a nakonfigurované ve vašem `PATH`.  
2. **Aspose.Tasks for Java JAR** – stáhněte nejnovější knihovnu z [zde](https://releases.aspose.com/tasks/java/) a přidejte ji do classpath vašeho projektu.  

## Import balíčků
Začněte importováním Aspose.Tasks jmenného prostoru potřebného pro manipulaci s projektem:

```java
import com.aspose.tasks.*;
```

## Krok 1: Nastavte adresář projektu
Definujte složku, která obsahuje soubor `.mpp`, který chcete analyzovat. Uložení cesty do proměnné činí kód znovupoužitelným:

```java
String dataDir = "Your Data Directory";
```

*Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou k složce, kde se nachází `project.mpp`.*

## Krok 2: Vytvořte instanci čtečky projektu
Načtěte soubor Microsoft Project do objektu `Project`. Tento objekt vám poskytne přístup ke všem vlastnostem projektu, včetně měnových nastavení:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Pokud má váš soubor jiný název, změňte `"project.mpp"` podle potřeby.*

## Krok 3: Zobrazte měnové vlastnosti
Nyní načtěte každounovou vlastnost pomocí výčtu `Prj` a vypište výsledky do konzole. API vrací objekty, které můžete převést na řetězce pro zobrazení:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Co uvidíte:**  
- **Currency Code** – ISO‑4217 kód, např. `USD`, `EUR`, `JPY`.  
- **Currency Digits** – obvykle `2` pro většinu měn, `0` pro japonský jen.  
- **Currency Symbol** – znak zobrazovaný v reportech (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` pro **před** částkou, `1` pro **za** částkou.

## Krok 4: Dokončení procesu
Signalizujte, že extrakce úspěšně skončila. Tato jednoduchá zpráva je užitečná, když kód běží jako součást větší dávkové úlohy:

```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` cesta je nesprávná nebo je špatně napsán název souboru. | Ověřte řetězec adresáře a ujistěte se, že soubor `.mpp` existuje na zadaném umístění. |
| **NullPointerException on `project.get(...)`** | Soubor projektu neobsahuje měnové informace (nepravděpodobné) nebo je špatný klíč vlastnosti. | Použijte `project.contains(Prj.CURRENCY_CODE)` k ověření existence před čtením. |
| **LicenseException** | Spuštění bez platné licence Aspose.Tasks v produkčním prostředí. | Aplikujte licenční soubor pomocí `License license = new License(); license.setLicense("Aspose.Tasks.lic");` před vytvořením objektu `Project`. |

## Často kladené otázky

**Q: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?**  
A: Aspose.Tasks podporuje soubory .mpp generované v Microsoft Project 2003‑2021, pokrývající jak starší, tak nejnovější formáty.

**Q: Mohu pomocí Aspose.Tasks měnit měnové vlastnosti?**  
A: Ano, můžete jak číst, tak zapisovat měnová nastavení. Použijte `project.set(Prj.CURRENCY_CODE, "EUR");` a poté projekt uložte.

**Q: Je Aspose.Tasks vhodný pro komerční použití?**  
A: Rozhodně. Jedná se o komerční knihovnu; licenci můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Nabízí Aspose.Tasks bezplatnou zkušební verzi?**  
A: Ano, plně funkční zkušební verze je k dispozici [zde](https://releases.aspose.com/).

**Q: Kde mohu získat pomoc nebo podporu pro Aspose.Tasks?**  
A: Oficiální fórum Aspose.Tasks je nejlepší místo pro asistenci – navštivte jej [zde](https://forum.aspose.com/c/tasks/15).

## Závěr
Nyní jste se naučili, jak **číst měnové vlastnosti Java** z MS Project souboru pomocí Aspose.Tasks for Java. Tato schopnost vám umožní začlenit měnová metadata do vlastních reportů, finančních analýz nebo integračních pipeline bez nutnosti používat samotný Microsoft Project. Nebojte se experimentovat s úpravou těchto vlastností nebo je kombinovat s dalšími atributy projektu pro vytvoření bohatších řešení.

---

**Poslední aktualizace:** 2025-12-04  
**Testováno s:** Aspose.Tasks for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}