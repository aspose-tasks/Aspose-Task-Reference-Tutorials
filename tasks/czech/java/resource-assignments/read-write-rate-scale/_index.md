---
date: 2026-01-10
description: Naučte se, jak číst měřítko sazeb a spravovat přiřazení zdrojů v Aspose.Tasks
  pro Javu. Definujte materiální zdroj, jak nastavit měřítko a přiřadit zdroje k úkolu.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak číst měřítko sazby a zapisovat měřítko sazby pro přiřazení zdrojů v Aspose.Tasks
url: /cs/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst a zapisovat Rate Scale pro přiřazení zdrojů v Aspose.Tasks

V tomto tutoriálu se dozvíte **jak číst** nastavení Rate Scale a upravit je pro přiřazení zdrojů pomocí Aspose.Tasks pro Java. Ať už vytváříte plánovač, nástroj pro reportování nebo jen potřebujete automatizovat aktualizace projektů, ovládnutí manipulace s Rate Scale vám poskytuje detailní kontrolu nad materiálovými a pracovnímí zdroji.

## Rychlé odpovědi
- **Jaká je hlavní třída pro práci se sazbou?** `ResourceAssignment` s vlastností `Asn.RATE_SCALE`.  
- **Který výčtový typ (enum) definuje možnosti měřítka?** `RateScaleType` (Day, Week, Month, atd.).  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná evaluační licence stačí pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu změnit měřítko po uložení?** Ano – načtěte projekt znovu a upravte `Asn.RATE_SCALE` podle ukázky.  
- **Podporovaná IDE?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, NetBeans) může kód zkompilovat.

## Co je Rate Scale?
Rate Scale určuje časovou jednotku (den, týden, měsíc, atd.), na kterou se aplikuje sazba nákladů zdroje. Úprava měřítka vám umožní přesně modelovat spotřebu materiálu nebo pracovní úsilí.

## Proč číst a zapisovat Rate Scale?
Čtení aktuálního měřítka vám pomáhá auditovat existující plány, zatímco zápis nového měřítka vám umožní sladit zdroje s fakturačními nebo spotřebními politikami projektu. To je zvláště užitečné při **definování materiálových zdrojů** nákladů nebo když potřebujete **nastavit měřítko** pro nestandardní pracovní kalendáře.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. **Java Development Environment** – nainstalovaný JDK 8 nebo vyšší.
2. **Aspose.Tasks for Java Library** – Stáhněte a nainstalujte knihovnu z [here](https://releases.aspose.com/tasks/java/).

## Import balíčků
Nejprve importujte potřebné třídy z Aspose.Tasks.

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
Vytvořte Maven nebo Gradle projekt a přidejte Aspose.Tasks JAR do classpath. Tento krok zajistí, že kompilátor najde importované třídy.

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
Nyní **přiřazujeme zdroje k úkolu** a specifikujeme **jak nastavit měřítko** pomocí `RateScaleType.Week`. Toto ukazuje jak čtení, tak zápis Rate Scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Krok 6: Uložte projekt
Uložte změny do nového souboru, abychom později mohli ověřit uložené Rate Scale.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Krok 7: Získejte přiřazení zdrojů
Načtěte uložený projekt znovu a **přečtěte Rate Scale**, abyste potvrdili, že bylo správně zapsáno.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Časté úskalí a tipy
- **Neshoda UID** – Při získávání přiřazení podle UID se ujistěte, že hodnoty UID odpovídají těm přiřazeným během tvorby.  
- **Nesprávný typ zdroje** – Použití `ResourceType.Material` pro pracovní zdroj způsobí neočekávané chování výpočtů sazby.  
- **Formát ukládání** – Vždy ukládejte pomocí `SaveFileFormat.Mpp` (nebo jiného podporovaného formátu), aby se zachovaly vlastní pole jako Rate Scale.

## Závěr
Správa a kontrola Rate Scale pro přiřazení zdrojů v Aspose.Tasks pro Java je jednoduchá, jakmile znáte příslušné třídy a vlastnosti. Dodržením tohoto návodu můžete **číst Rate** informace, **definovat materiálové zdroje**, **nastavit měřítko** a **přiřadit zdroje k úkolu** s jistotou.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks pro Java s jakýmkoli Java IDE?**  
A: Ano, Aspose.Tasks pro Java je kompatibilní se všemi hlavními Java IDE, včetně IntelliJ IDEA, Eclipse a NetBeans.

**Q: Podporuje Aspose.Tasks i jiné formáty souborů kromě MPP?**  
A: Ano, Aspose.Tasks podporuje různé formáty souborů, včetně MPP, XML a HTML.

**Q: Je Aspose.Tasks vhodný pro enterprise‑level řízení projektů?**  
A: Rozhodně, Aspose.Tasks nabízí komplexní funkce pro správu projektů jakékoliv velikosti, což jej činí vhodným pro enterprise‑level řízení projektů.

**Q: Mohu dále přizpůsobovat přiřazení zdrojů mimo Rate Scale?**  
A: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti pro přizpůsobení přiřazení zdrojů, včetně úprav nákladů, práce a trvání.

**Q: Existuje komunitní fórum pro podporu Aspose.Tasks?**  
A: Ano, podporu a interakci s ostatními uživateli najdete na fóru Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-01-10  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}