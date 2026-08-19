---
date: 2026-02-26
description: Naučte se, jak uložit projekt jako PDF a vytvořit list úkolů pomocí Aspose.Tasks
  pro Javu. Rychle exportujte MPP do PDF pomocí tohoto podrobných kroků.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Uložit projekt jako PDF – Vykreslit list úkolů pomocí Aspose.Tasks pro Javu
url: /cs/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení projektu jako PDF – Vykreslení listu úkolů v Aspose.Tasks

## Úvod
V tomto komplexním průvodci se dozvíte, jak **uložit projekt jako PDF** a vygenerovat list úkolů pomocí Aspose.Tasks pro Java. Ať už potřebujete exportovat soubor MPP do PDF pro revize zainteresovaných stran nebo jen vytvořit čistý list úkolů pro reportování, tento tutoriál vás provede každým krokem, vysvětlí, proč je každé nastavení důležité, a ukáže přesný kód, který je potřeba spustit.

## Rychlé odpovědi
- **Co dělá „save project as pdf“?** Převádí soubor Microsoft Project (MPP) do PDF dokumentu, volitelně jej formátuje jako list úkolů.  
- **Jaký formát se používá pro PDF listu úkolů?** Volba `PresentationFormat.TaskSheet` v `PdfSaveOptions`.  
- **Potřebuji licenci pro spuštění kódu?** Pro produkční nasazení je vyžadována dočasná nebo plná licence; pro hodnocení funguje bezplatná zkušební verze.  
- **Jaké jsou hlavní předpoklady?** Java JDK, knihovna Aspose.Tasks pro Java a platný soubor projektu (např. *.mpp).  
- **Mohu přizpůsobit rozvržení PDF?** Ano, Aspose.Tasks nabízí mnoho vlastností `PdfSaveOptions` pro stylování a nastavení stránky.

## Co je „save project as pdf“?
Uložení projektu jako PDF převádí interní data projektu do přenosného, pouze ke čtení určeného dokumentu. To je ideální pro sdílení harmonogramů, listů úkolů nebo stavových zpráv se zainteresovanými stranami, které nemají nainstalovaný Microsoft Project.

## Proč vykreslovat list úkolů?
List úkolů zobrazuje každý úkol v tabulkovém pohledu, ukazuje ID, názvy, datum zahájení/ukončení a další pole. Vykreslení do PDF zajišťuje konzistentní formátování napříč platformami a usnadňuje tisk nebo vložení do jiných dokumentů.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – nejnovější verzi nainstalovanou a `java`/`javac` dostupné v PATH.  
2. **Aspose.Tasks pro Java** – stáhněte knihovnu z oficiálního webu [here](https://releases.aspose.com/tasks/java/).  
3. Platný **soubor projektu** (`*.mpp`), který chcete převést, např. `NewProductDev.mpp`.  

## Import balíčků
Nejprve importujte požadované třídy Aspose.Tasks. Tyto importy vám umožní přístup k možnostem ukládání PDF, formátům prezentace a hlavnímu objektu `Project`.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Průvodce krok za krokem

### Krok 1: Nastavte adresář dokumentu
Definujte složku, kde se nachází zdrojový soubor MPP, a kam bude uložen vygenerovaný PDF. Lze použít absolutní i relativní cestu; jen se ujistěte, že složka existuje.

```java
String dataDir = "Your Document Directory";
```

### Krok 2: Načtěte soubor projektu
Vytvořte instanci `Project` načtením existujícího souboru MPP. Tento objekt představuje celou strukturu projektu v paměti.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Krok 3: Nakonfigurujte možnosti uložení – Export MPP do PDF
Vytvořte objekt `PdfSaveOptions` a řekněte Aspose.Tasks, že chcete PDF vykreslené jako **list úkolů**. Toto je klíčový krok pro scénář *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Krok 4: Uložte projekt jako list úkolů – Save Project as PDF
Zavolejte metodu `save` na objektu `Project`, předáte cílový název souboru a nakonfigurované možnosti. Tím **převodíte soubor MPP do PDF** formátovaného jako list úkolů.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Krok 5: Zkontrolujte výsledek
Přejděte do adresáře, který jste zadali (`dataDir`). Měli byste vidět `taskSheet.pdf` obsahující přehledně formátovaný seznam všech úkolů. Otevřete jej v libovolném PDF prohlížeči a ověřte, že konverze proběhla úspěšně.

## Časté problémy a řešení
- **FileNotFoundException** – Ujistěte se, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) a že název souboru MPP je správný.  
- **LicenseException** – Pokud se objeví chyby licence, aplikujte dočasnou nebo zakoupenou licenci před voláním jakékoli Aspose.Tasks API.  
- **Blank PDF** – Ověřte, že projekt skutečně obsahuje úkoly; prázdný projekt vytvoří prázdný PDF.

## Často kladené otázky

**Q: Je Aspose.Tasks kompatibilní se všemi verzemi Javy?**  
A: Ano, Aspose.Tasks funguje s širokou škálou verzí Javy. Podívejte se na [documentation](https://reference.aspose.com/tasks/java/) pro podrobnosti.

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Rozhodně! Prozkoumejte bezplatnou zkušební verzi [here](https://releases.aspose.com/).

**Q: Kde najdu podporu pro Aspose.Tasks?**  
A: Připojte se ke komunitě Aspose.Tasks na [forum](https://forum.aspose.com/c/tasks/15) pro podporu a diskuze.

**Q: Jak získám dočasnou licenci pro Aspose.Tasks?**  
A: Získejte svou dočasnou licenci [here](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit Aspose.Tasks pro Java?**  
A: Zakupte Aspose.Tasks pro Java [here](https://purchase.aspose.com/buy).

## Závěr
Postupným sledováním těchto kroků jste se naučili, jak **uložit projekt jako PDF**, konkrétně jak vykreslit list úkolů, pomocí Aspose.Tasks pro Java. Tato funkce vám umožní rychle *exportovat MPP do PDF*, sdílet čitelné výstupy projektu a integrovat data projektu do širších reportovacích workflow.

---

**Poslední aktualizace:** 2026-02-26  
**Testováno s:** Aspose.Tasks pro Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}