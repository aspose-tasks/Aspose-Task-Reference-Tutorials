---
title: Zpracování rozšířených atributů v projektech Aspose.Tasks
linktitle: Zpracování rozšířených atributů v projektech Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně zacházet s rozšířenými atributy v projektech Aspose.Tasks pomocí Javy. Návod krok za krokem pro efektivní řízení projektů.
type: docs
weight: 13
url: /cs/java/project-management/extended-attributes/
---
## Úvod
Správa rozšířených atributů v projektovém řízení je zásadní pro přizpůsobení a vylepšení projektových dat. Aspose.Tasks for Java poskytuje robustní nástroje pro efektivní zpracování rozšířených atributů v souborech MS Project. Tento tutoriál vás provede procesem krok za krokem a zajistí, že důkladně pochopíte každý koncept.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1. Základní znalost programování v Javě.
2. JDK (Java Development Kit) nainstalovaný ve vašem systému.
3. Knihovna Aspose.Tasks pro Java byla stažena a nastavena ve vašem projektu Java.
## Importujte balíčky
Nejprve naimportujte potřebné balíčky, abyste mohli začít:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## Krok 1: Definujte datový adresář
```java
String dataDir = "Your Data Directory";
```
 Zajistěte výměnu`"Your Data Directory"` s cestou k datovému adresáři vašeho projektu.
## Krok 2: Načtěte soubor projektu
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 Tento řádek načte soubor projektu s názvem`"project5.mpp"`.
## Krok 3: Přístup k rozšířeným definicím atributů
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
Zde načteme kolekci definic rozšířených atributů z projektu.
## Krok 4: Vytvořte rozšířenou definici atributu
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 Tento segment kódu vytváří definici rozšířeného atributu pro úkoly, která určuje typ vlastního pole jako`Start` a název atributu jako`"Start 7"`.
## Krok 5: Přidejte definici do projektu
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
Nově vytvořenou definici rozšířeného atributu přidáváme do projektu i kolekce definic atributů.
## Krok 6: Přístup k úloze a rozšířeným atributům
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
Zde načteme úkol z projektu a jeho přidružené rozšířené atributy.
## Krok 7: Vytvořte rozšířenou instanci atributů
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
Tento krok vytvoří instanci rozšířeného atributu na základě dříve definované definice atributu.
## Krok 8: Nastavte hodnotu atributu
```java
Date date = new Date();
ea.setDateValue(date);
```
Nastavíme hodnotu rozšířeného atributu, v tomto případě hodnotu data.
## Krok 9: Přidejte atribut do úkolu
```java
eas.add(ea);
```
Nakonec do úkolu přidáme rozšířený atribut.
## Krok 10: Uložte projekt
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
Tento řádek uloží upravený projekt s přidaným rozšířeným atributem do souboru XML.
## Závěr
V tomto tutoriálu jste se naučili, jak zacházet s rozšířenými atributy v projektech Aspose.Tasks pomocí Javy. Pomocí těchto kroků můžete efektivně spravovat vlastní projektová data a rozšiřovat tak možnosti řízení projektů.
## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Odpověď: Ano, Aspose.Tasks podporuje více programovacích jazyků včetně Java, .NET a C++.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z webu Aspose.Tasks.
### Otázka: Mohu přizpůsobit typy rozšířených atributů?
Odpověď: Aspose.Tasks vám samozřejmě umožňuje definovat vlastní typy rozšířených atributů přizpůsobené potřebám vašeho projektu.
### Otázka: Jak mohu získat přístup k dokumentaci Aspose.Tasks?
 Odpověď: Komplexní dokumentaci najdete na webu Aspose.Tasks[dokumentace](https://reference.aspose.com/tasks/java/).
### Otázka: Je pro uživatele Aspose.Tasks k dispozici technická podpora?
 Odpověď: Ano, k technické podpoře můžete přistupovat prostřednictvím fóra Aspose.Tasks[webová stránka](https://forum.aspose.com/c/tasks/15).