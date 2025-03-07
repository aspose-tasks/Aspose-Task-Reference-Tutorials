---
title: Napište shrnutí projektu MPP do Aspose.Tasks
linktitle: Napište shrnutí projektu MPP do Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se psát souhrny projektů MPP v Javě pomocí Aspose.Tasks. Nastavte a načtěte informace o projektu bez námahy.
weight: 27
url: /cs/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Napište shrnutí projektu MPP do Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíme, jak používat Aspose.Tasks pro Java k psaní souhrnů projektů MPP. Aspose.Tasks je výkonná Java knihovna pro práci se soubory Microsoft Project. Podle níže uvedených kroků budete moci nastavit a získat různé souhrnné informace o projektu pomocí této knihovny.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si preferované IDE pro vývoj v Javě, jako je IntelliJ IDEA, Eclipse nebo NetBeans.

## Importujte balíčky
Nejprve importujte potřebné balíčky do své třídy Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Krok 1: Nastavte projekt a definujte souhrnné informace
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
//Inicializujte nový objekt projektu s cestou k souboru projektu
Project project = new Project(dataDir + "project.mpp");
// Nastavte souhrnné informace o projektu
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Nastavte datum vytvoření projektu
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Nastavte klíčová slova pro projekt
project.set(Prj.KEYWORDS, "MPP Aspose");
// Nastavte datum posledního tisku projektu
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Krok 2: Uložte souhrnné informace o projektu
```java
// Uložte projekt zpět ve formátu MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Zobrazit zprávu o úspěchu
System.out.println("Process completed Successfully");
```
## Krok 3: Přečtěte si souhrnné informace o projektu
```java
// Čtení souhrnných informací o projektu
project = new Project(dataDir + "MppAspose.xml");
// Vytisknout autora projektu
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Vytisknout posledního autora projektu
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Vytisknout číslo revize projektu
System.out.println("Revision: " + project.get(Prj.REVISION));
// Vytiskněte klíčová slova projektu
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Tisk komentářů k projektu
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Tisk data vytvoření projektu
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Tisk klíčových slov projektu (znovu)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Tisk posledního vytištěného data projektu
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Závěr
tomto tutoriálu jsme probrali, jak psát souhrny projektů MPP pomocí Aspose.Tasks pro Javu. Pomocí těchto kroků můžete efektivně nastavit a získat různé souhrnné informace o souborech projektu. Aspose.Tasks zjednodušuje proces práce se soubory Microsoft Project v aplikacích Java, nabízí robustní funkce a snadné použití.
## FAQ
### Otázka: Mohu používat Aspose.Tasks for Java s jinými knihovnami Java?
Odpověď: Ano, Aspose.Tasks for Java lze hladce integrovat s jinými knihovnami Java, aby se zlepšily možnosti řízení vašich projektů.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Jak často se Aspose.Tasks for Java aktualizuje?
Odpověď: Aspose.Tasks for Java je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi Java a souborů Microsoft Project.
### Otázka: Mohu dále upravit souhrnné informace o projektu?
Odpověď: Rozhodně, Aspose.Tasks for Java poskytuje rozsáhlé možnosti přizpůsobení souhrnných informací o projektu podle vašich specifických požadavků.
### Otázka: Kde mohu získat podporu pro Aspose.Tasks for Java?
Odpověď: Podporu můžete získat na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
