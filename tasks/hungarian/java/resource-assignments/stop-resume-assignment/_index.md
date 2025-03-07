---
title: Állítsa le és folytassa az erőforrás-hozzárendeléseket az Aspose.Tasks programban
linktitle: Állítsa le és folytassa az erőforrás-hozzárendeléseket az Aspose.Tasks programban
second_title: Aspose.Tasks Java API
description: Ezzel a lépésenkénti oktatóanyaggal megtudhatja, hogyan kezelheti hatékonyan az erőforrás-hozzárendeléseket az Aspose.Tasks for Java programban.
weight: 23
url: /hu/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa le és folytassa az erőforrás-hozzárendeléseket az Aspose.Tasks programban

## Bevezetés
Ebben az oktatóanyagban megtanuljuk, hogyan állíthatjuk le és folytathatjuk az erőforrás-hozzárendeléseket az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy hatékony Java API, amely lehetővé teszi a fejlesztők számára, hogy Microsoft Project fájlokkal dolgozzanak anélkül, hogy Microsoft Projectet kellene telepíteniük a rendszerükre. A folyamatot kezelhető lépésekre bontjuk, hogy könnyen követhető legyen.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Tasks a Java könyvtárhoz letöltve. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
- A Java programozás alapvető ismerete.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat a Java projektünkbe:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## 1. lépés: Töltse be a projektfájlt
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
// Töltse be a projektfájlt
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Ebben a lépésben betöltjük a projektfájlt a`Project` objektum a fájl elérési útját használva.
## 2. lépés: Ismétlés az erőforrás-hozzárendeléseken keresztül
```java
// Határozza meg a minimális dátumot
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iteráljon erőforrás-hozzárendeléseken keresztül
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Itt meghatározunk egy minimális dátumot, és elkezdjük az iterációt a projekt minden erőforrás-hozzárendelésén keresztül.
## 3. lépés: Ellenőrizze a leállítási és folytatási dátumokat
```java
    // Ellenőrizze a leállítás dátumát
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Ellenőrizze az önéletrajz dátumát
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Ebben a lépésben ellenőrizzük, hogy az egyes erőforrás-hozzárendelések leállítási és folytatási dátuma a minimális dátum előtt van-e. Ha igen, akkor "NA"-t nyomtatunk, ellenkező esetben a megfelelő dátumokat.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthatjuk le és folytathatjuk az erőforrás-hozzárendeléseket az Aspose.Tasks for Java programban. A megadott lépések követésével könnyedén implementálhatja ezt a funkciót Java projektjeibe.

## GYIK
### Használhatom az Aspose.Tasks programot a Microsoft Project telepítése nélkül?
Igen, az Aspose.Tasks lehetővé teszi a Microsoft Project fájlokkal való munkát anélkül, hogy a Microsoft Projectet telepítenie kellene a rendszerére.
### Hol találok további dokumentációt?
 Részletes dokumentációt találhat[itt](https://reference.aspose.com/tasks/java/).
### Van ingyenes próbaverzió?
 Igen, ingyenes próbaverziót kaphat[itt](https://releases.aspose.com/).
### Hogyan kaphatok támogatást, ha bármilyen problémám van?
Támogatást kaphat a közösségtől[itt](https://forum.aspose.com/c/tasks/15).
### Vásárolhatok ideiglenes licencet?
 Igen, vásárolhat ideiglenes licencet[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
