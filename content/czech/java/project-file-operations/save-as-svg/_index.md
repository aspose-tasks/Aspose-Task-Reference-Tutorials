---
title: Převést MS Project na SVG v Javě
linktitle: Uložit jako SVG v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se ukládat soubory Microsoft Project jako SVG v Javě pomocí knihovny Aspose.Tasks. Podrobný průvodce s příklady kódu.
type: docs
weight: 18
url: /cs/java/project-file-operations/save-as-svg/
---
## Úvod
Aspose.Tasks for Java je výkonná knihovna pro práci se soubory projektového managementu, která umožňuje vývojářům manipulovat s projektovými daty, provádět různé operace a efektivně generovat sestavy. V tomto tutoriálu prozkoumáme, jak uložit projekt jako SVG pomocí Aspose.Tasks for Java. SVG (Scalable Vector Graphics) je široce používaný formát pro zobrazování vektorové grafiky na webu, který poskytuje škálovatelnost a vysoce kvalitní vykreslování.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
### Vývojové prostředí Java
Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK). JDK si můžete stáhnout a nainstalovat z webu Oracle.
### Aspose.Tasks for Java Library
 Stáhněte a nainstalujte knihovnu Aspose.Tasks for Java z webu. Odkaz ke stažení naleznete v poskytnuté dokumentaci[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve musíte do svého programu Java importovat potřebné balíčky, abyste mohli pracovat s funkcemi Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Nyní rozdělme poskytnutý příklad do několika kroků:
## Krok 2: Definujte datový adresář
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` cestou k adresáři, kde je umístěn váš projektový soubor.
## Krok 3: Načtěte soubor projektu
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Tento krok načte soubor projektu s názvem "HomeMovePlan.mpp" ze zadaného datového adresáře.
## Krok 4: Uložte jako SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Tento krok uloží načtený projekt ve formátu SVG s názvem "project5.svg" do zadaného datového adresáře.

## Závěr
V tomto tutoriálu jsme se naučili, jak uložit projekt jako SVG pomocí Aspose.Tasks for Java. Dodržováním uvedených kroků můžete efektivně převádět soubory projektu do formátu SVG, což umožňuje bezproblémovou integraci s webovými aplikacemi nebo vizualizačními nástroji.
## FAQ
### Je Aspose.Tasks for Java kompatibilní se všemi verzemi souborů Microsoft Project?
Ano, Aspose.Tasks for Java podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.
### Mohu upravit vzhled výstupu SVG?
Ano, vzhled výstupu SVG můžete upravit úpravou parametrů, jako jsou fonty, barvy a konfigurace rozvržení.
### Vyžaduje Aspose.Tasks for Java licenci pro komerční použití?
 Ano, pro komerční použití Aspose.Tasks for Java je vyžadována platná licence. Licenci můžete získat z webu[tady](https://purchase.aspose.com/temporary-license/).
### Mohu vyzkoušet Aspose.Tasks pro Javu před nákupem?
 Ano, můžete požádat o bezplatnou zkušební verzi Aspose.Tasks for Java z webu[tady](https://purchase.aspose.com/buy) vyhodnotit jeho vlastnosti a možnosti.
### Kde mohu získat podporu pro Aspose.Tasks for Java?
 Podporu pro Aspose.Tasks pro Javu můžete získat návštěvou fóra[tady](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a komunikovat s komunitou.