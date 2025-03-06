---
title: Přečtěte si MS Project z Primavera s Aspose.Tasks pro Javu
linktitle: Přečtěte si Project od Primavera v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se bezproblémově číst soubory MS Project z Primavera XML pomocí Aspose.Tasks for Java. Zvyšte efektivitu řízení svého projektu.
weight: 20
url: /cs/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přečtěte si MS Project z Primavera s Aspose.Tasks pro Javu

## Úvod
Při řízení projektů je interoperabilita mezi různými softwarovými platformami zásadní pro bezproblémový pracovní tok. Aspose.Tasks for Java poskytuje robustní funkce pro čtení souborů Microsoft Project z Primavera XML. Tento tutoriál vás provede procesem čtení souborů MS Project z Primavera pomocí Aspose.Tasks for Java, což vám umožní efektivně prozkoumat vlastnosti specifické pro Primavera úkolů.
## Předpoklady
Než budete pokračovat, ujistěte se, že máte nainstalované a nastavené následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Tasks for Java: Stáhněte si a nainstalujte Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Krok 1: Nastavte Data Directory
```java
String dataDir = "Your Data Directory";
```
 Zajistěte výměnu`"Your Data Directory"` se skutečnou cestou k vašemu datovému adresáři.
## Krok 2: Přečtěte si projekt z Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Zajistěte výměnu`"PrimaveraProject.xml"` se skutečným názvem vašeho Primavera XML souboru.
## Krok 3: Projděte úkoly a načtěte vlastnosti specifické pro Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Tento kód prochází každou úlohou v projektu a tiskne příslušné vlastnosti specifické pro Primavera.

## Závěr
tomto tutoriálu jste se naučili číst soubory MS Project z Primavera XML pomocí Aspose.Tasks for Java. Tato funkce umožňuje bezproblémovou integraci a analýzu projektových dat napříč různými platformami, čímž zvyšuje celkovou efektivitu řízení projektů.
## FAQ
### Otázka: Mohu upravit vlastnosti úloh specifické pro Primavera pomocí Aspose.Tasks for Java?
Odpověď: Ano, Aspose.Tasks for Java poskytuje API pro úpravu vlastností úloh specifických pro Primavera podle potřeby.
### Otázka: Podporuje Aspose.Tasks for Java čtení jiných formátů souborů projektu?
Odpověď: Ano, Aspose.Tasks for Java podporuje čtení různých formátů projektových souborů včetně MPP, XML a Primavera XML.
### Otázka: Je Aspose.Tasks for Java vhodný pro aplikace řízení projektů na podnikové úrovni?
Odpověď: Aspose.Tasks for Java nabízí robustní funkce a škálovatelnost, takže je vhodný pro aplikace pro řízení projektů na podnikové úrovni.
### Otázka: Mohu získat informace o zdrojích z projektů Primavera pomocí Aspose.Tasks for Java?
Odpověď: Ano, Aspose.Tasks for Java vám umožňuje extrahovat informace o zdrojích spolu s podrobnostmi úkolů z projektů Primavera.
### Otázka: Kde najdu další podporu nebo dokumentaci pro Aspose.Tasks for Java?
 Odpověď: Obsáhlou dokumentaci a přístup k fórům pro podporu naleznete na[Aspose.Tasks pro dokumentaci Java](https://reference.aspose.com/tasks/java/) strana.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
