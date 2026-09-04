---
date: 2026-06-10
description: Tanulja meg, hogyan olvassa a rate-et és hogyan írja a Rate Scale-t a
  resource assignments-hez az Aspose.Tasks for Java használatával. Támogatja a material
  resources-t, a multiple formats-t és a large projects-t.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Rate Scale olvasása és írása a Resource Assignments-hez az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan olvassuk és írjuk a Rate Scale-t a Resource Assignments-hez az Aspose.Tasks-ben
url: /hu/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan olvassuk és írjuk a ráta skálát a erőforrás hozzárendeléseknél az Aspose.Tasks-ben

Ebben az útmutatóban megtudja, **hogyan olvassa el a ráta** skála beállításait, és hogyan állíthatja be őket erőforrás hozzárendeléseknél az Aspose.Tasks for Java használatával. Akár ütemezőt, jelentéskészítő eszközt épít, akár csak projektfrissítéseket szeretne automatizálni, a ráta skála kezelésének elsajátítása finomhangolt ellenőrzést biztosít az anyag- és munkaforrások felett.

## Gyors válaszok
`ResourceAssignment` egy feladatot egy erőforráshoz kapcsol, és tárolja a hozzárendelés‑specifikus adatokat.  
`Asn` állandókat tartalmaz a hozzárendelési mezőkhöz, beleértve a `RATE_SCALE`-t.  
`RateScaleType` felsorolja a lehetséges időegységeket a ráta skálázáshoz.  

- **Mi a fő osztály a ráta kezeléséhez?** `ResourceAssignment` a `Asn.RATE_SCALE` tulajdonsággal.  
- **Melyik enum határozza meg a skála lehetőségeket?** `RateScaleType` (Day, Week, Month, stb.).  
- **Szükségem van licencre a példa futtatásához?** Egy ingyenes értékelő licenc működik teszteléshez; a termeléshez kereskedelmi licenc szükséges.  
- **Módosíthatom a skálát a mentés után?** Igen – töltse újra a projektet, és módosítsa a `Asn.RATE_SCALE`-t a bemutatott módon.  
- **Támogatott IDE-k?** Bármely Java IDE (IntelliJ IDEA, Eclipse, NetBeans) képes lefordítani a kódot.

## Hogyan olvassuk el a ráta skálát a erőforrás hozzárendeléseknél?

Töltse be a projektet, keresse meg a kívánt `ResourceAssignment`-ot, és hívja meg a `getRateScale()`‑t – ez egy `RateScaleType` értéket ad vissza, amely megmutatja, hogy a ráta napra, hétre, hónapra vagy más egységre van-e alkalmazva. A válasz azonnali, és csak két API hívást igényel, így ideális audit szkriptekhez vagy UI megjelenítésekhez.

## Hogyan írjuk be a ráta skálát a erőforrás hozzárendeléseknél?

Hozzon létre vagy szerezzen be egy `ResourceAssignment` objektumot, állítsa be a `Asn.RATE_SCALE` tulajdonságát a kívánt `RateScaleType`‑ra (pl. `RateScaleType.Week`), majd mentse a projektet. Ez az egyetlen tulajdonságváltoztatás automatikusan frissíti a költségszámításokat, és megmarad minden támogatott fájlformátumban. A skála beállítása után szükség lehet a erőforrás standard vagy túlóra rátájának módosítására az új időegység tükrözéséhez, biztosítva a költségszámítások pontosságát.

## Mi a ráta skála?

A ráta skála meghatározza azt az időegységet (nap, hét, hónap, stb.), amelyre egy erőforrás költség rátája alkalmazásra kerül. A skála módosítása lehetővé teszi az anyagfelhasználás vagy a munkaerő ráfordítás pontos modellezését. Például, ha a skálát Hétre állítja, a költség ráta heti költségként értelmeződik, és egy feladat teljes költségét a erőforrás hozzárendelésének heteinek száma alapján számítják ki.

## Miért olvassuk és írjuk a ráta skálát?

A jelenlegi skála olvasása segít az existing ütemtervek auditálásában, míg egy új skála írása lehetővé teszi az erőforrások összehangolását a projekt számlázási vagy fogyasztási szabályaival. Ez különösen hasznos, amikor **anyag erőforrás** költségeket definiál, vagy amikor **skálát kell beállítani** nem szabványos munkanaptárakhoz.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következő előfeltételekkel:
1. **Java fejlesztői környezet** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java könyvtár** – Töltse le és telepítse a könyvtárat innen: [here](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
A `ResourceAssignment` osztály egy feladat és egy erőforrás közötti kapcsolatot képvisel, míg a `RateScaleType` felsorolja a ráta lehetséges időegységeit. Importálja a szükséges Aspose.Tasks osztályokat, mielőtt kódolni kezdene.  

A `Project` a fő objektum, amely betölti és menti a Microsoft Project fájlokat.  
A `Resource` egy projekt erőforrást definiál, például munkát vagy anyagot.  
A `ResourceType` enum meghatározza, hogy egy erőforrás munka vagy anyag típusú-e.  
A `Task` egy munkatételt jelöl a projekt ütemezésében.  
A `SaveFileFormat` enum meghatározza a projekt mentésének kimeneti formátumát.

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

## 1. lépés: Állítsa be a Java projektet
Hozzon létre egy Maven vagy Gradle projektet, és adja hozzá az Aspose.Tasks JAR-t az osztályútvonalához. Ez a lépés biztosítja, hogy a fordító megtalálja az importált osztályokat.

## 2. lépés: Töltse be a projektfájlt
Töltse be a meglévő Microsoft Project fájlt, amelyen dolgozni szeretne.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 3. lépés: Feladat hozzáadása
Hozzon létre egy új feladatot, amely később erőforrás hozzárendeléseket kap.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 4. lépés: Erőforrások definiálása
Itt **anyag erőforrást definiálunk** és egy szabályos munkaforrást. Figyelje meg a `ResourceType.Material` használatát az anyag‑típusú erőforrásnál.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 5. lépés: Erőforrások hozzárendelése a feladathoz
Most **erőforrásokat rendelünk a feladathoz** és megadjuk a **skála beállításának módját** a `RateScaleType.Week` használatával. Ez bemutatja a ráta skála olvasását és írását is.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 6. lépés: Projekt mentése
Mentse el a változtatásokat egy új fájlba, hogy később ellenőrizhessük a tárolt ráta skálát.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 7. lépés: Erőforrás hozzárendelések lekérése
Töltse újra a mentett projektet, és **olvassa el a ráta** skálát, hogy megerősítse, helyesen lett-e írva.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Gyakori buktatók és tippek
- **UID eltérés** – UID alapján történő hozzárendelés lekérdezésekor győződjön meg róla, hogy az UID értékek megegyeznek a létrehozás során hozzárendelt értékekkel.  
- **Helytelen erőforrás típus** – `ResourceType.Material` használata munkaforráshoz váratlanul befolyásolja a ráta számításokat.  
- **Mentési formátum** – Mindig mentse `SaveFileFormat.Mpp` (vagy más támogatott formátum) használatával, hogy megőrizze az egyedi mezőket, például a ráta skálát.  
- **Nagy projektek** – Az Aspose.Tasks képes **500+ oldalas** fájlok feldolgozására anélkül, hogy az egész dokumentumot memóriába töltené, köszönhetően a streaming architektúrájának.

## Gyakran ismételt kérdések

**K: Használhatom az Aspose.Tasks for Java-t bármely Java IDE-vel?**  
V: Igen, az Aspose.Tasks for Java kompatibilis minden nagyobb Java IDE-vel, beleértve az IntelliJ IDEA, Eclipse és NetBeans-t.

**K: Támogatja az Aspose.Tasks más fájlformátumokat is az MPP mellett?**  
V: Igen, az Aspose.Tasks különféle fájlformátumokat támogat, beleértve az MPP, XML és HTML formátumokat.

**K: Alkalmas az Aspose.Tasks vállalati szintű projektmenedzsmenthez?**  
V: Teljes mértékben, az Aspose.Tasks átfogó funkciókat kínál bármilyen méretű projekt kezeléséhez, így alkalmas vállalati szintű projektmenedzsmentre.

**K: Testreszabhatom a erőforrás hozzárendeléseket a ráta skálán túl?**  
V: Igen, az Aspose.Tasks kiterjedt lehetőségeket biztosít az erőforrás hozzárendelések testreszabására, beleértve a költség, munka és időtartam módosítását.

**K: Van közösségi fórum az Aspose.Tasks támogatásához?**  
V: Igen, támogatást és felhasználókkal való interakciót talál az Aspose.Tasks fórumban [itt](https://forum.aspose.com/c/tasks/15).

---

**Utolsó frissítés:** 2026-06-10  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Erőforrás hozzárendelések létrehozása az Aspose.Tasks-ben](/tasks/java/resource-assignments/create-resource-assignments/)
- [Hogyan módosítsuk a hozzárendeléseket – Megosztott erőforrások olvasása az Aspose-szal](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Hogyan adjunk megjegyzéseket az erőforrás hozzárendelésekhez az Aspose.Tasks-ben](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}