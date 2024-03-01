---
title: Podpora funkcí hodnocení ve vzorcích Aspose.Tasks
linktitle: Podpora funkcí hodnocení ve vzorcích Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak podporovat hodnocení funkcí MS Project ve vzorcích Aspose.Tasks pomocí Javy. Zvyšte svou produktivitu pomocí Aspose.Tasks.
type: docs
weight: 10
url: /cs/java/formulas/evaluation-functions/
---

## Úvod
Aspose.Tasks for Java je výkonná knihovna, která umožňuje vývojářům programově manipulovat se soubory Microsoft Project. Jednou z jeho klíčových vlastností je schopnost podporovat hodnocení funkcí MS Project v rámci vzorců Aspose.Tasks. Tato schopnost umožňuje uživatelům provádět složité výpočty a analýzy přímo v aplikacích Java.
## Předpoklady
Než začnete s integrací funkcí MS Project do vzorců Aspose.Tasks, ujistěte se, že máte následující:
1. Vývojové prostředí Java: Ujistěte se, že máte na svém systému nainstalovanou Javu spolu s kompatibilním IDE pro vývoj v Javě, jako je IntelliJ IDEA nebo Eclipse.
2.  Knihovna Aspose.Tasks for Java: Stáhněte si a zahrňte knihovnu Aspose.Tasks for Java do svého projektu Java. Můžete si jej stáhnout z[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do vaší třídy Java, abyste mohli využívat funkce Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Krok 1: Vytvořte nový objekt projektu
 Nejprve vytvořte nový`Project`objekt, se kterým se má pracovat:
```java
Project project = new Project();
```
Tím se inicializuje nový prázdný projekt.
## Krok 2: Definujte rozšířený atribut pro úkoly
Dále definujte rozšířený atribut pro úkoly. Tento atribut bude obsahovat vlastní data spojená s úkoly:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Zde vytvoříme rozšířený atribut typu`Number` s názvem "Sinus" pro úkoly.
## Krok 3: Přidejte do projektu rozšířený atribut
Přidejte definici rozšířeného atributu do seznamu rozšířených atributů projektu:
```java
project.getExtendedAttributes().add(attr);
```
Tím se do projektu přidá vlastní atribut.
## Krok 4: Vytvořte nový úkol
Nyní vytvoříme nový úkol v rámci projektu:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Tím se do projektu přidá nový úkol s názvem "Task".
## Krok 5: Přiřaďte rozšířený atribut k úkolu
Přidružte dříve vytvořený rozšířený atribut k úkolu:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
To přidruží rozšířený atribut "Sine" k úkolu.

## Závěr
Závěrem lze říci, že integrace funkcí MS Project do vzorců Aspose.Tasks v Javě je přímočarý proces. Dodržováním uvedených kroků můžete efektivně využívat výkonné možnosti Aspose.Tasks for Java k programové manipulaci a analýze souborů Microsoft Project.
## FAQ
### Otázka: Dokáže Aspose.Tasks for Java zpracovat složité vzorce MS Project?
Odpověď: Ano, Aspose.Tasks for Java podporuje vyhodnocování široké škály funkcí MS Project, což umožňuje složité výpočty v aplikacích Java.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými verzemi souborů Microsoft Project?
Odpověď: Ano, Aspose.Tasks for Java podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.
### Otázka: Mohu před nákupem vyzkoušet Aspose.Tasks for Java?
 Odpověď: Ano, z webu si můžete stáhnout bezplatnou zkušební verzi Aspose.Tasks for Java[tady](https://purchase.aspose.com/buy).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks pro Java?
Odpověď: Podporu můžete získat na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Je k dispozici dočasná licence pro Aspose.Tasks for Java?
 Odpověď: Ano, dočasnou licenci pro testovací účely můžete získat z webu Aspose[tady](https://purchase.aspose.com/temporary-license/).