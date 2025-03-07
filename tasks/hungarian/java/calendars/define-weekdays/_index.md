---
title: Határozza meg a hétköznapokat a naptárban az Aspose.Tasks segítségével
linktitle: Határozza meg a hétköznapokat a naptárban az Aspose.Tasks segítségével
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan határozhatja meg a hétköznapokat az MS Project Calendar programban az Aspose.Tasks for Java segítségével. Könnyedén testreszabhatja a munkanapokat és az időpontokat.
weight: 12
url: /hu/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Határozza meg a hétköznapokat a naptárban az Aspose.Tasks segítségével

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a hétköznapok meghatározásának folyamatát egy MS Project Calendarban az Aspose.Tasks for Java segítségével. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. Letöltheti a[Oracle webhely](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ha még nem tetted meg.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat a[letöltési oldal](https://releases.aspose.com/tasks/java/). Kövesse a dokumentációban található telepítési utasításokat.

## Csomagok importálása
Kezdésként importálja az Aspose.Tasks programhoz szükséges csomagokat a Java projektben:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## 1. lépés: Hozzon létre egy projektpéldányt
Példányosítson egy Project objektumot, amely az MS Project fájlt képviseli, amellyel dolgozni fog:
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## 2. lépés: A naptár meghatározása
Hozzon létre egy új naptárpéldányt, és adja hozzá a projekthez:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## 3. lépés: Munkanapok hozzáadása
Határozza meg a munkanapokat hétfőtől csütörtökig az alapértelmezett időzítésekkel:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## 4. lépés: Állítsa be az egyéni munkanapot
Határozza meg a szombatot és a vasárnapot munkanapként:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## 5. lépés: Állítsa be a rövid munkanapot
Állítsa be a pénteket rövid munkanapnak egyéni munkaidővel:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## 6. lépés: Mentse el a projektet
Mentse el a módosított projektet XML fájlba:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Következtetés
Gratulálunk! Sikeresen meghatározta a hétköznapokat egy MS Project Calendarban az Aspose.Tasks for Java segítségével. Most már integrálhatja ezt a funkciót Java-alkalmazásaiba, hogy programozottan kezelje az MS Project fájlokat.
## GYIK
### 1. kérdés: Meghatározhatok egyéni munkaszüneti napokat az Aspose.Tasks for Java használatával?
 V: Igen, egyéni munkaszüneti napokat is megadhat a`DayWorking` tulajdonát`false` az adott hétköznapra.
### 2. kérdés: Hogyan adhatok ünnepnapokat a naptárhoz?
 V: Ünnepnapokat a példányok létrehozásával adhat hozzá`CalendarExceptions`és a munkaszüneti időpontok megadásával.
### 3. kérdés: Az Aspose.Tasks kompatibilis az MS Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks támogatja az MS Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### 4. kérdés: Módosíthatom a meglévő naptárakat egy MS Project fájlban?
V: Igen, betölthet egy meglévő projektet naptárral, módosításokat hajthat végre, majd a módosításokat visszamentheti az eredeti fájlba.
### 5. kérdés: Az Aspose.Tasks támogatást nyújt az ismétlődő feladatokhoz?
V: Igen, az Aspose.Tasks lehetővé teszi az ismétlődő feladatokkal való munkát, beleértve azok ismétlődési mintáinak és időtartamának meghatározását.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
