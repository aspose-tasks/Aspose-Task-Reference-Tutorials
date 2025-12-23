---
date: 2025-12-23
description: Ismerje meg, hogyan frissítheti az MS Project fájlokat és ütemezheti
  újra a befejezetlen munkákat az Aspose.Tasks for Java használatával. Továbbá tekintse
  meg, hogyan mentheti az MS Project XML-t.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project frissítése és a munka újraütemezése az Aspose.Tasks segítségével
url: /hu/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project frissítése és a munka újraütemezése az Aspose.Tasks segítségével

## Bevezetés
A Microsoft Project egy széles körben használt projektmenedzsment eszköz, amely segíti a csapatokat a munka megtervezésében, nyomon követésében és időben történő teljesítésében. Amikor az ütemtervek változnak, gyakran szükség van a **MS Project** fájlok programozott frissítésére — a munka befejezettnek jelölése, a hátralévő feladatok áthelyezése, és a projekt alapvonalának pontos megtartása. Az Aspose.Tasks for Java tiszta, típusbiztos API‑t biztosít ehhez anélkül, hogy meg kellene nyitni a felhasználói felületet. Ebben az útmutatóban megmutatjuk, hogyan frissítsünk egy projektet, hogyan jelöljünk be befejezett munkát egy adott dátumig, majd **hogyan ütemezzük újra a még függőben lévő MS Project munkát**.

## Gyors válaszok
- **Mit jelent a „MS Project frissítése”?** A feladatokat a megadott dátumig befejezettnek jelöli, és a változásokat visszaírja a fájlba.  
- **Automatikusan újraütemezhetem a hátralévő munkát?** Igen — használja a `rescheduleUncompletedWorkToStartAfter` metódust a befejezetlen feladatok előre tolásához.  
- **Milyen fájlformátumban mentődik?** A példák a projektet XML‑ként (`SaveFileFormat.Xml`) mentik.  
- **Szükség van licencre a kód futtatásához?** Fejlesztéshez egy ingyenes próba verzió elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Milyen Java verzió szükséges?** JDK 8 vagy újabb.

## Mi a „MS Project frissítése” a kódban?
A projekt frissítése azt jelenti, hogy programozottan módosítjuk a feladatok dátumait, időtartamát vagy befejezési százalékát, majd ezeket a változásokat elmentjük. Az Aspose.Tasks olyan metódusokat kínál, mint a `updateProjectWorkAsComplete`, amelyek a megadott referencia **Date** alapján alkalmazzák a módosításokat.

## Miért használjuk az Aspose.Tasks for Java‑t a MS Project frissítéséhez?
- **Nincs UI függőség** – tömeges módosítások automatizálása sok fájlon.  
- **Magas pontosság** – a könyvtár megőrzi a natív Project adatokat (erőforrások, naptárak, egyéni mezők).  
- **Keresztplatformos** – ugyanaz a kód futtatható Windows, Linux vagy macOS rendszeren.  
- **MS Project XML mentése** – a frissített projektet exportálhatja a széles körben támogatott XML formátumba, amely más eszközök számára is használható.

## Előfeltételek
1. Telepített Java Development Kit (JDK).  
2. Aspose.Tasks for Java könyvtár – letölthető [innen](https://releases.aspose.com/tasks/java/).  
3. Alapvető ismeretek a Java szintaxisról és az objektum‑orientált koncepciókról.

## Csomagok importálása
Először importálja a szükséges Aspose.Tasks osztályokat és a Java segédfüggvényeket:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 1. lépés: A projekt előkészítése
Hozzon létre egy új `Project` példányt, definiáljon néhány mintafeladatot, állítsa be azok időtartamát, és hozza létre a függőségeket. Ezután mentse el a kezdeti állapotot, hogy láthassa a „előtte‑utána” hatást.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## 2. lépés: Projektmunka frissítése
Jelölje be a munkát befejezettnek egy adott határidőig. Ez a **MS Project frissítése** központi része — az API automatikusan módosítja a feladatok előrehaladását és dátumait.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## 3. lépés: Befejezetlen munka újraütemezése
A befejezett munka jelölése után gyakran szükség van a hátralévő feladatok előre tolására. Az alábbi hívás minden befejezetlen munkát a határidő utánra helyez, ezáltal **hogyan ütemezzük újra a MS Project‑et**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A feladatok nem mutatják a frissített dátumokat | A projekt más formátumban lett mentve (pl. `.mpp`) | Használja a `SaveFileFormat.Xml`‑t az XML struktúra megőrzéséhez. |
| A `updateProjectWorkAsComplete` látszólag nem csinál semmit | A referencia dátum a projekt kezdete előtt van | Győződjön meg róla, hogy a `Calendar` dátuma a projekt idővonalán belül van. |
| Az újraütemezett feladatok átfedik egymást | Nincs naptár vagy erőforrás‑kiegyenlítés alkalmazva | Alkalmazzon egy `Project` naptárat, vagy a újraütemezés után manuálisan állítsa be a `Task.setStart` értéket. |

## Gyakran ismételt kérdések (bővített)

**Q: Kezelni tudja az Aspose.Tasks for Java a komplex projektstruktúrákat?**  
A: Igen, az Aspose.Tasks for Java robusztus API‑kat biztosít a feladatok, függőségek, erőforrások és egyéb projekt elemek hatékony kezeléséhez.

**Q: Elérhető-e próba verzió az Aspose.Tasks for Java‑hoz?**  
A: Igen, ingyenes próbaverzió letölthető [innen](https://releases.aspose.com/).

**Q: Hogyan kaphatok támogatást az Aspose.Tasks for Java‑hoz?**  
A: Látogasson el az [Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15) bármilyen segítség vagy kérdés esetén.

**Q: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java‑hoz?**  
A: Igen, ideiglenes licencek vásárolhatók [itt](https://purchase.aspose.com/temporary-license/).

**Q: Hol találok részletes dokumentációt az Aspose.Tasks for Java‑hoz?**  
A: A dokumentáció elérhető [itt](https://reference.aspose.com/tasks/java/), ahol átfogó útmutatók és API‑referenciák állnak rendelkezésre.

## Összegzés
Ebben az útmutatóban végigvezettük a **MS Project** fájlok **frissítésének** teljes folyamatát, a munka befejezettként való jelölését, majd a **MS Project** feladatok **újraütemezését** a még befejezetlen munkák esetén. Az XML‑ként való mentés biztosítja a kompatibilitást más eszközökkel, és átlátható audit‑nyomot hagy a változtatásokról. Használja ezeket a mintákat ütemezési módosítások automatizálásához nagy portfóliókban, CI‑pipeline‑okba való integráláshoz, vagy egyedi jelentéskészítő irányítópultok építéséhez.

---

**Utoljára frissítve:** 2025-12-23  
**Tesztelt verzió:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}