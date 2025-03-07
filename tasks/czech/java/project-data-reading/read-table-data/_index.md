---
title: Přečtěte si data tabulky ze souboru v Aspose.Tasks
linktitle: Přečtěte si data tabulky ze souboru v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Odemkněte sílu Aspose.Tasks for Java. Naučte se extrahovat data tabulky ze souborů v tomto komplexním kurzu.
weight: 17
url: /cs/java/project-data-reading/read-table-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přečtěte si data tabulky ze souboru v Aspose.Tasks

## Úvod
tomto tutoriálu prozkoumáme, jak číst data tabulky ze souboru pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonná Java knihovna, která umožňuje vývojářům pracovat s dokumenty Microsoft Project programově.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout a nainstalovat z webu Oracle.
2.  Aspose.Tasks for Java JAR File: Stáhněte si knihovnu Aspose.Tasks for Java z[odkaz ke stažení](https://releases.aspose.com/tasks/java/) a zahrňte jej do svého projektu Java.

## Importujte balíčky
Importujte potřebné balíčky pro práci s Aspose.Tasks ve vašem projektu Java:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## Krok 1: Nastavte Data Directory
Definujte cestu k adresáři, kde je umístěn váš projektový soubor:
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` se skutečnou cestou k vašemu datovému adresáři.
## Krok 2: Načtěte soubor projektu
Načtěte soubor projektu pomocí Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Nezapomeňte vyměnit`"Project2003.mpp"` s názvem souboru projektu.
## Krok 3: Načtěte informace o tabulce
Získejte tabulku z projektu a iterujte jejími poli:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Tento fragment kódu načte informace o polích tabulky, jako je šířka, nadpis a zarovnání.

## Závěr
tomto tutoriálu jsme se naučili číst data tabulky ze souboru pomocí Aspose.Tasks for Java. Pomocí těchto kroků můžete efektivně extrahovat a manipulovat s daty z dokumentů Microsoft Project ve vašich aplikacích Java.
## FAQ
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
Odpověď: Aspose.Tasks podporuje různé verze Microsoft Project, včetně Project 2003, 2007, 2010, 2013 a 2016.
### Otázka: Mohu upravit data tabulky a uložit je zpět do souboru projektu?
Odpověď: Ano, můžete použít Aspose.Tasks k programové úpravě dat tabulky a uložení změn do původního souboru projektu.
### Otázka: Vyžaduje Aspose.Tasks samostatnou licenci pro komerční použití?
 Odpověď: Ano, musíte si zakoupit licenci pro Aspose.Tasks, pokud jej zamýšlíte používat v komerčním prostředí. Licenci můžete získat od[nákupní stránku](https://purchase.aspose.com/buy).
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z[stránka vydání](https://releases.aspose.com/).
### Otázka: Kde najdu pomoc a podporu pro Aspose.Tasks?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)za pomoc a podporu od komunity a týmu Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
