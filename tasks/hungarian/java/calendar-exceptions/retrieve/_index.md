---
title: naptári kivételek lekérése az Aspose.Tasks segítségével
linktitle: naptári kivételek lekérése az Aspose.Tasks segítségével
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kérhet le naptári kivételeket az MS Projectből az Aspose.Tasks for Java segítségével. Lépésről lépésre bemutató útmutató a zökkenőmentes integrációhoz.
type: docs
weight: 13
url: /hu/java/calendar-exceptions/retrieve/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet naptárkivételeket lekérni az MS Projectből a Java Aspose.Tasks könyvtárával. Az Aspose.Tasks egy hatékony eszköz, amely lehetővé teszi a fejlesztők számára a Microsoft Project fájlok programozott kezelését. Lépésről lépésre végigvezetjük a folyamaton, az egyes példákat több lépésre bontva a könnyebb érthetőség érdekében.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java: Töltse le és telepítse az Aspose.Tasks for Java-t innen[itt](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): Bármely tetszőleges IDE-t használhat, például az IntelliJ IDEA-t vagy az Eclipse-t.

## Csomagok importálása
Először is importálnia kell a szükséges csomagokat az Aspose.Tasks használatához:
```java
import com.aspose.tasks.*;
```
## 1. lépés: Állítsa be az adattárat
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
```
 Biztosítsa a cserét`"Your Data Directory"` az MS Project fájlt tartalmazó könyvtár elérési útjával.
## 2. lépés: Töltse be az MS Project fájlt
```java
Project project = new Project(dataDir + "project.mpp");
```
 Ez a sor inicializál egy újat`Project` objektumot az elérési út által megadott MS Project fájl betöltésével.
## 3. lépés: A naptári kivételek lekérése
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Itt a projekt minden naptárán, majd az adott naptáron belüli minden naptárkivételen át ismételjük. Minden kivétel kezdő és befejező dátumát kinyomtatjuk.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet naptárkivételeket lekérni az MS Projectből az Aspose.Tasks for Java segítségével. Ezeket az egyszerű lépéseket követve zökkenőmentesen integrálhatja ezt a funkciót Java-alkalmazásaiba.
## Gyakran Ismételt Kérdések
### Az Aspose.Tasks képes kezelni az MS Project fájlok különböző verzióit?
Igen, az Aspose.Tasks támogatja az MS Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### Elérhető az Aspose.Tasks ingyenes próbaverziója?
 Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Tasks for Java dokumentációját?
 A dokumentációra hivatkozhat[itt](https://reference.aspose.com/tasks/java/).
### Hogyan kaphatok támogatást az Aspose.Tasks programhoz?
 Támogatást kaphat a közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).
### Van lehetőség ideiglenes licencekre az Aspose.Tasks számára?
 Igen, ideiglenes engedélyeket szerezhet be[itt](https://purchase.aspose.com/temporary-license/).