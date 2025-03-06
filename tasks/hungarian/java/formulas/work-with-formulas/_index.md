---
title: MS Project Formulák Aspose.Tasks-szal Java-hoz
linktitle: Dolgozzon képletekkel az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kezelheti az MS Project fájlokat Java nyelven az Aspose.Tasks könyvtár használatával. Az attribútumok egyszerű létrehozása, módosítása és kiszámítása.
weight: 11
url: /hu/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Formulák Aspose.Tasks-szal Java-hoz

## Bevezetés
Ebben az oktatóanyagban az Aspose.Tasks for Java használatával való MS Project Formulas-okkal való munkavégzésről fogunk beszélni. Az Aspose.Tasks egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat. Kiterjedt szolgáltatásaival könnyedén hozhat létre, olvashat, módosíthat és konvertálhat projektfájlokat Java alkalmazásokban.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy beállította a következő előfeltételeket:
### Java fejlesztői környezet
Győződjön meg arról, hogy Java Development Kit (JDK) van telepítve a rendszerére. A legújabb JDK letölthető és telepíthető az Oracle webhelyéről.
### Aspose.Tasks Library
Az Aspose.Tasks könyvtárat hozzá kell adni a Java projekthez. A könyvtár letölthető a[Aspose.Tasks for Java letöltési oldal](https://releases.aspose.com/tasks/java/) és vegye fel a projekt függőségei közé.

## Csomagok importálása
Mielőtt belevágna a példákba, importálja a szükséges csomagokat a Java kódjába:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Bontsuk fel a példát több lépésre:
## 1. lépés: Hozzon létre egy tesztprojektet egyéni mezővel
```java
Project project = CreateTestProjectWithCustomField();
```
 Először hozzon létre egy tesztprojektet egyéni mezővel a`CreateTestProjectWithCustomField()` módszer. Ez a metódus az újonnan létrehozott projektet képviselő Project objektumot ad vissza.
## 2. lépés: Adjon meg egy kiterjesztett attribútum-definíciót
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Töltse le a kiterjesztett attribútumdefiníciót a projektből, és állítsa be az álnevet és a képletet. Ebben a példában egy attribútumot határozunk meg a befejezés dátuma és a határidő közötti napok számának kiszámításához.
## 3. lépés: Állítsa be a feladat határidejét
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Hozzon létre egy naptárobjektumot, és állítsa be a határidő dátumát. Ezután kérjen le egy feladatot a projektből, és állítsa be a határidőt a Naptár objektum segítségével.
## 4. lépés: Mentse el a projektet
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Végül mentse a projektet a megadott néven és formátumú fájlba. Ebben az esetben MPP-fájlként mentjük el.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan dolgozhatunk az MS Project Formulákkal az Aspose.Tasks for Java használatával. Az alábbi lépések követésével hatékonyan kezelheti a projektfájlokat programozottan, egyéni mezőket adhat hozzá, és képletek alapján számíthat ki attribútumokat.

## GYIK
### K: Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
V: Igen, az Aspose.Tasks különféle programozási nyelveket támogat, beleértve a Java-t, a .NET-et és egyebeket.
### K: Elérhető az Aspose.Tasks ingyenes próbaverziója?
 V: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### K: Hol találom az Aspose.Tasks dokumentációját?
 V: Az Aspose.Tasks dokumentációját megtalálja[itt](https://reference.aspose.com/tasks/java/).
### K: Hogyan kaphatok támogatást az Aspose.Tasks-hoz?
 V: Támogatásért keresse fel a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### K: Szükségem van ideiglenes licencre az Aspose.Tasks használatához?
V: Ha további funkciókra van szüksége, ideiglenes licencet szerezhet be a webhelyen[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
