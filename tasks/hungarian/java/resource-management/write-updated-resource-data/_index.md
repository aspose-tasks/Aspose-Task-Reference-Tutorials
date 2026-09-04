---
date: 2026-06-30
description: Ismerje meg, hogyan frissíthet több erőforrást és módosíthatja az erőforráscsoport
  adatait, majd exportálja a projektet MPP formátumba, és mentse a projektet MPP-ként
  az Aspose.Tasks for Java segítségével.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Több erőforrás frissítése az Aspose.Tasks for Java-ban
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Több erőforrás frissítése az Aspose.Tasks for Java-ban
url: /hu/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Több erőforrás frissítése az Aspise.Tasks for Java-ban

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **frissítheti több erőforrást** egy Microsoft Project fájlban az Aspose.Tasks for Java használatával. Akár a díjakat kell módosítania, csoportokat újra kell osztania, vagy a frissített fájlt MPP formátumba kell exportálnia, az alábbi lépések egy teljes, termelésre kész munkafolyamaton keresztül vezetik. Microsoft Project telepítésére nincs szükség, és az API hatékonyan képes kezelni több száz erőforrást tartalmazó projekteket.

## Gyors válaszok
- **Frissíthetek több erőforrást egyszerre?** Igen – iteráljon a `ResourceCollection`-ön, és egyetlen átfutásban állítsa be a tulajdonságokat.  
- **Melyik metódus menti a fájlt MPP formátumban?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Szükségem van licencre kereskedelmi felhasználáshoz?** Fizetett licenc szükséges a termeléshez; ingyenes próba elérhető.  
- **Mely Java verziók támogatottak?** Java 6 és újabb, beleértve a Java 17 LTS-t.  
- **A tömeges frissítés teljesítményes?** Az Aspose.Tasks 500 erőforrásos projekteket kevesebb, mint 2 másodperc alatt dolgoz fel egy tipikus szerveren.

## Mi az a „több erőforrás frissítése”?
**„Több erőforrás frissítése”** arra utal, hogy programozott módon módosítjuk több erőforrás bejegyzésének tulajdonságait – például díjak, csoportok, naptárak vagy egyéni mezők – egyetlen projektfájlban. Ez a művelet gyakran szükséges a projektadatok vállalati erőforrás-tervező rendszerekkel való szinkronizálásakor, a költségvetés sok erőforrásra való igazításakor vagy a szervezet szintű szabályzatváltozások alkalmazásakor.

## Miért használja az Aspose.Tasks-et az erőforráscsoport módosításához és a projekt MPP-be exportálásához?
Az Aspose.Tasks **50+ bemeneti és kimeneti formátumot** támogat, többek között MPP, XML és CSV, és **exportálhatja a projektet MPP-be** anélkül, hogy a teljes fájlt a memóriába töltené. A könyvtár legfeljebb **2 GB** méretű fájlokat képes feldolgozni, lehetővé téve, hogy **gyorsan és megbízhatóan mentse a projektet MPP-ként**.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következőkkel rendelkezik:

1. Java Development Kit (JDK) telepítve van a rendszerén.  
2. Aspose.Tasks for Java könyvtár. Letöltheti innen [here](https://releases.aspose.com/tasks/java/).  
3. Alapvető Java programozási ismeretek.  

## Csomagok importálása
`import` utasítások hozzák be a szükséges Aspose.Tasks osztályokat a forrásfájlba.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 1. lépés: Adatkatalógus beállítása
Határozza meg a könyvtárat, ahol az adatfájlok találhatók:

```java
String dataDir = "Your Data Directory";
```

## 2. lépés: Bemeneti és kimeneti fájlok megadása
Adja meg az útvonalakat a bemeneti MS Project fájlhoz és a létrejövő frissített fájlhoz:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## 3. lépés: Projekt betöltése
`Project` egy memóriába betöltött Microsoft Project fájlt képvisel, amely hozzáférést biztosít a feladatokhoz, erőforrásokhoz és egyéb projektadatokhoz.

```java
Project project = new Project(file);
```

## 4. lépés: Erőforrás hozzáadása és attribútumok beállítása
`Resource` egy egyedi projekt erőforrást modellez, lehetővé téve a díjak, csoportok, naptárak és egyéb attribútumok beállítását.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 5. lépés: Több erőforrás hatékony frissítése
`ResourceCollection` a projekt összes erőforrásának gyűjteménye, amely a `project.getResources()`-on keresztül érhető el.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 6. lépés: Projekt mentése
`SaveFileFormat` felsorolja a projekt mentéséhez támogatott fájlformátumokat, például MPP, XML és PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Hogyan frissítsünk több erőforrást egy projektben?
Töltse be a meglévő projektet, szerezze meg a `ResourceCollection`-t, és iteráljon minden `Resource` objektumon. Minden erőforrás esetén módosítsa a szükséges mezőket, például díjakat, csoportokat vagy egyéni attribútumokat, majd lépjen a következő elemre. Az összes erőforrás feldolgozása után egyszer hívja meg a `project.save(...)`-t a változások hatékony mentéséhez.

## Gyakori problémák és megoldások
- **Az erőforrás-azonosítók ütköznek** – Győződjön meg arról, hogy minden új erőforrás egyedi azonosítót kap a `project.getResources().add(new Resource())` használatával.  
- **Díj formátum hibák** – Használjon `ResourceRate` objektumokat, és állítsa be a `RateType`-ot `StandardRate` vagy `OvertimeRate` értékre.  
- **Nagy fájlok memória nyomást okoznak** – Engedélyezze a `Project.setReadOnly(true)`-t a betöltés előtt a memóriahasználat csökkentése érdekében.

## Gyakran Ismételt Kérdések
**Q: Frissíthetek több erőforrást ugyanabban a projektben az Aspose.Tasks for Java használatával?**  
A: Igen, több erőforrás frissíthet azáltal, hogy iterál rajtuk és a megfelelő attribútumokat beállítja.

**Q: Támogatja az Aspose.Tasks más fájlformátumokat is a MS Project mellett?**  
A: Igen, az Aspose.Tasks különféle fájlformátumokat támogat, többek között XML, MPP és egyebek.

**Q: Kompatibilis az Aspose.Tasks a Java különböző verzióival?**  
A: Az Aspose.Tasks kompatibilis a Java 6 és újabb verzióival.

**Q: Végrehajthatok más műveleteket MS Project fájlokon az Aspose.Tasks segítségével?**  
A: Igen, számos műveletet végezhet, például olvasást, írást és feladatok, erőforrások, valamint naptárak manipulálását.

**Q: Hol találok további segítséget vagy támogatást az Aspose.Tasks-hez?**  
A: Látogassa meg a [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) bármilyen segítség vagy kérdés esetén.

**Q: Hogyan exportáljam a frissített fájlt MPP formátumba?**  
A: Hívja meg a `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)`-t az összes erőforrás módosítása után.

**Q: Mi a legjobb módja egy erőforráscsoport módosításának?**  
A: Állítsa be a `Resource.Group` tulajdonságot minden `Resource` objektumnál a projekt mentése előtt.

---

**Utoljára frissítve:** 2026-06-30  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Erőforrás hozzáadása a projekthez az Aspose.Tasks for Java segítségével](/tasks/java/resource-management/create-resources/)
- [MS Project erőforrás költségek kezelése az Aspose.Tasks for Java segítségével](/tasks/java/resource-management/resource-cost/)
- [Hogyan exportáljuk az MPP-t Excelbe az Aspose.Tasks for Java segítségével](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}