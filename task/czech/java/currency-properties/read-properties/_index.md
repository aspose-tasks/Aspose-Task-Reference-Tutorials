---
title: Přečtěte si Vlastnosti měny v projektech Aspose.Tasks
linktitle: Přečtěte si Vlastnosti měny v projektech Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak extrahovat informace o měně ze souborů MS Project pomocí Aspose.Tasks for Java. Poskytován průvodce krok za krokem.
type: docs
weight: 10
url: /cs/java/currency-properties/read-properties/
---
## Úvod
tomto tutoriálu se naučíme, jak využít Aspose.Tasks pro Java ke čtení vlastností měny ze souborů Microsoft Project. Aspose.Tasks je výkonné Java API, které umožňuje vývojářům manipulovat s dokumenty aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project. Podle níže uvedených kroků budete moci bez námahy extrahovat informace související s měnou.
## Předpoklady
Než budete pokračovat v tomto kurzu, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java JAR: Stáhněte si knihovnu Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/) a zahrňte jej do svého projektu Java.
## Importujte balíčky
Začněte importováním potřebných balíčků do vaší třídy Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Nastavte adresář projektu
Nejprve nastavte adresář projektu, kde je umístěn soubor aplikace Microsoft Project. Tuto cestu k adresáři můžete definovat následovně:
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` se skutečnou cestou k adresáři vašeho projektu.
## Krok 2: Vytvořte instanci Project Reader
 Instantovat a`Project` objekt poskytnutím cesty k vašemu souboru Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Zajistěte výměnu`"project.mpp"` s názvem vašeho souboru MS Project.
## Krok 3: Zobrazte vlastnosti měny
Načtěte a zobrazte vlastnosti měny ze souboru projektu:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Tento segment kódu načte informace, jako je kód měny, číslice, symbol a pozici symbolu, ze souboru MS Project a vytiskne je do konzoly.
## Krok 4: Dokončení procesu
Nakonec vytiskněte zprávu o úspěšném dokončení procesu:
```java
System.out.println("Process completed Successfully");
```
## Závěr
V tomto tutoriálu jsme prozkoumali, jak číst vlastnosti měny ze souborů Microsoft Project pomocí Aspose.Tasks for Java. Podle nastíněných kroků můžete bez námahy programově extrahovat informace týkající se měny ze souborů projektu, což umožňuje bezproblémovou integraci do vašich aplikací Java.
## FAQ
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
A: Aspose.Tasks podporuje různé verze Microsoft Project, včetně souborů MPP generovaných MS Project 2003-2021.
### Otázka: Mohu upravit vlastnosti měny pomocí Aspose.Tasks?
Odpověď: Ano, Aspose.Tasks vám umožňuje programově číst a upravovat vlastnosti měny v souborech MS Project.
### Otázka: Je Aspose.Tasks vhodný pro komerční použití?
 Odpověď: Ano, Aspose.Tasks je komerční knihovna určená pro profesionální použití. Můžete si zakoupit licenci[tady](https://purchase.aspose.com/buy).
### Otázka: Nabízí Aspose.Tasks bezplatnou zkušební verzi?
 Odpověď: Ano, můžete využít bezplatnou zkušební verzi Aspose.Tasks od[tady](https://releases.aspose.com/).
### Otázka: Kde mohu hledat pomoc nebo podporu pro Aspose.Tasks?
 Odpověď: Můžete navštívit fórum Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.