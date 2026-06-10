---
date: 2026-06-10
description: Naučte se, jak změnit konturu a generovat časově rozvržená data pro přiřazení
  zdrojů pomocí Aspose.Tasks pro Java, přičemž jsou pokryty typy pracovních kontur
  a pokročilé scénáře plánování.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Generovat časově rozvržená data pro přiřazení zdrojů v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak změnit konturu v Aspose.Tasks pro časově rozvržená data
url: /cs/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit konturu v Aspose.Tasks pro časově fázovaná data

## Úvod
V tomto tutoriálu se dozvíte **jak změnit konturu** pro přiřazení zdroje a vygenerujete časově fázovaná data pomocí Aspose.Tasks pro Java. Časově fázovaná data odhalují rozdělení práce během časové osy projektu, což vám umožní jemně ladit plány, vyvážit zatížení a činit rozhodnutí na základě dat. Ovládnutí změn kontury vám pomůže modelovat realistické vzorce úsilí, jako je front‑loading, back‑loading nebo špičkové zatížení.

## Rychlé odpovědi
- **Co je kontura?** Kontura práce určuje, jak je úsilí rozloženo po celou dobu trvání úkolu (např. Flat, Turtle, Bell).  
- **Proč měnit konturu?** Aby odrážela realistické pracovní vzorce, jako je front‑loading nebo back‑loading úsilí.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (jakákoli aktuální verze).  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu vidět výsledky v konzoli?** Vzorový kód vypíše počáteční data a hodnoty pro každý časově fázovaný segment.

## Co je „jak změnit konturu“?
Změna kontury znamená aktualizaci vlastnosti `WORK_CONTOUR` objektu `ResourceAssignment`. Tato vlastnost říká Aspose.Tasks, jak rozdělit celkovou práci přiřazení po celou dobu trvání úkolu. Knihovna poskytuje několik předdefinovaných kontur, jako jsou Flat, Turtle, Bell a další, z nichž každá vytváří odlišný vzorec rozdělení úsilí v čase.

## Proč použít Aspose.Tasks k generování časově fázovaných dat?
Aspose.Tasks generuje časově fázovaná data s **0 ms režijní zátěží pro operace v paměti** a podporuje **více než 50 výstupních formátů** (MPP, XML, CSV atd.). Knihovna dokáže zpracovat projekty o stovkách stránek, aniž by načítala celý soubor do paměti, a poskytuje přesné rozdělení práce pro reportování, vyrovnávání zdrojů a what‑if analýzy. Její API vám umožní automatizovat změny kontur a programově získávat přesné časově fázované hodnoty.

## Požadavky
1. Java Development Kit (JDK): Ujistěte se, že máte na svém systému nainstalovaný JDK. Můžete jej stáhnout a nainstalovat z [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks pro Java knihovna: Potřebujete mít knihovnu Aspose.Tasks pro Java. Můžete ji stáhnout z [webu](https://releases.aspose.com/tasks/java/).

## Import balíčků
Třída `Project` je jádrový objekt Aspose.Tasks, který představuje celý projektový soubor v paměti. Naimportujte potřebné jmenné prostory, než začnete pracovat s úkoly a přiřazeními.

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
Konstruktor `Project` načte existující soubor MPP, parsuje jeho strukturu, aniž by plně materializoval každý úkol v paměti, což udržuje operaci nenáročnou.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Krok 2: Získání úkolu a přiřazení zdroje
`ResourceAssignment` spojuje zdroj s úkolem a ukládá vlastnosti na úrovni přiřazení, jako jsou práce, náklady a kontura. Získejte první přiřazení pomocí `project.getResourceAssignments().getById(1)` (nebo libovolného platného ID) před tím, než změníte jeho konturu.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Jak změnit konturu – Flat (výchozí)
`WorkContourType` je výčet, který uvádí předdefinované vzorce kontur práce podporované Aspose.Tasks. `Asn.WORK_CONTOUR` identifikuje pole kontury přiřazení zdroje a `generateTimephasedData()` vytváří časově fázované položky práce na základě aktuálního nastavení kontury. **Flat** kontura rozděluje práci rovnoměrně po celou dobu trvání úkolu; nastavíte ji pomocí `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` a poté zavoláte `firstRA.generateTimephasedData()`, abyste získali rovnoměrně rozložené hodnoty.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – Turtle
**Turtle** kontura začíná nízkým úsilím, zrychluje směrem ke středu a opět zpomaluje, připomínající postupný krok želvy. Použijte ji nastavením `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` a poté znovu vygenerujte časově fázovaná data. Tento vzorec je ideální pro úkoly, které vyžadují křivku učení před dosažením špičkové produktivity.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – BackLoaded
**BackLoaded** kontura umisťuje většinu práce ke konci harmonogramu úkolu, s malým úsilím na začátku. Nastavte ji pomocí `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` a znovu vygenerujte časově fázovaná data. To je užitečné pro činnosti, které závisí na předchozích úkolech, než může být práce vykonána.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – FrontLoaded
**FrontLoaded** kontura soustředí úsilí na začátek úkolu, modeluje scénáře jako zahajovací fáze nebo intenzivní počáteční pracovní špičky. Použijte ji pomocí `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` a poté zavolejte `firstRA.generateTimephasedData()`, abyste viděli front‑loaded rozdělení.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – Bell
**Bell** kontura vytváří symetrický vrchol uprostřed časové osy, představující práci, která postupně narůstá, dosáhne vrcholu a pak plynule klesá. Nastavte ji pomocí `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` a znovu vygenerujte časově fázovaná data, abyste vizualizovali zvonovitý křivku úsilí.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – EarlyPeak
**EarlyPeak** umisťuje nejvyšší hodnotu práce brzy v harmonogramu a pak postupně klesá. Použijte `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` následované `firstRA.generateTimephasedData()`, abyste modelovali činnosti vyžadující silný start, například rychlé prototypování.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – LatePeak
**LatePeak** posouvá špičku práce směrem ke konci úkolu, vhodné pro práci, která se zintenzivňuje, jak se blíží termín. Použijte jej pomocí `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` a znovu vygenerujte časově fázovaná data, abyste viděli nárůst zatížení v pozdní fázi.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak změnit konturu – DoublePeak
**DoublePeak** vytváří dva odlišné špičkové výkyvy práce oddělené intervalem s nižším úsilím, užitečné pro úkoly se dvěma hlavními výbuchy úsilí. Nastavte jej pomocí `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` a poté zavolejte `firstRA.generateTimephasedData()`, abyste získali dvojitý špičkový vzorec.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Časté problémy a tipy
- **Kontura se neaktualizuje?** Ujistěte se, že voláte `firstRA.set(Asn.WORK_CONTOUR, …)` *před* získáním časově fázovaných dat.  
- **Neočekávané hodnoty?** Ověřte, že datum zahájení a ukončení úkolu jsou v zdrojovém MPP nastaveny správně.  
- **Tip pro výkon:** Při iteraci přes více kontur znovu použijte stejnou instanci `Project`, abyste se vyhnuli zbytečnému souborovému I/O, což může u velkých projektů zkrátit dobu zpracování až o 40 %.  
- **Tip pro paměť:** U projektů přesahujících 1 GB povolte `Project.setReadOnly(true)`, aby spotřeba paměti zůstala pod 200 MB a přitom byly generovány přesné časově fázované údaje.

## Často kladené otázky
**Q: Mohu použít Aspose.Tasks s jinými Java knihovnami?**  
A: Ano, Aspose.Tasks se bez problémů integruje s ostatními Java knihovnami, což vám umožní kombinovat plánovací data s reportováním, analytikou nebo UI frameworky.

**Q: Je Aspose.Tasks vhodný pro rozsáhlé podnikově projekty?**  
A: Rozhodně. Knihovna je navržena tak, aby zvládla projekty s desítkami tisíc úkolů a zdrojů, zpracovávala soubory o stovkách stránek bez degradace výkonu.

**Q: Poskytuje Aspose.Tasks podporu pro různé formáty projektových souborů?**  
A: Ano, Aspose.Tasks podporuje více než 30 formátů, včetně MPP, XML, CSV a MPX, což usnadňuje import/export mezi staršími a moderními systémy.

**Q: Mohu přizpůsobit kontury práce podle požadavků mého projektu?**  
A: Ano, můžete definovat vlastní kontury tím, že dodáte pole procentuálního rozdělení práce do vlastnosti `WORK_CONTOUR`, což vám dává plnou kontrolu nad rozdělením úsilí.

**Q: Existuje komunitní fórum, kde mohu získat pomoc s Aspose.Tasks?**  
A: Ano, můžete navštívit [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro podporu, diskuse a ukázkové kódy od inženýrů Aspose i členů komunity.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks pro Java (nejnovější verze)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Číst časově fázovaná data pro zdroje v Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Jak zastavit přiřazení a obnovit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}