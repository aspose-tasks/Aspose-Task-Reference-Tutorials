---
title: Vypočítat kritickou cestu projektu MS v Aspose.Tasks
linktitle: Vypočítat kritickou cestu v projektech Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se vypočítat kritickou cestu v MS Project pomocí Aspose.Tasks for Java. To poskytuje návod krok za krokem pro efektivní řízení projektu.
weight: 10
url: /cs/java/project-management/critical-path/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vypočítat kritickou cestu projektu MS v Aspose.Tasks

## Úvod
V tomto tutoriálu vás provedeme procesem výpočtu kritické cesty v MS Project pomocí Aspose.Tasks for Java. Kritická cesta je nezbytná pro projektové řízení, protože pomáhá identifikovat posloupnost úkolů, které je třeba dokončit včas, aby se zajistilo, že se celkový harmonogram projektu nezdrží.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Knihovna Aspose.Tasks pro Java byla stažena a přidána do vašeho projektu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do třídy Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Nastavte datový adresář
Definujte cestu k datovému adresáři, kde je umístěn váš soubor MS Project.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Načtěte soubor MS Project
Načtěte soubor MS Project pomocí knihovny Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Krok 3: Nastavte režim výpočtu
Chcete-li povolit výpočet kritické cesty, nastavte režim výpočtu na automatický.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## Krok 4: Přidejte úkoly
Přidejte úkoly do svého projektu. V tomto příkladu přidáme tři dílčí úkoly.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## Krok 5: Vytvořte odkazy na úkoly
Vytvořte odkazy na úkoly a definujte závislosti mezi úkoly.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## Krok 6: Zobrazte kritickou cestu
Načtěte a zobrazte kritickou cestu projektu.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## Krok 7: Zobrazení výsledku
Zobrazte zprávu o úspěšném dokončení procesu.
```java
System.out.println("Process completed Successfully");
```

## Závěr
Výpočet kritické cesty v MS Project pomocí Aspose.Tasks pro Java je zásadní pro efektivní řízení projektu. Podle kroků uvedených v tomto kurzu můžete přesně identifikovat posloupnost úkolů kritických pro časovou osu vašeho projektu.
## FAQ
### Otázka: Mohu použít Aspose.Tasks pro Javu s jakoukoli verzí souborů MS Project?
Odpověď: Ano, Aspose.Tasks for Java podporuje různé verze souborů MS Project, včetně souborů .mpp z MS Project 2003 až MS Project 2019.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Kde najdu podporu pro Aspose.Tasks for Java?
 A: Podporu najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks for Java?
 Odpověď: Ano, můžete si zakoupit dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Jak si mohu koupit Aspose.Tasks pro Java?
 Odpověď: Aspose.Tasks pro Javu si můžete zakoupit na webu[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
