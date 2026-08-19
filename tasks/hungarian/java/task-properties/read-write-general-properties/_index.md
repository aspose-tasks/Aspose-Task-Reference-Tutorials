---
date: 2026-02-26
description: Tanulja meg, hogyan hozhat létre feladat‑Aspose Java projekteket, és
  hogyan szerezheti meg a feladat kezdő dátumát az Aspose.Tasks for Java használatával.
  Lépésről‑lépésre útmutató az általános feladattulajdonságok olvasásához és írásához.
linktitle: Read and Write General Properties of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Feladat létrehozása Aspose Java – A feladat tulajdonságok elsajátítása
url: /hu/java/task-properties/read-write-general-properties/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladat létrehozása Aspose Java – A feladat tulajdonságok elsajátítása

## Bevezetés
Fedezze fel a feladatkezelés teljes potenciálját Java-ban az Aspose.Tasks segítségével. Ebben az átfogó útmutatóban **meg fogja tanulni, hogyan hozhat létre task Aspose Java** projekteket, hogyan olvashat és írhat általános tulajdonságokat, és akár **lekérheti a feladat kezdő dátumát** bármely feladatnál az ütemtervében. Akár tapasztalt fejlesztő, akár most kezd, ez a tutorial gyakorlati kódot biztosít, amelyet egyszerűen beilleszthet saját alkalmazásaiba.

## Gyors válaszok
- **Mit tehetek az Aspose.Tasks for Java-val?** Feladat tulajdonságok olvasása és írása, beleértve a kezdő dátumokat, időtartamokat és egyéni mezőket.  
- **Hogyan hozhatok létre új feladatot?** Használja a `project.getRootTask().getChildren().add("TaskName")` metódust, és állítsa be a tulajdonságokat a `Tsk` enumon keresztül.  
- **Hogyan kérhetem le egy feladat kezdő dátumát?** Hívja a `task.get(Tsk.START)` metódust a projekt betöltése vagy a feladat létrehozása után.  
- **Szükségem van licencre a fejlesztéshez?** Ideiglenes licenc teszteléshez elegendő; a teljes licenc a termeléshez kötelező.  
- **Melyik Java verzió támogatott?** Az Aspose.Tasks működik a Java 8 és újabb verziókkal, beleértve a Java 11-et és a Java 17-et.

## Mi az a “create task Aspose Java”?
Feladat létrehozása az Aspose.Tasks segítségével azt jelenti, hogy programozottan adunk hozzá egy új bejegyzést a projekt ütemtervéhez, meghatározva annak nevét, kezdési időpontját, befejezési időpontját és egyéb attribútumait anélkül, hogy manuálisan szerkesztenénk egy XML vagy MPP fájlt.

## Miért használjuk az Aspose.Tasks for Java-t?
- **Teljes irányítás** minden feladat attribútum felett (ID, UID, név, dátumok, stb.).  
- **Cross‑platform** – működik Windows, Linux és macOS rendszereken.  
- **Nincs COM vagy Office függőség** – tiszta Java könyvtár.  
- **Gazdag API** a projektadatok olvasásához, írásához és validálásához.

## Előfeltételek
Mielőtt belemerülnénk a tutorialba, győződjön meg róla, hogy az alábbi előfeltételek rendelkezésre állnak:
- Java Development Kit (JDK) telepítve van a rendszerén.  
- Aspose.Tasks for Java könyvtár letöltve és beállítva. A letöltési linket megtalálja [itt](https://releases.aspose.com/tasks/java/).  
- Kódszerkesztő, például IntelliJ IDEA vagy Eclipse.

## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java projektjébe. Ez a lépés biztosítja, hogy hozzáférjen az Aspose.Tasks funkciókhoz. Íme egy kódrészlet, amely útmutatást ad:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Hogyan hozhatunk létre task Aspose Java-t
### 1. lépés: Feladat létrehozása
Kezdje a feladat létrehozásával a projektben. Ez magában foglalja a feladat nevének, kezdő dátumának és egyéb releváns részletek beállítását. Az alábbi kód bemutatja a folyamatot:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```

### 2. lépés: Feladat tulajdonságok olvasása
Miután létrehozta a feladatot, most lekérjük és megjelenítjük általános tulajdonságait, beleértve a most beállított kezdő dátumot:

```java
// Reading General Properties of Tasks
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```

## Hogyan kérjük le a feladat kezdő dátumát
Ha **a feladat kezdő dátumát** kell lekérnie további számításokhoz (például ütemezés vagy jelentés), egyszerűen hívja meg a `Tsk.START` tulajdonságot bármely `Task` objektumon, ahogyan a fenti ciklusban látható. A visszaadott érték egy `java.util.Date`, amelyet igény szerint formázhat vagy összehasonlíthat.

## Feladatok általános tulajdonságainak írása
### 3. lépés: Projekt betöltése és gyűjtő létrehozása
Az általános tulajdonságok írásához vagy frissítéséhez töltse be egy meglévő projektet, és állítson be egy `ChildTasksCollector`-t:

```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```

### 4. lépés: Tulajdonságok feldolgozása és megjelenítése
Végül iteráljon a gyűjtött feladatokon, és jelenítse meg (vagy módosítsa) azok tulajdonságait:

```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```

> **Pro tipp:** Bármely tulajdonság frissítése után hívja meg a `prj.save("output.xml")` parancsot a változások új projektfájlba mentéséhez.

Gratulálunk! Sikeresen olvasott, írt és lekérdezett általános feladattulajdonságokat az Aspose.Tasks for Java segítségével.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| `NullPointerException` a `task.get(Tsk.START)` elérésekor | A feladat nem lett hozzáadva a projekt hierarchiájához. | Győződjön meg róla, hogy a feladatot a `project.getRootTask().getChildren()`-hez adja hozzá a tulajdonságok beállítása előtt. |
| `A dátumok egy nappal eltolódnak` | Az időzóna különbségek a Java `Date` és a projektfájl között. | Használjon `java.util.Calendar`-t explicit időzónával, vagy tárolja a dátumokat UTC-ben. |
| `A változások nem kerülnek mentésre` | Elfelejtett meghívni a `project.save(...)` metódust. | Mindig mentse a projektet a módosítások után. |

## Gyakran ismételt kérdések

**K: Az Aspose.Tasks kompatibilis a Java 11-vel?**  
V: Igen, az Aspose.Tasks kompatibilis a Java 11 és újabb verziókkal.

**K: Használhatom az Aspose.Tasks-et kereskedelmi projektekhez?**  
V: Természetesen! Az Aspose.Tasks egy erőteljes eszköz mind személyes, mind kereskedelmi projektekhez. Látogasson el [ide](https://purchase.aspose.com/buy) a licencelési lehetőségek megtekintéséhez.

**K: Hogyan szerezhetek ideiglenes licencet tesztelési célokra?**  
V: Szerezzen ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) teszteléshez és értékeléshez.

**K: Hol találok közösségi támogatást az Aspose.Tasks-hez?**  
V: Csatlakozzon a közösségi megbeszéléshez a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) segítség és együttműködés céljából.

**K: Van elérhető mintaprojekt referenciaként?**  
V: Tekintse meg a dokumentáció példák szekcióját [itt](https://reference.aspose.com/tasks/java/) mintaprojektek és kódrészletek számára.

## Következtetés
Ebben a tutorialban áttekintettük az alapvető lépéseket a **task Aspose Java** projektek létrehozásához, az általános tulajdonságok olvasásához és írásához, valamint a **feladat kezdő dátumának** egyszerű lekéréséhez. Ezeknek a technikáknak a elsajátításával egyszerűsítheti a feladatkezelést bármely Java‑alapú ütemező alkalmazásban, és gazdagabb projekttervezési funkciókat nyújthat felhasználóinak.

---

**Utoljára frissítve:** 2026-02-26  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}