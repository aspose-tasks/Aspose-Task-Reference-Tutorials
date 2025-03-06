---
title: Vzorce MS Project s Aspose.Tasks pro Javu
linktitle: Práce se vzorci v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se manipulovat se soubory MS Project v Javě pomocí knihovny Aspose.Tasks. Snadno vytvářejte, upravujte a vypočítávejte atributy.
type: docs
weight: 11
url: /cs/java/formulas/work-with-formulas/
---
## Úvod
V tomto tutoriálu se ponoříme do práce se vzorci MS Project pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonná knihovna, která umožňuje vývojářům programově manipulovat se soubory Microsoft Project. Díky rozsáhlým funkcím můžete snadno vytvářet, číst, upravovat a převádět soubory projektů v aplikacích Java.
## Předpoklady
Než začneme, ujistěte se, že máte nastaveny následující předpoklady:
### Vývojové prostředí Java
Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK). Nejnovější JDK si můžete stáhnout a nainstalovat z webu Oracle.
### Aspose.Tasks Library
Musíte mít knihovnu Aspose.Tasks přidanou do vašeho projektu Java. Knihovnu si můžete stáhnout z[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) a zahrňte jej do závislostí vašeho projektu.

## Importujte balíčky
Než se ponoříte do příkladů, importujte potřebné balíčky do kódu Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Rozdělme uvedený příklad do několika kroků:
## Krok 1: Vytvořte testovací projekt s vlastním polem
```java
Project project = CreateTestProjectWithCustomField();
```
 Nejprve vytvořte testovací projekt s vlastním polem pomocí`CreateTestProjectWithCustomField()` metoda. Tato metoda vrátí objekt Project představující nově vytvořený projekt.
## Krok 2: Definujte definici rozšířeného atributu
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Načtěte definici rozšířeného atributu z projektu a nastavte jeho alias a vzorec. V tomto příkladu definujeme atribut pro výpočet počtu dní od data dokončení do termínu.
## Krok 3: Nastavte konečný termín pro úkol
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Vytvořte objekt kalendáře a nastavte datum uzávěrky. Poté načtěte úkol z projektu a nastavte jeho termín pomocí objektu Kalendář.
## Krok 4: Uložte projekt
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Nakonec projekt uložte do souboru se zadaným názvem a formátem. V tomto případě jej ukládáme jako soubor MPP.

## Závěr
V tomto tutoriálu jsme se naučili pracovat se vzorci MS Project pomocí Aspose.Tasks for Java. Pomocí těchto kroků můžete efektivně programově manipulovat se soubory projektu, přidávat vlastní pole a počítat atributy na základě vzorců.

## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Odpověď: Ano, Aspose.Tasks podporuje různé programovací jazyky včetně Java, .NET a dalších.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).
### Otázka: Kde najdu dokumentaci k Aspose.Tasks?
 Odpověď: Můžete najít dokumentaci k Aspose.Tasks[tady](https://reference.aspose.com/tasks/java/).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks?
 Odpověď: Pro podporu můžete navštívit stránku[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Otázka: Potřebuji dočasnou licenci pro používání Aspose.Tasks?
Odpověď: Pokud požadujete další funkce, můžete získat dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).