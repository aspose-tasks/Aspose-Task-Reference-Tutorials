---
title: Támogassa az értékelési funkciókat az Aspose.Tasks formulákban
linktitle: Támogassa az értékelési funkciókat az Aspose.Tasks formulákban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan támogassa az MS Project függvények kiértékelését Aspose.Tasks képletekben Java használatával. Növelje termelékenységét az Aspose.Tasks segítségével.
weight: 10
url: /hu/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Támogassa az értékelési funkciókat az Aspose.Tasks formulákban


## Bevezetés
Az Aspose.Tasks for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat. Az egyik legfontosabb jellemzője, hogy támogatja az MS Project függvények kiértékelését az Aspose.Tasks formulákon belül. Ez a képesség lehetővé teszi a felhasználók számára, hogy összetett számításokat és elemzéseket végezzenek közvetlenül a Java-alkalmazásokon belül.
## Előfeltételek
Mielőtt elkezdené az MS Project függvények integrálását az Aspose.Tasks képletekbe, győződjön meg arról, hogy rendelkezik a következőkkel:
1. Java fejlesztői környezet: Győződjön meg arról, hogy a Java telepítve van a rendszeren, valamint a Java fejlesztéshez kompatibilis IDE, például az IntelliJ IDEA vagy az Eclipse.
2.  Aspose.Tasks for Java Library: Töltse le és foglalja bele az Aspose.Tasks for Java könyvtárat a Java projektbe. Letöltheti a[Aspose.Tasks for Java letöltési oldal](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Kezdésként importálja a szükséges csomagokat a Java osztályba az Aspose.Tasks funkciók használatához:
```java
import com.aspose.tasks.*;
```

## 1. lépés: Hozzon létre egy új projektobjektumot
 Először hozzon létre egy újat`Project`objektum, amellyel dolgozni:
```java
Project project = new Project();
```
Ez inicializál egy új üres projektet.
## 2. lépés: Határozzon meg egy kiterjesztett attribútumot a feladatokhoz
Ezután határozzon meg egy kiterjesztett attribútumot a feladatokhoz. Ez az attribútum a feladatokhoz társított egyéni adatokat tárol:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Itt létrehozunk egy kiterjesztett típusú attribútumot`Number` feladatokhoz "Sine" névvel.
## 3. lépés: Adja hozzá a kiterjesztett attribútumot a projekthez
Adja hozzá a kiterjesztett attribútumdefiníciót a projekt kiterjesztett attribútumainak listájához:
```java
project.getExtendedAttributes().add(attr);
```
Ez hozzáadja az egyéni attribútumot a projekthez.
## 4. lépés: Hozzon létre egy új feladatot
Most hozzunk létre egy új feladatot a projekten belül:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Ezzel a projekthez hozzáad egy új, „Feladat” nevű feladatot.
## 5. lépés: Társítsa a kiterjesztett attribútumot a feladathoz
Társítsa a korábban létrehozott kiterjesztett attribútumot a feladathoz:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Ez a "Sine" kiterjesztett attribútumot társítja a feladathoz.

## Következtetés
Összefoglalva, az MS Project funkcióinak integrálása a Java Aspose.Tasks képleteibe egy egyszerű folyamat. A megadott lépések követésével hatékonyan használhatja az Aspose.Tasks for Java hatékony képességeit a Microsoft Project fájlok programozott kezeléséhez és elemzéséhez.
## GYIK
### K: Az Aspose.Tasks for Java kezelheti az összetett MS Project képleteket?
V: Igen, az Aspose.Tasks for Java támogatja az MS Project függvények széles skálájának kiértékelését, lehetővé téve a Java alkalmazásokon belüli összetett számításokat.
### K: Az Aspose.Tasks for Java kompatibilis a Microsoft Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks for Java támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### K: Kipróbálhatom az Aspose.Tasks for Java programot vásárlás előtt?
 V: Igen, letöltheti az Aspose.Tasks for Java ingyenes próbaverzióját a webhelyről[itt](https://purchase.aspose.com/buy).
### K: Hogyan kaphatok támogatást az Aspose.Tasks for Java számára?
V: Támogatást kaphat az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).
### K: Rendelkezésre áll ideiglenes licenc az Aspose.Tasks for Java számára?
 V: Igen, tesztelési célból ideiglenes licencet szerezhet be az Aspose webhelyéről[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
