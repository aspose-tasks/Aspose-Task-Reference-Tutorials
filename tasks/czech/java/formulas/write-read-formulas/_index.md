---
date: 2025-12-07
description: Naučte se, jak uložit soubor projektu, zapisovat a číst vzorce MS Project
  a přidávat vlastní vzorce polí pomocí Aspose.Tasks pro Javu.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Uložte soubor projektu a zapisujte vzorce MS Project pomocí Aspose.Tasks
url: /cs/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení souboru projektu a zápis MS Project vzorců pomocí Aspose.Tasks

## Úvod
V oblasti řízení projektů je efektivní manipulace s daty naprosto zásadní. Aspose.Tasks pro Java je robustní řešení, které usnadňuje manipulaci a extrakci dat ze souborů Microsoft Project. Jednou z výkonných funkcí, které nabízí, je možnost zapisovat a číst MS Project vzorce. **Také se naučíte, jak *uložit soubor projektu* po aplikaci těchto vzorců**, čímž zajistíte, že vaše změny budou trvale uloženy pro budoucí analýzu. Tento tutoriál vás provede procesem využití této funkčnosti k vylepšení vašich úkolů řízení projektů.

## Rychlé odpovědi
- **Co dělá „uložit soubor projektu“?** Zapíše všechny změny v paměti zpět do souboru .mpp na disku.  
- **Mohu přidat vlastní vzorce pole?** Ano – můžete vytvořit vlastní pole a přiřadit vzorec, například „zdvojnásobit náklad úkolu“.  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební verze stačí pro hodnocení; pro produkční nasazení je vyžadována komerční licence.  
- **Které IDE je nejlepší?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, VS Code) zkompiluje ukázkový kód.  
- **Je API kompatibilní s nejnovější verzí MS Project?** Aspose.Tasks podporuje všechny aktuální formáty .mpp.

## Co znamená „uložit soubor projektu“ v Aspose.Tasks?
Uložení souboru projektu znamená trvalé uložení aktuálního stavu objektu `Project` – včetně úkolů, zdrojů a jakýchkoli vlastních vzorců – do fyzického souboru Microsoft Project (`.mpp`). Tato operace je nezbytná po úpravě dat, například po přidání vlastního pole nebo změně nákladů úkolu.

## Proč přidat vlastní pole a vytvořit vlastní vzorec pole?
Přidání vlastního pole vám poskytuje flexibilní kontejner pro doplňující informace, které nejsou pokryty výchozími poli. Připojením vzorce – například **zdvojnásobit náklad úkolu** – automatizujete výpočty, snížíte manuální chyby a udržíte data harmonogramu konzistentní.

## Předpoklady
Před tím, než se ponoříte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:

1. **Java Development Kit (JDK)** – Java 8 nebo vyšší nainstalovaná na vašem počítači.  
2. **Aspose.Tasks pro Java** – Stáhněte a nainstalujte z [zde](https://releases.aspose.com/tasks/java/).  
3. **Integrované vývojové prostředí (IDE)** – Vyberte si preferované IDE pro vývoj v Javě (IntelliJ IDEA, Eclipse, VS Code, atd.).  

## Importování balíčků
Pro začátek importujte potřebné balíčky do svého Java projektu:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Krok 1: Nastavení adresáře s daty
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Definujte složku, kde jsou uloženy vaše soubory MS Project. Zde načtete zdrojový soubor a později **uložíte soubor projektu**.

## Krok 2: Načtení souboru projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
Načtěte existující soubor Microsoft Project do objektu `Project`, abyste mohli číst nebo upravovat jeho obsah.

## Krok 3: Přidání vlastního pole a vytvoření vzorce vlastního pole
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
V tomto kroku **přidáme vlastní pole** „Double Costs“ a **vytvoříme vzorec vlastního pole**, který násobí `[Cost]` úkolu 2, čímž efektivně **zdvojnásobí náklad úkolu**. Metoda `setFormula` vloží výpočet přímo do souboru projektu.

## Krok 4: Přidání úkolu a nastavení nákladu
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Vytvořte nový úkol a přiřaďte mu základní náklad `100`. Když bude projekt uložen, vlastní pole automaticky zobrazí `200` díky dříve definovanému vzorci.

## Krok 5: Uložení souboru projektu
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Nakonec **uložte soubor projektu** se všemi úpravami. Metoda `save` zapíše aktualizovaný projekt, včetně nového vlastního pole a jeho vypočtených hodnot, do `saved.mpp`.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|---------|-------|--------|
| **Vzorec se neaplikoval** | Vlastní pole nebylo přidáno do kolekce `ExtendedAttributes` projektu. | Ujistěte se, že je před uložením provedeno `project.getExtendedAttributes().add(attr);`. |
| **Soubor nenalezen** | Nesprávná cesta `dataDir`. | Ověřte, že řetězec cesty končí oddělovačem (`/` nebo `\\`). |
| **Náklad se zobrazuje jako 0** | Náklad úkolu nebyl nastaven před uložením. | Zavolejte `task.set(Tsk.COST, ...)` před `project.save`. |

## Často kladené otázky
**Q: Je Aspose.Tasks kompatibilní se všemi verzemi MS Project?**  
A: Ano, Aspose.Tasks podporuje širokou škálu verzí MS Project, od starších formátů .mpp po nejnovější vydání.

**Q: Mohu integrovat Aspose.Tasks do existujícího Java projektu?**  
A: Rozhodně. API je navrženo pro bezproblémovou integraci; stačí přidat JAR Aspose.Tasks do classpath vašeho projektu.

**Q: Existují omezení ohledně typů vzorců, které mohu vytvořit?**  
A: Knihovna podporuje většinu nativní syntaxe MS Project vzorců, včetně aritmetických, logických a vestavěných funkcí. Složitější vlastní funkce mohou vyžadovat workaroundy.

**Q: Podporuje Aspose.Tasks nasazení na více platformách?**  
A: Ano, knihovna běží na jakékoli platformě, která podporuje Javu, včetně Windows, Linuxu a macOS.

**Q: Jak získám technickou podporu pro Aspose.Tasks?**  
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro komunitní pomoc, nebo otevřete ticket podpory, pokud máte komerční licenci.

## Závěr
V tomto tutoriálu jsme si ukázali, jak **uložit soubor projektu**, **přidat vlastní pole** a **vytvořit vzorec vlastního pole**, který **zdvojnásobí náklad úkolu** pomocí Aspose.Tasks pro Java. Dodržením těchto kroků můžete automatizovat výpočty, obohatit data projektu a zajistit, že všechny změny budou trvale uloženy pro budoucí reportování a analýzu.

---

**Poslední aktualizace:** 2025-12-07  
**Testováno s:** Aspose.Tasks pro Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}