---
title: Zjistěte verzi MS Project pomocí Aspose.Tasks
linktitle: Určete verzi projektu pomocí Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak určit verzi souborů MS Project programově pomocí Aspose.Tasks for Java. Podrobný průvodce s příklady kódu.
type: docs
weight: 12
url: /cs/java/project-management/determine-version/
---
## Úvod
Tento tutoriál vás provede pomocí Aspose.Tasks for Java k určení verze souboru MS Project krok za krokem. Aspose.Tasks je výkonné Java API, které umožňuje vývojářům manipulovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Soubor JAR Aspose.Tasks for Java: Stáhněte si knihovnu Aspose.Tasks for Java z[webová stránka](https://releases.aspose.com/tasks/java/) a přidejte jej do svého projektu Java.
3. Soubor MS Project: Připravte soubor MS Project (formát XML) pro testování.

## Importujte balíčky
Než se ponoříme do kódu, importujme potřebné balíčky:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Krok 1: Nastavte projekt
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` s cestou k adresáři obsahujícímu váš soubor MS Project.
## Krok 2: Načtěte projekt
```java
Project project = new Project(dataDir + "input.xml");
```
 Nahradit`"input.xml"` s názvem vašeho souboru MS Project.
## Krok 3: Určete verzi projektu
```java
//Zobrazit vlastnost verze projektu
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Tento fragment kódu načte a vytiskne verzi a datum posledního uložení souboru MS Project.
## Krok 4: Zobrazení výsledku
```java
//Zobrazit výsledek konverze.
System.out.println("Process completed Successfully");
```
Tento řádek označuje dokončení procesu.

## Závěr
V tomto tutoriálu jste se naučili, jak určit verzi souboru MS Project pomocí Aspose.Tasks for Java. Dodržováním tohoto podrobného průvodce můžete efektivně pracovat se soubory MS Project ve vašich aplikacích Java bez potíží.

## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Odpověď: Ano, Aspose.Tasks podporuje více programovacích jazyků včetně .NET, Java a C++.
### Otázka: Je Aspose.Tasks vhodný pro rozsáhlé projekty?
Odpověď: Rozhodně, Aspose.Tasks je navržen tak, aby snadno zvládl projekty jakékoli velikosti.
### Otázka: Mohu přizpůsobit data projektu pomocí Aspose.Tasks?
Odpověď: Ano, pomocí Aspose.Tasks můžete manipulovat s daty projektu, upravovat úkoly, zdroje a mnoho dalšího.
### Otázka: Vyžaduje Aspose.Tasks instalaci aplikace Microsoft Project?
A: Ne, Aspose.Tasks funguje nezávisle a nevyžaduje instalaci Microsoft Project.
### Otázka: Je pro Aspose.Tasks k dispozici technická podpora?
 Odpověď: Ano, technickou podporu můžete získat na fóru Aspose.Tasks na adrese[tady](https://forum.aspose.com/c/tasks/15).