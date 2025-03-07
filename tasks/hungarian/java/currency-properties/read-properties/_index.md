---
title: Olvassa el a valutatulajdonságokat az Aspose.Tasks projektekben
linktitle: Olvassa el a valutatulajdonságokat az Aspose.Tasks projektekben
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan nyerhet ki valutainformációkat az MS Project fájlokból az Aspose.Tasks for Java segítségével. Lépésről lépésre bemutatott útmutató.
weight: 10
url: /hu/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Olvassa el a valutatulajdonságokat az Aspose.Tasks projektekben

## Bevezetés
Ebben az oktatóanyagban megtanuljuk, hogyan használhatja az Aspose.Tasks for Java-t a valutatulajdonságok kiolvasására a Microsoft Project fájlokból. Az Aspose.Tasks egy hatékony Java API, amely lehetővé teszi a fejlesztők számára, hogy a Microsoft Project telepítése nélkül kezeljék a Microsoft Project dokumentumokat. Az alábbiakban ismertetett lépések követésével könnyedén kinyerheti a pénznemekkel kapcsolatos információkat.
## Előfeltételek
Mielőtt folytatná ezt az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java JAR: Töltse le az Aspose.Tasks for Java könyvtárat innen[itt](https://releases.aspose.com/tasks/java/) és vegye fel a Java projektbe.
## Csomagok importálása
Kezdje azzal, hogy importálja a szükséges csomagokat a Java osztályba:
```java
import com.aspose.tasks.*;
```
## 1. lépés: Állítsa be projektkönyvtárát
Először állítsa be a projektkönyvtárat, ahol a Microsoft Project fájl található. Ezt a könyvtár elérési útját a következőképpen határozhatja meg:
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` a projektkönyvtár tényleges elérési útjával.
## 2. lépés: Hozzon létre egy Project Reader példányt
 Példányosítás a`Project` objektumot a Microsoft Project fájl elérési útjának megadásával:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Biztosítsa a cserét`"project.mpp"` az MS Project fájl nevével.
## 3. lépés: Jelenítse meg a pénznem tulajdonságait
Pénznemtulajdonságok lekérése és megjelenítése a projektfájlból:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Ez a kódszegmens információkat, például pénznemkódot, számjegyeket, szimbólumot és szimbólumpozíciót kér le az MS Project fájlból, és kinyomtatja a konzolra.
## 4. lépés: A folyamat befejezése
Végül nyomtasson ki egy üzenetet, amely jelzi a folyamat sikeres befejezését:
```java
System.out.println("Process completed Successfully");
```
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan olvashatunk valutatulajdonságokat Microsoft Project-fájlokból az Aspose.Tasks for Java segítségével. A vázolt lépések követésével könnyedén kinyerheti a pénznemekkel kapcsolatos információkat a projektfájlokból programozottan, lehetővé téve a zökkenőmentes integrációt Java-alkalmazásaiba.
## GYIK
### K: Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?
V: Az Aspose.Tasks támogatja a Microsoft Project különféle verzióit, beleértve az MS Project 2003-2021 által generált MPP fájlokat.
### K: Módosíthatom a pénznem tulajdonságait az Aspose.Tasks segítségével?
V: Igen, az Aspose.Tasks lehetővé teszi az MS Project fájlokban lévő pénznemtulajdonságok programozott olvasását és módosítását.
### K: Az Aspose.Tasks alkalmas kereskedelmi használatra?
 V: Igen, az Aspose.Tasks egy professzionális használatra tervezett kereskedelmi könyvtár. Vásárolhat licencet[itt](https://purchase.aspose.com/buy).
### K: Az Aspose.Tasks ingyenes próbaverziót kínál?
 V: Igen, igénybe veheti az Aspose.Tasks ingyenes próbaverzióját[itt](https://releases.aspose.com/).
### K: Hol kérhetek segítséget vagy támogatást az Aspose.Tasks-hoz?
 V: Látogassa meg az Aspose.Tasks fórumot[itt](https://forum.aspose.com/c/tasks/15) bármilyen segítségért vagy kérdésért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
