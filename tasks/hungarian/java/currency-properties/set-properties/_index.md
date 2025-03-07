---
title: Állítsa be a pénznem tulajdonságait az Aspose.Tasks projektekben
linktitle: Állítsa be a pénznem tulajdonságait az Aspose.Tasks projektekben
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan állíthat be pénznemtulajdonságokat az Aspose.Tasks projektekben Java használatával. A Microsoft Project fájlokat könnyedén kezelheti.
weight: 11
url: /hu/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a pénznem tulajdonságait az Aspose.Tasks projektekben

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan állíthat be pénznemtulajdonságokat az Aspose.Tasks projektekben Java használatával. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat a[letöltési link](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): Válassza ki a kívánt IDE-t, például az Eclipse-t vagy az IntelliJ IDEA-t.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat az Aspose.Tasks használatához Java nyelven.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## 1. lépés: Állítsa be az adatkönyvtárat
Állítsa be az adatkönyvtárat, ahol a projektfájlok találhatók.
```java
String dataDir = "Your Data Directory";
```
## 2. lépés: Hozzon létre projektpéldányt
Hozzon létre egy új projektpéldányt az Aspose.Tasks használatával.
```java
Project project = new Project();
```
## 3. lépés: Állítsa be a pénznem tulajdonságait
Most állítsuk be a projekt pénznemtulajdonságait.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## 4. lépés: Mentse el a projektet
Mentse el a projektet a frissített pénznemtulajdonságokkal.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## 5. lépés: Befejezési üzenet megjelenítése
Jelenítsen meg egy üzenetet, amely jelzi a folyamat sikeres befejezését.
```java
System.out.println("Process completed Successfully");
```
Gratulálunk! Sikeresen beállította a pénznemtulajdonságokat egy Aspose.Tasks projektben Java használatával.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használhatja az Aspose.Tasks for Java-t pénznemtulajdonságok beállítására a projektfájlokban. Az Aspose.Tasks segítségével a fejlesztők hatékonyan kezelhetik a projektadatokat, így értékes eszközzé válik a projektmenedzsment alkalmazásokhoz.
## GYIK
### Beállíthatok több pénznemet egyetlen projektben az Aspose.Tasks segítségével?
Igen, az Aspose.Tasks lehetővé teszi több pénznem kezelését egyetlen projektfájlon belül.
### Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?
Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, így biztosítja a kompatibilitást a különböző környezetekben.
### Az Aspose.Tasks támogatja az egyéni pénznemformátumokat?
Az Aspose.Tasks minden bizonnyal rugalmasságot kínál az egyéni pénznemformátumok meghatározásában, hogy megfeleljen a konkrét projektkövetelményeknek.
### Integrálhatom az Aspose.Tasks-t más Java könyvtárakkal vagy keretrendszerekkel?
Igen, az Aspose.Tasks zökkenőmentesen integrálható más Java-könyvtárakba és -keretrendszerekbe, fokozva annak funkcionalitását és sokoldalúságát.
### Hol találhatok további támogatást vagy segítséget az Aspose.Tasks számára?
 További támogatásért keresse fel a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15), ahol hasznos forrásokat találhat, és kapcsolatba léphet a közösséggel.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
