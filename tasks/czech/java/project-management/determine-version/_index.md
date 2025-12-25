---
date: 2025-12-25
description: Prozkoumejte tento tutoriál Aspose Tasks pro Javu a zjistěte, jak určit
  verzi projektu v souborech MS Project. Podrobný návod krok za krokem s ukázkami
  kódu.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose Tasks Java tutoriál: Určete verzi MS Project'
url: /cs/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java Tutorial: Zjištění verze MS Project

## Introduction
V tomto **aspose tasks java tutorial** se dozvíte, jak programově zjistit verzi souboru Microsoft Project pomocí knihovny Aspose.Tasks pro Java. Znalost verze souboru vám pomůže řešit problémy s kompatibilitou, vynucovat migrační politiky nebo jednoduše zaznamenat, která verze Project vytvořila soubor. Provedeme vás všemi kroky – od nastavení prostředí po vytištění verze a data posledního uložení – abyste mohli tuto kontrolu s jistotou integrovat do jakékoli Java aplikace.

## Quick Answers
- **Co tento tutoriál pokrývá?** Zjištění verze souboru MS Project pomocí Aspose.Tasks pro Java.  
- **Potřebuji mít nainstalovaný Microsoft Project?** Ne, Aspose.Tasks funguje nezávisle.  
- **Jaké formáty souborů jsou podporovány?** XML‑založené soubory Project (MPP, XML, atd.).  
- **Jak dlouho trvá implementace?** Zhruba 5‑10 minut pro základní kontrolu.  
- **Je vyžadována licence?** Pro hodnocení funguje bezplatná zkušební verze; licence je potřeba pro produkci.

## What is Aspose Tasks Java Tutorial?
**aspose tasks java tutorial** poskytuje praktické vedení pro používání Aspose.Tasks API v Java projektech. Ukazuje, jak číst, upravovat a analyzovat data Microsoft Project bez potřeby samotného Microsoft Project.

## Why use Aspose.Tasks to determine project version?
- **Žádná závislost na Microsoft Project** – ideální pro automatizaci na serveru.  
- **Přesná metadata verze** – získá přesná pole SAVE_VERSION a LAST_SAVED.  
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.  
- **Vysoký výkon** – lehké parsování vhodné pro dávkové zpracování.

## Prerequisites
Před začátkem se ujistěte, že máte následující:

1. **Java Development Kit (JDK)** – libovolný aktuální JDK (8 nebo vyšší).  
2. **Aspose.Tasks for Java JAR** – stáhněte jej z [website](https://releases.aspose.com/tasks/java/) a přidejte do classpath projektu.  
3. **MS Project file** – XML‑založený soubor Project (např. `input.xml`), který chcete prozkoumat.  

> **Pro tip:** Uchovávejte soubor Project ve vyhrazené `data` složce, aby bylo zjednodušeno zpracování cest.

## Import Packages
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: Set Up the Project Directory
Define the folder that contains your Project file.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou, kde se nachází `input.xml`.

## Step 2: Load the Project
Create a `Project` instance by loading the XML file.

```java
Project project = new Project(dataDir + "input.xml");
```

Pokud má váš soubor jiný název, upravte `"input.xml"` podle potřeby.

## Step 3: How to Determine Project Version
Retrieve the version information and the last saved timestamp.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

`Prj.SAVE_VERSION` udává verzi Microsoft Project, která byla použita k uložení souboru (např. 12 pro Project 2010). `Prj.LAST_SAVED` vrací datum/čas posledního uložení.

## Step 4: Display Result
Signal successful completion of the version check.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Problém | Příčina | Řešení |
|---------|----------|--------|
| `NullPointerException` při `project.get(...)` | Soubor nenalezen nebo nesprávná cesta | Ověřte `dataDir` a název souboru; pro testování použijte absolutní cestu. |
| Neočekávané číslo verze (např. 0) | Načítání souboru, který není Project XML | Ujistěte se, že soubor je platný soubor Microsoft Project (MPP/XML). |
| Výjimka licence | Použití zkušební verze bez platné licence v produkci | Aplikujte svou licenci Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

### Q: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
A: Ano, Aspose.Tasks podporuje více jazyků včetně .NET, Java a C++.

### Q: Je Aspose.Tasks vhodný pro rozsáhlé projekty?
A: Rozhodně, Aspose.Tasks je navržen tak, aby snadno zvládl projekty jakékoli velikosti.

### Q: Mohu pomocí Aspose.Tasks přizpůsobit data projektu?
A: Ano, můžete manipulovat s daty projektu, upravovat úkoly, zdroje a mnohem více pomocí Aspose.Tasks.

### Q: Vyžaduje Aspose.Tasks instalaci Microsoft Project?
A: Ne, Aspose.Tasks funguje nezávisle a nevyžaduje instalaci Microsoft Project.

### Q: Je k dispozici technická podpora pro Aspose.Tasks?
A: Ano, technickou podporu získáte na fóru Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

### Additional Q&A

**Q: Jak získám další vlastnosti projektu (např. autora, společnost)?**  
A: Použijte `project.get(Prj.AUTHOR)` nebo `project.get(Prj.COMPANY)` podobně jako v příkladu pro verzi.

**Q: Můžu zkontrolovat verzi souboru MPP (binární formát)?**  
A: Ano, Aspose.Tasks může načíst soubory `.mpp` přímo; stejná vlastnost `Prj.SAVE_VERSION` funguje.

**Q: Existuje způsob, jak programově upgradovat starší soubor projektu na novější verzi?**  
A: Načtěte starší soubor a poté jej uložte pomocí `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks jej ve výchozím nastavení zapíše v nejnovějším formátu.

## Conclusion
Právě jste dokončili stručný **aspose tasks java tutorial**, který ukazuje **jak zjistit verzi projektu** souborů MS Project pomocí Aspose.Tasks pro Java. Začleňte tento úryvek do větších automatizačních pracovních toků, reportovacích nástrojů nebo migračních utilit, abyste vždy věděli, s jakou přesnou verzí Project pracujete.

---

**Poslední aktualizace:** 2025-12-25  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}