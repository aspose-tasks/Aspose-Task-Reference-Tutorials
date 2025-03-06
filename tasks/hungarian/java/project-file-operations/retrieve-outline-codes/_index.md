---
title: Az MS Project Outline kódok lekérése az Aspose.Tasks-ban
linktitle: Vázlatkódok lekérése az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kérheti le programozottan a Microsoft Project vázlatkódjait az Aspose.Tasks for Java használatával. Növelje projektmenedzsment képességeit.
weight: 15
url: /hu/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az MS Project Outline kódok lekérése az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban megtudjuk, hogyan lehet lekérni a Microsoft Project vázlatkódjait az Aspose.Tasks for Java használatával. Az MS Project vázlatkódjai strukturált módot biztosítanak a projektfeladatok, erőforrások és hozzárendelések kategorizálására és rendszerezésére. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék és kezeljék a Microsoft Project fájlokat.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy beállította a következő előfeltételeket:
### 1. Java fejlesztői környezet
Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszeren. A JDK letölthető és telepíthető az Oracle webhelyéről.
### 2. Aspose.Tasks Library
 Töltse le és foglalja bele az Aspose.Tasks könyvtárat a Java projektbe. A könyvtár letölthető a[Aspose.Tasks for Java letöltési oldal](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Először importálja a szükséges csomagokat az Aspose.Tasks-ból a Java-kódban:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Most bontsuk fel a megadott példakódot több lépésre:
## 1. lépés: Töltse be a projektet
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Ebben a lépésben betöltjük a Microsoft Project fájlt a`Project` objektumot a megadott fájlnév használatával.
## 2. lépés: Keresse le az Outline kódokat
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
A projektben minden egyes vázlatkód-definíción végigfutunk.
## 3. lépés: Nyissa meg az Outline Code tulajdonságait
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Lekérjük és kinyomtatjuk a vázlatkód-definíció különféle tulajdonságait, például Alias-t, Mezőazonosítót és Mezőnevet.
## 4. lépés: Ellenőrizze a vállalati egyéni kódot
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Ellenőrizzük, hogy a körvonalkód vállalati egyedi kód-e, és ennek megfelelően kinyomtatjuk az eredményt.
## 5. lépés: Vázlati kódmaszkok megjelenítése
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iterálunk minden, a vázlatkódhoz társított maszkot, és kinyomtatjuk a szint és a maszk értékét.
## 6. lépés: Jelenítse meg a vázlatkód értékeket
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Iterálunk minden vázlatkód értéket, és kinyomtatjuk annak leírását, értékazonosítóját, értékét és típusát.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet lekérni az MS Project vázlatkódjait az Aspose.Tasks for Java használatával. A megadott lépések követésével hatékonyan érheti el és kezelheti a Java-alkalmazások vázlatkódjait, lehetővé téve a fejlett projektkezelési lehetőségeket.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks for Java-t a vázlatkódok módosítására egy projektfájlban?
V: Igen, az Aspose.Tasks for Java API-kat biztosít az MS Project fájlok vázlatkódjainak programozott módosításához.
### 2. kérdés: Elérhető az Aspose.Tasks for Java próbaverziója?
 V: Igen, letöltheti az Aspose.Tasks Java ingyenes próbaverzióját a webhelyről[Aspose.Tasks webhely](https://releases.aspose.com/).
### 3. kérdés: Hogyan kaphatok műszaki támogatást az Aspose.Tasks for Java-hoz?
 V: Technikai támogatást kaphat, ha felkeresi a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) és elküldi a kérdéseit.
### 4. kérdés: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Igen, megvásárolhat egy ideiglenes licencet az Aspose.Tasks for Java számára a[vásárlási oldal](https://purchase.aspose.com/temporary-license/).
### 5. kérdés: Hol találom az Aspose.Tasks for Java teljes dokumentációját?
 V: Hivatkozhat a[dokumentáció](https://reference.aspose.com/tasks/java/) az Aspose.Tasks for Java használatával kapcsolatos részletes információkért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
