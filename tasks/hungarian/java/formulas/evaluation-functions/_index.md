---
date: 2025-12-09
description: Tanulja meg, hogyan hozhat létre projektobjektumot Java-ban, és hogyan
  támogatja az értékelési függvényeket az Aspose.Tasks képletekben Java használatával.
  Fedezze fel, hogyan hozhat létre kiterjesztett attribútumot a feladatokhoz.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Projektobjektum létrehozása Java-ban – Értékelő függvények támogatása az Aspose.Tasks-ben
url: /hu/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Támogassa az értékelő függvényeket az Aspose.Tasks képletekben

## Bevezetés
Az Aspose.Tasks for Java lehetővé teszi, hogy **create project object java** példányokat hozzon létre, és közvetlenül a Java kódjában értékelje a Microsoft Project függvényeket. Ezeknek a képleteknek a beágyazásával összetett számításokat végezhet, egyedi jelentéseket generálhat, és automatizálhatja a projekt‑elemzést anélkül, hogy elhagyná a fejlesztői környezetet. Ez az útmutató végigvezeti Önt a teljes folyamaton – a projektobjektum beállításától az egyéni adatokat tároló kiterjesztett attribútum hozzáadásáig.

## Gyors válaszok
- **Mit jelent a “create project object java”?** Egy memóriában lévő `Project` példányt hoz létre, amelyet programozottan módosíthat.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (letölthető a hivatalos oldalról).  
- **Szükségem van licencre?** Ideiglenes vagy teljes licenc szükséges a termelési használathoz; ingyenes próba elérhető.  
- **Használhatok egyéni mezőket?** Igen – definiálhat és felcsatolhat kiterjesztett attribútumokat feladatokhoz.  
- **Kompatibilis minden Project fájlformátummal?** Az Aspose.Tasks támogatja az MPP, MPT és XML formátumokat.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik a következőkkel:

1. **Java fejlesztői környezet** – JDK 8+ és egy IDE, például IntelliJ IDEA vagy Eclipse.  
2. **Aspose.Tasks for Java könyvtár** – Töltse le, és vegye fel a projektbe a [Aspose.Tasks for Java letöltési oldal](https://releases.aspose.com/tasks/java/) segítségével.

## Csomagok importálása
Adja hozzá az Aspose.Tasks névteret a Java osztályához, hogy a projektek, feladatok és kiterjesztett attribútumok kezelhetők legyenek:

```java
import com.aspose.tasks.*;
```

## 1. lépés: Create Project Object Java
Hozzon létre egy új `Project` objektumot. Ez lesz a tároló minden feladat, erőforrás és egyéni adat számára, amelyet definiálni fog.

```java
Project project = new Project();
```

A fenti sor **creates project object java**, amely kezdetben üres, és készen áll a testreszabásra.

## 2. lépés: Hogyan hozzunk létre kiterjesztett attribútumot
Definiáljon egy kiterjesztett attribútumot, amely egyedi numerikus adatot (például szinusz értéket) tárol minden feladatnál.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Itt **create extended attribute** típusú `Number` attribútumot hozunk létre „Sine” néven, és hozzárendeljük a feladatokhoz.

## 3. lépés: A kiterjesztett attribútum hozzáadása a projekthez
Regisztrálja az attribútumdefiníciót a projektben, hogy minden feladat hivatkozhasson rá.

```java
project.getExtendedAttributes().add(attr);
```

## 4. lépés: Új feladat létrehozása
Adjon hozzá egy egyszerű, „Task” nevű feladatot a projekt gyökérfeladata alá.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 5. lépés: A kiterjesztett attribútum összekapcsolása a feladattal
Kösse össze a korábban definiált kiterjesztett attribútumot az újonnan létrehozott feladattal.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Most a feladat egy egyedi „Sine” mezőt tartalmaz, amelyet képletekben vagy számításokban használhat.

## Miért használjunk értékelő függvényeket?
A MS Project függvények beágyazása az Aspose.Tasks képletekbe lehetővé teszi, hogy:

- Valós‑időben végezzen számításokat (például `Sin([Start])`) külső eszközök nélkül.  
- A projektlogikát egyetlen, karbantartható kódbázisban tartsa.  
- Dinamikus jelentéseket generáljon, amelyek tükrözik a valós‑időben változó adatokat.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **A képlet `NaN`‑t ad vissza** | Ellenőrizze, hogy az egyéni mező típusa megfelel-e a várt numerikus típusnak. |
| **A kiterjesztett attribútum nem látható** | Győződjön meg róla, hogy az attribútumdefiníció a feladatok **létrehozása előtt** került hozzáadásra a projekthez. |
| **Licenckivétel** | Telepítsen ideiglenes vagy teljes licencet; a próba mód bizonyos funkciókat korlátozhat. |

## Gyakran feltett kérdések

**K: Kezelni tudja az Aspose.Tasks for Java a bonyolult MS Project képleteket?**  
V: Igen, az Aspose.Tasks for Java támogatja a széles körű MS Project függvények értékelését, lehetővé téve a komplex számításokat Java‑alkalmazásokban.

**K: Kompatibilis-e az Aspose.Tasks for Java a különböző Microsoft Project fájlverziókkal?**  
V: Igen, az Aspose.Tasks for Java támogatja a Microsoft Project különböző verzióit, beleértve az MPP, MPT és XML formátumokat.

**K: Próbálhatom-e ki az Aspose.Tasks for Java‑t vásárlás előtt?**  
V: Igen, letölthet egy ingyenes próba verziót az Aspose.Tasks for Java‑ból a [itt](https://purchase.aspose.com/buy) található weboldalról.

**K: Hogyan kaphatok támogatást az Aspose.Tasks for Java‑hoz?**  
V: Támogatást a Aspose.Tasks közösségi fórumon kaphat [itt](https://forum.aspose.com/c/tasks/15).

**K: Van-e ideiglenes licenc az Aspose.Tasks for Java‑hoz?**  
V: Igen, ideiglenes licencet kérhet tesztelési célokra az Aspose weboldalról [itt](https://purchase.aspose.com/temporary-license/).

---

**Utoljára frissítve:** 2025-12-09  
**Tesztelt verzió:** Aspose.Tasks for Java 24.10  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}