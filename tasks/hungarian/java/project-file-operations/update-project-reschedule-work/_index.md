---
date: 2026-03-29
description: Tanulja meg, hogyan ütemezze át a befejezetlen munkát, frissítse a projektmunkát,
  és mentse el az MS Project fájlokat XML formátumban az Aspose.Tasks for Java segítségével.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Befejezetlen munka újraszervezése és MS Project fájlok frissítése az Aspose.Tasks
  segítségével
url: /hu/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Befejezetlen munka újrasütemezése és MS Project fájlok frissítése az Aspose.Tasks segítségével

## Bevezetés
A Microsoft Project egy széles körben használt projektmenedzsment eszköz, amely segíti a csapatokat a feladatok tervezésében, az erőforrások kiosztásában és az ütemtervek nyomon követésében. Az Aspose.Tasks for Java fejlesztőknek gazdag API-t biztosít a Microsoft Project fájlok programozott módon történő manipulálásához. Ebben az útmutatóban megtanulja, hogyan **frissítse a projekt munkáját**, **újrasütemezze a befejezetlen munkát**, és **mentse el a MS Project fájlt** XML formátumban az Aspose.Tasks for Java használatával.

## Gyors válaszok
- **Mi jelent a „befejezetlen munka újrasütemezése”?** A maradék feladatmunkát egy kiválasztott dátum utánra helyezi, a befejezett részeket érintetlenül hagyva.  
- **Melyik metódus jelöli meg a munkát befejezettként?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Hogyan menthetem el a változtatásokat?** Használja a `project.save(<path>, SaveFileFormat.Xml)` metódust.  
- **Szükségem van licencre a termeléshez?** Igen, a kereskedelmi használathoz érvényes Aspose.Tasks licenc szükséges.  
- **Melyik Java verzió támogatott?** A Java 8 és újabb verziók teljes mértékben támogatottak.

## Mi a „befejezetlen munka újrasütemezése”?
A befejezetlen munka újrasütemezése módosítja az összes még be nem fejezett feladat kezdődátumát, úgy, hogy azok egy megadott határdátum után induljanak. Ez akkor hasznos, ha a projekt ütemterve késések vagy hatókörváltozások miatt eltolódik.

## Miért használja az Aspose.Tasks-et a projekt munka frissítéséhez és a feladatok újrasütemezéséhez?
- **Finomhangolt vezérlés:** Közvetlenül beállíthatja a munka befejezési százalékát és dátumait.  
- **Nincs UI szükséges:** Automatizálja a tömeges frissítéseket számos projektfájlban.  
- **Keresztplatformos:** Bármely, Java-t futtató rendszeren működik.  
- **Megőrzi az adat integritását:** Minden függőség, korlátozás és erőforrás konzisztens marad.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következőkkel rendelkezik:
1. Java Development Kit (JDK) telepítve van a rendszerén.  
2. Aspose.Tasks for Java könyvtár. Letöltheti innen: [here](https://releases.aspose.com/tasks/java/).  
3. Alapvető ismeretek a Java programozási nyelvről.

## Csomagok importálása
Először importálja a szükséges csomagokat a Java kódjában:
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

## 1. lépés: A projekt beállítása
Inicializáljon egy új `Project` objektumot, definiálja a feladatokat, állítsa be a időtartamokat, és hozza létre a függőségeket. Ez létrehozza az alap projektet, amelyet később frissíteni és újrasütemezni fogunk.
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

## 2. lépés: Projekt munka frissítése
Jelölje meg a munkát befejezettként egy adott dátumig. Ez a lépés bemutatja a **projekt munka frissítése** műveletet, amely gyakran az első lépés az újrasütemezés előtt.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## 3. lépés: Befejezetlen munka újrasütemezése
Most áthelyezzük a maradék (befejezetlen) munkát, hogy az ugyanaz a határdátum után kezdődjön. Ez a **befejezetlen munka újrasütemezése** funkció központja.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Összegzés
Ebben az útmutatóban bemutattuk, hogyan **frissítheti a projekt munkáját**, **újrasütemezheti a befejezetlen munkát**, és **mentheti el a MS Project fájlt** XML formátumban az Aspose.Tasks for Java használatával. Ezek a képességek elengedhetetlenek, amikor a projekt ütemterveket a tényleges előrehaladás vagy a változó üzleti prioritások alapján kell módosítani.

## GYIK
### Q: Kezelheti az Aspose.Tasks for Java a komplex projektstruktúrákat?
A: Igen, az Aspose.Tasks for Java robusztus API-kat biztosít a feladatok, függőségek, erőforrások és egyéb projekt elemek hatékony kezeléséhez.  
### Q: Elérhető-e próbaverzió az Aspose.Tasks for Java-hoz?
A: Igen, ingyenes próbaverziót kaphat innen: [here](https://releases.aspose.com/).  
### Q: Hogyan kaphatok támogatást az Aspose.Tasks for Java-hoz?
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) bármilyen segítség vagy kérdés esetén.  
### Q: Vásárolhatok-e ideiglenes licencet az Aspose.Tasks for Java-hoz?
A: Igen, ideiglenes licencek vásárolhatók itt: [here](https://purchase.aspose.com/temporary-license/).  
### Q: Hol találok részletes dokumentációt az Aspose.Tasks for Java-hoz?
A: A dokumentációt itt tekintheti meg: [here](https://reference.aspose.com/tasks/java/) átfogó útmutatók és API-referenciák számára.

## További gyakran ismételt kérdések

**Q: Hogyan biztosíthatom, hogy a mentett fájl kompatibilis legyen a Microsoft Project régebbi verzióival?**  
A: Mentse a projektet a `SaveFileFormat.Xml` használatával; az XML széles körben támogatott a Project verziók között.

**Q: Tudok csak a **feladatok** egy részét újrasütemezni a teljes **projekt** helyett?**  
A: Igen, iterálhat a konkrét feladatokon, és a `task.setStart(date)` hívással állíthatja be az új kezdődátumot.

**Q: Mi történik az erőforrás-elosztásokkal, amikor újrasütemezem a befejezetlen munkát?**  
A: Az erőforrás‑hozzárendelések automatikusan áthelyeződnek, hogy megfeleljenek az új feladatkezdési dátumoknak, megőrizve az elosztási logikát.

**Q: Lehetséges programozottan visszavonni egy újrasütemezési műveletet?**  
A: Az eredeti projektfájlt (vagy egy mentést) újratölthető, hogy visszaállítsa a változtatásokat.

**Q: Támogatja az Aspose.Tasks a mentést más formátumokba, például .mpp?**  
A: Természetesen. Használja a `SaveFileFormat.MPP`‑t a natív Microsoft Project formátumba való mentéshez.

**Utoljára frissítve:** 2026-03-29  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}