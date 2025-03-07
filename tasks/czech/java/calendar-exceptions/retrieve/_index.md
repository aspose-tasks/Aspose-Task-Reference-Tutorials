---
title: Načtení výjimek kalendáře pomocí Aspose.Tasks
linktitle: Načtení výjimek kalendáře pomocí Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak načíst výjimky kalendáře z MS Project pomocí Aspose.Tasks for Java. Výukový program krok za krokem pro bezproblémovou integraci.
weight: 13
url: /cs/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Načtení výjimek kalendáře pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu prozkoumáme, jak načíst výjimky kalendáře z MS Project pomocí knihovny Aspose.Tasks pro Javu. Aspose.Tasks je výkonný nástroj, který umožňuje vývojářům programově manipulovat se soubory aplikace Microsoft Project. Provedeme vás procesem krok za krokem, přičemž každý příklad rozdělíme do několika kroků pro snadné pochopení.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java: Stáhněte si a nainstalujte Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/).
3. Integrované vývojové prostředí (IDE): Můžete použít libovolné IDE podle svého výběru, například IntelliJ IDEA nebo Eclipse.

## Importujte balíčky
Nejprve musíte importovat potřebné balíčky pro práci s Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Krok 1: Nastavte svůj datový adresář
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
```
 Zajistěte výměnu`"Your Data Directory"` s cestou k vašemu adresáři obsahujícímu soubor MS Project.
## Krok 2: Načtěte soubor MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```
 Tento řádek inicializuje nový`Project` objekt načtením souboru MS Project určeného cestou.
## Krok 3: Načtení výjimek kalendáře
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Zde iterujeme každý kalendář v projektu a poté každou výjimku kalendáře v tomto kalendáři. Vytiskneme datum zahájení a ukončení každé výjimky.

## Závěr
V tomto tutoriálu jsme se naučili, jak načíst výjimky kalendáře z MS Project pomocí Aspose.Tasks for Java. Pomocí těchto jednoduchých kroků můžete tuto funkci hladce integrovat do svých aplikací Java.
## Často kladené otázky
### Dokáže Aspose.Tasks zpracovat různé verze souborů MS Project?
Ano, Aspose.Tasks podporuje různé verze souborů MS Project, včetně formátů MPP, MPT a XML.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Tasks for Java?
 Můžete se podívat na dokumentaci[tady](https://reference.aspose.com/tasks/java/).
### Jak mohu získat podporu pro Aspose.Tasks?
 Podporu můžete získat na komunitním fóru[tady](https://forum.aspose.com/c/tasks/15).
### Existuje možnost dočasných licencí pro Aspose.Tasks?
 Ano, můžete získat dočasné licence od[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
