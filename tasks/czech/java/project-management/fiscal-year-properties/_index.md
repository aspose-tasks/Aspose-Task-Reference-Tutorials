---
title: Správa vlastností fiskálního roku v Aspose.Tasks
linktitle: Správa vlastností fiskálního roku v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně spravovat vlastnosti fiskálního roku pomocí Aspose.Tasks for Java. Průvodce krok za krokem s ukázkami.
type: docs
weight: 15
url: /cs/java/project-management/fiscal-year-properties/
---
## Úvod
Aspose.Tasks je výkonná Java knihovna, která umožňuje vývojářům efektivně spravovat soubory projektu, včetně zpracování vlastností fiskálního roku. V tomto tutoriálu si projdeme procesem správy vlastností fiskálního roku pomocí Aspose.Tasks v Javě.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java JAR: Stáhněte si knihovnu Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/) a zahrnout jej do svého projektu.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do souboru Java:
```java
import com.aspose.tasks.*;
```

Rozdělme poskytnutý příklad do několika kroků:
## Krok 1: Načtěte soubor projektu
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
V tomto kroku načteme soubor projektu s názvem "project.mpp" umístěný v zadaném datovém adresáři.
## Krok 2: Zobrazte vlastnosti fiskálního roku
```java
//Zobrazit vlastnosti fiskálního roku
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Tento krok načte a vytiskne počáteční datum a číslování fiskálního roku z načteného projektu.
## Krok 3: Nastavení vlastností fiskálního roku projektu
```java
//Vytvořte instanci projektu
Project prj = new Project();
//Nastavte vlastnosti fiskálního roku
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Uložte projekt jako soubor projektu XML
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Zde vytvoříme novou instanci projektu, nastavíme datum zahájení fiskálního roku na červenec a povolíme číslování fiskálního roku. Poté upravený projekt uložíme jako soubor XML.
## Krok 4: Zobrazení výsledku
```java
//Zobrazit výsledek konverze.
System.out.println("Process completed Successfully");
```
Nakonec vytiskneme zprávu o úspěšném dokončení procesu.

## Závěr
Správa vlastností fiskálního roku v Aspose.Tasks for Java je s poskytnutým API přímočará. Podle kroků uvedených v tomto kurzu můžete ve svých projektech efektivně zvládnout úkoly související s fiskálním rokem.
## FAQ
### Otázka: Mohu použít Aspose.Tasks for Java k manipulaci s jinými vlastnostmi projektu?
Odpověď: Ano, Aspose.Tasks poskytuje komplexní funkce pro správu různých vlastností projektu kromě vlastností fiskálního roku.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými formáty souborů projektu?
Odpověď: Ano, Aspose.Tasks podporuje širokou škálu formátů projektových souborů včetně MPP, XML a dalších.
### Otázka: Jak mohu získat podporu, pokud při používání Aspose.Tasks for Java narazím na nějaké problémy?
 Odpověď: Můžete požádat o pomoc komunitu Aspose.Tasks na[Fórum](https://forum.aspose.com/c/tasks/15)nebo kontaktujte přímo jejich tým podpory.
### Otázka: Nabízí Aspose.Tasks bezplatnou zkušební verzi?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).
### Otázka: Kde si mohu zakoupit licenci pro Aspose.Tasks for Java?
 A: Můžete si zakoupit licenci pro Aspose.Tasks for Java od[tady](https://purchase.aspose.com/buy).