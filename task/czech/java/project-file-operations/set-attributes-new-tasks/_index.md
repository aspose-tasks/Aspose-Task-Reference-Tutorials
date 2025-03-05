---
title: Nastavení atributů MS Project pro nové úkoly v Aspose.Tasks
linktitle: Nastavte atributy pro nové úkoly v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak nastavit atributy MS Project pro nové úkoly pomocí Aspose.Tasks for Java. Pomocí tohoto komplexního průvodce si snadno přizpůsobte vlastnosti úkolu.
type: docs
weight: 21
url: /cs/java/project-file-operations/set-attributes-new-tasks/
---
## Úvod
Vítejte v našem komplexním tutoriálu o nastavení atributů MS Project pro nové úkoly v Aspose.Tasks pro Java! V této příručce vás provedeme procesem krok za krokem a zajistíme, že můžete snadno spravovat a přizpůsobovat své úkoly pomocí této výkonné knihovny Java.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Vývojové prostředí Java: Ujistěte se, že máte na svém systému nainstalovanou Javu a že jste obeznámeni se základními koncepty programování Java.
2.  Aspose.Tasks for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java z[odkaz ke stažení](https://releases.aspose.com/tasks/java/).
3. Java IDE: Zvolte Java Integrated Development Environment (IDE), jako je Eclipse nebo IntelliJ IDEA pro kódování.

## Importujte balíčky
Než začneme nastavovat atributy MS Project pro nové úkoly, importujme potřebné balíčky:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## Krok 1: Definujte datový adresář
Nejprve zadejte cestu k adresáři, kam chcete uložit soubory projektu:
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` s cestou k požadovanému adresáři.
## Krok 2: Vytvořte instanci projektu
Vytvořte instanci nového objektu projektu, abyste mohli začít pracovat s projektem:
```java
Project prj = new Project();
```
Tím se vytvoří nová instance projektu.
## Krok 3: Nastavte novou vlastnost úlohy
Nyní nastavíme datum zahájení nových úkolů. V tomto příkladu jej nastavíme na aktuální datum:
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
 Tento řádek nastavuje vlastnost`NEW_TASK_START_DATE` na`TaskStartDateType.CurrentDate`.
## Krok 4: Uložte projekt
Uložte projekt s novými atributy úkolu ve formátu XML:
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Tento řádek uloží projekt se zadaným názvem souboru do adresáře definovaného dříve.
## Krok 5: Zobrazení výsledku
Nakonec vytiskněme zprávu, která potvrdí, že soubor projektu byl úspěšně vygenerován:
```java
System.out.println("Project file generated Successfully");
```
Tento řádek zobrazuje zprávu o úspěchu v konzole.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak nastavit atributy MS Project pro nové úkoly pomocí Aspose.Tasks for Java. S těmito znalostmi nyní můžete upravit vlastnosti úlohy podle svých požadavků a rozšířit tak možnosti řízení projektů.
## FAQ
### Otázka: Mohu použít Aspose.Tasks for Java k manipulaci se stávajícími soubory projektu?
Odpověď: Ano, Aspose.Tasks for Java poskytuje rozsáhlé funkce pro manipulaci se stávajícími soubory projektu, včetně jejich čtení, úprav a ukládání v různých formátech.
### Otázka: Kde najdu další dokumentaci a zdroje pro Aspose.Tasks for Java?
 Odpověď: Dokumentaci a zdroje můžete prozkoumat na[Aspose.Tasks pro stránku dokumentace Java](https://reference.aspose.com/tasks/java/).
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks for Java z[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat dočasné licence pro Aspose.Tasks for Java?
 A: Dočasné licence pro Aspose.Tasks for Java lze získat z[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu získat podporu pro jakékoli problémy nebo dotazy související s Aspose.Tasks for Java?
 Odpověď: Můžete získat podporu a komunikovat s komunitou na[Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15).