---
date: 2026-02-10
description: Naučte se, jak pomocí Aspose.Tasks pro Javu získat a aktualizovat vlastnosti
  projektu, jako je symbol měny. Jednoduše změňte měnu projektu a získejte symbol
  měny.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: vlastnosti projektu java – Extrahovat symbol měny z MPP pomocí Aspose.Tasks
  pro Java
url: /cs/java/currency/currency-symbols/
weight: 12
---

 to translate all text content, but keep technical terms in English. Also keep URLs unchanged. Ensure headings same.

We need to translate everything between the shortcodes, but not the shortcodes themselves. Also keep the shortcodes at top and bottom.

Let's produce final output.

We must translate:

- Title "# Extract currency symbol mpp using Aspose.Tasks for Java" => "# Extrahování symbolu měny mpp pomocí Aspose.Tasks pro Java"

- Introduction etc.

We need to translate all paragraphs, bullet points, table headings, etc.

Make sure to keep code block placeholders unchanged.

Also preserve markdown links.

Let's produce.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahování symbolu měny mpp pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se naučíte pracovat s **java project properties** — konkrétně jak extrahovat symbol měny ze souboru Microsoft Project (MPP) a jak **change currency symbol java** nebo **retrieve currency symbol java** pomocí knihovny Aspose.Tasks. Ať už vytváříte nástroj pro reportování, integrujete data z Projectu do finančního systému, nebo jen potřebujete zobrazit správný symbol měny ve vašem UI, zvládnutí tohoto malého, ale podstatného úkolu učiní vaše Java aplikace robustnější a uživatelsky přívětivější.

## Rychlé odpovědi
- **Co znamená „extract currency symbol mpp“?** Jedná se o načtení symbolu měny uloženého v souboru MPP (Microsoft Project).  
- **Která knihovna to řeší?** Aspose.Tasks pro Java poskytuje jednoduché API pro tento úkol.  
- **Potřebuji licenci?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Jak dlouho to trvá?** S kódem níže získáte symbol během méně než minuty.  
- **Mohu také změnit symbol?** Ano — můžete nastavit novou hodnotu pomocí stejné vlastnosti `Prj.CURRENCY_SYMBOL`.

## Co je „extract currency symbol mpp“?
Microsoft Project ukládá symbol měny (např. $, €, £) v hlavičce souboru projektu. Operace **extract currency symbol mpp** přečte tuto hodnotu, aby ji bylo možné zobrazit nebo programově manipulovat.

## Proč aktualizovat symbol měny v java project properties?
Projekty často zasahují více regionů. Schopnost **change project currency** nebo **update currency symbol** za běhu vám umožní přizpůsobit zprávy, faktury nebo dashboardy místnímu trhu, aniž byste museli znovu vytvářet celý soubor projektu. Tato flexibilita je klíčovou součástí efektivního řízení java project properties.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte:

1. **Java Development Kit (JDK)** — verze 8 nebo vyšší.  
2. **Aspose.Tasks pro Java** — stáhněte nejnovější JAR ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Platný soubor **project.mpp**, umístěný ve složce, na kterou můžete odkazovat z kódu.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat pro práci se soubory Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Krok 1: Definujte adresář s daty
Uveďte aplikaci, kde se nachází váš *.mpp* soubor.

```java
String dataDir = "Your Data Directory";
```

> **Tip:** Použijte `System.getProperty("user.dir")` k vytvoření absolutní cesty, která funguje na jakémkoli počítači.

## Krok 2: Načtěte soubor MS Project
Vytvořte objekt `Project`, který představuje MPP soubor v paměti.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Krok 3: Získejte (a případně změňte) symbol měny
Nyní **retrieve currency symbol java** přečteme vlastnost `Prj.CURRENCY_SYMBOL`. Můžete také **change currency symbol java** (nebo **change project currency**) přiřazením nového řetězce k téže vlastnosti.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Volání `System.out.println` vypíše symbol (např. `$`) do konzole a potvrdí, že extrakce proběhla úspěšně.

## Časté problémy a jejich řešení
| Symptom | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| `NullPointerException` při `project.get(...)` | Nesprávná cesta k souboru nebo soubor nebyl nalezen | Ověřte `dataDir` a název souboru; použijte `new File(dataDir).exists()` pro ladění |
| Neočekávaný symbol (např. `?`) | Projekt byl vytvořen s nestandardním locale | Ujistěte se, že zdrojový MPP soubor skutečně definuje symbol měny; můžete jej nastavit programově, jak je ukázáno výše |
| Chyba licence | Používáte zkušební verzi bez platného licenčního souboru | Načtěte licenci pomocí `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` před vytvořením objektu `Project` |

## Často kladené otázky

**Q: Mohu pomocí Aspose.Tasks manipulovat i s jinými atributy projektu kromě symbolu měny?**  
A: Ano, Aspose.Tasks umožňuje upravovat úkoly, zdroje, přiřazení, kalendáře a mnoho dalších vlastností projektu.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů MS Project?**  
A: Rozhodně. Podporuje formáty MPP, MPT i XML od Project 98 až po nejnovější verze.

**Q: Nabízí Aspose.Tasks dokumentaci a podporu pro vývojáře?**  
A: Kompletní API dokumentaci, ukázkové kódy a dedikované fórum podpory najdete na webu Aspose.Tasks.

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano — plně funkční bezplatnou zkušební verzi si můžete stáhnout ze [stránky Aspose](https://purchase.aspose.com/buy).

**Q: Jak získám dočasnou licenci pro Aspose.Tasks?**  
A: Dočasné licence jsou k dispozici na [stránce dočasných licencí Aspose](https://purchase.aspose.com/temporary-license/) pro evaluační účely.

---

**Poslední aktualizace:** 2026-02-10  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}