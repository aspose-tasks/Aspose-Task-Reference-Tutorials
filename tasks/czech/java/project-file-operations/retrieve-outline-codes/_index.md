---
title: Získejte kódy osnovy MS Project v Aspose.Tasks
linktitle: Získejte obrysové kódy v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak programově načíst kódy osnovy Microsoft Project pomocí Aspose.Tasks for Java. Vylepšete své schopnosti projektového řízení.
weight: 15
url: /cs/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získejte kódy osnovy MS Project v Aspose.Tasks

## Úvod
tomto tutoriálu se naučíme, jak získat obrysové kódy aplikace Microsoft Project pomocí Aspose.Tasks for Java. Obrysové kódy v MS Project poskytují strukturovaný způsob, jak kategorizovat a organizovat projektové úkoly, zdroje a přiřazení. Aspose.Tasks je výkonná knihovna Java, která umožňuje vývojářům manipulovat a spravovat soubory Microsoft Project programově.
## Předpoklady
Než začneme, ujistěte se, že máte nastaveny následující předpoklady:
### 1. Vývojové prostředí Java
Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK). JDK si můžete stáhnout a nainstalovat z webu Oracle.
### 2. Aspose.Tasks Library
 Stáhněte si a zahrňte knihovnu Aspose.Tasks do svého projektu Java. Knihovnu si můžete stáhnout z[Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Nejprve importujte potřebné balíčky z Aspose.Tasks v kódu Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Nyní rozdělíme poskytnutý příklad kódu do několika kroků:
## Krok 1: Načtěte projekt
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 V tomto kroku načteme soubor Microsoft Project do a`Project` objekt pomocí poskytnutého názvu souboru.
## Krok 2: Načtěte obrysové kódy
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Opakujeme každou definici kódu osnovy v projektu.
## Krok 3: Přístup k vlastnostem kódu osnovy
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Načítáme a tiskneme různé vlastnosti definice kódu osnovy, jako je Alias, ID pole a Název pole.
## Krok 4: Zkontrolujte vlastní kód podniku
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Zkontrolujeme, zda je kód osnovy firemním uživatelským kódem, a podle toho vytiskneme výsledek.
## Krok 5: Zobrazte masky obrysového kódu
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iterujeme každou masku spojenou s kódem osnovy a vytiskneme její úroveň a hodnotu masky.
## Krok 6: Zobrazte hodnoty obrysového kódu
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Každou hodnotu kódu osnovy iterujeme a vytiskneme její popis, ID hodnoty, hodnotu a typ.
## Závěr
V tomto tutoriálu jsme se naučili, jak získat obrysové kódy MS Project pomocí Aspose.Tasks pro Java. Dodržováním uvedených kroků můžete efektivně přistupovat a manipulovat s obrysovými kódy ve vašich aplikacích Java, což umožňuje pokročilé možnosti správy projektů.
## FAQ
### Q1: Mohu použít Aspose.Tasks for Java k úpravě kódů osnovy v souboru projektu?
Odpověď: Ano, Aspose.Tasks for Java poskytuje rozhraní API pro programovou úpravu kódů osnovy v souborech MS Project.
### Q2: Je k dispozici zkušební verze pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks for Java z webu[Web Aspose.Tasks](https://releases.aspose.com/).
### Q3: Jak mohu získat technickou podporu pro Aspose.Tasks pro Java?
 Odpověď: Technickou podporu získáte na adrese[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) a zveřejňovat tam své dotazy.
### Q4: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete si zakoupit dočasnou licenci pro Aspose.Tasks for Java z[nákupní stránku](https://purchase.aspose.com/temporary-license/).
### Q5: Kde najdu kompletní dokumentaci k Aspose.Tasks for Java?
 A: Můžete odkazovat na[dokumentace](https://reference.aspose.com/tasks/java/) pro podrobné informace o používání Aspose.Tasks for Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
