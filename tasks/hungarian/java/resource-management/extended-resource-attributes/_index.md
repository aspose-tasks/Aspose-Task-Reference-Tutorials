---
title: Hatékonyan kezelheti az MS projekt attribútumait az Aspose.Tasks segítségével
linktitle: Az Aspose.Tasks kiterjesztett erőforrás-attribútumainak kezelése
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kezelheti hatékonyan a kiterjesztett Microsoft Project erőforrás-attribútumokat az Aspose.Tasks for Java használatával. Egyszerű lépések és átfogó útmutató.
weight: 11
url: /hu/java/resource-management/extended-resource-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hatékonyan kezelheti az MS projekt attribútumait az Aspose.Tasks segítségével

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet hatékonyan kezelni a kiterjesztett Microsoft Project erőforrás-attribútumokat az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat, és kiterjedt funkciókat kínál a feladat- és erőforráskezeléshez.
## Előfeltételek
Mielőtt folytatná, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1. Java fejlesztői környezet: Állítsa be a Java Development Kit-et (JDK) a rendszeren.
2.  Aspose.Tasks for Java: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat innen[itt](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): Java fejlesztéshez telepítsen egy IDE-t, például az Eclipse-t vagy az IntelliJ IDEA-t.

## Csomagok importálása
Kezdje azzal, hogy importálja a szükséges csomagokat a Java projektbe. 
```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```
## 1. lépés: Adja meg az adatkönyvtárat
Állítsa be a projektadatokat tartalmazó könyvtár elérési útját.
```java
String dataDir = "Your Data Directory";
```
## 2. lépés: Töltse be a projektfájlt
 Példányosítás a`Project` objektumot a Microsoft Project fájl betöltésével.
```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```
## 3. lépés: Határozza meg a kiterjesztett attribútumot
Határozza meg az erőforrás kiterjesztett attribútumait.
```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```
## 4. lépés: Hozzon létre kiterjesztett attribútumot és állítsa be az értéket
Hozza létre a kiterjesztett attribútumot, és rendeljen hozzá egy számértéket.
```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```
## 5. lépés: Erőforrás és kiterjesztett attribútum hozzáadása
Adjon hozzá egy új erőforrást a projekthez a kiterjesztett attribútumával együtt.
```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```
## 6. lépés: Projekt mentése
Mentse el a módosított projektet egy új fájlba.
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
## 7. lépés: Eredmény megjelenítése
Nyomtasson ki egy üzenetet, amely megerősíti a folyamat befejezését.
```java
System.out.println("Process completed Successfully");
```
Ha ezeket a lépéseket aprólékosan követi, az Aspose.Tasks for Java segítségével problémamentesen kezelheti a kiterjesztett MS Project erőforrás-attribútumokat.

## Következtetés
Összefoglalva, az Aspose.Tasks for Java robusztus képességeket biztosít a Microsoft Project fájlok kezeléséhez, beleértve a kiterjesztett erőforrás-attribútumok kezelését is. Az Aspose.Tasks által kínált funkciók kihasználásával a fejlesztők hatékonyan kezelhetik a projektadatokat, hogy megfeleljenek a különféle követelményeknek.
## GYIK
### Az Aspose.Tasks képes kezelni az összetett projektstruktúrákat?
Igen, az Aspose.Tasks átfogó támogatást nyújt összetett projektstruktúrákhoz, lehetővé téve a felhasználók számára a feladatok, erőforrások és attribútumok zökkenőmentes kezelését.
### Az Aspose.Tasks kompatibilis a Microsoft Project legújabb verzióival?
Az Aspose.Tasks rendszert rendszeresen frissítik, hogy biztosítsák a kompatibilitást a Microsoft Project legújabb verzióival, megbízható megoldást biztosítva a felhasználóknak a projektmenedzsmenthez.
### Az Aspose.Tasks támogatja a platformok közötti fejlesztést?
Igen, a fejlesztők használhatják az Aspose.Tasks for Java-t különböző platformokon, így sokoldalú választás a projektmenedzsment alkalmazásokhoz.
### Integrálhatom az Aspose.Tasks-t más Java könyvtárakkal?
Természetesen az Aspose.Tasks zökkenőmentesen integrálható más Java-könyvtárakba a funkcionalitás javítása és a fejlesztési folyamatok egyszerűsítése érdekében.
### Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
Igen, a felhasználók hozzáférhetnek a technikai támogatáshoz az Aspose.Tasks fórumon keresztül, ahol segítséget kérhetnek és kapcsolatba léphetnek a közösséggel.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
