---
title: Aktualizujte soubor MPP v Aspose.Tasks
linktitle: Aktualizujte soubor MPP v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak plynule aktualizovat soubory MPP pomocí Aspose.Tasks for Java. Postupujte podle našeho podrobného průvodce pro efektivní manipulaci se soubory projektu.
type: docs
weight: 19
url: /cs/java/project-management/update-mpp/
---
## Úvod
V oblasti projektového řízení je manipulace a aktualizace projektových souborů zásadním úkolem. Aspose.Tasks for Java poskytuje vývojářům Java výkonné řešení pro bezproblémovou manipulaci se soubory aplikace Microsoft Project. V tomto tutoriálu se ponoříme do aktualizace souborů MPP pomocí Aspose.Tasks for Java.
## Předpoklady
Než se pustíte do tohoto návodu, ujistěte se, že máte následující:
1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou Javu.
2.  Aspose.Tasks for Java: Stáhněte si a nainstalujte Aspose.Tasks for Java z[stránka ke stažení](https://releases.aspose.com/tasks/java/).
3. Základní znalost Javy: Nutná je znalost programovacího jazyka Java spolu s příklady.

## Importujte balíčky
Nejprve musíte do svého projektu Java importovat potřebné balíčky, abyste mohli efektivně využívat funkce Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Tento řádek kódu importuje všechny základní třídy a metody z knihovny Aspose.Tasks, což vám umožňuje bez námahy pracovat se soubory Microsoft Project.

Nyní si rozeberme proces aktualizace souboru MPP pomocí Aspose.Tasks for Java do zvládnutelných kroků.
## Krok 2: Definujte datový adresář
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` se skutečnou cestou, kde se nachází váš soubor MPP.
## Krok 3: Přečtěte si existující projekt
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Tento kód přečte existující soubor projektu MPP s názvem`SampleMSP2010.mpp` ze zadaného datového adresáře.
## Krok 4: Vytvořte nový úkol
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Zde přidáme novou úlohu s názvem "Task1" do kořenové úlohy projektu.
## Krok 5: Nastavte datum zahájení a ukončení
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Tyto řádky kódu nastavují datum zahájení a datum dokončení nově vytvořeného úkolu.
## Krok 6: Uložte projekt
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Nakonec tento krok uloží aktualizovaný projekt s nově přidaným úkolem do nového souboru MPP s názvem`AfterLinking.mpp`.

## Závěr
tomto tutoriálu jsme prozkoumali, jak aktualizovat soubory MPP pomocí Aspose.Tasks for Java. Podle tohoto podrobného průvodce můžete efektivně manipulovat se soubory Microsoft Project v rámci vašich aplikací Java.
## FAQ
### Otázka: Dokáže Aspose.Tasks for Java zvládnout složité projektové struktury?
Odpověď: Ano, Aspose.Tasks for Java poskytuje robustní funkce pro efektivní zpracování složitých projektových struktur.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[webová stránka](https://releases.aspose.com/).
### Otázka: Podporuje Aspose.Tasks for Java různé verze souborů Microsoft Project?
Odpověď: Aspose.Tasks for Java rozhodně podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.
### Otázka: Mohu získat dočasné licence pro Aspose.Tasks pro Java?
 Odpověď: Ano, pro testovací účely jsou k dispozici dočasné licence. Můžete je získat z[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu hledat pomoc nebo podporu týkající se Aspose.Tasks for Java?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.