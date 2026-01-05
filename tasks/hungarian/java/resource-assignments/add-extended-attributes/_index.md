---
date: 2026-01-05
description: Tanulja meg, hogyan állíthatja be a projekt kezdő dátumát, és mentheti
  az MS Project XML-t az Aspose.Tasks for Java használatával. Lépésről lépésre útmutató
  Java fejlesztőknek.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt kezdő dátum beállítása az Aspose.Tasks for Java segítségével
url: /hu/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt kezdő dátum beállítása Aspose.Tasks for Java-val

## Bevezetés
Ebben az oktatóanyagban megtanulja, **hogyan állítsa be a projekt kezdő dátumát** egy Microsoft Project fájlban, majd **mentse el az MS Project XML-t** az Aspose.Tasks Java könyvtár segítségével. Akár jelentéskészítő csővezeték automatizálásáról, akár egy egyedi projektmenedzsment eszköz építéséről van szó, ennek a feladatnak a elsajátítása időt takarít meg, és kiküszöböli a kézi hibákat.

## Gyors válaszok
- **Mi a fő módszer a kezdő dátum beállításához?** Használja a `project.set(Prj.START_DATE, …)`-t.
- **Milyen formátumot használjak a fájl exportálásához?** Mentse XML-ként a `SaveFileFormat.Xml` segítségével.
- **Szükség van licencre ehhez a művelethez?** A próbaverzió működik, de a teljes licenc eltávolítja a vízjeleket.
- **Megváltoztathatom a kezdő dátumot a feladatok létrehozása után?** Igen, frissítse a projekt tulajdonságát a feladatok hozzáadása előtt.
- **Ez kompatibilis minden MS Project verzióval?** Az Aspose.Tasks támogatja az XML, MPP és egyéb formátumokat.

## Mi az a „Projekt kezdő dátum beállítása”?
A projekt kezdő dátumának beállítása meghatározza az alapnaptárat, amelyből minden feladat ütemezési számítás kiindul. Ez az első lépés egy megbízható projektmenetrend programozott felépítésében.

## Miért használja az Aspose.Tasks for Java-t?
Az Aspose.Tasks egy tiszta Java API-t biztosít, amely bármely platformon működik, anélkül, hogy a Microsoft Project telepítve lenne. Lehetővé teszi a projektadatok gyors létrehozását, módosítását és exportálását, így ideális a szerveroldali automatizáláshoz.

## Előfeltételek
1. **Java Development Kit (JDK)** – bármely friss JDK verzió.
2. **Aspose.Tasks for Java** – letölthető [itt](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse vagy a kedvenc Java IDE-je.

## Csomagok importálása
Először importálja a szükséges osztályokat:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 1. lépés: Adatkönyvtár beállítása
Határozza meg, hogy hol legyenek tárolva a generált fájlok.

```java
String dataDir = "Your Data Directory";
```

### 2. lépés: Projekt példány létrehozása
Hozzon létre egy új, üres projektet.

```java
Project project = new Project();
```

### 3. lépés: Projektinformációs tulajdonságok beállítása
Itt **beállítjuk a projekt kezdő dátumát** és a kapcsolódó ütemezési tulajdonságokat.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 4. lépés: MS Project XML mentése
Exportálja a beállított projektet egy XML fájlba.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Gyakori problémák és megoldások
- **Helytelen dátumformátum:** Győződjön meg róla, hogy a `java.util.Calendar`-t használja, és a hozzárendelés előtt meghívja a `getTime()`-t.
- **A fájl nem mentődik:** Ellenőrizze, hogy a `dataDir` egy létező, írható mappára mutat.
- **Licencfigyelmeztetések:** A próbaverzió vízjeleket ad hozzá; érvényes licenc alkalmazásával eltávolíthatók.

## Gyakran feltett kérdések

### K: Használhatom az Aspose.Tasks for Java-t MS Project fájlok olvasására?
**A:** Igen, az Aspose.Tasks for Java robusztus funkciókat biztosít mind MS Project fájlok olvasásához, mind írásához.

### K: Az Aspose.Tasks for Java kompatibilis a különböző MS Project verziókkal?
**A:** Teljes mértékben, az Aspose.Tasks for Java támogatja a különféle MS Project formátumokat, biztosítva a széles körű kompatibilitást.

### K: Vannak korlátozások a Aspose.Tasks for Java próbaverziójában?
**A:** A próbaverzió lehetővé teszi a könyvtár felfedezését, de vízjeleket ad a kimeneti fájlokhoz.

### K: Hogyan kaphatok támogatást az Aspose.Tasks for Java-hoz?
**A:** Segítséget kérhet az Aspose.Tasks közösségi fórumon [itt](https://forum.aspose.com/c/tasks/15).

### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java-hoz?
**A:** Igen, ideiglenes licencek elérhetők rövid távú használatra. Szerezzen egyet [itt](https://purchase.aspose.com/temporary-license/).

### K: Az XML-ként mentés megőrzi az egyedi mezőket?
**A:** Igen, amikor a `SaveFileFormat.Xml`-t használja, minden egyedi attribútum és kiterjesztett mező megmarad.

### K: Megváltoztathatom a kezdő dátumot a feladatok hozzáadása után?
**A:** A kezdő dátumot bármikor frissítheti a mentés előtt; csak hívja újra a `project.set(Prj.START_DATE, …)`-t.

---

**Utoljára frissítve:** 2026-01-05  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}