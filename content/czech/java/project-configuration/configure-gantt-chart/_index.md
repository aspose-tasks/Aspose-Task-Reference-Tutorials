---
title: Konfigurace zobrazení Ganttova diagramu v projektech Aspose.Tasks
linktitle: Konfigurace zobrazení Ganttova diagramu v projektech Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se konfigurovat zobrazení Gantt MS Project Chart v Aspose.Tasks pomocí Javy. Přizpůsobte si projekt a vizualizujte je v Ganttově diagramu krok za krokem.
type: docs
weight: 10
url: /cs/java/project-configuration/configure-gantt-chart/
---
## Úvod
V tomto tutoriálu se naučíte, jak nakonfigurovat zobrazení Gantt MS Project Chart v projektech Aspose.Tasks pomocí Javy. Aspose.Tasks je výkonné Java API, které vám umožňuje programově pracovat se soubory Microsoft Project. Podle těchto kroků budete moci upravit zobrazení Ganttova diagramu podle požadavků vašeho projektu.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu.
2.  Knihovna Aspose.Tasks: Stáhněte a nainstalujte knihovnu Aspose.Tasks. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si IDE podle svého výběru. Tento tutoriál používá IntelliJ IDEA, ale můžete použít jakékoli IDE, které vám vyhovuje.
## Importujte balíčky
Nejprve musíte importovat potřebné balíčky pro práci s Aspose.Tasks ve vašem projektu Java. Přidejte do svého souboru Java následující příkazy pro import:
```java
import com.aspose.tasks.*;
```
Nyní si rozeberme proces konfigurace zobrazení Gantt MS Project Chart na podrobné pokyny:
## Krok 1: Nastavte datový adresář
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` s cestou k adresáři projektových dat.
## Krok 2: Načtěte soubor projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
Načtěte soubor projektu (`project.mpp` v tomto příkladu) pomocí`Project` třídy z Aspose.Tasks.
## Krok 3: Přidejte novou aktivitu
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Vytvořte nový úkol ve svém projektu pomocí`Task` třídu a přidejte ji k dětem kořenového úkolu.
## Krok 4: Definujte vlastní atribut
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Definujte nový vlastní atribut pomocí`ExtendedAttributeDefinition`třídy a přidejte ji do rozšířených atributů projektu.
## Krok 5: Přidejte do úkolu vlastní atribut
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Přidejte vlastní atribut do vytvořené úlohy pomocí`createExtendedAttribute` metoda.
## Krok 6: Přizpůsobte tabulku
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Přizpůsobte tabulku přidáním pole textového atributu se zadanou šířkou, nadpisem a zarovnáním.
## Krok 7: Uložte projekt
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Uložte projekt pomocí nakonfigurovaného zobrazení grafu Gantt MS Project Chart. Výsledný soubor lze otevřít v aplikaci Microsoft Project 2010.
## Závěr
Gratulujeme! Úspěšně jste nakonfigurovali zobrazení grafu Gantt MS Project Chart v projektech Aspose.Tasks pomocí Java. Nyní můžete přizpůsobit atributy projektu a vizualizovat je v Ganttově diagramu podle potřeb vašeho projektu.
## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Odpověď: Ano, Aspose.Tasks je k dispozici pro více programovacích jazyků včetně .NET, Java a C++.
### Otázka: Je pro Aspose.Tasks k dispozici nějaká bezplatná zkušební verze?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Kde najdu podporu pro Aspose.Tasks?
Odpověď: Podporu a dotazy můžete najít na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Otázka: Jak si mohu zakoupit licenci pro Aspose.Tasks?
 Odpověď: Můžete si zakoupit licenci od[tady](https://purchase.aspose.com/buy).
### Otázka: Potřebuji dočasnou licenci pro testovací účely?
 Odpověď: Ano, můžete získat dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).