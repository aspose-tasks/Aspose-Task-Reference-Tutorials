---
title: Írja meg az MPP projekt összefoglalóját az Aspose.Tasks mappában
linktitle: Írja meg az MPP projekt összefoglalóját az Aspose.Tasks mappában
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan írhat MPP projekt összefoglalókat Java nyelven az Aspose.Tasks használatával. Könnyedén állíthatja be és kérheti le a projektinformációkat.
type: docs
weight: 27
url: /hu/java/project-file-operations/write-mpp-project-summary/
---
## Bevezetés
Ebben az oktatóanyagban megtanuljuk, hogyan használhatjuk az Aspose.Tasks for Java-t MPP projekt összefoglalók írásához. Az Aspose.Tasks egy hatékony Java könyvtár a Microsoft Project fájlokkal való munkavégzéshez. Az alábbiakban vázolt lépések követésével különböző összefoglaló információkat állíthat be és kérhet le egy projektről a könyvtár használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): Válassza ki a kívánt IDE-t a Java fejlesztéshez, például IntelliJ IDEA, Eclipse vagy NetBeans.

## Csomagok importálása
Először is importálja a szükséges csomagokat a Java osztályba:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## 1. lépés: A projekt beállítása és az összefoglaló információk meghatározása
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
//Inicializáljon egy új projektobjektumot a projektfájl elérési útjával
Project project = new Project(dataDir + "project.mpp");
// Állítson be összefoglaló információkat a projektről
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Állítsa be a projekt létrehozásának dátumát
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Állítson be kulcsszavakat a projekthez
project.set(Prj.KEYWORDS, "MPP Aspose");
// Állítsa be a projekt utolsó nyomtatási dátumát
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## 2. lépés: Mentse el a projekt összefoglaló információit
```java
// Mentse vissza a projektet MPP formátumban
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Sikerüzenet megjelenítése
System.out.println("Process completed Successfully");
```
## 3. lépés: Olvassa el a projekt összefoglaló információit
```java
// A projekt összefoglaló információinak olvasása
project = new Project(dataDir + "MppAspose.xml");
// A projekt nyomtatott szerzője
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Nyomtassa ki a projekt utolsó szerzőjét
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// A projekt verziószámának kinyomtatása
System.out.println("Revision: " + project.get(Prj.REVISION));
// Nyomtassa ki a projekt kulcsszavait
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Nyomtassa ki a projekt megjegyzéseit
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// A projekt létrehozási dátumának nyomtatása
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// A projekt kulcsszavainak nyomtatása (ismét)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Nyomtassa ki a projekt utolsó nyomtatási dátumát
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan írhat MPP-projekt összefoglalókat az Aspose.Tasks for Java használatával. Ezen lépések követésével hatékonyan állíthat be és kérhet le különféle összefoglaló információkat a projektfájlokról. Az Aspose.Tasks leegyszerűsíti a Microsoft Project fájlokkal végzett munkát a Java alkalmazásokban, robusztus funkcionalitást és egyszerű használatot kínálva.
## GYIK
### K: Használhatom az Aspose.Tasks for Java-t más Java könyvtárakkal?
V: Igen, az Aspose.Tasks for Java zökkenőmentesen integrálható más Java-könyvtárakba a projektkezelési képességek javítása érdekében.
### K: Elérhető az Aspose.Tasks for Java próbaverziója?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Milyen gyakran frissül az Aspose.Tasks for Java?
V: Az Aspose.Tasks for Java programot rendszeresen frissítik, hogy biztosítsák a kompatibilitást a Java és a Microsoft Project fájlok legújabb verzióival.
### K: Testreszabhatom a projekt összefoglaló adatait?
V: Természetesen az Aspose.Tasks for Java kiterjedt lehetőségeket kínál a projekt összefoglaló információinak testreszabására az Ön egyedi igényei szerint.
### K: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?
V: Támogatást kaphat az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).