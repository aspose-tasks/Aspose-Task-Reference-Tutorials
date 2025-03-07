---
title: Figyelje a túlórákat, a fennmaradó költségeket és a munkát az Aspose.Tasks-ban
linktitle: Figyelje a túlórákat, a fennmaradó költségeket és a munkát az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan figyelheti a túlórákat, a fennmaradó költségeket, és hogyan dolgozhat a Java-projektekben az Aspose.Tasks használatával. Egyszerű lépések a hatékony projektmenedzsmenthez.
weight: 18
url: /hu/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Figyelje a túlórákat, a fennmaradó költségeket és a munkát az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban megtanuljuk, hogyan használhatjuk az Aspose.Tasks for Java alkalmazást a túlórák, a fennmaradó költségek és a projektben végzett munka nyomon követésére. Ez felbecsülhetetlen értékű lehet a projektmenedzserek és a csapatvezetők számára annak érdekében, hogy a projektek a tervek szerint és a költségvetésen belül maradjanak.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK): Aspose.Tasks for Java Java SE 6 vagy újabb verziót igényel.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse a könyvtárat innen[itt](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): bármilyen Java IDE, például az Eclipse, az IntelliJ IDEA vagy a NetBeans.

## Csomagok importálása
Kezdje azzal, hogy importálja a szükséges csomagokat a Java fájlba:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 1. lépés: Állítsa be az adattárat
Határozza meg a könyvtárat, ahol a projektfájlja található:
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` a projektfájl elérési útjával.
## 2. lépés: Töltse be a projektet
 Példányosítás a`Project` objektumot, és töltse be a projektfájlt:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Cserélje ki`"ResourceAssignmentOvertimes.mpp"` a projektfájl nevével.
## 3. lépés: Ismétlés az erőforrás-hozzárendeléseken keresztül
Tekintse át a projektben szereplő egyes erőforrás-hozzárendeléseket:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## 4. lépés: Nyomtassa ki a túlóraköltségeket és a munkát
Minden erőforrás-hozzárendelésnél lekérheti és kinyomtathatja a túlóraköltségeket és a munkát:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## 5. lépés: Nyomtassa ki a fennmaradó költségeket és munkát
Kérje le és nyomtassa ki a fennmaradó költségeket és munkát az egyes erőforrás-hozzárendeléseknél:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## 6. lépés: Nyomtassa ki a fennmaradó túlóraköltségeket és munkát
Lekérheti és kinyomtathatja a fennmaradó túlóraköltségeket és munkát minden erőforrás-hozzárendeléshez:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Következtetés
A túlórák, a fennmaradó költségek és a projektben végzett munka nyomon követése elengedhetetlen a sikeres projektmenedzsmenthez. Az Aspose.Tasks for Java segítségével könnyedén elérheti és nyomon követheti ezeket az információkat, biztosítva ezzel, hogy projektjei az ütemtervben és a költségvetésen belül maradjanak.
## GYIK
### Használhatom az Aspose.Tasks for Java-t más Java könyvtárakkal?
Igen, az Aspose.Tasks for Java kompatibilis más Java könyvtárakkal és keretrendszerekkel.
### Az Aspose.Tasks támogatja a különböző projektfájlformátumokat?
Igen, az Aspose.Tasks különféle projektfájlformátumokat támogat, beleértve az MPP-t, az XML-t és egyebeket.
### Létezik próbaverzió?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### Hol találok támogatást, ha problémákba ütközöm?
 Látogassa meg az Aspose.Tasks fórumot[itt](https://forum.aspose.com/c/tasks/15) támogatásért.
### Hogyan vásárolhatok licencet az Aspose.Tasks számára?
 Engedélyt vásárolhat innen[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
