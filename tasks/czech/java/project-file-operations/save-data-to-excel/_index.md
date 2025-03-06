---
title: Uložit data MS Project do Excelu v Aspose.Tasks
linktitle: Uložit data do Excelu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se ukládat data aplikace Microsoft Project do souborů Excel pomocí Aspose.Tasks for Java. Snadná integrace pro vývojáře v Javě.
type: docs
weight: 19
url: /cs/java/project-file-operations/save-data-to-excel/
---
## Úvod
Aspose.Tasks for Java je výkonná knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project programově. V tomto tutoriálu vás krok za krokem provedeme procesem ukládání dat ze souboru projektu do souboru aplikace Excel.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Java. Nejnovější verzi JDK si můžete stáhnout a nainstalovat z webu Oracle.
2.  Aspose.Tasks for Java Library: Stáhněte si knihovnu Aspose.Tasks for Java z[odkaz ke stažení](https://releases.aspose.com/tasks/java/) a zahrňte jej do svého projektu Java.

## Importujte balíčky
Nejprve musíte do kódu Java importovat potřebné balíčky, abyste mohli pracovat s Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Rozdělme poskytnutý příklad do několika kroků:
## Krok 1: Definujte cestu k datovému adresáři
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` cestou k vašemu datovému adresáři, kde je umístěn soubor projektu.
## Krok 2: Načtěte soubor projektu
```java
Project project = new Project(dataDir + "project5.mpp");
```
Tento řádek kódu načte soubor projektu s názvem "project5.mpp" ze zadaného datového adresáře.
## Krok 3: Uložte projekt jako XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Tady,`save` metoda se používá k uložení načteného souboru projektu jako souboru aplikace Excel s názvem "project1.xlsx" ve stejném datovém adresáři. Upřesňujeme`SaveFileFormat.Xlsx` parametr pro uložení ve formátu XLSX.

## Závěr
V tomto tutoriálu jsme se naučili, jak uložit data ze souboru Microsoft Project do souboru Excel pomocí Aspose.Tasks for Java. Dodržováním uvedených kroků můžete tuto funkci bez problémů integrovat do svých aplikací Java.
## FAQ
### Mohu použít Aspose.Tasks for Java k programové manipulaci s daty projektu?
Ano, Aspose.Tasks for Java poskytuje rozsáhlé funkce pro manipulaci s projektovými daty, včetně čtení, zápisu a úprav projektových souborů.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks for Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks for Java z[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Tasks for Java?
Můžete najít dokumentaci k Aspose.Tasks for Java[tady](https://reference.aspose.com/tasks/java/).
### Jak mohu získat podporu pro jakékoli problémy nebo dotazy související s Aspose.Tasks for Java?
 Podporu můžete získat návštěvou fóra Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Mohu si zakoupit dočasnou licenci pro Aspose.Tasks for Java?
 Ano, můžete si zakoupit dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).