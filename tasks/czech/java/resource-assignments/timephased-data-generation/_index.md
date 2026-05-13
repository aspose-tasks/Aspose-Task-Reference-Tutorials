---
date: 2026-01-10
description: Naučte se, jak změnit konturu a generovat časově fázovaná data pro přiřazení
  zdrojů pomocí Aspose.Tasks pro Javu, čímž zlepšíte efektivitu řízení projektů.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak změnit konturu v Aspose.Tasks pro časově fázovaná data
url: /cs/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit konturu v Aspose.Tasks pro časově fázovaná data

## Úvod
V tomto tutoriálu se dozvíte **jak změnit konturu** pro přiřazení zdroje a vytvořit časově fázovaná data pomocí Aspose.Tasks pro Java. Časově fázovaná data ukazují rozdělení práce během časové osy projektu, což vám umožní jemně ladit plány, vyvážit zatížení a činit rozhodnutí založená na datech.

## Rychlé odpovědi
- **Co je kontura?** Kontura práce definuje, jak je úsilí rozloženo během trvání úkolu (např. Flat, Turtle, Bell).  
- **Proč měnit konturu?** Aby odrážela realistické pracovní vzorce, jako je předběžné nebo následné zatížení úsilí.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (jakákoli aktuální verze).  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu vidět výsledky v konzoli?** Vzorový kód vypisuje počáteční data a hodnoty pro každý časově fázovaný segment.

## Co je „jak změnit konturu“?
Změna kontury znamená aktualizaci vlastnosti `WORK_CONTOUR` objektu `ResourceAssignment`. Aspose.Tasks podporuje několik předdefinovaných kontur (Flat, Turtle, Bell atd.), které ovlivňují, jak je práce rozložena v čase.

## Proč používat Aspose.Tasks k vytvoření časově fázovaných dat?
- **Přesné reportování:** Exportujte přesné rozdělení práce pro nástroje reportování.  
- **Scénářové plánování:** Testujte různé kontury bez úpravy původního plánu.  
- **Automatizace:** Integrujte do CI pipeline k automatickému ověřování zdraví projektu.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte na systému nainstalovaný JDK. Můžete jej stáhnout a nainstalovat z [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks pro Java knihovna: Potřebujete mít knihovnu Aspose.Tasks pro Java. Můžete ji stáhnout z [webové stránky](https://releases.aspose.com/tasks/java/).

## Import balíčků
Nejprve importujme potřebné balíčky pro práci s Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Krok 1: Načtení zdrojového souboru MPP
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Krok 2: Získání úkolu a přiřazení zdroje
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Jak změnit konturu – Flat (výchozí)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Běžné problémy a tipy
- **Kontura se neaktualizuje?** Ujistěte se, že voláte `firstRA.set(Asn.WORK_CONTOUR, …)` *před* získáním časově fázovaných dat.
- **Neočekávané hodnoty?** Ověřte, že datum zahájení a ukončení úkolu jsou v zdrojovém MPP správně nastaveny.
- **Tip pro výkon:** Znovu použijte stejnou instanci `Project` při iteraci přes více kontur, abyste se vyhnuli zbytečnému I/O souborů.

## Často kladené otázky
### Mohu používat Aspose.Tasks s jinými knihovnami Java?
Ano, Aspose.Tasks lze integrovat s jinými knihovnami Java pro rozšíření schopností řízení projektů.

### Je Aspose.Tasks vhodný pro rozsáhlé podnikové projekty?
Rozhodně, Aspose.Tasks je navržen tak, aby zvládl projekty všech velikostí, včetně rozsáhlých podnikových iniciativ.

### Poskytuje Aspose.Tasks podporu pro různé formáty souborů projektů?
Ano, Aspose.Tasks podporuje řadu formátů, jako jsou MPP, XML a MPX.

### Mohu přizpůsobit pracovní kontury podle požadavků mého projektu?
Ano, můžete definovat vlastní pracovní kontury, které odpovídají konkrétním potřebám plánování.

### Existuje komunitní fórum, kde mohu získat pomoc s Aspose.Tasks?
Ano, můžete navštívit [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro podporu a diskuze.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}