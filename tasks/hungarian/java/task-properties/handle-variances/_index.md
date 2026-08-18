---
date: 2026-02-20
description: Ismerje meg, hogyan állíthatja be a projekt kezdő dátumát, és kezelheti
  a projekt eltéréseit az Aspose.Tasks for Java használatával. Ez az útmutató azt
  is bemutatja, hogyan állítható be hatékonyan a feladat időtartama.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt kezdő dátum beállítása és feladateltérések kezelése – Aspose.Tasks
url: /hu/java/task-properties/handle-variances/
weight: 19
---

 we didn't miss any markdown formatting.

Check code block placeholders: they are not fenced code blocks, but placeholders. The instruction says preserve code blocks. There are none actual code fences, only placeholders. So fine.

Now produce final content with all translations.

Let's assemble.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt kezdési dátum beállítása és feladateltérések kezelése Aspose.Tasks

## Bevezetés
A projektmenedzsment világában a **set project start date** az egyik első lépés, amellyel szilárd alapot ad a menetrendnek. Az Aspose.Tasks for Java egyszerűvé és megbízhatóvá teszi ezt a lépést – valamint a feladateltérések későbbi kezelését. Ebben az útmutatóban megtanulja, hogyan állítsa be a projekt kezdési dátumát, a feladat időtartamát, és hogyan kezelje hatékonyan a projekt eltéréseit.

## Gyors válaszok
- **Mi a fő módszer a projekt kezdési dátum beállításához?** Használja a `project.set(Prj.START_DATE, …)`-t egy `java.util.Calendar` példányával.  
- **Melyik osztály képviseli az alapvonalat az eltéréskövetéshez?** `BaselineType.Baseline`.  
- **Módosíthatom a feladat kezdő- és befejezési dátumát az alapvonal beállítása után?** Igen, egyszerűen frissítse a `Tsk.START` és `Tsk.STOP` értékeket.  
- **Szükségem van licencre fejlesztési használathoz?** Ideiglenes licenc elérhető értékeléshez.  
- **Melyik Aspose.Tasks verzió működik ezzel a kóddal?** A legújabb Aspose.Tasks for Java kiadás.

## Mi a **set project start date**?
A projekt kezdési dátum beállítása meghatározza azt a naptári napot, amelytől minden feladat dátuma számítódik. Befolyásolja a menetrend számításait, a kritikus út elemzését és az alapvonal létrehozását, így elengedhetetlen a pontos eltéréskezeléshez.

## Miért kell beállítani a projekt kezdési dátumát és kezelni az eltéréseket?
- **Előrejelezhetőség:** Egy ismert alapvonalat hoz létre a tényleges előrehaladás összehasonlításához.  
- **Rugalmasság:** Lehetővé teszi az egyes feladatok dátumának módosítását az eredeti terv elvesztése nélkül.  
- **Jelentéskészítés:** Lehetővé teszi a világos eltérésjelentéseket, amelyek kiemelik a menetrend csúszását vagy a korai befejezéseket.  

## Előfeltételek
Mielőtt belemerülnénk, győződjön meg róla, hogy a következőkkel rendelkezik:

- Java fejlesztői környezet – telepített JDK és egy IDE vagy build eszköz készen áll.  
- Aspose.Tasks könyvtár – töltse le a könyvtárat **[itt](https://releases.aspose.com/tasks/java/)**.  

## Csomagok importálása
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 1. lépés: A projekt beállítása
Hozzon létre egy új `Project` példányt, amely tartalmazni fogja az összes feladatot és a menetrendi információkat.

```java
Project project = new Project();
```

## 2. lépés: Feladat hozzáadása
Adjon hozzá egy feladatot a gyökérfeladat alá. Ez lesz a munkatétel, amelyet később módosítunk.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 3. lépés: Kezdő dátum és időtartam beállítása
Határozza meg a projekt kezdő dátumát, és adjon a feladatnak egy időtartamot. Ez a gyakorlatban bemutatja a **set task duration**-t.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## 4. lépés: Alapvonal beállítása
Hozzon létre egy alapvonalat, hogy később össze tudja hasonlítani a tervezett és a tényleges dátumokat – ez elengedhetetlen a **manage project variances**-hez.

```java
project.setBaseline(BaselineType.Baseline);
```

## 5. lépés: Feladat kezdő- és befejezési dátumainak módosítása
Módosítsa a feladat kezdő- és befejezési dátumait egy eltéréses forgatókönyv szimulálásához.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Nyugodtan módosítsa a dátumokat és időtartamokat, hogy megfeleljenek projektje konkrét igényeinek.*

## Gyakori problémák és tippek
- **Az alapvonalat a dátumok módosítása előtt kell beállítani.** Ha előbb módosítja a dátumokat, az alapvonal a módosított menetrendet rögzíti az eredeti terv helyett.  
- **A naptári hónapok nullával kezdődnek.** Ne feledje, hogy a `Calendar.FEBRUARY` a 1‑es hónapnak felel meg, nem a 2‑esnek.  
- **Időtartam egységek:** A `project.getDuration(2)` alapértelmezés szerint két napos időtartamot hoz létre; állítsa be az egységet, ha órákat vagy heteket szeretne.  

## Következtetés
A **set project start date**, **set task duration**, és **manage project variances** elsajátításával teljes irányítást nyerhet projektmenetrendje felett az Aspose.Tasks for Java használatával. A fenti lépések szilárd alapot biztosítanak, amelyet bővíthet összetettebb forgatókönyvekre, például többfázisú projektekre, erőforrás-elosztásra és automatizált jelentéskészítésre.

## Gyakran Ismételt Kérdések
### Az Aspose.Tasks alkalmas minden projektmenedzsment igényre?
Az Aspose.Tasks egy sokoldalú eszköz, amely számos projektmenedzsment igényre alkalmas, rugalmasságot és robusztus funkciókat biztosít.

### Integrálhatom az Aspose.Tasks-et a meglévő Java projektembe?
Igen, könnyedén integrálhatja az Aspose.Tasks-et a Java projektjébe a megadott dokumentáció **[itt](https://reference.aspose.com/tasks/java/)** követésével.

### Elérhető ideiglenes licenc az Aspose.Tasks-hez?
Igen, ideiglenes licencet szerezhet az Aspose.Tasks-hez **[itt](https://purchase.aspose.com/temporary-license/)**.

### Hol kaphatok támogatást az Aspose.Tasks-hez?
Támogatásért és megbeszélésekért látogassa meg az Aspose.Tasks fórumot **[itt](https://forum.aspose.com/c/tasks/15)**.

### Letölthetem az Aspose.Tasks-et Java-hoz?
Igen, töltse le az Aspose.Tasks for Java legújabb verzióját **[itt](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2026-02-20  
**Tesztelve:** Aspose.Tasks legújabb Java kiadás  
**Szerző:** Aspose