---
title: Az MS Project naptárinformációinak lekérése az Aspose.Tasks-ban
linktitle: A naptáradatok lekérése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kérheti le az MS Project naptáradatait az Aspose.Tasks for Java segítségével. Útmutató lépésről lépésre a naptár részleteinek programozott eléréséhez.
weight: 14
url: /hu/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az MS Project naptárinformációinak lekérése az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet naptáradatokat lekérni a Microsoft Project fájlokból az Aspose.Tasks for Java könyvtár használatával. Az Aspose.Tasks hatékony funkciókat kínál a projektadatok kezeléséhez, beleértve a naptáradatok, például a munkanapok és órák elérését.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- Java programozási alapismeretek.
- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Tasks a Java könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Először is importálnia kell a szükséges csomagokat a Java kódba az Aspose.Tasks funkciók használatához.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Most bontsuk fel a megadott példát több lépésre a jobb megértés érdekében.
## 1. lépés: Állítsa be az adatkönyvtárat
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` a projektfájlok könyvtárának elérési útjával.
## 2. lépés: Adja meg az időegységeket
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Ezek az állandók az időegységeket mikroszekundumban jelentik.
## 3. lépés: Hozzon létre projektpéldányt
```java
Project project = new Project(dataDir + "project.mpp");
```
 Ez a sor létrehozza a`Project` osztályt, inicializálva a projektfájl elérési útjával (`project.mpp`).
## 4. lépés: A naptárak információinak lekérése
```java
CalendarCollection alCals = project.getCalendars();
```
Itt lekérjük a projektfájlban található naptárak gyűjteményét.
## 5. lépés: Ismétlés a naptárak segítségével
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Naptár információk
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Ismétlés a hét napjain keresztül
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Idő ezredmásodpercben
            double time = ts / (OneHour); // Átalakítás órákra
            if (wd.getDayWorking()) {
                // Munkanapok és órák megjelenítése
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Ez a ciklus minden naptáron áthalad, és kinyomtatja az UID-t, a nevét és a munkanapokat a megfelelő munkaidővel együtt.
## 6. lépés: Befejezési üzenet megjelenítése
```java
System.out.println("Process completed Successfully");
```
Végül egy üzenet jelenik meg, amely jelzi a folyamat befejezését.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet naptáradatokat lekérni MS Project fájlokból az Aspose.Tasks for Java segítségével. Ha követi ezeket a lépéseket, hatékonyan érheti el és kezelheti a projektadatokat Java-alkalmazásaiban.

## GYIK
### K: Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
V: Igen, az Aspose.Tasks több platformot és programozási nyelvet támogat, beleértve a .NET-et és a C-t++, Python és Java.
### K: Elérhető az Aspose.Tasks ingyenes próbaverziója?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást az Aspose.Tasks-hoz?
V: Támogatást kaphat az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks számára?
 V: Igen, ideiglenes licencek megvásárolhatók[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol találom az Aspose.Tasks részletes dokumentációját?
 V: Tekintse meg a dokumentációt[itt](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
