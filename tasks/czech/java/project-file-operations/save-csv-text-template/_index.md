---
title: Uložit jako CSV, text a šablonu v Aspose.Tasks
linktitle: Uložit jako CSV, text a šablonu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se ukládat soubory Microsoft Project ve formátech CSV, Text a Template pomocí Aspose.Tasks for Java.
weight: 16
url: /cs/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložit jako CSV, text a šablonu v Aspose.Tasks

## Úvod
tomto tutoriálu prozkoumáme, jak pomocí Aspose.Tasks for Java uložit soubory projektu v různých formátech, jako je CSV, Text a Template. Aspose.Tasks je výkonná Java knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project bez nutnosti instalace Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Aspose.Tasks pro knihovnu Java staženou a nakonfigurovanou ve vašem projektu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
3. Základní znalost programovacího jazyka Java.

## Importujte balíčky
Nejprve musíte importovat potřebné balíčky do souboru Java:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Uložit projekt jako CSV
Pojďme si rozebrat kroky k uložení projektu jako CSV:
### Krok 1: Načtěte projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Krok 2: Uložit jako CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Uložit projekt jako text
Zde je návod, jak uložit projekt jako text:
### Krok 1: Načtěte projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Krok 2: Uložit jako text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Uložit projekt jako šablonu
Uložení projektu jako šablony zahrnuje následující kroky:
### Krok 1: Načtěte projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Krok 2: Nastavte možnosti šablony
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Krok 3: Uložit jako šablonu
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Závěr
tomto tutoriálu jsme se naučili, jak uložit soubory Microsoft Project jako CSV, text a šablonu pomocí Aspose.Tasks for Java. Pomocí těchto jednoduchých kroků můžete efektivně spravovat soubory projektu v různých formátech a zvýšit tak svou produktivitu jako vývojář v jazyce Java.
## FAQ
### Otázka: Dokáže Aspose.Tasks for Java zpracovat složité projektové soubory?
A: Rozhodně! Aspose.Tasks for Java si snadno poradí s projekty různé složitosti a poskytuje komplexní podporu pro formáty souborů Microsoft Project.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks for Java od[tady](https://releases.aspose.com/).
### Otázka: Kde najdu podporu pro Aspose.Tasks for Java?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy týkající se Aspose.Tasks for Java.
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks for Java?
 Odpověď: Ano, můžete si zakoupit dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/), což vám umožní zhodnotit plný potenciál knihovny.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými operačními systémy?
Odpověď: Ano, Aspose.Tasks for Java je kompatibilní s různými operačními systémy, včetně Windows, macOS a Linux.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
