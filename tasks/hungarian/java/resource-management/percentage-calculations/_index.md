---
title: MS Project erőforrás százalékos számítás az Aspose.Tasks segítségével
linktitle: Végezze el az Aspose.Tasks erőforrásainak százalékos számításait
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan számíthatja ki az MS Project erőforrás százalékos arányát az Aspose.Tasks for Java segítségével. Lépésről lépésre útmutató kódpéldákkal.
weight: 14
url: /hu/java/resource-management/percentage-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project erőforrás százalékos számítás az Aspose.Tasks segítségével

## Bevezetés
Üdvözöljük lépésről lépésre szóló útmutatónkban az MS Project erőforrások százalékos számításairól az Aspose.Tasks for Java használatával. Ebben az oktatóanyagban az Aspose.Tasks kihasználásának folyamatát mutatjuk be, amellyel hatékonyan lehet manipulálni és kinyerni az erőforrásadatokat a Microsoft Project fájlokból. Az Aspose.Tasks egy hatékony Java API, amely átfogó szolgáltatásokat nyújt a Microsoft Project dokumentumokkal való munkavégzéshez, lehetővé téve a fejlesztők számára, hogy zökkenőmentesen integrálják a projektmenedzsment funkciókat Java alkalmazásaikba.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy beállította a következő előfeltételeket:
### Java fejlesztői környezet
 Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszerén. A JDK-t letöltheti és telepítheti innen[itt](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks Library
Az Aspose.Tasks könyvtárat integrálni kell a Java projektbe. Ha még nem tette meg, letöltheti a könyvtárat innen[itt](https://releases.aspose.com/tasks/java/) és kövesse a dokumentációban található telepítési utasításokat[itt](https://reference.aspose.com/tasks/java/).

## Csomagok importálása
Mielőtt elkezdenénk a kódolást, importáljuk az ehhez az oktatóanyaghoz szükséges csomagokat:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## 1. lépés: A Project File Path beállítása
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` a Microsoft Project fájl elérési útjával.
## 2. lépés: Töltse be a projektet
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Ez a kód betölti a „Software Development.mpp” nevű Microsoft Project fájlt, amely a megadott adatkönyvtárban található.
## 3. lépés: Ismétlés az erőforrásokon keresztül
```java
for (Resource res : prj.getResources()) {
```
A projektben minden egyes erőforrást végigfutunk.
## 4. lépés: Ellenőrizze az erőforrás nevét és a befejezett munka százalékos arányát
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Ellenőrizzük, hogy az erőforrás neve nem null-e, majd kinyomtatjuk az egyes erőforrások elvégzett munka százalékos arányát.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használhatja az Aspose.Tasks for Java-t az MS Project erőforrásaira vonatkozó százalékos számítások hatékony végrehajtásához. Az alábbi lépések követésével zökkenőmentesen integrálhatja a projektmenedzsment funkciókat Java-alkalmazásaiba, így továbbfejlesztett vezérlést és betekintést nyújt a projekt erőforrás-felhasználásába.
## GYIK
### Használhatom az Aspose.Tasks for Java-t más Java-keretrendszerekkel?
Igen, az Aspose.Tasks for Java kompatibilis a különféle Java-keretrendszerekkel, például a Spring, a Hibernate stb.
### Az Aspose.Tasks támogatja a Microsoft Project fájlok összes verzióját?
Az Aspose.Tasks támogatja a Microsoft Project fájlok összes verzióját, beleértve az MPP-t, az MPT-t, az XML-t és egyebeket.
### Módosíthatom a projekt ütemezését az Aspose.Tasks segítségével?
Természetesen az Aspose.Tasks átfogó szolgáltatásokat kínál a projekt ütemezésének módosításához, beleértve a feladatokat, erőforrásokat, naptárakat és egyebeket.
### Létezik közösségi fórum az Aspose.Tasks támogatására?
 Igen, segítséget találhat és kapcsolatba léphet más felhasználókkal az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).
### Az Aspose.Tasks kínál ideiglenes licenceket értékelési célokra?
 Igen, ideiglenes engedélyt szerezhet az értékeléshez[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
