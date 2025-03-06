---
title: Hétköznapi tulajdonságok az Aspose.Tasks-ban
linktitle: Hétköznapi tulajdonságok az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg a hétköznapi tulajdonságok hatékony kezelését az Aspose.Tasks for Java programban. Könnyedén testreszabhatja a hét kezdési dátumait, a hónap napjait és még sok mást.
weight: 25
url: /hu/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hétköznapi tulajdonságok az Aspose.Tasks-ban

## Bevezetés
Az Aspose.Tasks for Java egy hatékony API, amely lehetővé teszi a Java fejlesztők számára, hogy Microsoft Project fájlokkal dolgozzanak anélkül, hogy Microsoft Project lenne telepítve a gépre. Egyik legfontosabb funkciója a hétköznapok tulajdonságainak kezelése, amely lehetővé teszi a felhasználók számára a hét kezdési dátumának, a hónap napjainak, a napi perceknek és a heti perceknek a testreszabását. Ez az oktatóanyag részletes útmutatót ad ezeknek a funkcióknak a hatékony használatához.
## Előfeltételek
Mielőtt belevágna az Aspose.Tasks for Java programba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### Java fejlesztőkészlet (JDK)
Győződjön meg arról, hogy a JDK telepítve van a rendszeren. A legújabb JDK letölthető és telepíthető az Oracle webhelyéről.
### Aspose.Tasks for Java Library
 Töltse le és telepítse az Aspose.Tasks for Java könyvtárat a webhelyről. A letöltési linket elérheti[itt](https://releases.aspose.com/tasks/java/).
### Integrált fejlesztési környezet (IDE)
Válasszon egy IDE-t a Java fejlesztéshez. A népszerű választások közé tartozik az IntelliJ IDEA, az Eclipse vagy a NetBeans.
## Csomagok importálása
kezdéshez importálja a szükséges Aspose.Tasks csomagokat a Java projektbe. Itt van, hogyan:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Most bontsuk le a megadott példát több lépésre a jobb megértés érdekében.
## 1. lépés: Töltse be a projektfájlt
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Ez a lépés egy "project.mpp" nevű projektfájl betöltését jelenti a megadott adatkönyvtárból.
## 2. lépés: Jelenítse meg a hétköznapok tulajdonságait
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Itt lekérjük és kinyomtatjuk a betöltött projekt heti kezdési dátumát, havi napjait, napi perceit és heti perceit.
## 3. lépés: Hétköznapi tulajdonságok beállítása
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Ebben a lépésben létre kell hozni egy új projektpéldányt, és be kell állítani az egyéni hétköznapi tulajdonságokat, például a hét kezdőnapját, a hónap napjait, a napi perceket és a heti perceket.
## 4. lépés: Projekt mentése
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Végül XML-fájlként mentjük a módosított projektet a frissített hétköznap tulajdonságokkal.
## 5. lépés: Eredmény megjelenítése
```java
System.out.println("Process completed Successfully");
```
Ez a lépés megerősíti a folyamat sikeres befejezését.
## Következtetés
Az Aspose.Tasks for Java hétköznapi tulajdonságainak elsajátítása elengedhetetlen a hatékony projektmenedzsmenthez. Az oktatóanyag követésével megtanulta, hogyan lehet könnyedén kezelni és testreszabni a hétköznapi tulajdonságokat. Fedezze fel a további dokumentációkat és példákat projektmenedzsment képességeinek fejlesztéséhez.
## GYIK
### K: Az Aspose.Tasks for Java kezelheti az összetett projektstruktúrákat?
V: Igen, az Aspose.Tasks for Java átfogó támogatást nyújt az összetett projektstruktúrák egyszerű kezeléséhez.
### K: Az Aspose.Tasks for Java kompatibilis a Microsoft Project fájlok különböző verzióival?
V: Az Aspose.Tasks for Java természetesen támogatja a Microsoft Project fájlok különféle verzióit, biztosítva a platformok közötti kompatibilitást.
### K: Integrálhatom az Aspose.Tasks for Java-t a meglévő Java alkalmazásaimba?
V: Igen, az Aspose.Tasks for Java zökkenőmentes integrációs lehetőségeket kínál, lehetővé téve, hogy Java-alkalmazásait hatékony projektmenedzsment funkciókkal bővítse.
### K: Az Aspose.Tasks for Java dokumentációt és támogatást nyújt?
 V: Igen, hozzáférhet az Aspose.Tasks for Java kiterjedt dokumentációjához és közösségi támogatásához[weboldal](https://releases.aspose.com/).
### K: Elérhető az Aspose.Tasks for Java ingyenes próbaverziója?
V: Igen, letöltheti az Aspose.Tasks Java ingyenes próbaverzióját az ő oldalukról[weboldal](https://reference.aspose.com/tasks/java/) hogy vásárlás előtt ismerkedjen meg funkcióival.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
