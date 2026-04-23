---
date: 2026-02-07
description: Naučte se, jak v Javě číst vlastnosti měny a extrahovat symbol měny z MS Project
  souborů pomocí Aspose.Tasks pro Javu. Postupujte podle tohoto krok‑za‑krokem průvodce
  a programově získávejte kód měny, symbol, počet desetinných míst a jeho umístění.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Čtení měnových vlastností v Javě s projekty Aspose.Tasks
url: /cs/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přečíst vlastnosti měny Java s projekty Aspose.Tasks

## Úvod
V tomto tutoriálu **přečtete vlastnosti měny java** z souborů Microsoft Project pomocí API Aspose.Tasks pro Java. Aspose.Tasks vám umožňuje pracovat se soubory .mpp, aniž byste potřebovali nainstalovaný Microsoft Project, což je ideální pro automatizované reportování, migraci dat nebo integraci do podnikově orientovaných aplikací v Javě. Na konci tohoto průvodce budete schopni přímo ze souboru projektu získat kód měny, symbol, počet desetinných míst a pozici symbolu.

## Rychlé odpovědi
- **Co znamená “read currency properties java”?** Jedná se o získání metadat souvisejících s měnou (kód, symbol, počet desetinných míst, pozice) ze souboru MS Project pomocí Java kódu.  
- **Potřebuji licenci k vyzkoušení?** K dispozici je bezplatná zkušební verze Aspose.Tasks; pro produkční použití je vyžadována komerční licence.  
- **Jaká verze JDK je vyžadována?** Java 8 nebo vyšší.  
- **Mohu po načtení měnu upravit?** Ano, Aspose.Tasks umožňuje jak čtení, tak zápis vlastností měny.  
- **Je to kompatibilní se všemi verzemi .mpp?** API podporuje soubory vytvořené v Microsoft Project 2003‑2021.

## Co je “read currency properties java”?
Čtení vlastností měny v Javě znamená přístup k nastavením na úrovni projektu, která určují, jak jsou peněžní hodnoty zobrazovány v souboru Microsoft Project. Tato nastavení zahrnují ISO kód měny (např. **USD**), symbol (**$**), počet desetinných míst a zda se symbol zobrazuje před nebo za částkou.

## Proč číst vlastnosti měny java s Aspose.Tasks?
- **Není potřeba instalace Microsoft Project** – API funguje na libovolné platformě, která podporuje Javu.  
- **Rychlé, v‑procesu prováděné získání** – ideální pro dávkové zpracování velkého počtu souborů projektů.  
- **Plná kontrola** – můžete získané hodnoty kombinovat s vlastním reportováním nebo je integrovat do ERP systémů.  
- **Podpora napříč verzemi** – funguje se soubory .mpp od Project 2003 až po nejnovější verzi 2021.

## Požadavky
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – Java 8 nebo novější nainstalovanou a nakonfigurovanou v `PATH`.  
2. **Aspose.Tasks for Java JAR** – stáhněte si nejnovější knihovnu [zde](https://releases.aspose.com/tasks/java/) a přidejte ji do classpath vašeho projektu.  

## Import Packages
Začněte importováním jmenného prostoru Aspose.Tasks potřebného pro manipulaci s projektem:

```java
import com.aspose.tasks.*;
```

## Krok 1: Nastavte adresář projektu
Definujte složku, která obsahuje soubor `.mpp`, který chcete analyzovat. Uložení cesty do proměnné usnadňuje opakované použití kódu:

```java
String dataDir = "Your Data Directory";
```

*Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou ke složce, kde se nachází `project.mpp`.*

## Krok 2: Vytvořte instanci čtečky projektu
Načtěte soubor Microsoft Project do objektu `Project`. Tento objekt vám poskytne přístup ke všem vlastnostem projektu, včetně nastavení měny:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Pokud má váš soubor jiný název, změňte `"project.mpp"` podle potřeby.*

## Krok 3: Zobrazte vlastnosti měny
Nyní načtěte každou vlastnost měny pomocí výčtu `Prj` a výpis výsledků do konzole. API vrací objekty, které můžete převést na řetězce pro zobrazení:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Co uvidíte:**  
- **Currency Code** – ISO‑4217 kód jako `USD`, `EUR`, `JPY`.  
- **Currency Digits** – obvykle `2` pro většinu měn, `0` pro japonský jen.  
- **Currency Symbol** – znak zobrazovaný v reportech (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` pro **před** částkou, `1` pro **za** částkou.

## Jak extrahovat symbol měny java?
Pokud vás zajímá pouze samotný symbol, můžete se zaměřit na vlastnost `Prj.CURRENCY_SYMBOL`. Stejný volání `project.get(...)` vrátí symbol, který můžete uložit, zaznamenat nebo předat dalšímu servisu pro další zpracování. To je zvláště užitečné, když potřebujete **extrahovat symbol měny java** pro finanční dashboardy nebo lokalizované UI komponenty.

## Krok 4: Dokončení zpracování
Signalizujte, že extrakce úspěšně skončila. Tato jednoduchá zpráva je užitečná, když kód běží jako součást většího dávkového úkolu:

```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **FileNotFoundException** | Cesta `dataDir` je nesprávná nebo je špatně napsán název souboru. | Ověřte řetězec adresáře a ujistěte se, že soubor `.mpp` existuje na zadaném místě. |
| **NullPointerException on `project.get(...)`** | Soubor projektu neobsahuje informace o měně (málo pravděpodobné) nebo je špatný klíč vlastnosti. | Použijte `project.contains(Prj.CURRENCY_CODE)` k ověření existence před čtením. |
| **LicenseException** | Spouštění bez platné licence Aspose.Tasks v produkčním prostředí. | Načtěte licenční soubor pomocí `License license = new License(); license.setLicense("Aspose.Tasks.lic");` před vytvořením objektu `Project`. |

## Často kladené otázky

**Q: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?**  
A: Aspose.Tasks podporuje soubory .mpp generované v Microsoft Project 2003‑2021, zahrnující jak starší, tak nejnovější formáty.

**Q: Mohu pomocí Aspose.Tasks měnit vlastnosti měny?**  
A: Ano, můžete jak číst, tak zapisovat nastavení měny. Použijte `project.set(Prj.CURRENCY_CODE, "EUR");` a poté projekt uložte.

**Q: Je Aspose.Tasks vhodný pro komerční použití?**  
A: Rozhodně. Jedná se o komerční knihovnu; licenci můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Nabízí Aspose.Tasks bezplatnou zkušební verzi?**  
A: Ano, plně funkční zkušební verze je k dispozici [zde](https://releases.aspose.com/).

**Q: Kde mohu získat pomoc nebo podporu pro Aspose.Tasks?**  
A: Oficiální fórum Aspose.Tasks je nejlepší místo pro asistenci – navštivte jej [zde](https://forum.aspose.com/c/tasks/15).

## Další FAQ (AI‑Optimalizované)

**Q: Jak programově získat pouze symbol měny v Javě?**  
A: Zavolejte `project.get(Prj.CURRENCY_SYMBOL)` a výsledek přetypujte na `String`. Vrátí přesný symbol použitý v souboru projektu.

**Q: Mohu číst vlastnosti měny z .mpp souboru chráněného heslem?**  
A: Ano. Načtěte soubor pomocí příslušného přetížení konstruktoru `Project`, který přijímá heslo, a poté vlastnosti čtěte podle výše uvedeného postupu.

**Q: Jaký výkon mohu očekávat při zpracování mnoha souborů projektů?**  
A: Aspose.Tasks běží v‑procesu a typicky načte standardní .mpp soubor během několika milisekund. Pro hromadné operace zvažte opakované použití stejné instance `Project`, kde je to možné.

## Závěr
Nyní jste se naučili, jak **přečíst vlastnosti měny java** a **extrahovat symbol měny java** ze souboru MS Project pomocí Aspose.Tasks pro Java. Tato schopnost vám umožní začlenit metadata měny do vlastních reportů, finančních analýz nebo integračních pipeline bez nutnosti používat samotný Microsoft Project. Nebojte se experimentovat s úpravou těchto vlastností nebo kombinovat tato data s dalšími atributy projektu pro tvorbu bohatších řešení.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}