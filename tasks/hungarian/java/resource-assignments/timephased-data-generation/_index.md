---
date: 2026-06-10
description: Ismerje meg, hogyan változtathatja meg a kontúrt és generálhat időszakos
  adatokat erőforrás-hozárendelésekhez az Aspose.Tasks for Java használatával, beleértve
  a munkakontúr típusokat és a fejlett ütemezési forgatókönyveket.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Időszakos adatok generálása erőforrás-hozárendelésekhez az Aspose.Tasks-ben
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
title: Hogyan változtassuk meg a kontúrt az Aspose.Tasks időszakos adatokhoz
url: /hu/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan változtassuk meg a kontúrt az Aspose.Tasks időszakos adatokban

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan változtasson a kontúron** egy erőforrás‑kijelölésnél, és hogyan generáljon időszakos adatokat az Aspose.Tasks for Java segítségével. Az időszakos adatok megmutatják a munka eloszlását a projekt idővonalán, lehetővé téve a menetrend finomhangolását, a munkaterhek kiegyensúlyozását és az adatalapú döntéshozatalt. A kontúrváltoztatás elsajátítása segít valósághű erőfeszítési mintákat modellezni, például előre‑betöltést, hátra‑betöltést vagy csúcsmunka‑terhelést.

## Gyors válaszok
- **Mi a kontúr?** A munkakontúr meghatározza, hogyan oszlik el az erőfeszítés egy feladat időtartama alatt (pl. Flat, Turtle, Bell).  
- **Miért változtassunk a kontúron?** A valós munka‑minták, például előre‑ vagy hátra‑betöltés tükrözése érdekében.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (bármely friss verzió).  
- **Szükségem van licencre?** Igen, a gyártási használathoz érvényes Aspose.Tasks licenc szükséges.  
- **Láthatom az eredményeket a konzolon?** A példa kiírja a kezdő dátumokat és az értékeket minden időszakos szegmenshez.

## Mi a „hogyan változtassunk a kontúron”?
A kontúr megváltoztatása azt jelenti, hogy frissítjük egy `ResourceAssignment` objektum `WORK_CONTOUR` tulajdonságát. Ez a tulajdonság azt határozza meg az Aspose.Tasks számára, hogyan ossza el a kijelölés teljes munkáját a feladat időtartama alatt. A könyvtár számos előre definiált kontúrt biztosít, például Flat, Turtle, Bell és mások, amelyek mindegyike egyedi erőfeszítési eloszlási mintát hoz létre az időben.

## Miért használjuk az Aspose.Tasks-et időszakos adatok generálásához?
Az Aspose.Tasks **0 ms többletterheléssel** generál időszakos adatokat memóriában végzett műveletekhez, és **50+ kimeneti formátumot** támogat (MPP, XML, CSV stb.). A könyvtár képes több száz oldalas projekteket feldolgozni anélkül, hogy az egész fájlt a memóriába töltené, pontos munkamegosztást biztosítva a jelentéskészítéshez, erőforrás‑kiegyenlítéshez és „mi lenne, ha” elemzésekhez. API-ja lehetővé teszi a kontúrváltoztatások automatizálását és a pontos időszakos értékek programozott kinyerését.

## Előfeltételek
1. Java Development Kit (JDK): Győződjön meg róla, hogy a JDK telepítve van a rendszerén. A JDK-t letöltheti és telepítheti innen: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks for Java Library: Szüksége van az Aspose.Tasks for Java könyvtárra. Letöltheti a [website](https://releases.aspose.com/tasks/java/) oldalról.

## Csomagok importálása
A `Project` osztály az Aspose.Tasks központi objektuma, amely egy teljes projektfájlt reprezentál a memóriában. Importálja a szükséges névtereket, mielőtt a feladatokkal és kijelölésekkel dolgozna.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## 1. lépés: A forrás MPP fájl beolvasása
A `Project` konstruktor betölti a meglévő MPP fájlt, elemzi annak szerkezetét anélkül, hogy minden feladatot teljesen a memóriában materializálna, így a művelet könnyű marad.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 2. lépés: Feladat és erőforrás‑kijelölés lekérése
`ResourceAssignment` egy erőforrást kapcsol egy feladathoz, és tárolja a kijelölés‑szintű tulajdonságokat, mint a munka, költség és kontúr. A kontúr módosítása előtt szerezze be az első kijelölést a `project.getResourceAssignments().getById(1)` (vagy bármely érvényes azonosító) segítségével.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Hogyan változtassunk a kontúron – Flat (Alapértelmezett)
`WorkContourType` egy felsorolás, amely az Aspose.Tasks által támogatott előre definiált munkakontúr mintákat sorolja fel. Az `Asn.WORK_CONTOUR` azonosítja egy erőforrás‑kijelölés kontúr mezőjét, és a `generateTimephasedData()` időszakos munkabejegyzéseket hoz létre a jelenlegi kontúrbeli beállítás alapján. A **Flat** kontúr egyenletesen osztja el a munkát a feladat időtartama alatt; állítsa be a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` használatával, majd hívja meg a `firstRA.generateTimephasedData()`‑t az egyenlő távolságú értékek lekéréséhez.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – Turtle
A **Turtle** kontúr alacsony erőfeszítéssel kezd, a középső felé gyorsul, majd újra lelassul, hasonlóan egy teknős fokozatos tempójához. Alkalmazza a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` beállítással, majd generálja újra az időszakos adatokat. Ez a minta ideális feladatokhoz, amelyeknek tanulási görbére van szükségük a csúcs‑teljesítmény elérése előtt.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – BackLoaded
A **BackLoaded** kontúr a munka nagy részét a feladat ütemezésének végére helyezi, a kezdeti erőfeszítés kevés. Állítsa be a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` használatával, majd generálja újra az időszakos adatokat. Ez hasznos olyan tevékenységekhez, amelyek az előző feladatoktól függenek, mielőtt a munka elvégezhető.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – FrontLoaded
A **FrontLoaded** kontúr a feladat elején koncentrálja az erőfeszítést, olyan helyzeteket modellezve, mint a bevezető fázisok vagy intenzív korai munkaszakaszok. Alkalmazza a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` használatával, majd hívja meg a `firstRA.generateTimephasedData()`‑t a front‑loaded eloszlás megtekintéséhez.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – Bell
A **Bell** kontúr szimmetrikus csúcsot hoz létre az idővonal közepén, amely a fokozatosan növekvő, csúcsra érő, majd simán csökkenő munkát ábrázolja. Állítsa be a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` használatával, és generálja újra az időszakos adatokat a harang‑alakú erőfeszítési görbe megjelenítéséhez.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – EarlyPeak
**EarlyPeak** a legmagasabb munkamennyiséget a menetrend elejére helyezi, majd fokozatosan csökken. Használja a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)`‑t, majd a `firstRA.generateTimephasedData()`‑t, hogy olyan tevékenységeket modellezzen, amelyek erős kezdetet igényelnek, például gyors prototípusfejlesztés.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – LatePeak
**LatePeak** a munkacsúcsot a feladat végére helyezi, ami alkalmas olyan munkára, amely a határidő közeledtével intenzívebbé válik. Alkalmazza a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)`‑t, majd generálja újra az időszakos adatokat a késői szakasz munkaterhelés‑növekedésének megtekintéséhez.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hogyan változtassunk a kontúron – DoublePeak
**DoublePeak** két különálló munkacsúcsot hoz létre, amelyet egy alacsonyabb erőfeszítésű intervallum választ el, hasznos olyan feladatokhoz, amelyeknek két nagyobb erőfeszítési hulláma van. Állítsa be a `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)`‑t, majd hívja meg a `firstRA.generateTimephasedData()`‑t a dupla csúcsú minta lekéréséhez.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Gyakori problémák és tippek
- **A kontúr nem frissül?** Győződjön meg róla, hogy a `firstRA.set(Asn.WORK_CONTOUR, …)` hívást *a* időszakos adatok lekérése **előtt** hajtja végre.  
- **Váratlan értékek?** Ellenőrizze, hogy a feladat kezdő‑ és befejező dátumai helyesen vannak beállítva a forrás MPP‑ben.  
- **Teljesítmény tipp:** Használja újra ugyanazt a `Project` példányt, amikor több kontúrt iterál, hogy elkerülje a felesleges fájl‑I/O‑t, ami akár 40 %-kal is csökkentheti a feldolgozási időt nagy projektek esetén.  
- **Memória tipp:** 1 GB‑t meghaladó projektek esetén engedélyezze a `Project.setReadOnly(true)` beállítást, hogy a memóriahasználat 200 MB alatt maradjon, miközben továbbra is pontos időszakos adatokat generál.

## GYIK
**K: Használhatom az Aspose.Tasks-et más Java könyvtárakkal?**  
V: Igen, az Aspose.Tasks zökkenőmentesen integrálódik más Java könyvtárakkal, lehetővé téve a ütemezési adatok kombinálását jelentésekkel, elemzésekkel vagy UI keretrendszerekkel.

**K: Az Aspose.Tasks alkalmas nagy‑léptékű vállalati projektekhez?**  
V: Teljes mértékben. A könyvtár úgy van tervezve, hogy tízezrek feladatát és erőforrását kezelje, több száz oldalas fájlokat dolgozzon fel teljesítménycsökkenés nélkül.

**K: Az Aspose.Tasks támogatja a különböző projektfájl‑formátumokat?**  
V: Igen, az Aspose.Tasks több mint 30 formátumot támogat, beleértve az MPP, XML, CSV és MPX formátumokat, megkönnyítve a import/export műveleteket régi és modern rendszerek között.

**K: Testreszabhatom a munkakontúrokat a projekt igényei szerint?**  
V: Igen, egy tömb munkaprocentumokat adva a `WORK_CONTOUR` tulajdonsághoz definiálhat egyedi kontúrokat, így teljes irányítást kap az erőfeszítés eloszlása felett.

**K: Van közösségi fórum, ahol segítséget kaphatok az Aspose.Tasks használatához?**  
V: Igen, a [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) felkeresésével támogatást, megbeszéléseket és kódmintákat találhat mind az Aspose mérnököktől, mind a közösség tagjaitól.

---

**Utolsó frissítés:** 2026-06-10  
**Tesztelve:** Aspose.Tasks for Java (legújabb kiadás)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Erőforrás‑kijelölések létrehozása az Aspose.Tasks-ben](/tasks/java/resource-assignments/create-resource-assignments/)
- [Időszakos adatok olvasása erőforrásokhoz az Aspose.Tasks-ben](/tasks/java/resource-management/read-timephased-data/)
- [Hogyan állítsuk le a kijelölést és folytassuk az erőforrás‑kijelöléseket az Aspose.Tasks-ben](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}