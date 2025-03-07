---
title: Psaní a čtení vzorců MS Project v Aspose.Tasks
linktitle: Pište a čtěte vzorce v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se efektivně psát a číst vzorce MS Project s Aspose.Tasks pro Javu. Vylepšete své dovednosti projektového řízení.
weight: 12
url: /cs/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Psaní a čtení vzorců MS Project v Aspose.Tasks

## Úvod
V oblasti projektového řízení je efektivní nakládání s daty prvořadé. Aspose.Tasks for Java je robustní řešení, které usnadňuje manipulaci a extrakci dat ze souborů Microsoft Project. Jednou z výkonných funkcí, které nabízí, je schopnost psát a číst vzorce MS Project. Tento výukový program vás provede procesem využití této funkce k vylepšení úkolů řízení projektů.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu.
2.  Aspose.Tasks for Java: Stáhněte si a nainstalujte Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si preferované IDE pro vývoj v Javě.

## Import balíčků
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Krok 1: Nastavte datový adresář
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
```
V tomto kroku definujte adresář, kde jsou umístěny vaše soubory MS Project.
## Krok 2: Načtěte soubor projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
Zde načtěte soubor MS Project do a`Project` objekt pro manipulaci.
## Krok 3: Definujte vlastní vzorec
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Tento krok zahrnuje vytvoření vlastního pole se vzorcem, který zdvojnásobí náklady na úkol.
## Krok 4: Přidejte úkol a nastavte cenu
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Zde je přidán nový úkol a jeho cena je nastavena na 100.
## Krok 5: Uložte soubor projektu
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Nakonec uložte upravený soubor projektu.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak psát a číst vzorce MS Project pomocí Aspose.Tasks for Java. Pomocí těchto kroků můžete efektivně manipulovat s daty projektu tak, aby splňovaly vaše specifické požadavky.
## FAQ
### Je Aspose.Tasks kompatibilní se všemi verzemi MS Project?
Aspose.Tasks nabízí kompatibilitu s různými verzemi MS Project a zajišťuje uživatelům flexibilitu.
### Mohu integrovat Aspose.Tasks do svého stávajícího projektu Java?
Absolutně! Aspose.Tasks poskytuje bezproblémovou integraci s projekty Java pomocí jednoduchého použití API.
### Existují nějaká omezení pro typy vzorců, které mohu vytvořit?
Aspose.Tasks máte rozsáhlou flexibilitu při vytváření vlastních vzorců přizpůsobených potřebám vašeho projektu.
### Podporuje Aspose.Tasks multiplatformní nasazení?
Ano, Aspose.Tasks podporuje nasazení na více platformách, což zvyšuje jeho všestrannost.
### Jak mohu získat technickou podporu pro Aspose.Tasks?
 Pro technickou pomoc a podporu komunity navštivte stránku[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
