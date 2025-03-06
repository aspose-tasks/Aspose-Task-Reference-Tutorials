---
title: Vytvořte plán úloh MS Project v Aspose.Tasks
linktitle: Vytvoření základního plánu úkolu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak vytvořit základní plán úloh Microsoft Project v Javě pomocí Aspose.Tasks, výkonné knihovny pro snadnou správu projektových dat.
type: docs
weight: 11
url: /cs/java/task-baselines/create-task-baseline/
---
## Úvod
tomto tutoriálu se ponoříme do procesu vytváření základního plánu úkolů Microsoft Project pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonná knihovna Java, která umožňuje vývojářům pracovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project. S Aspose.Tasks můžete bez námahy manipulovat s projektovými daty, včetně úkolů, zdrojů a kalendářů, a zjednodušit tak úkoly projektového řízení.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Aspose.Tasks for Java vyžaduje na vašem systému nainstalovaný JDK. JDK si můžete stáhnout a nainstalovat z webu Oracle.
2.  Aspose.Tasks for Java Library: Stáhněte si knihovnu Aspose.Tasks for Java z[odkaz ke stažení](https://releases.aspose.com/tasks/java/) pokud.

## Importujte balíčky
Chcete-li začít pracovat s Aspose.Tasks ve svém projektu Java, importujte potřebné balíčky:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Krok 1: Vytvořte objekt projektu
```java
Project project = new Project();
```
 Nejprve vytvořte nový`Project` objekt. Tento objekt představuje soubor Microsoft Project, se kterým budete pracovat.
## Krok 2: Přidejte do projektu úkol
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Za použití`getRootTask()` zpřístupněte kořenovou úlohu projektu a poté do ní přidejte novou úlohu pomocí`add()` metoda. Zadejte název úkolu v závorkách.
## Krok 3: Nastavte základní plán pro zadané úkoly
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Chcete-li nastavit směrný plán pro konkrétní úkoly, vytvořte seznam úkolů (`myList` v tomto případě) a naplňte jej úkoly, pro které chcete nastavit základní linii. Poté použijte`setBaseline()` s uvedením základního typu a seznamu úkolů.
## Krok 4: Nastavte základní plán pro celý projekt
```java
project.setBaseline(BaselineType.Baseline);
```
 Případně můžete nastavit základní linii pro celý projekt jednoduše zavoláním na`setBaseline()` metoda se zadaným typem základní linie.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak vytvořit základní plán úloh aplikace Microsoft Project pomocí Aspose.Tasks for Java. Podle výše uvedených kroků můžete efektivně spravovat projektová data a snadno zjednodušit úkoly projektového řízení.
## FAQ
### Mohu používat Aspose.Tasks pro Javu bez nainstalovaného Microsoft Project?
Ano, Aspose.Tasks for Java vám umožňuje pracovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project do vašeho systému.
### Je Aspose.Tasks for Java kompatibilní s různými verzemi Microsoft Project?
Ano, Aspose.Tasks for Java podporuje různé verze Microsoft Project a zajišťuje kompatibilitu v různých prostředích.
### Mohu manipulovat se zdroji projektu pomocí Aspose.Tasks for Java?
Aspose.Tasks for Java rozhodně poskytuje robustní funkce pro manipulaci se zdroji projektu, včetně přidávání, aktualizace a odstraňování zdrojů podle potřeby.
### Podporuje Aspose.Tasks pro Java nastavení závislostí úloh?
Ano, pomocí Aspose.Tasks for Java můžete snadno nastavit závislosti úkolů, což vám umožní stanovit pořadí úkolů v rámci vašeho projektu.
### Je k dispozici technická podpora pro Aspose.Tasks for Java?
 Ano, k technické podpoře Aspose.Tasks pro Javu můžete přistupovat prostřednictvím[Fórum podpory](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a hledat pomoc od komunity a pracovníků podpory Aspose.