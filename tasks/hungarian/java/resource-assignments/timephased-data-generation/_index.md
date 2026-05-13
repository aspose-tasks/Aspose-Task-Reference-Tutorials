---
date: 2026-01-10
description: Tanulja meg, hogyan változtathatja meg a kontúrt, és generálhat időfázisos
  adatokat az erőforrás‑kiosztásokhoz az Aspose.Tasks for Java használatával, javítva
  a projektmenedzsment hatékonyságát.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan változtassuk meg a kontúrt az Aspose.Tasks időszakos adataiban
url: /hu/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan változtassuk meg a kontúrt az Aspose.Tasks időszakos adatokban

## Gyors válaszok
- **Mi az a kontúr?** A munkakontúr meghatározza, hogyan oszlik el a ráfordítás a feladat időtartama alatt (pl. Flat, Turtle, Bell).  
- **Miért változtassunk kontúrt?** A valós munka minták, például a munka előre‑ vagy hátrafelé terhelésének tükrözése érdekében.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (bármely friss verzió).  
- **Szükségem van licencre?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termelési használathoz.  
- **Megtekinthetem az eredményeket a konzolon?** A példa kiírja a kezdő dátumokat és az értékeket minden időszakos szegmenshez.

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan változtassa meg a kontúrt** egy erőforrás hozzárendelésnél, és hogyan generáljon időszakos adatokat az Aspose.Tasks for Java használatával. Az időszakos adatok megmutatják a munka eloszlását a projekt idővonalán, lehetővé téve a menetrend finomhangolását, a munkaterhelés kiegyensúlyozását és az adatalapú döntéshozatalt.

## Mi a “hogyan változtassuk meg a kontúrt”?
A kontúr módosítása azt jelenti, hogy frissítjük egy `ResourceAssignment` `WORK_CONTOUR` tulajdonságát. Az Aspose.Tasks több előre definiált kontúrt támogat (Flat, Turtle, Bell, stb.), amelyek befolyásolják, hogyan oszlik el a munka az időben.

## Miért használjuk az Aspose.Tasks-et időszakos adatok generálásához?
- **Pontos jelentéskészítés:** Exportálja a pontos munkamegoszlást a jelentéskészítő eszközök számára.  
- **Forgatókönyv tervezés:** Teszteljen különböző kontúrokat az eredeti ütemterv módosítása nélkül.  
- **Automatizálás:** Integrálja CI folyamatokba a projekt állapotának automatikus ellenőrzéséhez.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszerén. A JDK-t letöltheti és telepítheti [itt](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java könyvtár: Szüksége van az Aspose.Tasks for Java könyvtárra. Letöltheti a [weboldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először importáljuk a szükséges csomagokat az Aspose.Tasks használatához:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## 1. lépés: Forrás MPP fájl beolvasása
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 2. lépés: Feladat és erőforrás hozzárendelés lekérése
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Kontúr módosítása – Flat (Alapértelmezett)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kontúr módosítása – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Gyakori problémák és tippek
- **A kontúr nem frissül?** Győződjön meg róla, hogy a `firstRA.set(Asn.WORK_CONTOUR, …)` hívást a időszakos adatok lekérése *előtt* hajtja végre.
- **Váratlan értékek?** Ellenőrizze, hogy a feladat kezdő és befejező dátumai helyesen vannak beállítva a forrás MPP-ben.
- **Teljesítmény tipp:** Használja újra ugyanazt a `Project` példányt több kontúr iterálásakor, hogy elkerülje a felesleges fájl I/O műveleteket.

## GYIK
### Használhatom az Aspose.Tasks-et más Java könyvtárakkal?
Igen, az Aspose.Tasks integrálható más Java könyvtárakkal a projektmenedzsment képességek bővítése érdekében.

### Alkalmas az Aspose.Tasks nagy léptékű vállalati projektekhez?
Teljes mértékben, az Aspose.Tasks úgy lett tervezve, hogy bármilyen méretű projektet kezeljen, beleértve a nagy léptékű vállalati kezdeményezéseket.

### Támogatja az Aspose.Tasks a különböző projektfájl-formátumokat?
Igen, az Aspose.Tasks számos formátumot támogat, például MPP, XML és MPX.

### Testreszabhatom a munkakontúrokat a projekt követelményei szerint?
Igen, definiálhat egyedi munkakontúrokat a specifikus ütemezési igényekhez.

### Van közösségi fórum, ahol segítséget kaphatok az Aspose.Tasks használatához?
Igen, felkeresheti az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) támogatás és megbeszélések céljából.

---

**Utolsó frissítés:** 2026-01-10  
**Tesztelve:** Aspose.Tasks for Java (legújabb kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}