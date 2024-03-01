---
title: Zvládnutí manipulace s MS Project s Aspose.Tasks pro Javu
linktitle: Přidejte rozšířené atributy do přiřazení prostředků v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně psát informace z MS Project pomocí Aspose.Tasks for Java. Podrobný průvodce pro vývojáře Java.
type: docs
weight: 10
url: /cs/java/resource-assignments/add-extended-attributes/
---
## Úvod
V tomto tutoriálu se ponoříme do využití Aspose.Tasks for Java, výkonné knihovny pro programovou manipulaci se soubory Microsoft Project. Zaměříme se na základní úkol: psaní informací z MS Project pomocí Aspose.Tasks. Ať už jste ostřílený vývojář nebo teprve začínáte svou cestu v programování Java, tento průvodce vás provede procesem krok za krokem.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java. Můžete jej získat z[tady](https://releases.aspose.com/tasks/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si IDE podle svých preferencí. Doporučujeme IntelliJ IDEA nebo Eclipse.

## Importujte balíčky
Nejprve importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
#Pojďme si uvedený příklad rozdělit do několika kroků:
## Krok 1: Nastavte datový adresář
Definujte adresář, kde budou uložena data vašeho projektu.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Vytvořte instanci projektu
Inicializujte novou instanci projektu.
```java
Project project = new Project();
```
## Krok 3: Nastavte vlastnosti informací o projektu
Nastavte vlastnosti projektu, jako je datum zahájení, plán od začátku a datum stavu.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## Krok 4: Uložte projekt jako XML
Uložte projekt s aktualizovanými informacemi jako soubor XML.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak psát informace z MS Project pomocí Aspose.Tasks for Java. S těmito nově získanými znalostmi můžete automatizovat různé úlohy související se soubory Microsoft Project a zvýšit tak svou produktivitu jako vývojář v jazyce Java.
## FAQ
### Otázka: Mohu použít Aspose.Tasks pro Java ke čtení souborů MS Project?
Odpověď: Ano, Aspose.Tasks for Java poskytuje robustní funkce pro čtení i zápis souborů MS Project.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými verzemi MS Project?
Odpověď: Rozhodně, Aspose.Tasks for Java podporuje různé verze MS Project, což zajišťuje kompatibilitu napříč různými formáty souborů.
### Otázka: Existují nějaká omezení zkušební verze Aspose.Tasks for Java?
Odpověď: Zatímco zkušební verze vám umožňuje prozkoumat možnosti knihovny, má určitá omezení, jako jsou vodoznaky na výstupních souborech.
### Otázka: Jak mohu získat podporu pro Aspose.Tasks pro Java?
 Odpověď: Můžete požádat o pomoc na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks for Java?
 Odpověď: Ano, dočasné licence jsou k dispozici pro krátkodobé použití. Můžete získat jeden z[tady](https://purchase.aspose.com/temporary-license/).