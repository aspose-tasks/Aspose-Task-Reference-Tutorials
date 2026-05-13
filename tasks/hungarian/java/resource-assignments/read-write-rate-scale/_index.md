---
date: 2026-01-10
description: Tanulja meg, hogyan olvassa el a díjskálát és kezelje az erőforrás-hozzárendeléseket
  az Aspose.Tasks for Java-ban. Definiálja az anyag erőforrást, hogyan állítsa be
  a skálát, és rendelje hozzá az erőforrásokat a feladathoz.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan olvassuk és írjuk az árskálát az erőforrás-kiosztásokhoz az Aspose.Tasks-ben
url: /hu/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan olvassuk és írjuk a Rate Scale-t erőforrás hozzárendelésekhez az Aspose.Tasks-ben

Ebben az útmutatóban megtudhatja, **hogyan olvassa a Rate Scale** beállításait, és hogyan állítsa be őket erőforrás hozzárendelésekhez az Aspose.Tasks for Java segítségével. Legyen szó ütemező, jelentéskészítő eszköz fejlesztéséről, vagy egyszerűen csak projektfrissítések automatizálásáról, a Rate Scale manipulálásának elsajátítása finomhangolt vezérlést biztosít az anyag- és munkaforrások felett.

## Gyors válaszok
- **Mi a fő osztály a rate kezeléshez?** `ResourceAssignment` a `Asn.RATE_SCALE` tulajdonsággal.  
- **Melyik enum határozza meg a skála lehetőségeket?** `RateScaleType` (Day, Week, Month, stb.).  
- **Szükségem van licencre a minta futtatásához?** Egy ingyenes értékelési licenc teszteléshez működik; a termeléshez kereskedelmi licenc szükséges.  
- **Módosíthatom a skálát mentés után?** Igen – töltsd be újra a projektet és módosítsd a `Asn.RATE_SCALE`-t, ahogy látható.  
- **Támogatott IDE-k?** Bármely Java IDE (IntelliJ IDEA, Eclipse, NetBeans) lefordíthatja a kódot.

## Mi az a Rate Scale?
A Rate Scale meghatározza azt az időegységet (nap, hét, hónap stb.), amelyre egy erőforrás költségarányát alkalmazzák. A skála módosítása lehetővé teszi az anyagfelhasználás vagy a munkaidő pontos modellezését.

## Miért olvassuk és írjuk a Rate Scale-t?
A jelenlegi skála olvasása segít az ütemezés auditálásában, míg egy új skála írása lehetővé teszi, hogy az erőforrásokat a projekt számlázási vagy fogyasztási szabályaihoz igazítsuk. Ez különösen hasznos **anyag erőforrás** költségek definiálásakor vagy **skála beállításakor** nem szabványos munkanaptárak esetén.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következőkkel:
1. **Java fejlesztői környezet** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java könyvtár** – Töltsd le és telepítsd a könyvtárat [itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először importáld a szükséges Aspose.Tasks osztályokat.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## 1. lépés: Állítsd be a Java projekted
Hozz létre egy Maven vagy Gradle projektet, és add hozzá az Aspose.Tasks JAR‑t az osztályúthoz. Ez biztosítja, hogy a fordító megtalálja az importált osztályokat.

## 2. lépés: Töltsd be a projektfájlt
Töltsd be a meglévő Microsoft Project fájlt, amelyen dolgozni szeretnél.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 3. lépés: Feladat hozzáadása
Hozz létre egy új feladatot, amely később erőforrás hozzárendeléseket kap.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 4. lépés: Erőforrások definiálása
Itt **anyag erőforrást** és egy szokásos munkaforrást definiálunk. Figyeld meg a `ResourceType.Material` használatát az anyag‑típusú erőforrásnál.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 5. lépés: Erőforrások hozzárendelése a feladathoz
Most **erőforrásokat rendeljünk a feladathoz**, és a **skála beállítását** a `RateScaleType.Week` használatával adjuk meg. Ez bemutatja a Rate Scale olvasását és írását is.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 6. lépés: Projekt mentése
Mentsd el a változtatásokat egy új fájlba, hogy később ellenőrizhessük a tárolt Rate Scale‑t.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 7. lépés: Erőforrás hozzárendelések lekérése
Töltsd be újra a mentett projektet, és **olvasd a Rate Scale**-t, hogy megerősítsd, helyesen lett-e írva.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Gyakori hibák és tippek
- **UID eltérés** – UID alapján történő hozzárendelés lekérdezésekor győződj meg róla, hogy az UID értékek megegyeznek a létrehozáskor hozzárendelt értékekkel.  
- **Helytelen erőforrás típus** – `ResourceType.Material` használata munkavégző erőforrásra váratlan rate számításokat eredményez.  
- **Mentési formátum** – Mindig `SaveFileFormat.Mpp` (vagy más támogatott formátum) használatával ments, hogy megőrizd az egyedi mezőket, például a Rate Scale‑t.

## Következtetés
A Rate Scale kezelése és ellenőrzése erőforrás hozzárendelésekhez az Aspose.Tasks for Java‑ban egyszerű, ha ismered a megfelelő osztályokat és tulajdonságokat. Ezt az útmutatót követve **olvasni tudod a rate** információkat, **definiálni a material resource** objektumokat, **beállítani a skálát**, és **erőforrásokat hozzárendelni a feladathoz** magabiztosan.

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Tasks for Java‑t bármely Java IDE‑val?**  
A: Igen, az Aspose.Tasks for Java kompatibilis minden főbb Java IDE‑val, beleértve az IntelliJ IDEA‑t, az Eclipse‑t és a NetBeans‑t.

**Q: Az Aspose.Tasks támogat más fájlformátumokat is az MPP‑n kívül?**  
A: Igen, az Aspose.Tasks különféle fájlformátumokat támogat, többek között MPP, XML és HTML.

**Q: Az Aspose.Tasks alkalmas vállalati szintű projektmenedzsmentre?**  
A: Teljes mértékben, az Aspose.Tasks átfogó funkciókat kínál bármilyen méretű projekt kezeléséhez, így vállalati szintű projektmenedzsmentre is alkalmas.

**Q: Testreszabhatom az erőforrás hozzárendeléseket a Rate Scale‑en túl?**  
A: Igen, az Aspose.Tasks kiterjedt lehetőségeket biztosít az erőforrás hozzárendelések testreszabására, beleértve a költség, munka és időtartam módosítását.

**Q: Van közösségi fórum az Aspose.Tasks támogatásához?**  
A: Igen, támogatást és felhasználói interakciót találsz az Aspose.Tasks fórumon [itt](https://forum.aspose.com/c/tasks/15/).

---

**Utolsó frissítés:** 2026-01-10  
**Tesztelve:** Aspose.Tasks for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}