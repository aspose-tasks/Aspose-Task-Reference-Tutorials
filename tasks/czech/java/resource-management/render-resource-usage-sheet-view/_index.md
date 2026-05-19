---
date: 2026-01-15
description: Naučte se, jak uložit projekt jako PDF a vykreslit zobrazení Resource
  Usage a Sheet v MS Project pomocí Aspose.Tasks pro Javu. Postupujte podle našeho
  krok‑za‑krokem průvodce a snadno exportujte projekt do PDF.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Uložit projekt jako PDF – vykreslit využití zdrojů a listový pohled v Aspose.Tasks
url: /cs/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení projektu jako PDF – vykreslení zobrazení Využití zdrojů a Listu v Aspose.Tasks

## Úvod
V tomto tutoriálu se dozvíte, jak **uložit projekt jako PDF** při vykreslování zobrazení Využití zdrojů a Listu souboru Microsoft Project. Ať už potřebujete vytvořit tisknutelnou zprávu pro zainteresované strany nebo převést soubory MPP do univerzálně zobrazitelného formátu, Aspose.Tasks pro Java proces zjednodušuje – není vyžadována instalace Microsoft Project.

##ychlé odpovědi
- **Co dělá „uložit projekt jako pdf“?** Převádí soubor projektu (MPP) do PDF dokumentu se zachováním vybraného zobrazení.  
- **Které zobrazení lze exportovat?** Využití zdrojů, List, Gantt, Využití úkolů a další.  
- **Mohu v PDF změnit časovou osu?** Ano – možnosti zahrnují Dny, TřetinyMěsíců a Měsíce.  
- **Je potřeba mít nainstalovaný Microsoft Project?** Ne, Aspose.Tasks funguje samostatně.  
- **Je pro produkční použití vyžadována licence?** Ano, pro ne‑zkušební použití je potřeba komerční licence.

## Co je „uložit projekt jako PDF“?
Uložení projektu jako PDF vytvoří statické, vysoce rozlišené zobrazení vybraného pohledu projektu. To je ideální pro sdílení s klienty, archivaci nebo tisk bez odhalení podkladového souboru projektu.

## Proč použít Aspose.Tasks k exportu projektu do PDF?
- **Žádné externí závislosti** – funguje na jakékoli platformě podporující Java.  
- **Detailní kontrola** – můžete vybrat pohled, časovou osu a rozvržení.  
- **Vysoká věrnost** – PDF odráží vzhled původního pohledu v Projectu.  
- **Připraveno pro automatizaci** – integrujte do CI pipeline, reportingových služeb nebo dávkových konvertorů.

## Prerequisites
Než se pustíme dál, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – doporučena nejnovější verze.  
2. **Aspose.Tasks for Java** – stáhněte z [stránky ke stažení](https://releases.aspose.com/tasks/java/).  

## Import balíčků
Nejprve importujte potřebné třídy do svého Java projektu:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Průvodce krok za krokem

### Krok 1: Načtení zdrojového projektu
Načtěte soubor MPP, který chcete převést.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Krok 2: Definujte SaveOptions s požadovanou časovou osou (Export projektu do PDF)
Nastavte možnosti exportu PDF a zvolte požadovanou časovou osu.  
*Zde používáme jako příklad **Days**.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Krok 3: Nastavte PresentationFormat na ResourceUsage
Vyberte pohled, který chcete vykreslit. V tomto případě pohled **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Krok 4: Uložení projektu (převod MPP na PDF)
Spusťte konverzi a vygenerujte PDF soubor.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Krok 5: Vykreslení pohledů pro jiné nastavení časové osy (Změna časové osy PDF)
Opakujte předchozí kroky k vytvoření PDF s různými časovými osami, jako jsou **ThirdsOfMonths** a **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Časté problémy a řešení
- **Chyby souboru nenalezen** – Ověřte, že `dataDir` ukazuje na správnou složku a že název souboru MPP přesně odpovídá.  
- **Prázdný výstup PDF** – Ujistěte se, že `PresentationFormat` odpovídá pohledu, který obsahuje data (např. ResourceUsage).  
- **Nesprávná časová osa** – Zkontrolujte, že `options.setTimescale()` je voláno před každým `project.save()`.

## Často kladené otázky

### Může Aspose.Tasks vykreslovat jiné pohledy kromě Využití zdrojů a Listu?
Aspose.Tasks podporuje vykreslování různých pohledů, jako jsou Gantt Chart, Task Usage a Calendar, a další.

### Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?
Ano, Aspose.Tasks podporuje širokou škálu formátů souborů Microsoft Project, včetně MPP, MPT a XML.

### Mohu přizpůsobit vzhled vykreslených pohledů pomocí Aspose.Tasks?
Rozhodně! Aspose.Tasks poskytuje rozsáhlé možnosti pro přizpůsobení vzhledu a rozvržení vykreslených pohledů podle vašich konkrétních požadavků.

### Vyžaduje Aspose.Tasks instalaci Microsoft Project na systému?
Ne, Aspose.Tasks je samostatná knihovna a nevyžaduje instalaci Microsoft Project pro své fungování.

### Je technická podpora k dispozici pro uživatele Aspose.Tasks?
Ano, uživatelé Aspose.Tasks mohou využít technickou podporu prostřednictvím [fóra Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-15  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---