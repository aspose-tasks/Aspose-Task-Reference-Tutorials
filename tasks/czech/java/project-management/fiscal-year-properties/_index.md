---
date: 2026-04-01
description: Naučte se, jak uložit XML, nastavit fiskální rok a převést MPP na XML
  pomocí Aspose.Tasks pro Javu. Průvodce krok za krokem s ukázkami kódu.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Jak uložit XML a spravovat fiskální rok v Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak uložit XML a spravovat fiskální rok v Aspose.Tasks
url: /cs/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uložit XML a spravovat fiskální rok v Aspose.Tasks

## Úvod
Pokud potřebujete **jak uložit xml** soubory generované z dat Microsoft Project, Aspose.Tasks pro Java vám poskytuje čistý, bezlicenční způsob, jak to provést. V tomto tutoriálu projdeme načtením souboru MPP, zobrazením informací o fiskálním roce, nastavením vlastností fiskálního roku a nakonec **jak uložit xml** výstup. Také uvidíte, jak **jak nastavit fiskální** podrobnosti a **jak převést mpp** soubory, aniž byste kdykoliv otevírali Microsoft Project.

## Rychlé odpovědi
- **Co znamená „manage fiscal year“ v Aspose.Tasks?** Umožňuje vám definovat počáteční měsíc fiskálního roku a povolit číslování fiskálního roku pro projekt.  
- **Jak nastavit počáteční měsíc fiskálního roku?** Použijte vlastnost `Prj.FY_START_DATE` s hodnotou výčtu `Month` (např. `Month.JULY`).  
- **Mohu načíst soubor MPP?** Ano, jednoduše vytvořte instanci `Project` s cestou k souboru *.mpp*.  
- **Jak převést MPP na XML?** Zavolejte `project.save(..., SaveFileFormat.Xml)` po nastavení požadovaných vlastností.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  

## Co je „manage fiscal year“ v projektových souborech?
Správa fiskálního roku znamená konfiguraci kalendáře, který váš projekt používá pro finanční výkaznictví. To zahrnuje nastavení počátečního měsíce fiskálního roku a volitelné povolení číslování fiskálního roku, což ovlivňuje, jak jsou data vypočítávána a zobrazována v reportech.

## Proč používat Aspose.Tasks pro správu fiskálního roku?
- **Microsoft Project není vyžadován** – pracujte s projektovými soubory přímo v Javě.  
- **Plná kontrola** – nastavte začátek fiskálního roku, povolte číslování a programově převádějte formáty.  
- **Robustní API** – spolehlivé zpracování velkých souborů MPP a plynulý export do XML.  

## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.  
2. Aspose.Tasks pro Java JAR – stáhněte jej z [zde](https://releases.aspose.com/tasks/java/) a přidejte jej do classpath vašeho projektu.

## Import balíčků
Pro zahájení importujte potřebné třídy ve vašem Java zdrojovém souboru:
```java
import com.aspose.tasks.*;
```

## Jak načíst soubor MPP a zobrazit informace o fiskálním roce
Níže rozdělujeme proces do jasných, číslovaných kroků.

### Krok 1: Načíst projektový soubor
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Zde **načteme soubor MPP** (`project.mpp`) ze zadaného adresáře. Toto je první krok v jakékoli manipulaci související s fiskálním rokem.

### Krok 2: Zobrazit vlastnosti fiskálního roku
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Vlastnosti `Prj.FY_START_DATE` a `Prj.FISCAL_YEAR_START` vám umožní **zobrazit podrobnosti fiskálního roku**, čímž odpovídají na otázku „jaká je aktuální fiskální konfigurace?“.

### Krok 3: Nastavit začátek fiskálního roku a povolit číslování
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
V tomto kroku **jak nastavit fiskální** nastavení:
- `Month.JULY` určuje počáteční měsíc fiskálního roku.  
- `NullableBool(true)` zapíná číslování fiskálního roku.  
- Nakonec je projekt **převeden z MPP na XML** pomocí `SaveFileFormat.Xml`.

### Krok 4: Potvrdit operaci
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Jednoduchá zpráva v konzoli potvrzuje, že fiskální rok byl nastaven a soubor uložen.

## Proč je to důležité
Uložení projektu jako XML vám poskytuje přenosnou, textovou reprezentaci, kterou lze snadno parsovat, verzovat nebo integrovat s jinými systémy. Když jsou nastavení fiskálního roku správná, následné finanční reporty a dashboardy budou odpovídat účetním obdobím vaší organizace.

## Běžné případy použití
- **Finanční výkaznictví** – Přizpůsobte harmonogramy projektů fiskálnímu kalendáři před exportem do BI nástrojů.  
- **Migrace dat** – Převést starší soubory *.mpp* do XML pro import do cloudových platforem pro řízení projektů.  
- **Automatizované audity** – Programově ověřit, že každý projekt používá správný počáteční měsíc fiskálního roku.

## Tipy pro řešení problémů a běžné úskalí
| Problém | Řešení |
|-------|----------|
| **Nesprávná hodnota měsíce** | Ujistěte se, že používáte výčet `Month` (např. `Month.JANUARY`). |
| **Soubor nenalezen** | Ověřte, že `dataDir` ukazuje na správnou složku a název souboru odpovídá. |
| **Ukládání selhalo** | Zkontrolujte oprávnění k zápisu do cílového adresáře a že `SaveFileFormat` je podporován. |
| **Fiskální rok se neodráží v XML** | Po uložení otevřete XML a potvrďte, že uzly `<FiscalYearStart>` a `<FiscalYearNumbering>` obsahují očekávané hodnoty. |

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks pro Java k manipulaci s jinými vlastnostmi projektu?**  
A: Ano, Aspose.Tasks poskytuje komplexní funkčnost pro správu různých vlastností projektu nad rámec nastavení fiskálního roku.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými formáty projektových souborů?**  
A: Ano, podporuje širokou škálu formátů včetně MPP, XML a dalších.

**Q: Jak mohu získat podporu, pokud narazím na problémy při používání Aspose.Tasks pro Java?**  
A: Můžete požádat o pomoc v komunitě Aspose.Tasks na [fóru](https://forum.aspose.com/c/tasks/15) nebo kontaktovat jejich podpora tým přímo.

**Q: Nabízí Aspose.Tasks bezplatnou zkušební verzi?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks z [zde](https://releases.aspose.com/).

**Q: Kde mohu zakoupit licenci pro Aspose.Tasks pro Java?**  
A: Licenci pro Aspose.Tasks pro Java můžete zakoupit z [zde](https://purchase.aspose.com/buy).

## Závěr
Správa vlastností fiskálního roku v Aspose.Tasks pro Java je jednoduchá. Dodržením výše uvedených kroků můžete **jak uložit xml**, **načíst soubor mpp**, **zobrazit fiskální rok**, **nastavit fiskální rok** a **převést mpp na xml** s jistotou. Použijte tyto techniky k tomu, aby vaše projektové harmonogramy byly v souladu s finančním kalendářem vaší organizace a k vytvoření přenosných XML reprezentací pro následné zpracování.

---

**Poslední aktualizace:** 2026-04-01  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}