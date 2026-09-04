---
date: 2026-06-10
description: Naučte se, jak číst sazbu a jak zapisovat měřítko sazby pro přiřazení
  zdrojů pomocí Aspose.Tasks pro Java. Podporuje materiální zdroje, různé formáty
  a velké projekty.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Číst a zapisovat měřítko sazby pro přiřazení zdrojů v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak číst měřítko sazby a zapisovat měřítko sazby pro přiřazení zdrojů v Aspose.Tasks
url: /cs/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst a zapisovat měřítko sazby pro přiřazení zdrojů v Aspose.Tasks

## Rychlé odpovědi
`ResourceAssignment` spojuje úkol se zdrojem a obsahuje data specifická pro přiřazení.  
`Asn` obsahuje konstanty pro pole přiřazení, včetně `RATE_SCALE`.  
`RateScaleType` výčet (enum) uvádí možné časové jednotky pro škálování sazby.  

- **Jaká je hlavní třída pro práci se sazbou?** `ResourceAssignment` s vlastností `Asn.RATE_SCALE`.  
- **Který výčet (enum) definuje možnosti měřítka?** `RateScaleType` (Day, Week, Month, atd.).  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební licence funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu měřítko změnit po uložení?** Ano – načtěte projekt znovu a upravte `Asn.RATE_SCALE` podle ukázky.  
- **Podporovaná IDE?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, NetBeans) může kód zkompilovat.

## Jak číst měřítko sazby pro přiřazení zdrojů?

Načtěte projekt, najděte požadovaný `ResourceAssignment` a zavolejte `getRateScale()` – tato metoda vrátí hodnotu typu `RateScaleType`, která určuje, zda je sazba aplikována za den, týden, měsíc nebo jinou jednotku. Odpověď je okamžitá a vyžaduje jen dva volání API, což je ideální pro auditní skripty nebo zobrazení v UI.

## Jak zapisovat měřítko sazby pro přiřazení zdrojů?

Vytvořte nebo získejte objekt `ResourceAssignment`, nastavte jeho vlastnost `Asn.RATE_SCALE` na požadovaný `RateScaleType` (např. `RateScaleType.Week`) a poté projekt uložte. Tato jednorázová změna vlastnosti automaticky aktualizuje výpočty nákladů a zachová se napříč všemi podporovanými formáty souborů. Po nastavení měřítka může být také nutné upravit standardní sazbu zdroje nebo přesčasovou sazbu, aby odrážely novou časovou jednotku a zajistily přesnost výpočtů nákladů.

## Co je měřítko sazby?

Měřítko sazby určuje časovou jednotku (den, týden, měsíc atd.), na kterou se aplikuje nákladová sazba zdroje. Úprava měřítka vám umožní přesně modelovat spotřebu materiálu nebo pracovní úsilí. Například nastavení měřítka na Week znamená, že nákladová sazba je interpretována jako náklad za týden a celkové náklady úkolu se vypočítají na základě počtu týdnů, po které je zdroj přiřazen.

## Proč číst a zapisovat měřítko sazby?

Čtení aktuálního měřítka vám pomůže auditovat existující plány, zatímco zápis nového měřítka vám umožní sladit zdroje s fakturačními nebo spotřebními politikami projektu. To je zvláště užitečné při **definování nákladů materiálových zdrojů** nebo když potřebujete **nastavit měřítko** pro nestandardní pracovní kalendáře.

## Předpoklady
1. **Java vývojové prostředí** – nainstalovaný JDK 8 nebo vyšší.  
2. **Aspose.Tasks for Java knihovna** – Stáhněte a nainstalujte knihovnu z [zde](https://releases.aspose.com/tasks/java/).

## Import balíčků
Třída `ResourceAssignment` představuje spojení mezi úkolem a zdrojem, zatímco `RateScaleType` enumeruje možné časové jednotky pro sazbu. Importujte potřebné třídy Aspose.Tasks před zahájením kódování.  

`Project` je hlavní objekt, který načítá a ukládá soubory Microsoft Project.  
`Resource` definuje projektový zdroj, jako je práce nebo materiál.  
`ResourceType` enum určuje, zda je zdroj práce nebo materiál.  
`Task` představuje pracovní položku v harmonogramu projektu.  
`SaveFileFormat` enum definuje výstupní formát pro uložení projektu.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Krok 1: Nastavte svůj Java projekt
Vytvořte Maven nebo Gradle projekt a přidejte JAR Aspose.Tasks do classpathu. Tento krok zajistí, že kompilátor najde importované třídy.

## Krok 2: Načtěte soubor projektu
Načtěte existující soubor Microsoft Project, se kterým chcete pracovat.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Krok 3: Přidejte úkol
Vytvořte nový úkol, který později obdrží přiřazení zdrojů.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Krok 4: Definujte zdroje
Zde **definujeme materiálový zdroj** a běžný pracovní zdroj. Všimněte si použití `ResourceType.Material` pro materiálový typ zdroje.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Krok 5: Přiřaďte zdroje k úkolu
Nyní **přiřazujeme zdroje k úkolu** a specifikujeme **jak nastavit měřítko** pomocí `RateScaleType.Week`. Toto ilustruje jak čtení, tak zápis měřítka sazby.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Krok 6: Uložte projekt
Uložte změny do nového souboru, abychom později mohli ověřit uložené měřítko sazby.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Krok 7: Získejte přiřazení zdrojů
Načtěte uložený projekt znovu a **přečtěte měřítko sazby**, abyste potvrdili, že bylo správně zapsáno.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Časté úskalí a tipy
- **Neshoda UID** – Při získávání přiřazení podle UID se ujistěte, že hodnoty UID odpovídají těm přiřazeným během tvorby.  
- **Nesprávný typ zdroje** – Použití `ResourceType.Material` pro pracovní zdroj způsobí neočekávané chování výpočtů sazby.  
- **Formát ukládání** – Vždy ukládejte pomocí `SaveFileFormat.Mpp` (nebo jiného podporovaného formátu), aby se zachovaly vlastní pole jako měřítko sazby.  
- **Velké projekty** – Aspose.Tasks dokáže zpracovat soubory s **500+ stránkami** bez načítání celého dokumentu do paměti díky své streamovací architektuře.

## Často kladené otázky

**Otázka: Mohu používat Aspose.Tasks pro Java s jakýmkoli Java IDE?**  
Ano, Aspose.Tasks pro Java je kompatibilní se všemi hlavními Java IDE, včetně IntelliJ IDEA, Eclipse a NetBeans.

**Otázka: Podporuje Aspose.Tasks i jiné formáty souborů kromě MPP?**  
Ano, Aspose.Tasks podporuje různé formáty souborů, včetně MPP, XML a HTML.

**Otázka: Je Aspose.Tasks vhodný pro podnikové řízení projektů?**  
Rozhodně, Aspose.Tasks nabízí komplexní funkce pro řízení projektů jakékoliv velikosti, což jej činí vhodným pro podnikové řízení projektů.

**Otázka: Mohu přizpůsobit přiřazení zdrojů dále než jen měřítko sazby?**  
Ano, Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení přiřazení zdrojů, včetně úprav nákladů, práce a trvání.

**Otázka: Existuje komunitní fórum pro podporu Aspose.Tasks?**  
Ano, podporu a komunikaci s ostatními uživateli najdete na fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-06-10  
**Testováno s:** Aspose.Tasks for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Jak upravit přiřazení – číst sdílené zdroje s Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Jak přidat poznámky k přiřazením zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}