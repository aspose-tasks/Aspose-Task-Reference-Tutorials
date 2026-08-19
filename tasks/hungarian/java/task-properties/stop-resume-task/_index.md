---
date: 2026-02-26
description: Tanulja meg, hogyan lehet folytatni és leállítani a feladatot az Aspose.Tasks
  for Java-ban, beleértve a feladatok dátum szerinti szűrését a pontos projektvezérlés
  érdekében.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan folytassuk a feladatot és állítsuk le a feladatot az Aspose.Tasks-ben
url: /hu/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan folytassuk a feladatot és állítsuk le a feladatot az Aspose.Tasks-ben

## Bevezetés
Ha Java‑alapú projektmenedzsment megoldást építesz, gyakran szükség lesz egy feladat **ideiglenes szüneteltetésére**, majd később **folytatására**. Az Aspose.Tasks for Java ezt egyszerűvé teszi beépített tulajdonságokkal a feladatok leállításához és folytatásához. Ebben az útmutatóban megtudod, **hogyan folytassuk a feladatot** és **hogyan állítsuk le a feladatot** programozottan, valamint láthatod, hogyan **szűrhetünk feladatokat dátum szerint**, hogy csak a menetrended releváns elemeivel dolgozz.

## Gyors válaszok
- **Mit jelent a „stop” egy feladatnál?** Egy stop dátumot állít be, amely után a munka szünetel.  
- **Hogyan folytathatom a leállított feladatot?** Egy resume dátumot adva meg, amely későbbi a stop dátumnál.  
- **Korlátozhatom a műveletet egy dátumtartományra?** Igen – használj minimum dátumot a feladatok szűréséhez.  
- **Melyik könyvtárverzió szükséges?** Bármely friss Aspose.Tasks for Java kiadás (az API stabil marad).  
- **Szükség van licencre fejlesztéshez?** Egy ingyenes próba verzió tesztelésre elegendő; licenc a termeléshez kötelező.

## Mi az a „hogyan folytassuk a feladatot” az Aspose.Tasks-ben?
Egy feladat folytatása egyszerűen azt jelenti, hogy **RESUME** dátumot adunk meg egy `Task` objektumon. Amikor a projektmotor feldolgozza a menetrendet, a munka ettől a dátumtól folytatódik. Ez különösen hasznos megszakítások, például erőforrás hiány vagy külső függőségek kezelésekor.

## Miért használjuk a stop/continue (resume) funkciót?
- **Idővonalak irányítása:** A munka szüneteltethető a feladat törlése nélkül.  
- **Pontos jelentés:** Reális kezdő/lezáró dátumok megjelenítése Gantt-diagramokban.  
- **Könnyű automatizálás:** Dátumszűrőkkel kombinálva egyszerre több feladatot is frissíthetünk.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy:

- Jól ismered a Java alapjait.  
- A JDK telepítve van a gépeden.  
- Az Aspose.Tasks for Java könyvtár hozzá van adva a projekthez (letölthető [innen](https://releases.aspose.com/tasks/java/)).  

## Importálás
Először hozd be a szükséges osztályokat, hogy a projektek és feladatok kezelése elérhető legyen.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## 1. lépés: Projekt és Gyűjtő inicializálása
Hozz létre egy `Project` példányt, amely a MPP fájlodra mutat, és állíts be egy `ChildTasksCollector`‑t, hogy összegyűjtse a hierarchia minden feladatát.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## 2. lépés: Minimum dátum definiálása a szűréshez
Ha csak olyan feladatokkal szeretnél dolgozni, amelyeknek van értelmes stop vagy resume dátuma, definiálj egy **minimum dátumot**. Ez a *feladatok dátum szerinti szűrése* technika központja.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## 3. lépés: Iterálás, ellenőrzés és a Stop/Resume értékek kiírása
Most járd be a gyűjtött feladatokat, alkalmazd a **hogyan állítsuk le a feladatot** logikát, és írd ki a dátumokat. A kód emellett bemutatja, hogyan **folytassuk a feladatot** a `RESUME` tulajdonság olvasásával.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Pro tipp:** Cseréld le a `System.out.println` hívásokat a saját logikádra (pl. dátumok frissítése, fájlba naplózás vagy a feladatobjektumok módosítása), hogy ténylegesen *leállítsd* vagy *folytasd* a feladatokat a szükséges módon.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| `NullPointerException` a `tsk.get(Tsk.STOP)`‑nál | A feladatnak nincs beállítva stop dátum. | Ellenőrizd a `null` értéket, mielőtt a `.before(minDate)`‑t hívod. |
| A dátumok `NA`‑ként jelennek meg a beállítás után is | A minimum dátum túl friss. | Használj korábbi `minDate`‑t vagy vedd le a szűrőt. |
| A módosítások nem jelennek meg a mentett MPP‑ben | A projekt nincs mentve a változtatások után. | Hívd meg a `project.save("output.mpp");`‑t a feladatok frissítése után. |

## Gyakran feltett kérdések

### Alkalmas-e az Aspose.Tasks for Java nagy‑léptékű projektekhez?
Teljes mértékben! Az Aspose.Tasks for Java úgy van tervezve, hogy különböző méretű projekteket kezeljen, biztosítva a hatékonyságot és a megbízhatóságot.

### Testreszabhatom a stop és resume dátumokat?
Igen, a bemutatott példa lehetővé teszi a minimum dátum rugalmas beállítását a projekt igényei szerint.

### Hol találok további támogatást az Aspose.Tasks for Java‑hoz?
Látogasd meg az [Aspose.Tasks Fórumot](https://forum.aspose.com/c/tasks/15) a közösségi támogatás és a megbeszélések érdekében.

### Van ingyenes próba verzió az Aspose.Tasks for Java‑hoz?
Igen, elérhető a [free trial](https://releases.aspose.com/) a funkciók kipróbálásához vásárlás előtt.

### Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java‑hoz?
Ideiglenes licencet vásárolhatsz [itt](https://purchase.aspose.com/temporary-license/) tesztelési célokra.

**További Q&A**

**K: Hogyan állíthatok be új stop dátumot egy feladatra?**  
V: Használd a `tsk.set(Tsk.STOP, new Date(...));`‑t, majd mentsd a projektet.

**K: Szűrhetem a feladatokat egy konkrét tartományra a csak minimum dátum helyett?**  
V: Igen – hasonlítsd össze a `before` és `after` feltételeket a kezdő és befejező dátumaiddal.

**K: Az API automatikusan újraszámolja a menetrendet a stop/resume dátumok módosítása után?**  
V: A dátumok módosítása után hívd meg a `project.calculateCriticalPath();`‑t a menetrend frissítéséhez.

## Összegzés
Ebben az útmutatóban bemutattuk, **hogyan folytassuk a feladatot** és **hogyan állítsuk le a feladatot** az Aspose.Tasks for Java segítségével, valamint egy gyakorlati módszert a **feladatok dátum szerinti szűrésére**. Ezeket a kódrészleteket beépítve alkalmazásodba finomhangolt vezérlést kapsz a projekt idővonalak felett, és magabiztosan automatizálhatod a menetrend módosításait.

---

**Utolsó frissítés:** 2026-02-26  
**Tesztelt verzió:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}