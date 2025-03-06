---
title: Zapište aktualizovaná data zdrojů do Aspose.Tasks
linktitle: Zapište aktualizovaná data zdrojů do Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak snadno aktualizovat zdrojová data v souborech MS Project pomocí Aspose.Tasks for Java.
weight: 21
url: /cs/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapište aktualizovaná data zdrojů do Aspose.Tasks

## Úvod
V tomto tutoriálu vás provedeme aktualizací dat zdrojů aplikace Microsoft Project pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonné Java API, které vám umožňuje manipulovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project do vašeho systému.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Aspose.Tasks pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
3. Základní znalost programování v Javě.

## Importujte balíčky

Nejprve musíte importovat potřebné balíčky pro práci s Aspose.Tasks ve vašem kódu Java. Přidejte do svého souboru Java následující příkazy pro import:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Nastavte svůj datový adresář

Definujte adresář, kde jsou umístěny vaše datové soubory:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Zadejte vstupní a výstupní soubory

Definujte cesty pro vstupní soubor MS Project a výsledný aktualizovaný soubor:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Testovací soubor s jedním rsc k aktualizaci
String resultFile = dataDir + "OutputMPP.mpp"; // Soubor pro psaní testovacího projektu
```

## Krok 3: Načtěte projekt

 Načtěte soubor MS Project do a`Project` objekt:

```java
Project project = new Project(file);
```

## Krok 4: Přidejte zdroj a nastavte atributy

Přidejte do projektu nový zdroj a nastavte jeho atributy, jako je standardní sazba, sazba přesčas a skupina:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Krok 5: Uložte projekt

Uložte aktualizovaný projekt s upravenými daty zdrojů:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Závěr

V tomto tutoriálu jsme ukázali, jak aktualizovat zdrojová data MS Project pomocí Aspose.Tasks for Java. Pomocí těchto kroků můžete efektivně manipulovat s informacemi o zdrojích v souborech MS Project programově.

## FAQ

### Q1: Mohu aktualizovat více zdrojů ve stejném projektu pomocí Aspose.Tasks for Java?

Odpověď 1: Ano, můžete aktualizovat více zdrojů jejich opakováním a odpovídajícím nastavením jejich atributů.

### Q2: Podporuje Aspose.Tasks jiné formáty souborů kromě MS Project?

Odpověď 2: Ano, Aspose.Tasks podporuje různé formáty souborů včetně XML, MPP a dalších.

### Q3: Je Aspose.Tasks kompatibilní s různými verzemi Java?

Odpověď 3: Aspose.Tasks je kompatibilní s verzí Java 6 a vyšší.

### Q4: Mohu provádět další operace se soubory MS Project pomocí Aspose.Tasks?

Odpověď 4: Ano, můžete provádět širokou škálu operací, jako je čtení, zápis a manipulace s úkoly, zdroji a kalendáři.

### Q5: Kde najdu další pomoc nebo podporu pro Aspose.Tasks?

 A5: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
