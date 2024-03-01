---
title: Generujte časově uspořádaná data v Aspose.Tasks
linktitle: Generujte časově uspořádaná data pro přiřazení zdrojů v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se generovat časově uspořádaná data pro přiřazení zdrojů pomocí Aspose.Tasks for Java. Zlepšete efektivitu projektového řízení pomocí tohoto komplexního průvodce.
type: docs
weight: 24
url: /cs/java/resource-assignments/timephased-data-generation/
---
## Úvod
V tomto tutoriálu projdeme procesem generování časově uspořádaných dat pro přiřazení zdrojů pomocí Aspose.Tasks for Java. Časově uspořádaná data poskytují cenné informace o tom, jak jsou zdroje v průběhu času alokovány v rámci projektu, a pomáhají projektovým manažerům činit informovaná rozhodnutí.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. JDK si můžete stáhnout a nainstalovat z[tady](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java Library: Musíte mít knihovnu Aspose.Tasks for Java. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
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
## Krok 1: Přečtěte si zdrojový soubor MPP
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
// Přečtěte si zdrojový soubor MPP
Project project = new Project(dataDir + "project.mpp");
```
## Krok 2: Získejte přiřazení úkolů a zdrojů
```java
// Získejte první úkol projektu
Task task = project.getRootTask().getChildren().getById(1);
// Získejte první přiřazení zdrojů projektu
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Krok 3: Generujte časově uspořádaná data s plochým obrysem
```java
// Plochý obrys je výchozí obrys
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 4: Změňte Contour na Turtle
```java
// Změňte obrys na Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 5: Změňte Contour na BackLoaded
```java
// Změňte obrys na BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 6: Změňte Contour na FrontLoaded
```java
// Změňte obrys na FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 7: Změňte Contour na Bell
```java
// Změňte obrys na Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 8: Změňte Contour na EarlyPeak
```java
// Změňte obrys na EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 9: Změňte Contour na LatePeak
```java
// Změňte obrys na LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 10: Změňte Contour na DoublePeak
```java
// Změňte obrys na DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Závěr
tomto tutoriálu jsme probrali, jak generovat časově uspořádaná data pro přiřazení zdrojů pomocí Aspose.Tasks for Java. Pochopení různých pracovních obrysů může projektovým manažerům pomoci efektivně řídit přidělování zdrojů a plánování v jejich projektech.
## FAQ
### Mohu používat Aspose.Tasks s jinými knihovnami Java?
Ano, Aspose.Tasks lze integrovat s jinými knihovnami Java, aby se zlepšily možnosti řízení projektů.
### Je Aspose.Tasks vhodný pro rozsáhlé podnikové projekty?
Aspose.Tasks je rozhodně navržen tak, aby zvládal projekty všech velikostí, včetně rozsáhlých podnikových projektů.
### Poskytuje Aspose.Tasks podporu pro různé formáty souborů projektu?
Ano, Aspose.Tasks podporuje různé formáty souborů projektu, včetně MPP, XML a MPX.
### Mohu upravit pracovní obrysy podle požadavků mého projektu?
Ano, Aspose.Tasks umožňuje uživatelům definovat vlastní pracovní obrysy tak, aby vyhovovaly jejich specifickým projektovým potřebám.
### Existuje komunitní fórum, kde mohu získat pomoc s Aspose.Tasks?
 Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu a diskuze.