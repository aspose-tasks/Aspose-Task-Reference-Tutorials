---
date: 2026-02-13
description: Tanulja meg, hogyan hozhat létre új tevékenységet, állíthatja be az adatkönyvtárat,
  és mentheti a projektet MPP formátumban az Aspose.Tasks Java-ban. Ez a lépésről‑lépésre
  útmutató a táblázatmezők testreszabását is bemutatja.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Új tevékenység létrehozása és adatkönyvtár beállítása az Aspose.Tasks-ben
url: /hu/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Új tevékenység létrehozása és adatkönyvtár beállítása Aspose.Tasks

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **állítsa be az adatkönyvtárat**, hogyan **hozzon létre új tevékenységet**, és hogyan **mentse a projektet MPP formátumban**, miközben konfigurálja a Gantt MS Project diagram nézetet az Aspose.Tasks projektekben Java használatával. Az Aspose.Tasks egy robusztus Java API, amely lehetővé teszi a Microsoft Project fájlok programozott kezelését. A útmutató végére képes lesz **testreszabni a táblázat mezőket**, módosítani az adatkönyvtárat, és pontosan úgy megjeleníteni a projektet, ahogy szükséges.

## Gyors válaszok
- **Mi az első lépés?** Állítsa be az adatkönyvtár útvonalát, ahol a projektfájlok találhatók.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (letölthető a hivatalos oldalról).  
- **Hozzáadhatok egyéni attribútumokat?** Igen – definiálhat kiterjesztett attribútumokat és megjelenítheti őket a Gantt-diagramon.  
- **Szükségem van licencre a teszteléshez?** Ideiglenes licenc érhető el értékelési célokra.  
- **Melyik IDE a legjobb?** Bármely Java IDE (IntelliJ IDEA, Eclipse, NetBeans) működik.

## Mi az a „adatkönyvtár beállítása”, és miért fontos?
Az adatkönyvtár beállítása megmondja az Aspose.Tasks-nek, hol olvassa és írja a projektfájlokat. Helytelen útvonal esetén az API nem tudja megtalálni a `.mpp` fájlokat, ami FileNotFound hibákhoz vezet. Ennek a könyvtárnak a kód elején történő definiálása tisztává és újrahasználhatóvá teszi a további munkafolyamatot.

## Miért testreszabjuk a táblázat mezőket egy Gantt-diagramban?
Az egyedi táblázatmezők lehetővé teszik további információk – például egyéni attribútumok, erőforrás adatok vagy projektspecifikus megjegyzések – közvetlen megjelenítését a Gantt-nézetben. Ez informatívabbá teszi a diagramot az érintettek számára, és csökkenti a több jelentés közti váltás szükségességét.

## Hogyan hozzunk létre új tevékenységet?
Új tevékenység (feladat) létrehozása a projekt ütemezés építése vagy frissítése során az egyik alapvető művelet. Feladatok programozott hozzáadásával automatizálhatja a komplex projekttervek létrehozását, integrálhat adatokat más rendszerekből, vagy tömeges módosításokat végezhet manuális szerkesztés nélkül.

## Előfeltételek
1. **Java Development Kit (JDK)** – bármely friss verzió (8+).  
2. **Aspose.Tasks Library** – töltse le innen: [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse vagy bármely általad preferált Java‑kompatibilis szerkesztő.

## Csomagok importálása
Először importálja az Aspose.Tasks névteret, hogy használhassa annak osztályait:

```java
import com.aspose.tasks.*;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Adatkönyvtár beállítása
Határozza meg azt a mappát, amely a projektfájlokat tartalmazza. Ez a **adatkönyvtár beállítása** lépés, amelyre az útmutató fókuszál.

```java
String dataDir = "Your Data Directory";
```

Cserélje le a `"Your Data Directory"` értéket a `project.mpp` fájlt tartalmazó mappa abszolút útvonalára.

### 2. lépés: Projektfájl betöltése
Hozzon létre egy `Project` példányt egy meglévő Microsoft Project fájl betöltésével.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. lépés: Új tevékenység hozzáadása
Helyezzen be egy új feladatot (tevékenységet) a projekt gyökerébe. Ez bemutatja, hogyan **hozzunk létre új tevékenységet** programozottan.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 4. lépés: Egyéni attribútum definiálása
Hozzon létre egy egyéni attribútumdefiníciót, amelyet később feladatokhoz csatolhat.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 5. lépés: Egyéni attribútum hozzáadása feladathoz
Rendelje hozzá az újonnan definiált attribútumot a létrehozott feladathoz.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 6. lépés: Táblázat testreszabása – **customize table fields**
Adja hozzá az egyéni attribútumot oszlopként a Gantt-diagram táblázatához, megadva a szélességet, címet és igazítást.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### 7. lépés: Projekt mentése
Mentse el a módosításokat egy új fájlba, amely megnyitható a Microsoft Projectben. Ez a lépés **menti a projektet MPP formátumban**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **FileNotFoundException** a projekt betöltésekor | Az **adatkönyvtár beállítása** útvonal helytelen vagy hiányzik a záró perjel. | Ellenőrizze, hogy a `dataDir` a pontos mappára mutat, és tartalmazza a megfelelő fájlelválasztót (`/` vagy `\\`). |
| Az egyéni attribútum nem látható a Gantt-nézetben | A táblázatmező rossz indexen lett hozzáadva, vagy az oszlopszélesség túl kicsi. | Győződjön meg róla, hogy a `table.getTableFields().add(3, attrField);` érvényes indexet használ, és szükség szerint állítsa be a `setWidth` értékét. |
| LicenseException mentéskor | Nem lett érvényes licenc alkalmazva a termelési használathoz. | Alkalmazzon ideiglenes vagy állandó licencet a `project.save()` hívása előtt. |

## Gyakran ismételt kérdések

**K: Használhatom az Aspose.Tasks-et más programozási nyelvekkel?**  
**V: Igen, az Aspose.Tasks több programozási nyelven is elérhető, többek között .NET, Java és C++.**

**K: Van ingyenes próba az Aspose.Tasks-hez?**  
**V: Igen, letölthet egy ingyenes próbát innen: [here](https://releases.aspose.com/).**

**K: Hol találok támogatást az Aspose.Tasks-hez?**  
**V: Támogatást és kérdéseket a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) találhat.**

**K: Hogyan vásárolhatok licencet az Aspose.Tasks-hez?**  
**V: Licencet vásárolhat innen: [here](https://purchase.aspose.com/buy).**

**K: Szükségem van ideiglenes licencre a teszteléshez?**  
**V: Igen, ideiglenes licencet szerezhet innen: [here](https://purchase.aspose.com/temporary-license/).**

## Következtetés
Most már megtanulta, hogyan **állítsa be az adatkönyvtárat**, **hozzon létre új tevékenységet**, definiáljon és csatoljon egy egyéni attribútumot, valamint hogyan **mentse a projektet MPP formátumban**, miközben **testreszabja a táblázat mezőket** egy Gantt-diagram nézetben az Aspose.Tasks for Java használatával. Ezek a lépések teljes irányítást adnak a projektadatok megjelenítése felett, így a Gantt-diagramok informatívabbak és a résztvevők igényeihez igazítottak lesznek.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}