---
date: 2025-12-20
description: Naučte se, jak programově získat kódy osnov v MS Project pomocí Aspose.Tasks
  pro Javu. Zvyšte své schopnosti v řízení projektů.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Získat kódy osnov v MS Project v Aspose.Tasks
url: /cs/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Načtení kódů osnov v MS Project pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se dozvíte **jak načíst kódy osnov v MS Project** pomocí Aspose.Tasks pro Java. Kódy osnov v MS Project vám poskytují výkonný způsob, jak kategorizovat úkoly, zdroje a přiřazení, a jejich programatický přístup vám umožní vytvářet vlastní reporty, automatizaci nebo integrační řešení. Provedeme vás kompletním příkladem krok za krokem, který můžete zkopírovat do svého projektu.

## Rychlé odpovědi
- **Co kód dělá?** Načte soubor Project a vypíše každou definici kódu osnov, její masky a hodnoty.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (jakákoli aktuální verze).  
- **Potřebuji licenci?** Zkušební verze funguje pro vývoj; pro produkci je vyžadována plná licence.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.  
- **Mohu kódy po načtení upravit?** Ano – stejné API vám umožní přidávat, upravovat nebo mazat kódy osnov.

## Co jsou kódy osnov v MS Project?
Kódy osnov jsou vlastní pole, která umožňují projektovým manažerům seskupovat a filtrovat úkoly nad rámec výchozí hierarchie. Mohou být jednoduché číselné hodnoty, řetězce nebo dokonce podnikové vlastní kódy definované na úrovni organizace. Čtením těchto kódů můžete napájet řídicí panely, exportovat data nebo automaticky vynucovat pojmenovací konvence.

## Proč načítat kódy osnov v MS Project pomocí Aspose.Tasks?
- **Automatizace:** Generovat reporty nebo spouštět pracovní postupy bez ručního exportu.  
- **Integrace:** Synchronizovat kódy osnov s ERP, PPM nebo BI nástroji.  
- **Přizpůsobení:** Aplikovat obchodní pravidla na základě hodnot kódu (např. alokace nákladů).  
- **Cross‑platform:** Funguje na Windows, Linuxu i macOS, nezávisle na uživatelském rozhraní Microsoft Project.

## Předpoklady
Než začneme, ujistěte se, že máte nastaveny následující předpoklady:

### 1. Vývojové prostředí Javy
Ujistěte se, že máte na svém systému nainstalovaný Java Development Kit (JDK). JDK můžete stáhnout a nainstalovat z webu Oracle.

### 2. Knihovna Aspose.Tasks
Stáhněte a zahrňte knihovnu Aspose.Tasks do svého Java projektu. Knihovnu můžete stáhnout ze stránky [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).

## Import balíčků
Nejprve importujte potřebné balíčky z Aspose.Tasks ve svém Java kódu:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Nyní rozdělíme poskytnutý ukázkový kód do několika kroků:

## Krok 1: Načtení projektu
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
V tomto kroku načteme soubor Microsoft Project do objektu `Project` pomocí zadaného názvu souboru.

## Krok 2: Načtení kódů osnov
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Procházíme každou definici kódu osnov v projektu.

## Krok 3: Přístup k vlastnostem kódu osnov
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Načteme a vypíšeme různé vlastnosti definice kódu osnov, jako Alias, Field ID a Field Name.

## Krok 4: Kontrola podnikového vlastního kódu
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Zkontrolujeme, zda je kód osnov podnikovým vlastním kódem, a výsledek podle toho vypíšeme.

## Krok 5: Zobrazení masek kódu osnov
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Procházíme každou masku spojenou s kódem osnov a vypíšeme její úroveň a hodnotu masky.

## Krok 6: Zobrazení hodnot kódu osnov
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Procházíme každou hodnotu kódu osnov a vypíšeme její popis, ID hodnoty, hodnotu a typ.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Žádný výstup** | Cesta k souboru projektu je nesprávná | Ověřte, že `projectName` ukazuje na platný soubor `.mpp`. |
| **Null hodnoty** | Kód osnov není v souboru definován | Ujistěte se, že soubor Project skutečně obsahuje kódy osnov (zkontrolujte v UI MS Project). |
| **LicenseException** | Použití zkušební verze bez řádné aktivace | Aplikujte dočasnou nebo plnou licenci pomocí `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Často kladené otázky

**Q: Můžu použít Aspose.Tasks pro Java k úpravě kódů osnov v souboru Project?**  
A: Ano, Aspose.Tasks pro Java poskytuje API pro programatickou úpravu kódů osnov. Můžete přidávat, upravovat nebo mazat definice pomocí stejného objektu `Project`.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro Java ze [stránky Aspose.Tasks](https://releases.aspose.com/).

**Q: Jak mohu získat technickou podporu pro Aspose.Tasks pro Java?**  
A: Technickou podporu získáte návštěvou [fóra Aspose.Tasks](https://forum.aspose.com/c/tasks/15) a zasláním svých dotazů tam.

**Q: Můžu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Ano, dočasnou licenci pro Aspose.Tasks pro Java můžete zakoupit na [stránce nákupu](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu kompletní dokumentaci pro Aspose.Tasks pro Java?**  
A: Kompletní informace o používání Aspose.Tasks pro Java najdete v [dokumentaci](https://reference.aspose.com/tasks/java/).

## Závěr
V tomto tutoriálu jsme se naučili, jak načíst **kódy osnov v MS Project** pomocí Aspose.Tasks pro Java. Dodržením uvedených kroků můžete efektivně přistupovat k kódům osnov a manipulovat s nimi ve svých Java aplikacích, což umožňuje pokročilé funkce řízení projektů, jako jsou vlastní reporty, automatizace a integrace s dalšími podnikovými systémy.

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}