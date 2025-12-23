---
date: 2025-12-23
description: Ismerje meg, hogyan hozhat létre feladatfüggőségeket és számíthatja ki
  a kritikus útvonalat az MS Projectben az Aspose.Tasks for Java használatával. Lépésről
  lépésre útmutató a projektmenedzsmenthez.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Feladatfüggőségek létrehozása és a kritikus út számítása az Aspose.Tasks-ben
url: /hu/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladatfüggőségek létrehozása és a kritikus út számítása az Aspose.Tasks-ben

## Bevezetés
Ebben az oktatóanyagban **meg fogod tanulni, hogyan hozz létre feladatfüggőségeket** és hogyan számítsd ki a kritikus utat egy MS Project fájlban az Aspose.Tasks for Java segítségével. A kritikus út megértése és vizualizálása segít a projekt időben tartásában, míg a feladatok helyes összekapcsolása biztosítja, hogy minden késés azonnal látható legyen. Végigvezetünk a teljes folyamaton, a környezet beállításától a végső kritikus út megjelenítéséig.

## Gyors válaszok
- **Mi az első lépés?** Állítsd be a Java projektedet és add hozzá az Aspose.Tasks könyvtárat.  
- **Melyik módot kell engedélyezni?** `CalculationMode.Automatic` (állítsd be az automatikus számítást).  
- **Hogyan kapcsoljam össze a feladatokat?** Használd a `project.getTaskLinks().add(...)`-t a feladatfüggőségek létrehozásához.  
- **Hogyan tekinthetem meg a kritikus utat?** Iterálj a `project.getCriticalPath()`-en és írd ki minden feladat nevét.  
- **Szükségem van licencre?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz.

## Mi az a „feladatfüggőségek létrehozása”?
A feladatfüggőségek létrehozása azt jelenti, hogy kapcsolatokat (pl. Befejezés‑kezdés) definiálsz a feladatok között, hogy az ütemterv a valós világ korlátozásait tükrözze. Az Aspose.Tasks-ben ezt `TaskLink` objektumokkal valósítjuk meg.

## Miért számítsuk ki a kritikus utat az MS Projectben?
A **MS Project kritikus út** a leghosszabb függő feladatok sorozatát mutatja, amely meghatározza a projekt minimális időtartamát. Ennek kiszámításával gyorsan azonosíthatod azokat a feladatokat, amelyek nem csúszhatnak anélkül, hogy befolyásolnák az összidővonalat – elengedhetetlen a hatékony **project management Java** alkalmazásokhoz.

## Előkövetelmények
1. Java Development Kit (JDK) telepítve van a rendszereden.  
2. Aspose.Tasks for Java könyvtár letöltve és hozzáadva a projektedhez. Letöltheted [itt](https://releases.aspose.com/tasks/java/).  

## Csomagok importálása
To start, import the necessary packages in your Java class:
```java
import com.aspose.tasks.*;
```

## Hogyan állítsuk be az automatikus számítást?
Setting the calculation mode to automatic ensures that any change to tasks or links instantly updates the schedule, including the critical path.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Lépésről‑lépésre útmutató

### 1. lépés: Adatkönyvtár beállítása
Define the path to the folder that contains your MS Project file.
```java
String dataDir = "Your Data Directory";
```

### 2. lépés: MS Project fájl betöltése
Load the existing project file (e.g., *New project 2013.mpp*) using Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### 3. lépés: Feladatok hozzáadása
Create three simple subtasks that we will later link together.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### 4. lépés: Feladatkapcsolatok létrehozása (feladatfüggőségek létrehozása)
Define the dependencies between the tasks. Here we use a Finish‑to‑Start link, which is the most common type.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### 5. lépés: Kritikus út megjelenítése (kritikus út megjelenítése)
Retrieve and print the critical path. The `getCriticalPath()` method returns the list of tasks that form the critical chain.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### 6. lépés: Befejezés megerősítése
Show a friendly message once the process finishes.
```java
System.out.println("Process completed Successfully");
```

## Gyakori problémák és megoldások
| Issue | Solution |
|-------|----------|
| **A kritikus út üres** | Győződj meg róla, hogy a `CalculationMode.Automatic` be van állítva a kapcsolatok hozzáadása előtt. |
| **A feladatok nincsenek összekapcsolva** | Ellenőrizd, hogy minden függőséghez hozzáadtad a `TaskLink` objektumokat. |
| **Licenc kivétel** | Tölts be egy érvényes Aspose.Tasks licencet a `Project` példány létrehozása előtt. |

## GYIK

### Q: Használhatom az Aspose.Tasks for Java-t bármely MS Project fájl verzióval?
A: Igen, az Aspose.Tasks for Java támogatja a különböző MS Project fájl verziókat, beleértve a .mpp fájlokat a MS Project 2003-tól a MS Project 2019-ig.

### Q: Elérhető ingyenes próba az Aspose.Tasks for Java-hoz?
A: Igen, letölthetsz egy ingyenes próbát [itt](https://releases.aspose.com/).

### Q: Hol találok támogatást az Aspose.Tasks for Java-hoz?
A: Támogatást találsz a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15).

### Q: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java-hoz?
A: Igen, ideiglenes licencet vásárolhatsz [itt](https://purchase.aspose.com/temporary-license/).

### Q: Hogyan vásárolhatom meg az Aspose.Tasks for Java-t?
A: Az Aspose.Tasks for Java-t megvásárolhatod a weboldalon [itt](https://purchase.aspose.com/buy).

## Összegzés
A lépések követésével **létrehoztad a feladatfüggőségeket**, beállítottad az **automatikus számítást**, és sikeresen **megjelenítetted a kritikus utat** a MS Project fájlodhoz. Ez a munkafolyamat teljes ellenőrzést biztosít az ütemezési logika felett, és segít a projektek nyomon követésében Java‑alapú **project management** kód használatával.

**Utoljára frissítve:** 2025-12-23  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}