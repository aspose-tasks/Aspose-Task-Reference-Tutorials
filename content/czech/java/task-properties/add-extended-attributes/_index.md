---
title: Přidejte rozšířené atributy do úkolů v Aspose.Tasks
linktitle: Přidejte rozšířené atributy do úkolů v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte sílu Aspose.Tasks Java při přizpůsobování souborů aplikace Microsoft Project s rozšířenými atributy. Vylepšete své možnosti řízení projektů bez námahy.
type: docs
weight: 11
url: /cs/java/task-properties/add-extended-attributes/
---
## Úvod
Pro efektivní sledování úkolů a správu zdrojů je zásadní vylepšit schopnosti řízení projektů. Aspose.Tasks for Java poskytuje vývojářům Java výkonné řešení pro bezproblémovou manipulaci se soubory aplikace Microsoft Project. V tomto tutoriálu prozkoumáme, jak přidat rozšířené atributy k úlohám pomocí Aspose.Tasks for Java, což vám umožní přizpůsobit a organizovat data projektu podle vašich specifických požadavků.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Tasks pro Java. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/tasks/java/).
- Java Integrated Development Environment (IDE) nainstalované ve vašem systému.
## Importujte balíčky
Ve svém projektu Java importujte potřebné balíčky pro přístup k funkcím Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Nyní si každý příklad rozdělíme do několika kroků:
## 1. Přidání atributu prostého textu
1. Nastavte cestu k adresáři dokumentu:
```java
String dataDir = "Your Document Directory";
```
2. Vytvořte nový projekt:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Vytvořte rozšířenou definici atributu typu Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Přidejte definici do kolekce Extended Attributes projektu:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Přidejte úkol do projektu:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Vytvořte rozšířený atribut z definice atributu:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Přiřaďte hodnotu vygenerovanému rozšířenému atributu:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Přidejte k úkolu rozšířený atribut:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Uložte projekt:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Přidání textového atributu s možností vyhledávání
Postupujte podle stejných kroků jako výše, nahraďte Text1 textem Text2 a přizpůsobte hodnoty vyhledávání.
## 3. Přidání atributu trvání s možností vyhledávání
Postupujte podle stejných kroků jako výše, nahraďte Text1 hodnotou Duration2 a přizpůsobte hodnoty vyhledávání.
## Závěr
Podle tohoto podrobného průvodce jste se naučili, jak využít Aspose.Tasks for Java k přidání rozšířených atributů k úkolům v souborech aplikace Microsoft Project. Toto přizpůsobení vám umožní přizpůsobit váš přístup k řízení projektů a zvýšit flexibilitu a efektivitu.
## Často kladené otázky
### Otázka: Mohu používat Aspose.Tasks for Java s jinými knihovnami Java?
Odpověď: Ano, Aspose.Tasks for Java lze bez problémů integrovat do vašich projektů Java a funguje dobře s jinými knihovnami Java.
### Otázka: Je Aspose.Tasks for Java vhodný pro aplikace řízení rozsáhlých projektů?
Odpověď: Rozhodně, Aspose.Tasks for Java je navržen tak, aby zvládal projekty různých velikostí, včetně rozsáhlých aplikací.
### Otázka: Existují nějaké licenční úvahy pro použití Aspose.Tasks for Java v komerčním projektu?
 Odpověď: Ano, nezapomeňte si přečíst licenční informace uvedené na webu[Web Aspose.Tasks](https://purchase.aspose.com/buy).
### Otázka: Jak mohu získat podporu nebo pomoc s Aspose.Tasks for Java?
 A: Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a diskuze.
### Otázka: Mohu před nákupem vyzkoušet Aspose.Tasks for Java?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).